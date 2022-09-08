---
layout: default
title: Rules
nav_order: 10
---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Rules

| Version      | Date        | Description |
|:-------------|:------------|:------------|
| 1.0          | August 2022 | Ported from original site and refactored significantly  |

> **❗Important:** Participation in Parks on the Air®(POTA) is at your own risk of injury or death. The conditions of your radio license, all local and federal laws, and regulations must be followed; they supersede anything contained in these documents.
{: .pota-info}

At a foundational level, POTA is about radio operators visiting parks and making contacts from within the parks with other radio operators at any location. The following sections go into more detail, formally defining this.

### Key Definitions
- **Activator:** An activator is a licensed amateur radio operator in a park on POTA's designated list and contacts other licensed amateurs.
- **Hunter:** A hunter is any other licensed radio operator who contacts an activator at a park. The term "chaser" is sometimes synonymously used.
- **Activity:** The act of an activator visiting a park intending to operate POTA is termed an _activity_.

### Activations / Attempts
1. A successful activation requires a minimum of 10 QSOs from a park in the designated list within a single UTC day (Zulu day).
    * Courteous activators will still submit logs for unsuccessful activations to ensure their hunters get credit for the QSOs.
    * Multiple activities at the same park in the same state/province/entity and the same UTC day count as a single activation, provided that the ten or more QSOs combined were made.

