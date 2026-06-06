---
name: hour-rectification-standalone
description: "Standalone birth hour rectification (校时/命盘校正) skill for narrowing down an unknown Hour Pillar using known life facts. No other skills required — Claude will handle the 3-pillar calibration before beginning rectification. Use this skill whenever the user wants to find, guess, or narrow down a person's birth hour using facts about their life — such as children count and gender, sibling count, marriages, deaths, illnesses, career events, or personality traits. Also trigger when the user says 'what hour could they be born?', 'can we figure out the hour?', 'my client's birth time is unknown', or provides life facts and asks which BaZi or ZWDS configuration fits."
---

# Birth Hour Rectification (命盘校时) — Standalone

This skill guides a systematic, evidence-based process for narrowing an unknown Hour Pillar from 12 candidates to a shortlist of 1–3. The method works because each of the 12 possible Hour Pillars adds a unique stem, branch, hidden stems, and branch interactions to the existing three-pillar chart — making certain life facts incompatible with certain hours.

This is the standalone version — no other skills are required. Claude will complete the 3-pillar calibration (Step 0) before beginning rectification.

---

## Step 0: 3-Pillar Calibration

Before rectification can begin, Claude must derive and calibrate the Year, Month, and Day Pillars from the person's date of birth.

**Required input:** Full date of birth (year, month, day). Sex of the person. Birth location is helpful but not required for BaZi.

**Claude will:**

1. **Calculate the 3-pillar chart** using the solar calendar (节气-based month boundaries). State the Year, Month, and Day Pillars — each with their stem (天干) and branch (地支).

2. **Identify the Day Master (DM)** — the Day Stem is the DM; this is the person's core element.

3. **Assess DM strength** — check:
   - Whether the DM is in season (月令): born in a month where the DM element is dominant, neutral, or weak
   - How many 比劫 (peer/sibling elements) and 印 (Seal/resource) elements are present in stems and branches to support the DM
   - How many 官杀/财 (attacking/draining) elements are present to weaken it
   - Result: classify as 身强 (strong), 身弱 (weak), or 中等 (moderate)

4. **Identify 用神/喜神/忌神/凶神:**
   - 用神 = the element the DM most needs (the core useful god)
   - 喜神 = elements that produce or support the 用神 (secondary helpers)
   - 忌神 = elements that harm the DM or destroy the 用神
   - 凶神 = elements that produce the 忌神

5. **Note key branch interactions** already present in the 3-pillar chart (clashes, harmonies, punishments, combinations) — these are the baseline the Hour Pillar will interact with.

6. **State the 格局 (pattern) from 3 pillars** — e.g. 七杀格, 食神生财格, 官印相生格. This may shift once the Hour Pillar is added, but knowing the 3-pillar tendency helps constrain which hours are structurally plausible.

Once Step 0 is complete, proceed to Step 1.

---

---

## Step 1: Derive All 12 Hour Pillars (五鼠遁日起时)

The Hour Stem is determined by the Day Stem using the Five Rat Escaping formula. The Hour Branch is simply the 12 earthly branches in sequence from 子 to 亥.

| Day Stem | 子 Hour Stem | Sequence |
|---|---|---|
| 甲 or 己 | 甲 | 甲乙丙丁戊己庚辛壬癸甲乙 |
| 乙 or 庚 | 丙 | 丙丁戊己庚辛壬癸甲乙丙丁 |
| 丙 or 辛 | 戊 | 戊己庚辛壬癸甲乙丙丁戊己 |
| 丁 or 壬 | 庚 | 庚辛壬癸甲乙丙丁戊己庚辛 |
| 戊 or 癸 | 壬 | 壬癸甲乙丙丁戊己庚辛壬癸 |

**晚子时 note:** If the person was born between 23:00 and 00:00, they are in 子时 of the *current* day's calendar — the day pillar does not advance until midnight. Most modern systems (including 三合派/lunar-javascript) use this convention; confirm with the app being used.

