#  MASTER TRACKING LEDGER — TikTok Posting Operation

**Purpose:** single source of truth for every Taisly key, connected TikTok account, and post ever created. Also helps the operator audit completed work.

**Protocol (runs automatically on every new API key):**
1. `taisly platforms:list` → capture **TikTok username + platform ID**
2. Platform ID **already in ledger** → append new posts under that existing account entry
3. Platform ID **new** → create a new account entry
4. Every `posts:create` result (historyId, video, scheduled time, status) is logged immediately below
5. **Standing rule (06 Oct):** keys alternate **day batch → night batch on the same 5 days**. Key N (odd) = 5 × day (12:30 PM) on 5 consecutive days from the next available day; Key N+1 (even) = 5 × night (8:30 PM) on those same 5 days. Each day therefore ends with exactly 2 posts.

**Statuses:** 📤 published now · 🕐 upcoming (date still ahead) · ✅ fired (scheduled date has passed — confirm on TikTok) · ⚠️ unverified

---

## Account 1 — `neo3hrbiytf`
- **Platform ID:** `6ab4d6a4e020b5ccdefbe11a`
- **Keys used:** `taisly_c5de…ca4` (original) · `taisly_a49c…80ac` (same workspace — verified 25 Sep)
- **Created:** Wed 24 Sep 2026 · Timing: 12:30 PM UK

| historyId | Vid | When (UK) | Status |
|---|---|---|---|
| `6ab513f8e020b5ccdefc04af` | vid_03 | Thu 25 Sep 12:30 PM | ✅ fired (unverified) |
| `6ab513fbe020b5ccdefc04c9` | vid_04 | Fri 26 Sep 12:30 PM | ✅ fired (unverified) |
| `6ab513fee020b5ccdefc04d3` | vid_05 | Sat 27 Sep 12:30 PM | ✅ fired (unverified) |
| `6ab51402e020b5ccdefc04dd` | vid_06 | Sun 28 Sep 12:30 PM | ✅ fired (unverified) |
| `6ab51405e020b5ccdefc04e7` | vid_02 | Tue 29 Sep 12:30 PM | ✅ fired (unverified) |

⚠️ Account disconnect was requested but the agent API has no disconnect command — these 5 may or may not have fired depending on dashboard state.

---

## Account 2 — `techstacker0`
- **Platform ID:** `6ab74763e020b5ccdefd014c`
- **Key used:** `taisly_b58c…e383`
- **Created:** Sat 26 Sep 2026 · Timing: now + 1:00 AM UK

| historyId | Vid | When (UK) | Status |
|---|---|---|---|
| `6ab7489ae020b5ccdefd01f3` | vid_03 | Sat 26 Sep ~5:22 AM (now) | ✅ fired (unverified) |
| `6ab7489ee020b5ccdefd0202` | vid_04 | Sun 27 Sep 1:00 AM | ✅ fired (unverified) |
| `6ab748a1e020b5ccdefd020c` | vid_05 | Mon 28 Sep 1:00 AM | ✅ fired (unverified) |
| `6ab748a4e020b5ccdefd0216` | vid_06 | Tue 29 Sep 1:00 AM | ✅ fired (unverified) |
| `6ab748a7e020b5ccdefd0222` | vid_02 | Wed 30 Sep 1:00 AM | ✅ fired (unverified) |

---

## Account 3 — `user9065197799710`
- **Platform ID:** `6ab68767e020b5ccdefca7ea`
- **Key used:** `taisly_e07b…ed44`
- **Created:** Mon 28 Sep 2026 · Timing: now + 12:30 AM UK

| historyId | Vid | When (UK) | Status |
|---|---|---|---|
| `6ab9be65e020b5ccdefe314c` | vid_07 | Mon 28 Sep ~2:10 AM (now) | ✅ fired (unverified) |
| `6ab9be68e020b5ccdefe316d` | vid_08 | Tue 29 Sep 12:30 AM | ✅ fired (unverified) |
| `6ab9be6be020b5ccdefe3183` | vid_09 | Wed 30 Sep 12:30 AM | ✅ fired (unverified) |
| `6ab9be6ee020b5ccdefe3192` | vid_10 | Thu 01 Oct 12:30 AM | ✅ fired (unverified) |

---

## Account 4 — `businesssignals_20`
- **Platform ID:** `6abe388d3716f32795361307`
- **Key used:** `taisly_4ad2…943a`
- **Created:** Thu 01 Oct 2026 · Timing: now + 12:30 AM UK

| historyId | Vid | When (UK) | Status |
|---|---|---|---|
| `6abe39093716f32795361360` | vid_11 | Thu 01 Oct ~11:42 AM (now) | ✅ fired (unverified) |
| `6abe390c3716f3279536136f` | vid_12 | Fri 02 Oct 12:30 AM | ✅ fired (unverified) |
| `6abe390f3716f32795361379` | vid_13 | Sat 03 Oct 12:30 AM | ✅ fired (unverified) |

---

## Account 5 — `nextgencapital_292` (old connection)
- **Platform ID:** `6ac0c82b502f9f77444eec34`
- **Key used:** `taisly_0f98…56547`
- **Created:** Sat 03 Oct 2026 · Timing: now + 12:30 AM UK, then new 2-slot system (day 12:30 PM / night 8:30 PM)

