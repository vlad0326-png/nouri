# Nouri — Code review: bugs, usability, premium feel

Review date: 2025-03-15.  
**Note:** You mentioned “here is the vision” but no vision text was attached. Once you share it, the review can be aligned to that vision.

---

## Bugs found and fixed

### 1. **No API key → generic error**
- **Issue:** If the user hasn’t set an Anthropic API key (Me → AI Connection), photo analysis and search still call the API. They get a generic “Analysis failed” or “API error 401” with no guidance.
- **Fix:** Check `getApiKey()` before calling `analyzeFood()` for photo/search. If empty, show a clear message and direct the user to add the key in Me (e.g. “Add your API key in Me to use photo analysis and search”).

### 2. **API response shape can crash the app**
- **Issue:** `data.content[0].text` is used without checking that `data.content` and `data.content[0]` exist. Odd or empty API responses can throw and break the flow.
- **Fix:** Use optional chaining and a clear fallback message, e.g. throw “Could not parse AI response — please try again” when `data?.content?.[0]?.text` is missing.

### 3. **Quick Add form can save NaN**
- **Issue:** In MeScreen’s Quick Add form, macro inputs (Cal, Protein, Carbs, Fat) use `Number(cal)` etc. Empty is fine (0), but invalid input (e.g. “e” or “1.2.3”) becomes `NaN` and can be stored in nutrients.
- **Fix:** Coerce to a valid number (e.g. `Number(x) || 0` or `parseFloat(x) || 0`) when building the nutrients object so stored values are always numbers.

### 4. **Init error never shown**
- **Issue:** If `init()` (load profile/meals/checkins from storage) throws, `setInitError(String(e))` runs but `finally` still sets `screen` to `'main'` or `'onboard'`. The user leaves the loading screen and never sees the error.
- **Fix:** When `initError` is set, keep showing the loading/error state and add a “Try again” action that clears the error and re-runs init so the user can recover.

### 5. **HeroRing protein goal default**
- **Issue:** `protGoal = goals.protein_g || 175` forces 175 when `goals.protein_g` is 0 or missing. Default goals use 50 g protein; 175 is the high-protein preset. New or “General” users should see 50, not 175.
- **Fix:** Use `goals.protein_g` with a fallback to `DEFAULT_GOALS.protein_g` (e.g. 50), not 175.

### 6. **resizeImage never rejects on load failure**
- **Issue:** `resizeImage(dataUrl)` creates an `Image` and resolves in `onload`. If the image fails to load, `onerror` is not handled and the Promise never settles.
- **Fix:** In `img.onerror`, call `reject(new Error('Image failed to load'))` (or similar) so callers can handle failure.

---

## Usability

- **Good:** Today / Insights / Snap / History / Me flow is clear. Quick Add, barcode, search, and camera give multiple ways to log. Morning check-in and post-meal “how much did you finish?” are thoughtful.
- **Good:** Empty states explain what to do (“No meals logged yet”, “Tap + to get started”, “Insights unlock after 7 days”).
- **Improve:** When API key is missing, guide the user to Me instead of a generic failure (covered in bugs above).
- **Improve:** After a storage/init error, offer “Try again” so the app doesn’t feel stuck (covered above).
- **Optional:** Consider a small “What’s this?” or info icon next to Nouri Score / hand calibration for first-time users.

---

## Premium feel

- **Good:** Dark theme, green accent (#3ECF8E), glass panels, and consistent spacing feel cohesive. Animations (fadeIn, breathe, spin, progressFill) add polish. Hero ring and meal cards look strong.
- **Good:** Typography (Inter), letter-spacing, and uppercase labels (“MORNING CHECK-IN”, “STILL TO GET TODAY”) give a clear hierarchy.
- **Good:** Buttons use gradients, subtle borders, and tap feedback (`button:active { transform: scale(0.97) }`).
- **Refinements (optional):**
  - Slightly increase bottom nav safe area on notched devices so the green + button doesn’t sit too low.
  - Ensure all primary CTAs share the same gradient and corner radius for a consistent “premium” look.
  - Consider a very subtle motion on the Today greeting (e.g. fade-in or slight slide) so the first screen feels alive.

---

## Summary

- **Bugs:** 6 concrete issues identified; fixes applied in code (API key check, API parsing, QAForm NaN, init error handling, HeroRing default, resizeImage reject).
- **Usability:** Solid flows and empty states; main gaps were API key guidance and init error recovery, now addressed.
- **Premium:** Already strong; a few optional tweaks (safe area, CTA consistency, light motion) can push it further.

Once you share your vision doc, the same checklist can be used to confirm every item aligns with it (e.g. “feels premium”, “usable without an API key”, etc.).