**DM lifecycle in each branch (quick reference):**
| Branch | 甲 | 丙 | 戊 | 庚 | 壬 |
|---|---|---|---|---|---|
| 子 | 沐浴 | 胎 | 胎 | 死 | 帝旺 |
| 丑 | 冠带 | 养 | 养 | 墓 | 衰 |
| 寅 | 临官 | 长生 | 长生 | 绝 | 病 |
| 卯 | 帝旺 | 沐浴 | 沐浴 | 胎 | 死 |
| 辰 | 衰 | 冠带 | 冠带 | 养 | 墓 |
| 巳 | 病 | 临官 | 临官 | 长生 | 绝 |
| 午 | 死 | 帝旺 | 帝旺 | 沐浴 | 胎 |
| 未 | 墓 | 衰 | 衰 | 冠带 | 养 |
| 申 | 绝 | 病 | 病 | 临官 | 长生 |
| 酉 | 胎 | 死 | 死 | 帝旺 | 沐浴 |
| 戌 | 养 | 墓 | 墓 | 衰 | 冠带 |
| 亥 | 长生 | 绝 | 绝 | 病 | 临官 |

For Yin DMs (乙/丁/己/辛/癸): use the opposite-polarity Yang DM's table above and reverse the scale (帝旺↔长生, 临官↔沐浴, etc.) — or refer to a dedicated table. In practice, the most important check is whether the DM lifecycle in the Hour Branch is supportive (长生/临官/帝旺) or depleting (死/绝/墓/病).

---

## Step 2: Build the Candidate Table

For each of the 12 hours, record:

| 时辰 | Time | Stem | 十神 | Branch | DM in Branch | Metal 比劫 Hidden? | Key Branch Interaction with Natal |
|---|---|---|---|---|---|---|---|
| 子时 | 23–01 | — | — | 子 | — | — | check natal for 午: 子午冲 |
| 丑时 | 01–03 | — | — | 丑 | — | 辛 (湿土 bonus) | check natal for 午: 丑午害; 未: 丑未冲 |
| ... | | | | | | | |

Key branch interactions to check for each Hour Branch against ALL natal branches (Year, Month, Day):

- **六冲 (Clash):** 子午, 丑未, 寅申, 卯酉, 辰戌, 巳亥
- **六合 (Harmony):** 子丑, 寅亥, 卯戌, 辰酉, 巳申, 午未
- **三合 (Triple Harmony, partial):** 申子辰, 寅午戌, 巳酉丑, 亥卯未
- **六害 (Six Harm):** 子未, 丑午, 寅巳, 卯辰, 申亥, 酉戌
- **三刑 (Punishment):** 寅巳申 (持势), 丑戌未 (无礼), 子卯 (无恩), 辰/午/酉/亥 (自刑 — same branch pairs)
- **自刑 (Self-Punishment):** 辰辰, 午午, 酉酉, 亥亥

Interactions with the natal structure are cumulative — a double natal branch (e.g., 寅寅) means the Hour Branch interacts with it twice.

---

## Step 3: Quick Eliminations (Structural Incompatibilities)

Some hours can be eliminated immediately based on structural severity before asking any questions:

**Hard eliminations:**
- **Hour Branch completes 三合 with two natal branches:** e.g., 戌時 when natal has 寅 and 午 = completes 寅午戌 Fire 三合. For a weak Metal DM, completing a Fire 三合 with the Hour is catastrophic — effectively immolates the DM. Eliminate unless the chart is a 从格.
- **Hour Branch 自刑 on a branch already in the natal chart:** e.g., 午时 when 午 is already the Month Branch = 午午 自刑 on the Seal branch. The Seal self-destructs.
- **Hour Branch clashes the DM's Seal while natal Seal is already compromised:** Compounds an already-broken defense.
- **Hour Stem doubles an already-dominant 忌神:** e.g., 七杀 on Hour Stem when 七杀 is already transparent on Month Stem and DM is extremely weak. This pushes the chart past the breaking point.