### Eligible QSOs
1. **Bands/Modes**: All Bands and Modes available to the activator based on their license class may be used in Parks on the Air, according to the details specified in the [logging requirements section](/docs/rules.html#logging-requirements) of this document.
   * **Note:** POTA is not a contest; POTA QSOs may take place on any amateur band, including the WARC bands (30m/17m/12m).
2. **Land repeaters are not allowed**: Contacts made via land repeaters are not permitted.
   * Refer to [Parks on the Air's glossary](/docs/glossary.html) for the definition of a Land Repeater as it pertains to POTA.
   * You may use a repeater to request direct contacts, but the QSOs submitted for activator credit should not be via a land repeater.
3. **Satellite repeaters are allowed**: Satellite contacts are permitted.
   * Refer to [Parks on the Air's glossary](/docs/glossary.html) for the definition of a Satellite Repeater as it pertains to POTA.
   * Logs should be submitted with the band information for the activator's transmit frequency.
4. **Spotting**: You may self-spot yourself on the [POTA spotting page](https://pota.app/); anyone (including hunters) can also spot/respot you, regardless of whether they are working that activator.
   * Spots will disappear from the spotting page approximately 30 minutes after the last spot or if the spot comment marks QRT.
   * If you are activating a park but also leveraging the QSOs for getting credit for other programs, _e.g., operating from a park for ARRL Field day_, there may be rules against self-spotting in the other program. Please operate in the spirit of the programs.
5. **Power limits**: POTA does not have a power limit. However, you must still adhere to legal limits based on your license class/band plans and use the minimum transmitter power necessary to carry out the desired communications.
6. **Fully automated QSOs are prohibited**: Each contact must include direct action by both operators making the contact. Fully automated contacts are prohibited.

### Activation Location and Access
1. Activations must be performed from parks in [POTA's designated list](https://pota.app/#/parklist), which are also open to the public.
    * A park is considered open when the public has civil and legal access, or a special permission/permit to the public lands defined by the park boundary map is obtainable. Such access must comply with any other specific civil or legal restrictions mentioned by the governing agency/website.
    * A park is closed when the governing agency/website clearly says that public access is prohibited or when the park itself ceases to exist.
    * Seasonal closure of facilities, concessions, offices, some gates, or even large portions of the park may still allow lawful access to the remainder. If in doubt, please call the park office/administrator.
2. The activator and all equipment must be within the park's boundary and on public property.
    * Use maps provided by POTA as guidelines only. Refer to official park websites and agencies to find the official boundaries.
    * Activations from vehicles, RVs, etc., parked on public property within the park's boundary are permissible.
    * Aeronautical activations are permitted if the QSOs are made from airspace directly above the park.
3. Activators may not trespass on private property to access state/provincial, or federal lands.
4. Activators may not attempt to activate from private property, even if the private property is adjacent to, or surrounded by, park property.
5. If a trail system or a river is designated as a POTA entity by itself (not as parts of a land park having a defined boundary), the activator and the station equipment must be on public property within 30.5 meters (100 feet) from the edge of the trail or river.
6. Activations of multiple references ("Multi-loc" or "two-fer," "three-fer," etc.) are permitted with POTA.
    * Activation Location and Access Rule #1 applies to simultaneous activations. Such a multi-park activation requires an overlapped area where all activated parks' boundaries intersect. The intersection must entirely contain the activator and the station equipment.
    * A separate log must be submitted for each park of the multi-park simultaneous activation

### Hunter Location
1. The Hunter can contact the activator from home or any other property or station.
   * If a hunter is also at a [designated POTA park](https://pota.app/#/parklist), this QSO becomes a "Park to Park" (P2P). All other activator rules have to be followed for it to be a valid park to park QSO. See our [Park to park](activator_reference/park_2_park.html) page for more info.

### Logging Requirements
1. Logs have to be submitted following the logging requirements documented below to count as a valid activation.
   * Hunters do not submit logs to the program. Only activators do. Hunters earn credit through the activator's logs.
2. There are no time limits for log submission.
   * Courteous operators upload their logs without excessive delay, as hunters depend on the activator's log for credit/awards.
3. One log can cover multiple activity days but should be for only one park. This also applies to club and multiple-operators activities.
4. Logs must be in ADIF format, with exceptions identified at the end of this section.
    * See the [Activator Reference Section](activator_reference/submitting_logs.html) for a detailed description of how we use these ADIF fields.
    * **Required Fields:**
        - `<STATION_CALLSIGN>` or `<OPERATOR>`
            - Club/group logs must include both `<STATION_CALLSIGN>` AND `<OPERATOR>` fields for each QSO, with the `<STATION_CALLSIGN>` field containing the club or group's callsign
            - Individual logs should contain the same call in both fields or include only one of the fields
        - `<CALL>`
        - `<QSO_DATE>`
        - `<TIME_ON>`
        - `<BAND>`
        - `<MODE>` or `<SUBMODE>`
          - POTA stores a single mode field. If both Mode and Submode are provided, submode supersedes mode
    * **Optional Fields:**
        - `<MY_SIG>`
        - `<MY_SIG_INFO>`
        - `<SIG>`
        - `<SIG_INFO>`
        - `<MY_STATE>`
    * Exceptions to ADIF Accepted by POTA
        - POTA accepts `<BAND>` of 'SUBMM' for Sub-millimeter wavelength contacts
5. Club or group logs must be uploaded via a POTA account designated for the club/group, not via an individual's account
6. Invalid QSOs in the log will be rejected
   * Duplicate QSOs will be rejected by the upload tool.
   * For POTA, the uniqueness of a QSO is determined by the combination of:
       * User account that the log was uploaded under (i.e., owner of the `<STATION_CALLSIGN>`), `<CALL>`, `<MODE>`, `<QSO_DATE>`, `<BAND>`, `<MY_SIG_INFO>`, `<SIG_INFO>`, Location (Chosen at time of upload if park crosses state lines)
   * `<CALL>` may not be the same as `<STATION_CALLSIGN>` or `<OPERATOR>` (i.e., a station or operator cannot work themselves)
   * QSOs cannot be dated in the future.

> 💡 **Note:** If the information documented in the rules section differs from information provided elsewhere on the site(guides etc.), the rules section will take precedence. Please send us a note at [help@parksontheair.com](mailto:help@parksontheair.com) to inform us about the inconsistency.

## Additional notes / guidance

### Parks on the Air does not require a specific exchange in a QSO.

### Qualification of Parks, Trails, and Rivers for Addition to Parks on the Air
1. All new parks must be owned and operated by a State/Provincial or Federal/National agency. We do not include parks that have part/shared ownership, sponsorship, or are operated by private organizations or local governments
2. To be considered for inclusion, the park must meet the above requirements and offer an informational website detailing current boundary maps.
3. POTA does not create sub-parks within existing parks if both parks are owned and operated by the same State/Provincial or Federal/National agency.

### Reporting Violations of the Rules
Parks on the Air is a self-regulated, community-monitored program. If you observe a violation of these rules that you feel need to be followed up on, you may report the violation to [help@parksontheair.com.](mailto:help@parksonthair.com) You must provide enough details to prove without a doubt that the violation occurred before any action will be taken.

### Park Access & Information
If a listed park is permanently closed, public access is prohibited per the Park Access Section of these Rules, the park no longer exists, you are told you are not allowed to operate, or any of the information about the park needs to be updated, please report it to [help@parksontheair.com.](mailto:help@parksonthair.com)

### Guidelines, Interpretation & Intent
Parks on the Air has kept its rules simple because the idea is just to get out and have fun. For some individuals, though, this can be somewhat ambiguous, so this document section provides guidelines on POTA administrators' and developers' intent when setting up the system. Deviating from these guidelines won't get you in any trouble, but it may cause your stats and awards to behave differently than what you and others may expect.

#### Park Boundaries and Multi-Park Activations
Please be aware of the beauty in the simplicity of the rule "the activator and all equipment must be within the park's boundary and on public property." If an activator is straddling the park or state lines, they are, therefore, not fully within the boundary and are out of compliance with the rule. Similarly, for multi-park activations, the activator and all equipment must be entirely within the bounds of each park being claimed, so multi-park activations can only occur if the activator is physically located in an intersection where all the claimed parks overlap.

#### Clubs & Multiple Operators
In general, individuals should not use each other's callsigns on the air but instead, use a club or special event call in situations with multiple operators. The club or special event call should be used over the air (just like field day!) and be recorded in the `<STATION_CALLSIGN>` field. The individual who made the contact should record their callsign (Generally not used over the air) in the `<OPERATOR>` field. Once uploaded to the account for the holder of the `<STATION_CALLSIGN>` (see [logging requirements section 3](/docs/rules.html#logging-requirements)), the system will count the QSO(s) towards awards for both the holder of the `<STATION_CALLSIGN>` and for the holder of the `<OPERATOR>` callsign.

Please refer to POTA's [Guide for Clubs](/docs/activator_reference/activator_guide_clubs.html) for our recommended practices for planning, conducting, and spotting for club or group activations.

##### Passing the Mic
When multiple individuals are activating together but not under a club call, the operators may choose to 'pass the mic' and take turns making contacts. In these situations, each individual should maintain and submit their own log according to the [logging requirements section](/docs/rules.html#logging-requirements) of these rules

A minimum necessary deviation from the guidelines may be made to accommodate an operator with a disability in club and multiple-operator activations and the practice of passing the mic within the country's rules and regulations.
