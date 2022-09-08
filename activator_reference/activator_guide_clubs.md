---
layout: default
title: Club Activation Guide
parent: Activator Reference
nav_order: 20
---
**Parks on the Air® Club Activation Guide**

![](/assets/images/pota-256x256.png)

**Table of Contents**
1. TOC
{:toc}

---
# What constitutes a club activation?

A club activation involves multiple members activating with the club callsign as a group, planned or ad-hoc. The activation can be in one or more park entities.

Some sponsored events, such as the summer plaque event, may require a certain number of operators to be qualified.

Everyone exclusively uses the club callsign on air, not their personal callsigns, during a club activation, like Field Day.

QSOs are tallied across all individual operators. Duplicate QSO rules apply to the club's callsign, not the operator's.

The individual members participating as operators are not required, although encouraged, to have their individual POTA accounts.

Follow the country's laws and regulations regarding control and individual operators' privileges.

# Creating a POTA account for your club

A club must have a separate POTA account with the club's callsign as the primary one to participate in POTA. A club callsign should never be added under an individual account.

Your club's POTA manager should be an active member who coordinates log files for club activations and manages the club's account at <https://pota.app/>.

# Planning the club activation

Spur-of-the-moment activations are very common. However, planning an activation sufficiently in advance promotes member participation.

Plan your stations' technical specs and footprints to ensure physical and RF safety in the park, which is a public space. If you are planning a multiple-station activation, keep in mind that running multiple radios takes a lot of room.

Since duplicate QSOs are tracked across all operators using the club callsign, networked logging is highly recommended for multiple stations, mainly if stations can operate on the same band and mode within the same park and state. (Duplicate QSOs waste a bit of time, but there is no penalty for including them in the logs submitted to POTA.)

If you have many operators, plan out operating shifts, so everyone gets a turn.

There is no "pass the mic" in a club activation since everyone uses the club callsign.

# Day of the Activation

### Spotting

If the activation consists of one station, where operators take turns, spot normally, using the club callsign.

If the activation comprises multiple stations, spot each additional station using callsign/R01, /R02, /R03, etc., so each station is spotted separately. On-the-air exchange should use the plain callsign without these differentiators. While /R01, etc., on the spot indicates that multiple radios/stations are running simultaneously, any three characters can be used for this purpose. Be sure to agree, in advance, which station will use which differentiator.

Differentiators can be similarly used if you have stations in more than one park or state.

One downside for multi-station CW and data operation: reverse-beacon-based automatic re-spotting will not work for stations with differentiators.

On-the-air exchange of the callsign must comply with the regulation in your country. For example, your country may require you to send your callsign/p, /1, etc., during portable operation. Unfortunately, that may limit the number of stations simultaneously listed on the POTA spot.

### Making QSOs

When it comes time to start making contacts, an excellent resource is the [On the Air section of the POTA activators guide](docs/activator_reference/activator_guide-english.html#on-the-air).

A typical contact may sound something like this:

**Activator:** CQ POTA CQ POTA. This is Kilo One Uniform Bravo Calling CQ
Parks on the Air.

**Hunter**: Whiskey Three Alpha Alpha X-ray.

**Activator**: Whiskey Three Alpha Alpha X-ray, you are five-nine in
K-1234.

**Hunter**: Thanks for the five-nine in K-1234. You are five-seven in
Florida.

**Activator**: Thanks for the five-seven in Florida, 73.

**Hunter**: Whiskey Three Alpha Alpha X-ray 73.

Note that the activator only gave the club call (K1UB) since this is a club activation. It is also strongly recommended that even if you use/modifiers on the spotter to differentiate between multiple stations, you ONLY exchange the base callsign on the air. This keeps logging and callsign management the simplest. Following standard best amateur practices, anyone that hunts you should be recording your callsign in their logs the way you announce it over the air.

### Logging

Regardless of the logging software used, be sure all required fields are present in the [ADIF](<https://adif.org/>) file. See the [Logging Requirements](/docs/rules.html#logging-requirements) section of the POTA rules, and the [ADIF reference for POTA](/docs/activator_reference/ADIF_for_POTA_reference.html) for details.

While not required, you may also want to combine multiple operators' logs for stations within the same park and state into a single log before submitting. This will simplify the effort for the individual to upload the club's log. A single ADIF file may contain multiple days.

The `STATION_CALLSIGN` field in the log must be the club callsign for every QSO. The `OPERATOR` field holds the individual operator's callsign for each QSO.

* Mode should be detailed mode -- i.e., SSB, FT8, etc., not Phone, Digital, etc.

* `STATION_CALLSIGN` and `OPERATOR` are sometimes omitted for individual logs but **must** be included for a club log, as this is how we differentiate between the club (station) and the person making the contact (operator).

* `SIG` and `SIG_INFO` are used in [park-to-park contacts.](/docs/activator_reference/park_2_park.html)

# Submitting the logs

[Logs can be submitted](/docs/activator_reference/submitting_logs.html) by uploading to your club account using the self-upload feature available from the "My Log Uploads" section in the pota.app menu under your club's callsign, or by email attachment to your log coordinator.

# How activation credit is awarded

When your club log(s) are fully processed, the club will receive the credit similarly to individual stations. Additionally, each valid (non-duplicate) club QSO automatically generates individual credits to the operator's callsign, as if the operator made that QSO personally, to encourage individuals to participate in club activations. Do not upload a copy of the log to your individual (or any other) POTA account.

# Special Considerations

### QSO Uniqueness / Duplicates
Refer to the section of the POTA Rules that covers [Invalid QSOs](/docs/rules.html#invalid-qsos) for details on what makes a QSO unique.

Duplicate check logic includes a couple of club-specific tests:

* Duplicate QSO checks are performed across logs from all callsigns that belong to a pota.app account. (The 'account' is part of the uniqueness.) Multiple club callsigns under the same account do not increase the maximum possible QSO or P2P credits, given a fixed number of other activators and hunters.

* If a club has stations in a park (with one park number) but across multiple states/provinces/prefectures, the club and any hunters working those stations will earn credits for each station in the unique location. This can happen in, for example, the Appalachian Trail, North Country Trail, and Yellowstone.

### Self-Working / Self Park-to-Park

The system prevents a callsign, either station or operator, from "working itself." I.e., you cannot be both the station or operator and the worked callsign of a QSO (refer to the [Invalid QSOs](/docs/rules.html#invalid-qsos) section of the POTA rules.) This same logic applies to a club callsign, so if a club has multiple stations running, those stations cannot work each other for QSO or Park to Park credit.

However, the POTA rule does not prohibit a club member from working the club as an individual, using their personal callsign. In this case, you essentially have a personal mini activation alongside the club's, and each individual station must submit a separate log for just those contacts made under the individual callsign to obtain the QSO, P2P, and possible activation credits.

### Mic Passing

"Passing the Mic" is not part of a club activation. "Passing the Mic" occurs when multiple individuals are activating but not as a club, and each will submit their logs.