**Soft eliminations (lower probability, not disqualified):**
- Hour introduces 申寅冲 or similar clash into a natal chart where those branches already host important stars — structurally tense but liveable.
- Hour brings 六害 between its branch and a key natal branch — chronic friction, but not catastrophic.

---

## Step 4: Cross-Reference Known Facts

This is the core of rectification. For each remaining candidate, test it against every known life fact. A candidate is more likely when more facts are mechanistically explained.

### 4A. Siblings (兄弟姐妹)
For the DM's element: 比肩 = same-sex siblings; 劫财 = opposite-sex siblings (in most schools, for Yang DM: 比肩 = brothers, 劫财 = sisters; reverse for Yin DM).

**Method:** Count total 比劫 visible in the chart including the Hour Pillar:
- Transparent 比劫 on stems (Year, Month, Hour) each count strongly
- 比劫 hidden in branches at 临官/帝旺/长生 count moderately
- 比劫 hidden at 死/绝/墓 count weakly or not at all
- The Day Branch hidden stem IS counted (it's the DM's own branch)

If the known sibling count is high (4–6+) but zero 比劫 exists in the 3-pillar chart, the Hour Pillar almost certainly provides the missing Metal/peer energy.

### 4B. Children (子女)
For the DM: output stars (食神/伤官) = children. For male DM: 食神 = son, 伤官 = daughter (common school). For female DM: conventions vary by school — use whichever is consistent with other verified readings in the practice.

The lifecycle phase of the output star matters:
- Output star at 病/死/绝 → difficulty bearing children; abortions, complications
- Output star at 临官/帝旺 → children more easily/prominently realized
- Number visible = upper bound on children (one transparent output star = maximum one line of children without timing activation)

### 4C. Parents (父母)
- **印星 (Seal) = Mother** for most DMs. The branch(es) hosting the Seal star are the "mother's home."
- The year a parent dies: a 流年 that clashes or harms the branch hosting the parent star. If verifying death year, check: which natal branch hosts the parent star → what clash/harm destroys that branch → does that match the death year?
- The Hour Pillar may introduce a new Seal branch (strengthening/weakening the mother) or clash an existing one.

### 4D. Spouse (配偶)
- For female DM: 官杀 = husband. 七杀 = dominant/forceful partner; 正官 = conventional/stable partner.
- For male DM: 财星 = wife. 偏财 = affairs/multiple relationships; 正财 = conventional wife.
- Hour Stem visibility of spouse star: if a transparent spouse star is on the Hour stem, the person's partner energy is very present in the life axis.
- Marriage year: DM typically marries when 大运/流年 strongly activates the spouse star or strengthens the DM enough to support marriage.

### 4E. Health and Illness
The Hour Pillar can either:
1. **Worsen** a constitutional weakness (Hour Branch adds more of the attacking element, or attacks the Seal)
2. **Partially protect** (Hour brings Seal support or 比劫 peer support)
3. **Reveal timing** of illness onset (Hour Branch in conflict with 大运 that triggered the illness)

Map known illnesses to Five Element organ correspondences and check whether the Hour's element contribution is consistent.

**Five Element organ correspondence table:**

| Element | Yin Organ (阴) | Yang Organ (阳) | Body Systems |
|---|---|---|---|
| Wood (木) | Liver (肝) | Gallbladder (胆) | Tendons, eyes, nervous system |
| Fire (火) | Heart (心) | Small Intestine (小肠) | Blood vessels, tongue |
| Earth (土) | Spleen/Pancreas (脾) | Stomach (胃) | Muscles, digestive system |
| Metal (金) | Lungs (肺) | Large Intestine (大肠) | Skin, respiratory system, colon |
| Water (水) | Kidneys (肾) | Bladder (膀胱) | Bones, ears, reproductive system |

An excess or deficiency of an element in the Hour Pillar can worsen or protect the corresponding organ system. A weak DM element attacked by the Hour Branch typically manifests as illness in the organ system governed by the DM element.