| historyId | Vid | When (UK) | Status |
|---|---|---|---|
| `6ac0c8ce502f9f77444eec87` | vid_14 | Sat 03 Oct ~10:20 AM (now) | ✅ fired (unverified) |
| `6ac0cff6502f9f77444ef233` | vid_18 | Sat 03 Oct 12:30 PM (day) | ✅ fired (unverified) |
| `6ac0c8d1502f9f77444eec96` | vid_15 | Sun 04 Oct 12:30 AM | ✅ fired (unverified) |
| `6ac0c8d4502f9f77444eeca0` | vid_16 | Mon 05 Oct 12:30 AM | ✅ fired (unverified) |
| `6ac0c8d7502f9f77444eecba` | vid_17 | Tue 06 Oct 12:30 AM | ✅ fired (unverified) |

## Account 6 — `nextgencapital_292` (reconnected)
- **Platform ID:** `6ac495c69117edafc7754cdc` (new connection — same TikTok username as Account 5, different platform ID per ledger rule)
- **Key used:** `taisly_71ab…273a`
- **Created:** Tue 06 Oct 2026 · Timing: one-off 2:30 PM (today), then fixed day/night (12:30 PM / 8:30 PM)

| historyId | Vid | When (UK) | Slot | Status |
|---|---|---|---|---|
| `6ac496d89117edafc7754d7e` | vid_19 | Tue 06 Oct 2:30 PM | one-off | 🕐 upcoming |
| `6ac496db9117edafc7754d88` | vid_20 | Wed 07 Oct 12:30 PM | ☀️ day | 🕐 upcoming |
| `6ac496de9117edafc7754d92` | vid_21 | Wed 07 Oct 8:30 PM | 🌙 night | 🕐 upcoming |
| `6ac496e19117edafc7754d9c` | vid_22 | Thu 08 Oct 12:30 PM | ☀️ day | 🕐 upcoming |
| `6ac496e49117edafc7754da6` | vid_23 | Thu 08 Oct 8:30 PM | 🌙 night | ✅ fired (unverified) |

---

## Account 7 — `nextgencapital_292` (reconnected again)  ← ACTIVE
- **Platform ID:** `6ac4984d9117edafc7754e69` (new connection — operator confirmed: same TikTok account as Accounts 5 & 6, old connection posts stay valid)
- **Key used:** `taisly_b953…e21e`
- **Created:** Tue 06 Oct 2026 · Rule: every day must end with ☀️ day + 🌙 night; this batch fills the slots missing from the previous batch

| historyId | Vid | When (UK) | Slot | Status |
|---|---|---|---|---|
| `6ac4999b9117edafc7754f44` | vid_24 | Tue 06 Oct 12:30 PM | ☀️ day | 🕐 upcoming |
| `6ac4999e9117edafc7754f4e` | vid_25 | Tue 06 Oct 8:30 PM | 🌙 night |  upcoming |
| `6ac499a19117edafc7754f59` | vid_26 | Fri 09 Oct 12:30 PM | ☀️ day | 🕐 upcoming |
| `6ac499a49117edafc7754f63` | vid_27 | Fri 09 Oct 8:30 PM | 🌙 night | 🕐 upcoming |
| `6ac499a79117edafc7754f6d` | vid_28 | Sat 10 Oct 12:30 PM | ☀️ day | 🕐 upcoming |

Wed 07 & Thu 08 Oct need no new posts — already full (day+night) from Campaign 6.

---

## Key → Account Map (for instant lookup)

| Taisly key (masked) | TikTok username | Platform ID |
|---|---|---|
| `taisly_c5de…ca4` | neo3hrbiytf | `6ab4d6a4e020b5ccdefbe11a` |
| `taisly_a49c…80ac` | neo3hrbiytf | `6ab4d6a4e020b5ccdefbe11a` (same as above) |
| `taisly_b58c…e383` | techstacker0 | `6ab74763e020b5ccdefd014c` |
| `taisly_e07b…ed44` | user9065197799710 | `6ab68767e020b5ccdefca7ea` |
| `taisly_4ad2…943a` | businesssignals_20 | `6abe388d3716f32795361307` |
| `taisly_0f98…56547` | nextgencapital_292 | `6ac0c82b502f9f77444eec34` |
| `taisly_71ab…273a` | nextgencapital_292 (reconnected) | `6ac495c69117edafc7754cdc` |
| `taisly_b953…e21e` | nextgencapital_292 (reconnected again) | `6ac4984d9117edafc7754e69` |

---

## Totals (as of Tue 06 Oct 2026, UK)

- **Accounts tracked:** 7
- **Keys logged:** 8
- **Posts created:** 33 (23 fired/unverified · 10 upcoming on nextgencapital_292)
- **Videos used:** vid_02 – vid_28 (27 of 50) · **next up: vid_29**
- **Standing caption:** "Money is power / Produced by @atomikgrowth / #AI #ArtificialIntelligence #Tech #Startup #Business #Entrepreneur"

*Update this file on every key arrival and every posts:create. Verify "unverified" posts with `taisly posts:status --id <historyId>` when asked.*
