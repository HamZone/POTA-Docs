---
layout: default
title: Park to Park
parent: Activator Reference
nav_order: 45
---

**Parks on the Air® Park-to-Park Contacts Guide**

![](/assets/images/pota-256x256.png)

**Table of Contents**
1. TOC
{:toc}

---

## Park-to-Park Contacts
An activator can work another activator to earn a park-to-park (P2P) credit. Both activators are strongly recommended (although not required) to record the park number of the other activator in the ADIF log file's `SIG_INFO` ADIF field (see [ADIF for POTA Reference](/docs/activator_reference/ADIF_for_POTA_reference.html#sig-and-sig_info)) in all park-to-park contacts.

Proper use of `SIG_INFO` is necessary to receive all eligible P2P credits when one or both activators are activating multiple parks.
For example, if you work a three-fer activator, you are eligible for three P2P credits. In that case, list the same QSO three times in the ADIF log file, each with one of the three park references in `SIG_INFO`, with the rest unchanged. Failure to do so will give you only one P2P credit and two hunter credits.

Another slightly different scenario is when you work the same activator multiple times from unique parks within the same UTC day. Your ADIF file contains one line for each QSO. However, without `SIG_INFO` with unique park references, the system rejects all but the first as duplicates.

### Matching Rules
POTA's P2P detection logic depends on the `SIG_INFO` data when an activator is activating multiple parks, either simultaneously (two-fer, etc.) or sequentially (rover).

After surviving the duplicate QSO check, each line in the ADIF log file can earn at most one P2P. Unique park reference in each line's `SIG_INFO` prevents getting de-duped.

Example: you worked a three-fer, and your log has three lines. Without a unique `SIG_INFO` field, the latter two of the three lines would be rejected as duplicates. (Note: altering the QSO time will not prevent getting de-duped.) Another example: you worked an activator twice, each from a different park. Your log has two QSOs with unique times and perhaps different signal reports, but the latter of the two would be de-duped without having a unique `SIG_INFO` field. In both examples, the latter de-duped QSOs only earn hunter credits.

P2P match requires that the QSO times in both activators' logs coincide within 15 minutes.

All required fields (see [Rules, Logging Requirements](/docs/rules.html#logging-requirements)) must match.

Exact matching of callsigns is necessary. If I record my callsign as N3VEM/M and the other activator records my callsign as N3VEM, the QSOs will not match. Following the best amateur practice of "logging what is exchanged over the air" will prevent these situations from happening.

### Multi-Park to Multi-Park Activations
If you are two-fer and working a three-fer activator, you generate two ADIF log files, each having three lines. The other activator generates three ADIF files, each having two lines. As a result, you will get 6 P2P credits, and the activator will also get 6 P2P credits from this contact.

Again, unique `SIG_INFO` fields in the log files, as detailed in the [Rules, Logging Requirements](/docs/rules.html#logging-requirements), are essential.

### Duplicate QSOs in the log

There is no need to make an effort to identify and remove duplicate QSOs before uploading ADIF log files, as the POTA system will do that process, and there is no penalty.
