---
layout: default
title: ADIF for POTA Technical Reference
parent: Activator Reference
nav_order: 50
---

**Parks on the Air® ADIF Technical Reference Guide**

![](/assets/images/pota-256x256.png)

Original author: W8MSC

**Table of Contents**
1. TOC
{:toc}

---

# About ADIF for POTA

POTA requires activators to submit their log files in the [ADIF format](https://adif.org). This document provides some ADIF fields that POTA uses in POTA-specific ways. This document also includes a general illustration of common ADIF fields with examples. The latter part is intended to be explanatory and not limit or redefine the ADIF standard.

## Required ADIF fields

At a minimum, POTA requires the following items to tally your QSOs properly:

### STATION_CALLSIGN or OPERATOR

__STATION_CALLSIGN__:  This is the callsign given over the air. This may be identical to __OPERATOR__ or omitted for individual activations. Club/group activations must use the club's callsign.

__OPERATOR__: This is the callsign of the individual making contact. This may be identical to __STATION_CALLSIGN__ or omitted for individual activations. Club/group activations must include this field.

Each field consists of alphabet characters A-Z, numbers 0-9, and the / character. No other characters, including accents, are allowed here.

Example:  `<STATION_CALLSIGN:4>N8SL`

### CALL

__CALL__:  This is the callsign of the hunter. Same allowed characters as __STATION_CALLSIGN__.

Example:  `<CALL:5>K8ERS`

### QSO_DATE

__QSO_DATE__:  This is the date the QSO was made.

It is entered as an 8-digit number in YYYYMMDD format, with a 4-digit year, 2-digit month, and 2-digit day.

Future dates are rejected.

The month is entered with 2-digits, with a leading digit of 0 up to September. Numbers less than 01 or more than 12 will result in an invalid month. Example:  January is 01, February is 02, through 12 for December.
The day is entered with 2-digits, with a leading digit of 0 for the first nine days. Example: the first day of a month is 01, the second day is 02, through 31 for the last day of a month.

Example: July 15, 2019 is recorded as `<QSO_DATE:8>20190715`

### TIME_ON

__TIME_ON__:  This is the time a QSO was started.  *POTA tallies QSOs based on when a QSO was started, not completed.*

This can be either 4 or 6 digits, entered as HHMM or HHMMSS, where HH is the hour 00 through 23, MM is minute 00 through 59, and SS for second 00 through 59. Hour and minute are required, while seconds are optional.

Example:  `<TIME_ON:4>0945` or `<TIME_ON:6>094500`

### BAND

__BAND__:  This is the band the QSO took place.

The band is recorded with the unit measurement. For example, a QSO on 20 meters will be recorded as 20M, not 20.

Most QSOs are simplex. In duplex or cross-band QSOs, such as satellite contacts, specify the activator's transmission or uplink band in this field.

Example:  `<BAND:3>20M`

### MODE or SUBMODE

__MODE__: This is the mode used to make the QSO.

__SUBMODE__: This is the submode used to make the QSO.

Valid modes and submodes are listed in the ADIF spec. POTA allows certain expectations as listed in the [Parks on the Air rules](/docs/rules.html#logging-requirements). POTA only stores a single MODE field; if both mode and submode are provided, submode takes precedence.

Example:  `<MODE:3>SSB`

## Optional ADIF fields

Optional ADIF fields support park-specific information. These data are processed for your activation location and park-to-park contacts, primarily when an activator is located at multiple parks during the same UTC day or when many operators contribute to contacts for a club callsign or special event callsign. When the `MY_SIG` and `MY_SIG_INFO` fields are missing or invalid, the POTA uploader will prompt the user for the needed information during the upload process.

### MY_SIG and MY_SIG_INFO

__MY_SIG__: Special Interest Group. Insert "POTA" in this field.

Example:

`<MY_SIG:4>POTA`

__MY_SIG_INFO__:  Specify the POTA park reference number for the activator's park: the POTA program prefix (K, VE, etc.) followed by a hyphen (-) and then a number.

Example:

`<MY_SIG_INFO:6>K-0005` represents Badlands National Park in the United States.

`<MY_SIG_INFO:7>VE-0005` represents Banff National Park in Canada.

The following optional fields are used in park-to-park QSO to specify the other activator's park reference.

### SIG and SIG_INFO

__SIG__: Special Interest Group. Specify "POTA" in this field.

__SIG_INFO__: The park reference number of the other activator's park.

A P2P contact with another activator would be logged with:
`<SIG:4>POTA`  and `<SIG_INFO:6>K-0008`

### MY_STATE

__MY_STATE__: The logging station's primary administrative subdivision code (e.g., US state, JA prefecture, VE province). If the park being activated crosses administrative lines (state, province, etc.), the uploader will try to use the code in this field to determine the location of the activator. If missing, invalid, or unrecognized, the uploader will prompt the user for this information.

### Example of a simple log file

The following short log file is an example of a properly formatted log file.

```
Parks On The Air Field Logger
<PROGRAMID:17>POTA Field Logger
<PROGRAMVERSION:5>0.2.8
<CREATED_TIMESTAMP:13>20201002 134537<EOH>
<STATION_CALLSIGN:5>W8MSC <CALL:5>W8TAM <QSO_DATE:8>20201002 <TIME_ON:6>134100 <BAND:3>40M <MODE:3>SSB <MY_SIG:4>POTA <MY_SIG_INFO:6>K-3315 <EOR>
<STATION_CALLSIGN:5>W8MSC <CALL:5>N3VEM <QSO_DATE:8>20201002 <TIME_ON:6>134200 <BAND:3>40M <MODE:3>SSB <MY_SIG:4>POTA <MY_SIG_INFO:6>K-3315 <EOR>
<STATION_CALLSIGN:5>W8MSC <CALL:5>W3AAX <QSO_DATE:8>20201002 <TIME_ON:6>134300 <BAND:3>40M <MODE:3>SSB <MY_SIG:4>POTA <MY_SIG_INFO:6>K-3315 <EOR>
<STATION_CALLSIGN:5>W8MSC <CALL:4>N0AW <QSO_DATE:8>20201002 <TIME_ON:6>134500 <BAND:3>40M <MODE:3>SSB <MY_SIG:4>POTA <MY_SIG_INFO:6>K-3315 <SIG:4>POTA <SIG_INFO:6>K-0008 <EOR>
<STATION_CALLSIGN:5>W8MSC <CALL:4>W5RB <QSO_DATE:8>20201002 <TIME_ON:6>134600 <BAND:3>40M <MODE:3>SSB <MY_SIG:4>POTA <MY_SIG_INFO:6>K-3315 <EOR>
<STATION_CALLSIGN:5>W8MSC <CALL:6>HI8ILO <QSO_DATE:8>20201002 <TIME_ON:6>135000 <BAND:3>20M <MODE:3>SSB <MY_SIG:4>POTA <MY_SIG_INFO:6>K-3315 <EOR>
<STATION_CALLSIGN:5>W8MSC <CALL:5>N3NWV <QSO_DATE:8>20201002 <TIME_ON:6>135100 <BAND:3>20M <MODE:3>SSB <MY_SIG:4>POTA <MY_SIG_INFO:6>K-3315 <EOR>
```
A downloadable version of this sample file [is available here for reference.](/assets/documents/exampleLog.adi)

Each QSO is composed of the station callsign of the activator, the callsign of each hunter, date, time, band, mode, and the POTA fields listing the park being activated. A single space separates fields.
The QSO with N0AW describes a park-to-park contact with the park information of the other park listed in the optional fields.