### 4F. Major Life Events (Career, Relocation, Transitions)
Large transitions (immigration, major career shift, founding a business) typically have a BaZi mechanism: a 大运 or 流年 activating the relevant ten god domain. The Hour Pillar can reveal which domains are "live" in the natal chart — a transparent Wealth star on the Hour stem means financial/external-world events are more prominently triggered in their timing years.

ZWDS is the more precise tool for relocation (迁移宫) and career events (事业宫) — if the birth time can be narrowed to 2–3 candidates, running all candidates in the Destiny Reading App and comparing palace configurations is highly recommended.

### 4G. Personality Traits Beyond 3 Pillars
The Hour Pillar represents the innermost layer — private self, deeply held drives. If a known personality trait cannot be explained by the 3-pillar structure, ask: which Hour Stem would add that ten god?

- Unexplained assertiveness/competitiveness beyond what Day Stem shows → 比劫 Hour Stem?
- Strong creative output / non-conformism not yet in chart → 食伤 Hour Stem?
- Hidden intellectual depth, strong internal values → 印 Hour Stem?
- Restless external drive, entrepreneurial instinct → 财 Hour Stem?
- Hidden authority complex / unconventional power dynamic → 官杀 Hour Stem?

### 4H. LP Arc 格局 Consistency Test

This is one of the most powerful BaZi-internal elimination tests available — and it requires no ZWDS chart. The logic is:

> The Hour Pillar determines the final 格局 of the chart. Different 格局s predict fundamentally different outcomes for the same LP stem. If a candidate hour produces a 格局 that makes a person's most successful decades structurally catastrophic, or their most disastrous decades structurally auspicious — that hour is wrong.

**Why the Hour Pillar determines 格局:**
The Hour Stem is the fourth and final transparent stem. Adding it can shift the dominant 格局 entirely — e.g., a three-pillar chart without a transparent 官杀 becomes 七杀格 if the Hour Stem is 七杀; or a three-pillar chart with apparent 财格 structure becomes 伤官生财格 if the Hour Stem is 伤官. Different 格局s have fundamentally different responses to LP energies.

**How to apply:**

1. Identify 2–3 candidate hours still in the running.
2. For each candidate, determine what 格局 that Hour Pillar produces.
3. Map the known LP arc against that 格局's predicted LP responses (see table below).
4. Check: does the 格局 explain why the person's richest/most successful LPs were auspicious? Does it explain why their crisis LPs were hard?
5. If a candidate 格局 predicts the wrong outcomes for known LP events — eliminate it.

**Known LP events to test (use the most extreme):**
- The person's single greatest decade of wealth creation or career achievement
- The person's worst financial crisis or personal tragedy
- Any LP where a specific major event (founding a company, losing everything, marrying, divorcing) is documented

**Common 格局 × LP interaction patterns:**

| 格局 | 比劫 LP | 食伤 LP | 财 LP | 官杀 LP | 印 LP |
|---|---|---|---|---|---|
| **七杀格 + 食神制杀** (身强) | Often GOOD — Metal generates Water → strengthens 食神制杀 chain; also gives DM capacity to face 七杀 | GOOD — directly powers the 制杀 mechanism | Mixed — 财生七杀 can intensify 七杀 pressure beyond what 制杀 manages; or excellent if DM can absorb | Mixed — 正官 adds structure; 七杀 intensifies total 杀 load | Mixed — 印 supports DM but can suppress 食神 (枭印夺食), weakening the 制杀 mechanism |
| **伤官生财格** (身强) | BAD — 劫财 directly competes with 财星; 比肩 adds more competitors for same wealth pool | GOOD — strengthens output→wealth chain | GOOD — activates 财星 | Mixed — can provide structure if DM is also generating 食伤 | BAD — 印 suppresses 食伤, killing the output engine; 身强 + 印 = complacency + no output |
| **食神生财格** (身强) | BAD — 比劫 competes for 财; 劫财 is most dangerous | GOOD | GOOD | Mixed | BAD — 印 suppresses 食神; the entire wealth mechanism is 食神生财, so suppressing 食神 is catastrophic |
| **官印相生格** (身弱) | Mixed — 比劫 provides DM support, enabling DM to receive the 官→印→DM chain; can be helpful | BAD — 食伤 drains 身弱 DM; 伤官见官 is especially dangerous if 正官 is present | BAD — 财 destroys 印; 身弱 cannot hold 财 without Seal protection | GOOD — activates the chain | GOOD — nurtures the DM and sustains the chain |
| **杀印相生格** (身弱) | Mixed — 比劫 provides DM peer support; can be helpful in moderation | BAD — 食伤 can suppress 七杀, breaking the 杀→印→DM chain | BAD — 财 destroys 印 | GOOD (七杀) — feeds the chain | GOOD — essential Seal nurturing |

