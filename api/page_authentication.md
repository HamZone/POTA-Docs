---
layout: default
title: Authentication
parent: Public API
nav_order: 20
permalink: /api/authentication.html
nav_exclude: true
search_exclude: true
---

# Authentication
To facilitate applications wishing to interact with the the authenticated portions of the Parks on the Air API, an API key based authentication mechanism has been implemented.

There are two keys required before sending an authenticated request to the Parks on the Air API:
* `Application Key` - Issued to the application developer
* `API Key` - Issued to the end user

To make an authenticated request using the API an application must:
1. Be issued an `Application Key` by Parks on the Air
2. Obtain an `API Key` from the user
3. Retrieve a `Session Key` using your `Application Key`
4. Generate a `Request Key` using the `Session Key` and the `API Key`
5. Send HTTP request containing the generated `Request Key`


## Abuse, Privacy, and Tracking
Parks on the Air may choose to revoke any `Application Key` used in any perceived abuse of the API.

Parks on the Air may choose to deny or restrict access to the API to any developer or user due to abuse or privacy concerns.

Parks on the Air does not permit the use of the API in an application containing any form of 3rd party tracking.


## Application Key
To request an `Application Key` please send an email to <a href="mailto:help@parksontheair.com">help@parksontheair.com</a> with the following information:
* Your callsign (or full name)
* Valid email address
* Application name or use case ("Personal Use" is a valid use case)

An `Application Key` will be freely issued to any application developer or user requesting one.


## API Key
A user may generate an `API Key` by visting their My Account page. The user must manually generate and provide the `API Key` to the application. [Link to required steps to generate and provide API key.]

### API Key Format
API keys are broken into two parts separated by an ASCII period (`.`). The first part is referred to as the `prefix` and the second part is referred to as the `auth-key`.
> &lt;prefix>.&lt;auth-key>

#### Example Key
> oi7za94t.qz0mtfksu8sexfqt


## Session Key
A `Session Key` can be retrieved from the API by making an unauthenticated GET request to the `/session` endpoint with your `Application Key`. The returned `Session Key` is a short ASCII string of random alphanumeric characters.

> https://api.pota.app/session/&lt;application-key>

### API response codes
* 200 - Success; the `Session Key` is returned as the content of the response
* 403 - Invalid `Application Key` or the `Application Key` has been revoked
* 500 - An error occurred while starting the session; please try again later

### Session Duration
The `Session Key` will expire 1 hour after it is last used. To keep the `Session Key` alive when the application is idle, the application may make additional requests to the `/session` endpoint at a rate of no more than once every 5 minutes.

The session is tied to the user's public IP address and a new session will be started if the user's public IP address changes. If the application is in a highly dynamic roaming environment where the user's public IP address may change rapidly, the application should request a new `Session Key` before each request.

Additionally, if the application will be making very few authenticated requests, it may be more efficient to request the `Session Key` before each request.


## Request Key
To generate a `Request Key` the application must combine an API provided `Session Key` with the user provided `API Key`. The application may cache the generated `Request Key` as it will only change if the `Session Key` is changed.

If the application will be making requests for multiple users, the `Session Key` may be reused, but the generated `Request Key` will be unique for each user.

### Request Key Format
> &lt;session-key>.&lt;prefix>.&lt;**sha1(**&lt;session-key>.&lt;prefix>.&lt;auth-key>**)**>

#### Example Request Key Generation
```python
def generate_request_key(session_key, api_key):
    # api_key = <prefix>.<auth-key>
    (prefix, auth_key) = api_key.split('.')

    # auth_hash = sha1(<session-key>.<prefix>.<auth-key>)
    hash_input = session_key + '.' + prefix + '.' + auth_key
    auth_hash = hashlib.sha1(hash_input.encode('utf-8')).hexdigest()

    # request_key = <session-key>.<prefix>.<auth-hash>
    return session_key + '.' + prefix + '.' + auth_hash
```

#### Test Case
```python
session_key = '4toztnck'
api_key = '005gubdi.ztv2055n3bulji1e'
request_key = generate_request_key(session_key, api_key)

expected_output = '4toztnck.005gubdi.8c287089997fdd5c6ab3ea274805e202a7eac4c3'

assert(request_key == expected_output)
```


## API Request
When making an authenticated API request, the application must include the generated `Request Key` in the request. The `Request Key` may be provided in the `X-API-Key` HTTP header or as the `api` query parameter.
