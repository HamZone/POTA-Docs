---
layout: default
title: CW 通联指南
nav_order: 52
nav_exclude: false
---

**空中公园® CW 通联指南**

![](/assets/images/pota-256x256.png)

原作者: AB1WX

**目录**
1. TOC
{:toc}


# POTA CW 通联

POTA 不需要在 QSO 中添加任何特定的交换信息。因此，POTA 的 QSO 可以像比赛一样快速或像大爷下棋一样缓慢，但大多数 POTA 的 QSO 是基于礼貌、简洁和淡定自如的。

POTA 的 QSO 通常包括简单的问候语，像是 "GM" "GA" 或是 "GE," 或者是 CW 昵称（如果你知道的话）。通联时通常会给出真实的 RST 信号报告，而不是敷衍了事的 559 或 599。追逐台通常会在 QSO 时发送他们的 QTH (美国和加拿大的两个字母的州代码)，但DX追逐台可以使用既定的州/省/国家代码（例如 SKCC 有一个列表）或省略QTH。

POTA 的 QSO 通常以简短而恰当的 73 来结束通联。 激活台经常使用追逐台的 QTH 代码，就如同猎人的手柄，比如 "TU CA 73 e e"

Other than that, POTA QSOs are perhaps similar to brief and simple DX QSOs.

Compared to DXpedition or contest-style QSOs, POTA QSOs can include all those above and usually are at a slower speed. When ending a message, "BK," "K," or "KN" is usually used (and the other station usually does not jump in right after the last dash but starts like a rural driver).