**CRITICAL warning — 格局 can be more nuanced than the simple table suggests.** Always check:
- Does the LP stem generate or destroy a key chain element? (e.g., 比劫 Metal in a 七杀格 feeds Metal→Water→食神→制杀 — this is a two-step indirect benefit, not obvious from the table)
- Does the LP branch contain hidden stems that change the picture? (e.g., LP stem is 印 but the LP branch contains 食神 at 帝旺 — the 印 effect is partially counteracted)
- Is there a special combination between the LP stem and a natal stem? (e.g., 乙庚合 means a 劫财 LP cannot easily steal 乙正财 because it is already bonded to the DM)

**Calibration example — Jeff Bezos (庚金 DM):**

Known facts: LP4 辛酉 (33–42, 1996–2005) = Amazon IPO + Blue Origin founding = peak wealth creation. LP5 庚申 (43–52, 2006–2015) = AWS launch + Washington Post = continued dominance.

Two candidate hours:
- **甲戌時 (wrong):** Hour Stem = 甲偏财. 格局 = 伤官生财格 + 双财透干. In this 格局, 比劫 LPs are worst-case: LP4 辛劫财 directly attacks 乙正财 (Month Stem) and 甲偏财 (Hour Stem); LP5 庚比肩 adds more Metal competition for the same two wealth stars. Both LPs should produce financial rivalry and wealth loss. Contradicts known reality. **ELIMINATED.**
- **丙戌時 (correct):** Hour Stem = 丙七杀. 格局 = 七杀格 + 食神制杀. In this 格局, 比劫 Metal LPs generate Water (Metal→Water generating cycle), which strengthens 壬食神 (hidden in 申), which powers the 食神制杀 mechanism, channeling 七杀 aggression most productively. Additionally, 乙庚合 protects 乙正财 from 辛劫财 interference. Both LPs should produce peak competitive output. Matches known reality. **CONFIRMED.**

The LP arc produces a clean binary outcome: one hour makes LP4/LP5 structurally disastrous; the other makes them structurally auspicious. This is often the strongest pre-ZWDS elimination test available.

**Calibration example — JK Rowling (丙火 DM):**

Known fact: LP4 丁亥 (34–43, 1998–2007) = entire Harry Potter series (Books 1–7) + becoming the world's richest author = peak creative and financial achievement.

The 丙戌 Hour Pillar (confirmed) produces a 伤官格 + 官印相生 structure. LP4 丁亥 brings: 亥 Branch contains 壬七杀 at 帝旺 + 甲偏印 at 长生 → 杀印相生 fires (七杀→印→DM). In 杀印相生, external pressure (七杀/public criticism/institutional pressure) converts into creative inspiration (偏印), which nourishes the DM's output capacity. The entire HP series — written under the pressure of single-parent poverty, publisher rejections, and institutional doubt — is structurally encoded in LP4's 杀印相生 mechanism. Any hour that does NOT produce 伤官格 or that disrupts this chain would fail to explain LP4's creative explosion. The LP arc confirms the 格局 derived from 戌時. ✓

