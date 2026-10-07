#  TikTok Posting Operations — Memoir & Work Log

**Account operator:** @atomikgrowth
**Video source repo:** [swathigampa354-ship-it/deepseek-openai-title-variants](https://github.com/swathigampa354-ship-it/deepseek-openai-title-variants)
- `videos/` — **Batch 1**: vid_01–vid_50 (50)
- `batch2/` — **Batch 2**: vid_01–vid_50 (50, added 06 Oct) — same video/style, different headlines. Numbering restarts, so always reference as `batch1/vid_XX` vs `batch2/vid_XX`.
**Posting platform:** Taisly agent API (`@taisly/agent` npm CLI, `taisly` binary)
**Target platforms:** TikTok (9 accounts) + Instagram (1 account: businessdecoded67)

> Security note: Taisly API keys and tokens are deliberately **masked** in this document (per skill safety rules: never print secrets). Full credentials live only in the operator's possession.

---

## 1. Standing Caption (used on every post)

```
Money is power

Produced by @atomikgrowth

#AI #ArtificialIntelligence #Tech #Startup #Business #Entrepreneur
```

---

## 2. Timing Strategy (researched from 2026 data: Buffer 7.1M posts, RecurPost 2M+ posts, Sprout Social, UK-specific studies of 7M+ UK posts)

| Strategy | Window (UK) | Notes |
|---|---|---|
| Lunch peak | 12:30 PM | Most reliable midday slot; post 30–60 min before the 1 PM scroll wave ("velocity rule") |
| Evening prime | 7:00 PM | Before the 8–9 PM UK peak; biggest audience window 7–10 PM |
| Overnight (adopted) | **12:30 AM** | Best slot inside the 12 AM–5 AM band (peak = 12–1 AM; 2–5 AM is the dead zone) |
| Avoid | Mon before 9 AM, weekdays 2–5 PM, 2–5 AM | Documented low engagement |

Original 2-per-day plan: **12:30 PM + 7:00 PM** (6.5 h gap). Later consolidated to single overnight slot at **12:30 AM UK**.

**DST note:** UK on BST (UTC+1) until Sun 25 Oct 2026, then GMT (UTC+0). All Taisly schedules use explicit offsets, so UK wall-clock time must be re-checked at the switch.

**Batch pattern (STANDING RULE since 06 Oct):** each new Taisly key = **5 posts**. Batches **alternate day → night on the SAME 5 days**:
- Odd key → **day batch**: 5 posts at 12:30 PM UK on 5 consecutive days (starting the next available day)
- Even key → **night batch**: 5 posts at 8:30 PM UK on **those same 5 days**
- Result: every day = exactly 2 posts (day + night, 8h gap). 2 keys = 10 days = 20 posts.
- Always: verify username + platform ID via `platforms:list` (same ID = append, new ID = new ledger entry) and take the next unused videos in order.
- **Auto-choose (06 Oct):** operator sends bare keys without day/night labels; the agent continues the alternation itself (day → night → day → …).

---

## 3. Video Inventory (repo: vid_01–vid_50)

| Vid | Used? | Campaign |
|---|---|---|
| vid_01 | — not used | |
| vid_02 | ✅ | Campaign 1 (moved to end), Campaign 2 (1 AM slot) |
| vid_03 | ✅ | Campaign 1 (day 1), Campaign 2 (posted NOW 26 Sep) |
| vid_04 | ✅ | Campaign 1 (day 2), Campaign 2 (1 AM 27 Sep) |
| vid_05 | ✅ | Campaign 1 (day 3), Campaign 2 (1 AM 28 Sep) |
| vid_06 | ✅ | Campaign 1 (day 4), Campaign 2 (1 AM 29 Sep) |
| vid_07 | ✅ | Campaign 3 (posted NOW 28 Sep) |
| vid_08 | ✅ | Campaign 3 (12:30 AM 29 Sep) |
| vid_09 | ✅ | Campaign 3 (12:30 AM 30 Sep) |
| vid_10 | ✅ | Campaign 3 (12:30 AM 01 Oct) |
| vid_11 | ✅ | Campaign 4 (posted NOW 01 Oct) |
| vid_12 | ✅ | Campaign 4 (12:30 AM 02 Oct) |
| vid_13 | ✅ | Campaign 4 (12:30 AM 03 Oct) |
| vid_14 | ✅ | Campaign 5 (posted NOW 03 Oct) |
| vid_15 | ✅ | Campaign 5 (12:30 AM 04 Oct) |
| vid_16 | ✅ | Campaign 5 (12:30 AM 05 Oct) |
| vid_17 | ✅ | Campaign 5 (12:30 AM 06 Oct) |
| vid_18–vid_50 | ⏳ | 33 videos remaining — next batch starts at vid_18 |

Video specs: ~2.27 MB MP4, ISO Media, TikTok schema-compliant (≤500 MB, 3–90 s, 9:16).

---

## 4. Campaign Log

### Campaign 1 — TikTok `neo3hrbiytf` (platform id `6ab4d6a4e020b5ccdefbe11a`)
- **Key:** `taisly_c5de…ca4` (later also accessed with `taisly_a49c…80ac` — same workspace)
- **Date:** Wed 24 Sep 2026 · **Timing:** 12:30 PM UK (BST)
- **Plan evolution:** initially 03/04/05/06 at 12:30 PM on 25–28 Sep with 02 on 29 Sep; user had already posted manually that day → "cancel today, move vid_02 to the end" → final schedule below.
- **Final schedule & historyIds:**

| When (UK) | Video | historyId | Status at log time |
|---|---|---|---|
| Thu 25 Sep 12:30 PM | vid_03 | `6ab513f8e020b5ccdefc04af` | PENDING |
| Fri 26 Sep 12:30 PM | vid_04 | `6ab513fbe020b5ccdefc04c9` | PENDING |
| Sat 27 Sep 12:30 PM | vid_05 | `6ab513fee020b5ccdefc04d3` | PENDING |
| Sun 28 Sep 12:30 PM | vid_06 | `6ab51402e020b5ccdefc04dd` | PENDING |
| Tue 29 Sep 12:30 PM | vid_02 | `6ab51405e020b5ccdefc04e7` | PENDING |

- ⚠️ **Open item:** these 5 scheduled posts were never cancelled (Taisly agent API has **no cancel/delete** capability). If that workspace/account is still active, they may have fired on schedule — verify in Taisly dashboard / TikTok account.
- ⚠️ **Disconnect request (24–25 Sep):** user asked to remove the connected TikTok account. Verified exhaustively: the agent API (CLI + full MCP tool list) exposes **no disconnect/remove command** — only possible manually at app.taisly.com.

### Campaign 2 — TikTok `techstacker0` (platform id `6ab74763e020b5ccdefd014c`)
- **Key:** `taisly_b58c…e383` · **Date:** Sat 26 Sep 2026
- **Timing:** immediate post + 1:00 AM UK (chosen by user after overnight-window research)
- **Order rule:** "leave the 1st vid" → vid_02 deferred to end of line.

| When (UK) | Video | historyId |
|---|---|---|
| Sat 26 Sep ~5:22 AM (NOW) | vid_03 | `6ab7489ae020b5ccdefd01f3` |
| Sun 27 Sep 1:00 AM | vid_04 | `6ab7489ee020b5ccdefd0202` |
| Mon 28 Sep 1:00 AM | vid_05 | `6ab748a1e020b5ccdefd020c` |
| Tue 29 Sep 1:00 AM | vid_06 | `6ab748a4e020b5ccdefd0216` |
| Wed 30 Sep 1:00 AM | vid_02 | `6ab748a7e020b5ccdefd0222` |

- ⚠️ 1:00 AM sits just past the overnight peak (12–1 AM); user subsequently moved the timing to 12:30 AM for Campaign 3+.

### Campaign 3 — TikTok `user9065197799710` (platform id `6ab68767e020b5ccdefca7ea`)
- **Key:** `taisly_e07b…ed44` · **Date:** Mon 28 Sep 2026
- **Timing:** 12:30 AM UK (new standing overnight slot) · **Batch:** vid_07–10

| When (UK) | Video | historyId |
|---|---|---|
| Mon 28 Sep ~2:10 AM (NOW) | vid_07 | `6ab9be65e020b5ccdefe314c` |
| Tue 29 Sep 12:30 AM | vid_08 | `6ab9be68e020b5ccdefe316d` |
| Wed 30 Sep 12:30 AM | vid_09 | `6ab9be6be020b5ccdefe3183` |
| Thu 01 Oct 12:30 AM | vid_10 | `6ab9be6ee020b5ccdefe3192` |

### Campaign 4 — TikTok `businesssignals_20` (platform id `6abe388d3716f32795361307`)
- **Key:** `taisly_4ad2…943a` · **Date:** Thu 01 Oct 2026
- **Timing:** 12:30 AM UK (standing overnight slot) · **Batch:** vid_11–13

| When (UK) | Video | historyId |
|---|---|---|
| Thu 01 Oct ~11:42 AM (NOW) | vid_11 | `6abe39093716f32795361360` |
| Fri 02 Oct 12:30 AM | vid_12 | `6abe390c3716f3279536136f` |
| Sat 03 Oct 12:30 AM | vid_13 | `6abe390f3716f32795361379` |

### Campaign 5 — TikTok `nextgencapital_292` (platform id `6ac0c82b502f9f77444eec34`)  ← LATEST
- **Key:** `taisly_0f98…56547` · **Date:** Sat 03 Oct 2026
- **Timing:** 12:30 AM UK (standing overnight slot) · **Batch:** vid_14–17

| When (UK) | Video | historyId |
|---|---|---|
| Sat 03 Oct ~10:20 AM (NOW) | vid_14 | `6ac0c8ce502f9f77444eec87` |
| **Sat 03 Oct 12:30 PM** (new 2-slot system: 12:30 PM + 8:30 PM, 8h gap) | vid_18 | `6ac0cff6502f9f77444ef233` |
| Sun 04 Oct 12:30 AM | vid_15 | `6ac0c8d1502f9f77444eec96` |
| Mon 05 Oct 12:30 AM | vid_16 | `6ac0c8d4502f9f77444eeca0` |
| Tue 06 Oct 12:30 AM | vid_17 | `6ac0c8d7502f9f77444eecba` |

- ℹ️ **Correction (03 Oct):** source repo actually contains **vid_01–vid_50 (50 videos)** — an earlier truncated listing made me wrongly report the inventory as exhausted. Used so far: vid_02–vid_17; next up: vid_18.

### Campaign 6 — TikTok `nextgencapital_292` reconnected (platform id `6ac495c69117edafc7754cdc`)  ← LATEST
- **Key:** `taisly_71ab…273a` · **Date:** Tue 06 Oct 2026
- **Note:** same TikTok username as Campaign 5 but a **new connection/platform ID** — ledger rule: new ID = new entry.
- **Timing:** one-off 2:30 PM UK (06 Oct), then fixed **day 12:30 PM / night 8:30 PM** from 07 Oct.

| When (UK) | Video | Slot | historyId |
|---|---|---|---|
| Tue 06 Oct 2:30 PM | vid_19 | one-off | `6ac496d89117edafc7754d7e` |
| Wed 07 Oct 12:30 PM | vid_20 | day | `6ac496db9117edafc7754d88` |
| Wed 07 Oct 8:30 PM | vid_21 | night | `6ac496de9117edafc7754d92` |
| Thu 08 Oct 12:30 PM | vid_22 | day | `6ac496e19117edafc7754d9c` |
| Thu 08 Oct 8:30 PM | vid_23 | night | `6ac496e49117edafc7754da6` |

### Campaign 7 — TikTok `nextgencapital_292` reconnected again (platform id `6ac4984d9117edafc7754e69`)  ← LATEST
- **Key:** `taisly_b953…e21e` · **Date:** Tue 06 Oct 2026
- **Rule change:** operator confirmed old + new connection IDs are the same account (old posts valid). New standing rule: **every day must end with exactly 2 posts — ☀️ day 12:30 PM + 🌙 night 8:30 PM.** Each new batch checks existing schedules per date and adds only the missing slot(s) on that same day.
- Wed 07 & Thu 08 Oct skipped (already full from Campaign 6).

| When (UK) | Video | Slot | historyId |
|---|---|---|---|
| Tue 06 Oct 12:30 PM | vid_24 | day | `6ac4999b9117edafc7754f44` |
| Tue 06 Oct 8:30 PM | vid_25 | night | `6ac4999e9117edafc7754f4e` |
| Fri 09 Oct 12:30 PM | vid_26 | day | `6ac499a19117edafc7754f59` |
| Fri 09 Oct 8:30 PM | vid_27 | night | `6ac499a49117edafc7754f63` |
| Sat 10 Oct 12:30 PM | vid_28 | day | `6ac499a79117edafc7754f6d` |

---

### Campaign 8 — TikTok `slashybks18` / founderintel (platform id `6ac4ce719117edafc7756bcd`)  ← LATEST
- **Key:** `taisly_f436…f364` · **Date:** Tue 06 Oct 2026
- **First brand-new account (not a reconnect).** Operator: "nothing today" → day batch starts Wed 07 Oct.
- **Day batch** (standing rule): 5 × 12:30 PM, Wed 07 → Sun 11 Oct. Night batch = next key, same 5 days at 8:30 PM.

| When (UK) | Video | Slot | historyId |
|---|---|---|---|
| Wed 07 Oct 12:30 PM | vid_29 | day | `6ac4cef89117edafc7756c1e` |
| Thu 08 Oct 12:30 PM | vid_30 | day | `6ac4cefb9117edafc7756c28` |
| Fri 09 Oct 12:30 PM | vid_31 | day | `6ac4cefe9117edafc7756c42` |
| Sat 10 Oct 12:30 PM | vid_32 | day | `6ac4cf019117edafc7756c4c` |
| Sun 11 Oct 12:30 PM | vid_33 | day | `6ac4cf049117edafc7756c56` |

---

### Campaign 9 — TikTok `slashybks18` / founderintel reconnected (platform id `6ac4cf699117edafc7756cc0`)  ← LATEST
- **Key:** `taisly_515e…c98` · **Date:** Tue 06 Oct 2026
- **Night batch** (standing rule): 5 × 8:30 PM on the same 5 anchor days as Campaign 8 (Wed 07 → Sun 11 Oct).

| When (UK) | Video | Slot | historyId |
|---|---|---|---|
| Wed 07 Oct 8:30 PM | vid_34 | night | `6ac4cfa99117edafc7756d14` |
| Thu 08 Oct 8:30 PM | vid_35 | night | `6ac4cfac9117edafc7756d1e` |
| Fri 09 Oct 8:30 PM | vid_36 | night | `6ac4cfaf9117edafc7756d3a` |
| Sat 10 Oct 8:30 PM | vid_37 | night | `6ac4cfb29117edafc7756d66` |
| Sun 11 Oct 8:30 PM | vid_38 | night | `6ac4cfb59117edafc7756d70` |

- ✅ **First full day+night week complete** (07–11 Oct). Next cycle from Mon 12 Oct: next key = day batch.

---

### Campaign 10 — TikTok `slashybks18` / founderintel reconnected #2 (platform id `6ac4d30e9117edafc77571b5`)  ← LATEST
- **Key:** `taisly_f696…8d1` · **Date:** Tue 06 Oct 2026
- **Auto-choose era begins:** operator sends bare keys; agent picks day/night itself (continuing alternation: prev = night → this = day).
- **Day batch:** 5 × 12:30 PM, Mon 12 → Fri 16 Oct. Night batch = next key, same 5 days.

| When (UK) | Video | Slot | historyId |
|---|---|---|---|
| Mon 12 Oct 12:30 PM | vid_39 | day | `6ac4d3909117edafc775720e` |
| Tue 13 Oct 12:30 PM | vid_40 | day | `6ac4d3939117edafc7757218` |
| Wed 14 Oct 12:30 PM | vid_41 | day | `6ac4d3979117edafc7757222` |
| Thu 15 Oct 12:30 PM | vid_42 | day | `6ac4d39a9117edafc775722c` |
| Fri 16 Oct 12:30 PM | vid_43 | day | `6ac4d39d9117edafc7757236` |

---

### Campaign 11 — TikTok `startupdecoded` (platform id `6ac4e3e89117edafc7757e24`)  ← LATEST
- **Key:** `taisly_d5f5…53f2` · **Date:** Tue 06 Oct 2026
- **Brand-new account** (4th distinct TikTok username after neo3hrbiytf, techstacker0, user9065197799710/businesssignals_20, slashybks18). New account = **day batch first**.
- **Day batch:** 5 × 12:30 PM, Wed 07 → Sun 11 Oct (batch1/vid_44–48). Night batch = next key, same days.

| When (UK) | Video | Slot | historyId |
|---|---|---|---|
| Wed 07 Oct 12:30 PM | batch1/vid_44 | day | `6ac4e5129117edafc7757efb` |
| Thu 08 Oct 12:30 PM | batch1/vid_45 | day | `6ac4e5159117edafc7757f05` |
| Fri 09 Oct 12:30 PM | batch1/vid_46 | day | `6ac4e5189117edafc7757f15` |
| Sat 10 Oct 12:30 PM | batch1/vid_47 | day | `6ac4e51c9117edafc7757f2e` |
| Sun 11 Oct 12:30 PM | batch1/vid_48 | day | `6ac4e51f9117edafc7757f45` |

---

### Campaign 12 — TikTok `moneymindset996` / MoneyMindset (platform id `6ac4ed559117edafc77583b6`)  ← LATEST
- **Key:** `taisly_fc1d…d68c` · **Date:** Tue 06 Oct 2026
- **Brand-new account.** Operator rule refined: "new ID starts again — day, night" (each new account begins its own day→night cycle).
- **Day batch:** 5 × 12:30 PM, Wed 07 → Sun 11 Oct. **This batch completes batch 1 (vid_49–50) and begins batch 2 (vid_01–03).**

| When (UK) | Video | Slot | historyId |
|---|---|---|---|
| Wed 07 Oct 12:30 PM | batch1/vid_49 | day | `6ac4ee709117edafc77584af` |
| Thu 08 Oct 12:30 PM | batch1/vid_50 | day | `6ac4ee739117edafc77584b9` |
| Fri 09 Oct 12:30 PM | batch2/vid_01 | day | `6ac4ee769117edafc77584c3` |
| Sat 10 Oct 12:30 PM | batch2/vid_02 | day | `6ac4ee7a9117edafc77584db` |
| Sun 11 Oct 12:30 PM | batch2/vid_03 | day | `6ac4ee7d9117edafc77584ee` |

- ✅ **Batch 1 (videos/vid_02–vid_50): fully deployed.** Queue now runs on batch2.

---

### Campaign 13 — TikTok `moneymindset996` / MoneyMindset reconnected (platform id `6ac4f3229117edafc77587ce`)  ← LATEST
- **Key:** `taisly_de96…741` · **Date:** Tue 06 Oct 2026
- **Night batch** (5 × 8:30 PM on the same 5 anchor days as Campaign 12). Completes moneymindset996's week 07–11 Oct (day+night every day).

| When (UK) | Video | Slot | historyId |
|---|---|---|---|
| Wed 07 Oct 8:30 PM | batch2/vid_04 | night | `6ac4f35b9117edafc7758821` |
| Thu 08 Oct 8:30 PM | batch2/vid_05 | night | `6ac4f35e9117edafc775882b` |
| Fri 09 Oct 8:30 PM | batch2/vid_06 | night | `6ac4f3619117edafc7758835` |
| Sat 10 Oct 8:30 PM | batch2/vid_07 | night | `6ac4f3649117edafc775883f` |
| Sun 11 Oct 8:30 PM | batch2/vid_08 | night | `6ac4f3679117edafc775884c` |

---

### Campaign 14 — TikTok `wealthtechmedia` (platform id `6ac5812545ccb79f0ef25b59`)  ← LATEST
- **Key:** `taisly_e995…69b7` · **Date:** Wed 07 Oct 2026, 00:16 AM UK
- **Brand-new account (9th distinct).** Operator: "post a vid. Now" → immediate off-cycle post (batch2/vid_09). Cycle (day → night) continues with the next keys.

| When (UK) | Video | Slot | historyId |
|---|---|---|---|
| Wed 07 Oct ~12:16 AM (NOW) | batch2/vid_09 | night (today's post) | `6ac5816845ccb79f0ef25bae` |
| Thu 08 Oct 12:30 PM | batch2/vid_10 | day | `6ac583a345ccb79f0ef25c9d` |
| Thu 08 Oct 8:30 PM | batch2/vid_11 | night | `6ac583a645ccb79f0ef25cab` |
| Fri 09 Oct 12:30 PM | batch2/vid_12 | day | `6ac583ae45ccb79f0ef25cb5` |
| Fri 09 Oct 8:30 PM | batch2/vid_13 | night | `6ac583b445ccb79f0ef25cd1` |

---

### Campaign 15 — Instagram `businessdecoded67` (platform id `6ac61a5845ccb79f0ef2cfd1`)  ← LATEST
- **Key:** `taisly_3743…cd5` · **Date:** Wed 07 Oct 2026
- **📸 First Instagram account** — the operation now spans TikTok + Instagram (same CLI, 9:16 reels, same caption).
- **Operator instruction:** "pick from the 5th vid, 5-min gap between each post, post all today" → burst of 5 at 12:30/12:35/12:40/12:45/12:50 PM (batch1/vid_05–09, cross-account reuse).

| When (UK) | Video | historyId |
|---|---|---|
| Wed 07 Oct 12:30 PM | batch1/vid_05 | `6ac61be645ccb79f0ef2d0c2` |
| Wed 07 Oct 12:35 PM | batch1/vid_06 | `6ac61be945ccb79f0ef2d0f2` |
| Wed 07 Oct 12:40 PM | batch1/vid_07 | `6ac61bec45ccb79f0ef2d0fc` |
| Wed 07 Oct 12:45 PM | batch1/vid_08 | `6ac61bef45ccb79f0ef2d106` |
| Wed 07 Oct 12:50 PM | batch1/vid_09 | `6ac61bf245ccb79f0ef2d114` |

---

### Campaign 16 — Instagram `businessdecoded67` reconnected (platform id `6ac61d8b45ccb79f0ef2d202`)  ← LATEST
- **Key:** `taisly_3116…46f` · **Date:** Wed 07 Oct 2026
- **4-post burst, same format as Campaign 15** (5-min gaps, today, from day slot): batch1/vid_10–13 at 12:30/12:35/12:40/12:45 PM.

| When (UK) | Video | historyId |
|---|---|---|
| Wed 07 Oct 12:30 PM | batch1/vid_10 | `6ac61e5d45ccb79f0ef2d269` |
| Wed 07 Oct 12:35 PM | batch1/vid_11 | `6ac61e6045ccb79f0ef2d276` |
| Wed 07 Oct 12:40 PM | batch1/vid_12 | `6ac61e6345ccb79f0ef2d280` |
| Wed 07 Oct 12:45 PM | batch1/vid_13 | `6ac61e6745ccb79f0ef2d29a` |

---

## 5. Operational Notes (gotchas learned)

1. **Sandbox resets** wipe the installed CLI between sessions → always `npm install -g @taisly/agent` (npm prefix = `~/.npm-global`, add `~/.npm-global/bin` to PATH) before running `taisly`.
2. **No destructive API:** Taisly agent API can connect/list/validate/create/status/list/repost — but **no** disconnect, delete, cancel, or reschedule. Changes to scheduled posts = create new + manually cancel old in dashboard.
3. **Status checks:** `taisly posts:status --id <historyId>` · history list: `taisly posts:list --page 1`.
4. **Schedules are one-shot** (ISO datetime with explicit UTC offset); nothing auto-repeats.
5. **Never print secrets** — keys masked here; GitHub token used for the push is not stored in this repo.
6. **DST switch 25 Oct 2026** (BST→GMT): re-verify UK wall-clock times for any posts scheduled after that date.
7. **Videos are pulled on demand** from the source repo and removed from the workspace after each campaign (operator rule: no video files kept in workspace).

## 6. Open Items / Next Steps

- [ ] **Push this memoir repo — PENDING VALID GITHUB TOKEN.** User decision 28 Sep: repo must be **PUBLIC**. The token supplied (`ghp_ikQ8…3mtdfj`) returns 401 (invalid/revoked) — awaiting a fresh token. Everything is committed locally and ready to push: README, MEMOIR.md, HISTORY.md, skill guide.
- [ ] Verify Campaign 1's 5 posts (neo3hrbiytf) — did they fire or were they killed by the disconnect?
- [ ] Verify Campaign 2's 1 AM posts (techstacker0) fired on 27–30 Sep.
- [x] Batch vid_11–13 deployed (Campaign 4, businesssignals_20)
- [x] Batch vid_14–17 deployed (Campaign 5, nextgencapital_292) — next up: batch2/vid_14
- [ ] After ~2 weeks of posts, pull per-account follower-activity analytics and let actual data override the generic peak windows.

## 7. Workspace State

- `tiktok_campaign/MEMOIR.md` — this file
- `tiktok_campaign/TRACKING.md` — **MASTER LEDGER**: every key → TikTok account (ID + username) → all posts
- `tiktok_campaign/HISTORY.md` — machine-usable post history (all historyIds per account)
- `tiktok-memoir-repo/` — local git mirror of the memoir repo (pending push)
- `uploads/` — original TikTok Account Posting Skill
- **No video files** — removed after each campaign per operator rule

---
*Log maintained in `tiktok_campaign/` · last updated 2026-10-06 (Tue) UK time — Campaign 7*