Most POTA QSOs omit words expected from the context, in contrast to classic rubber stamp QSOs. When calling CQs, activators often omit "DE" and "K." When responding to a CQ, hunters simply send their callsign once (without repeating the activator's callsign followed by a "DE," and also omitting "K" at the end). When sending signal reports and QTH, many stations send "UR 569 56N MA MA," whereas an old-fashioned QSO might go like "UR RST IS 569 56N IN QTH MA MA." When sending QTH in the QSO, many POTA people prefer to omit "in" as a preposition since it is unnecessary and confusing with Indiana. Prosigns like "BT" and "AR" are rarely used because the exchange is brief.

In the POTA context, QTH could refer to the state/province code or the park reference (e.g., K-1234). Occasionally, hunters who are apparently not using [the POTA spot page](https://pota.app/#/) ask "QTH?" The activator might want to send both.

Above is a general observation of the POTA QSOs. Because POTA does not require a specific exchange, QSOs under other exchange formats (e.g., contests, SKCC, and other clubs) can also count as POTA contacts, as long as the other POTA requirements (such as operating from a POTA park) are met.

# Park-to-park QSOs

An activator can call another activator to "hunt" a P2P. You'll often compete with fixed stations with superior antennas and higher output power in a pileup, despite P2P being desirable to the other activator. So, entering a pileup with "P2P" is acceptable instead of your callsign. When the other activator responds to "P2P," send your callsign.

When you call another activator, it is recommended that you send your park reference(s) and QTH following RST, like "UR 599 5nn P2P K6876 K6876 MA MA BK." You probably know the other activator's park reference from the spot page, but they are also likely to reciprocate with their park reference(s), especially if they are 2-fer. Save that info for the `SIG_INFO` field of your ADIF log to earn all eligible P2P credits.

# Zero-beat pileups

Recent transceivers have an automatic zero-beat tuning or indicator. RBN may also accurately report the activator's frequency. But in POTA CW hunting, accurate tuning can hurt!

Hunters, please dial your transmit frequency somewhere between 20 and 100 Hz off the activator's frequency when you hear or anticipate a pileup. You can vary the offsets if you are not getting a response. The point is to avoid calling exactly at the activator's frequency (zero-beat frequency). One situation when zero-beat calling is appropriate is when the activator has been calling CQ without a taker.

Zero-beat pileup is a frustrating phenomenon a CW activator has to deal with. Unlike SSB, when multiple stations call at the same frequency (usually the same as the activator's), the activator hears one long tone, which is nearly impossible to decode. If you hear an activator requesting callsign repeated many times and then promptly giving out a 599, this could be one likely reason (other possibility includes poor code, weather/people distractions, and QRM). Conversely, if you call at a slight offset, even if your signal is weak, your signal may stand out and get picked up quickly.

Activators in RF-noisy areas are more likely to use a very narrow filter (say 60 or 120 Hz bandwidth), while those in quiet rural parks away from noise sources may operate with a 500 Hz filter. Each hunter bets on their optimal offset that falls inside the activator's receiver bandwidth but adds a unique tone to their signal to stand out. If the activator is not hearing anyone, including you, you can reduce your offset (Once the QSO begins, keep the offset unchanged).

An easy way to offset your transmit frequency is to set your transceiver's XIT dial at the desired offset. Otherwise, use RIT and the main dial to achieve the same effect.

# Reverse Beacon Network

Networked skimmers constantly monitor CW activities in amateur bands. They detect your callsign when you call CQ. You can view the data on the [Reverse Beacon Network website.](http://reversebeacon.net) POTA has its RBN gateway to pick up that information and update [the POTA spot page](https://pota.app/#/) automatically for [registered](https://pota.app/#/activations) and currently spotted activations.

If activating in an area without reliable cellular data service, ensure your activation registration is accurate before leaving home.

To maximize the likelihood of RBN picking up your signal, use your transmitter's message keyer feature to call CQs in perfect code, at least sometimes, even if you prefer manual keying for the rest. For this purpose, you can send "CQ CQ CQ POTA W3AAX W3AAX W3AAX" or any variation. If you are testing equipment and don't want anyone to respond, you could send "V V V TEST TEST TEST W3AAX W3AAX W3AAX V V V." "TEST" is handled synonymously as "CQ" by the skimmers. The V's signal other stations that you are only testing rather than participating in a contest. If your message keyer programs the message by the paddle input (rather than choosing letters) maintain correct spacing when entering the message. Clean code with proper spacing is the key.

When you send:

“CQ POTA W3AAX W3AAX K1234 K”

and it is heard by K1TTT, RBN gives the POTA gateway the data in the following format:

“K1TTT,K,NA,7032.5,40m,W3AAX,K,NA,CQ,14,2019-07-20 14:24:57,17,CW”

From such data, the POTA gateway searches the callsign in (1) the POTA current spots and (2) the currently scheduled activations. If the callsign is found, [the POTA spot page](https://pota.app/#/) updates its listing with the freshest frequency data while preserving the current park reference (e.g., K-0000).

# RBN-POTA Troubleshooting

When your CQ is not reflected on the [POTA spot](https://pota.app/#/) in a few moments, make sure your frequency is clear, and send CQs in very clean code (use the message keyer function). If that does not work, your radio/antenna setup may not be functioning correctly.

Also, check the other activators' spot histories. If no one gets automatic spot updates, the RBN-POTA gateway may be down. This problem recurs occasionally, and work is underway to increase the system's reliability. For now, a message on the [POTA Slack](https://parksontheair.slack.com) channel #potahelp is often the quickest way to get the gateway rebooted.

# Give CW a try with Parks on the Air

Below in this section is a short article titled **Give CW a try with Parks on the Air** by Steve Carter, K0GUZ. He made this based on a Facebook POTA group thread in 2021 and distributed it there. His entire article is included with permission as-is:

Are you looking to work some of the CW stations you hear but are intimidated by the fact that they’re calling CQ at 20-25 wpm? Don’t be. Here are a few suggestions that may help you get over your fears that you’ll be drilled by someone sending your call like a machine gun.

First of all, if you can actually spot and hear an activator calling CQ, you’re almost there. The sequence most activators use is: CQ POTA K7XYZ. Sometimes, they repeat the call sign. Since you know from the spot what call you’re looking for, if you can pick out the CQ and the fact that there’s a number in the callsign and a couple of other letters in the call sign, you’re ready to reply to him.

Listen carefully, and if you hear the CQ repeated a couple of times, then he’s looking and not hearing anybody. When there’s a pause after his call sign, jump in and send your call sign, once, at the speed you’re comfortable with, be it 5, 10, or 15 wpm. Remember that he will answer somebody; if you try, there’s a chance that it will be you. If you don’t try, then there’s a 100% chance that it won’t. And if you don’t get him the first time, keep trying.

Nearly every good CW operator will adjust his speed to match yours and reply repeating your call, and usually a signal report and maybe the state he’s in, as in “KE0HNW 479 CO” If the activator didn’t get all of your call, he may repeat a part of it with or without a question mark, as “KE?” or “0”. You should reply to a partial call by repeating yours once. After you’ve copied your call sign and maybe the signal report, reply to him with a signal report and the state you’re in, as “5NN MI”. He may reply “QSL” or maybe “TNX” or perhaps a couple of dits. If he sends you a couple of dits, send two back to him. That’s it! Congratulations. For a successful POTA contact you need only exchange calls. You do NOT need to copy the signal report or the state (although both are interesting and make it more fun), so if you missed a part, write down what you did copy with a question mark and chalk it up to experience.

What’s the worst that could happen? Nothing. Either the activator won’t call you or he won’t slow down, in which case you can try again later with somebody else.

I’ve had at least one QSO like that on nearly every activation, and it makes me feel great to know that somebody’s working hard at building up their CW skills. No, I don’t mind it, and since this isn’t a contest, I’d rather work somebody new than rack up QSOs at 30 wpm. CW, which should be known as Human Readable Digital Code, is a great mode that will become even more enjoyable with the next sunspot cycle. Think of it as FT8 without a computer. Thanks for joining in, and I hope to see you in my logbook.

73’s Steve, KØGUZ CWOPS Member # 1889 k0guz at arrl.net

# Video: Parks On The Air (POTA) CW exchanges explained

A Youtube video **Parks On The Air (POTA) CW exchanges explained** by Thomas K4SWL.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Fq3teRrNypA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
