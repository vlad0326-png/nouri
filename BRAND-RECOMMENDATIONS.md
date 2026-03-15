# Nouri — Recommendations from Brand Voice & Competitive Analysis

Based on **nouri-brand-voice-guidelines.md** and **nouri-competitive-analysis.md**.  
Changes below are applied in `index.html` where noted; the rest are recommendations for future iterations.

---

## 1. Copy changes applied in code

| Location | Before | After | Reason |
|----------|--------|-------|--------|
| Toast after logging meal | "Meal logged!" | "Logged." | **Speed is respect** — tight confirmations. |
| Insights long-term gaps header | "CONSISTENT GAPS" | "NUTRIENTS TO BUILD" | **No judgment** — forward-looking, not clinical. |
| Today 7-day card header | "YOUR PICTURE" | "BUILDING YOUR PICTURE" | **Locked copy** — early logging card. |
| Phase 2 insight (late eating) | "Whoop sleep recovery" | "Whoop recovery + HRV data" | **Phase 2 voice** — matches brand note. |
| Analysis error (Snap) | "Analysis failed. Try again or use search." | "Couldn't analyze the photo. Try again or use Search mode." | **Error states** — direct, actionable, one sentence. |
| Search error (Snap) | "Search failed. Please try again." | "Couldn't complete search. Try again." | Same tone. |

---

## 2. Already aligned (no change)

- **Score labels:** Excellent, Good, Fair, Light — no Poor/Bad.
- **Gap card (Today):** "STILL TO GET TODAY" — matches locked copy.
- **Empty state:** "No meals logged yet. Tap + to get started." — factual, calm.
- **Greeting:** "Good morning" / "Good afternoon" / "Good evening" — warm, brief.
- **Analysis steps:** "Identifying foods...", "Estimating portions...", "Calculating nutrients...", "Almost done..." — informative, active.
- **Me footer:** "Your food. Your body. Connected." — tagline present.
- **Saved:** "Saved!" for goals — short.
- **MORNING CHECK-IN,** **DAILY GOALS** — section headers label, don’t editorialize.

---

## 3. Recommendations for future work

### Voice & framing

- **Lead with life area before nutrient:** Wherever a single nutrient is highlighted, prefer "😴 Sleep & Recovery: Magnesium" over "Magnesium" alone. Already done in LIFE_IMPACT / gap cards; extend to any new surfaces (e.g. tooltips, insights).
- **Insight tone:** Keep observations in the style of the guidelines: data + felt outcome (e.g. "When your magnesium is on target, you rate your energy 4.1 vs 2.8 on low days"). Avoid prescription or alarm.
- **Weekly summary:** Line "{gapNut} needs more attention" is acceptable (helpful, not shaming). Optional softer variant: "Worth adding: {gapNut}."

### Product & positioning

- **Category language:** In app store copy, one-liners, or any external-facing text, use **"health intelligence"** (not "food tracker" or "calorie counter") to align with competitive positioning.
- **One-sentence pitch:** Use the refined line from competitive analysis in marketing and pitch materials: *"Nouri is the first app that shows you the connection between what you eat and how you live — 30 nutrients tracked, patterns found automatically, no judgment, ever."*
- **Phase 2 in the product:** Keep and reuse the Phase 2 line wherever you reference future wearable integration: *"In Phase 2, this will correlate with Whoop recovery + HRV data."* Confident, not promotional.

### Optional micro-copy (applied)

- **App load:** "Loading..." → **"Starting Nouri…"** (branded bootstrap moment).
- **Check-in done:** "✓ Morning check-in logged" → **"✓ Check-in logged"** (shorter, same meaning).
- **Weekly summary:** "{gapNut} needs more attention" → **"Worth adding: {gapNut}"** (softer, forward-looking).

---

## 4. Locked copy checklist (reference)

Ensure these stay as specified in the brand doc:

- Food Detail primary CTA: **"Portions look right — Log it ✓"**
- Add item placeholder: **"What else was on the plate?"**
- Calibration value prop: **"One photo calibrates your hand size forever."**
- Skip pattern: **"Skip — I'll do this later"**
- Badges: **"✓ Verified manufacturer data"** / **"✓ High confidence — hand scale used"** / **"~ AI-estimated values"**
- App tagline / footer: **"Your food. Your body. Connected."**
- Gap card header: **"Still to get today"**
- Early logging card: **"Building your picture"**
- 30-day milestone: **"30 days. This isn't a diet. This is a habit."**

---

*These recommendations should be revisited when adding new screens, onboarding flows, or marketing copy.*