---

### 4I. ZWDS Palace Verification
If 2–3 candidates remain after BaZi elimination, run each through the Destiny Reading App and compare:
- **命宫 star**: does the ZWDS 命宫 star match the person's known personality?
- **夫妻宫**: does the marriage palace match known relationship history?
- **疾厄宫**: does the illness palace explain known health conditions?
- **父母宫/兄弟宫**: do these palaces match known family facts?
- **交友宫/事业宫**: are career and network palaces consistent with actual life?

ZWDS is often the tiebreaker when 2 BaZi candidates both seem plausible.

---

## Step 5: Interactive Questioning Framework

Work through these question categories in order of elimination power — start with questions most likely to eliminate the most candidates at once:

1. **Time of day (rough):** "Do you know roughly what time of day they were born — morning, afternoon, evening, or night?" This eliminates ~half the 12 candidates immediately. Even "definitely daytime" or "late at night" is useful.

1B. **LP arc consistency (if client is public/historical figure or LP history is known):** Before asking personal questions, check whether the known LP arc eliminates any candidates via 格局 inconsistency (Step 4H). This is the strongest pre-ZWDS filter and requires no personal questioning — just calendar matching and structural logic. Do this silently against the candidate table before proceeding.

2. **Sibling count and gender breakdown:** If zero 比劫 in 3 pillars, this is the primary constraint. Ask: how many siblings, and what genders? Then check: which hours supply Metal (for Metal DM's 比劫)?

3. **Children:** How many children? Any pregnancies that were lost? For female charts: were there difficult pregnancies or complications? This cross-checks the output star lifecycle in the candidate hours.

4. **Spouse character:** For female chart — was the husband a dominant/controlling type (七杀) or stable/conventional (正官)? Did the Hour Stem contribute a spouse star not already visible?

5. **Specific personality dimension:** Is there a striking trait not already explained by the 3-pillar structure? Ask Andy to describe what's distinctive about the person beyond their Day Master's typical profile.

6. **Health specifics:** Any illnesses other than what's already verified? Location in the body? Onset timing?

7. **Career and occupation:** What field did they work in? This can suggest which ten god is most prominent in the Hour.

8. **ZWDS tiebreaker:** If down to 2–3 candidates, ask Andy to run those hours in the Destiny Reading App and compare 命宫 stars against what he knows about the person.

---

## Step 6: Present the Shortlist and Eliminate

After each round of questioning, update the candidate table:

- Mark eliminated candidates with ✗ and the reason
- Mark probables with ✓ and the supporting evidence
- Mark strong candidates with ✓✓

**Goal:** Reach a shortlist of 1–3 candidates with documented reasoning, then recommend ZWDS verification for the final call.

**Final output format:**
```
Remaining candidates: [丑时, 酉时]
Most likely: 酉时 (乙酉) — because [mechanism A, mechanism B verified]
Runner-up: 丑时 (丁丑) — because [mechanism C] but [concern D]
Eliminated: [list with reasons]
Recommended next step: Run 酉时 and 丑时 in Destiny Reading App, compare 命宫/夫妻宫/疾厄宫
```

---

## Quick Reference: Hidden Stems by Branch

| Branch | Main Hidden Stem | Secondary | Minor |
|---|---|---|---|
| 子 | 壬 | — | 癸 |
| 丑 | 己 | 癸 | 辛 |
| 寅 | 甲 | 丙 | 戊 |
| 卯 | 乙 | — | — |
| 辰 | 戊 | 乙 | 癸 |
| 巳 | 丙 | 庚 | 戊 |
| 午 | 丁 | — | 己 |
| 未 | 己 | 丁 | 乙 |
| 申 | 庚 | 壬 | 戊 |
| 酉 | 辛 | — | — |
| 戌 | 戊 | 辛 | 丁 |
| 亥 | 壬 | — | 甲 |
