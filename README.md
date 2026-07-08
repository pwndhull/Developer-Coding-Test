# Developer-Coding-Test
 
**Role:** React Native / Mobile Developer
**Time expected:** 3–4 hours (hard cap: submit whatever you have at 5 hours)
**Submission:** GitHub repo link (public or invite `<pwndhull>`) + a short Loom/video walkthrough (optional but a plus)
 
---
 
## Part 1 — Take-Home Task: "Mini Tracker"
 
Build a small React Native (Expo) app backed by Supabase with the following:
 
### Requirements
 
**1. Auth**
- Email/password sign up and sign in using Supabase Auth
- Persist session across app restarts
- Basic error states (wrong password, network failure)
**2. Items list (CRUD)**
- After login, show a list of "items" belonging to the signed-in user only (e.g., tasks, bills, notes — your choice)
- Create, edit, delete items
- Each item: title, amount or count (numeric), status (e.g., pending/done), created_at
- Pull-to-refresh
**3. One "real-world" feature (pick ONE):**
- **Offline-first:** items created while offline sync when connection returns
- **Realtime:** list updates live when a row changes in Supabase (test with two simulators or the Supabase dashboard)
- **Edge Function:** a Supabase Edge Function that runs a summary (e.g., total pending amount) and the app displays its result
**4. Code quality expectations**
- TypeScript
- Sensible folder structure (screens/components/hooks/services separated)
- Row Level Security enabled on the Supabase table — users must NOT be able to read each other's data
- A README with: setup steps, what you'd do differently with more time, and any trade-offs you made
### What we provide
- Nothing — create a free Supabase project yourself and include the schema (SQL or migration file) in the repo. Do NOT commit your service role key.
### Explicitly NOT required
- Fancy UI/animations (clean and functional is enough)
- Tests (a bonus, not required)
- App icons, splash screens, store config
---
 
## Part 2 — Written Questions (answer in README, 2–4 sentences each)
 
1. Where did you put the Supabase anon key, and why is it acceptable (or not) to ship it in the app bundle? What must protect the data instead?
2. Your FlatList of 2,000 items is janky. Name three concrete things you'd check or change.
3. A user reports "my items disappeared." Walk through how you'd debug this in production (what logs/tools, in what order).
4. When would you choose an Edge Function over doing the work client-side?
---
 
## Evaluation Rubric (internal — don't send to candidates)
 
Score each 0–3: 0 = missing/broken, 1 = attempted but flawed, 2 = solid, 3 = excellent.
 
| Area | What to look for | Weight |
|---|---|---|
| App runs from README alone | `npx expo start` works following their steps, no missing env explanation | x2 |
| Auth correctness | Session persists, errors handled, no crash on bad input | x2 |
| RLS actually works | Check their SQL: policies scoped to `auth.uid()`. Try reading another user's row from the dashboard | x3 |
| CRUD + state management | No stale UI after mutations, loading/error states exist | x2 |
| Chosen "real-world" feature | Actually works, not just scaffolded | x2 |
| Code structure & TypeScript | Typed properly (not `any` everywhere), logical separation | x2 |
| README & trade-offs | Honest about shortcuts; shows judgement | x1 |
| Written answers | Q1 is the key filter — anyone who says "the anon key is secret" or doesn't mention RLS fails it | x2 |
 
**Rough bar:** 
- Hire-track: ≥ 70% of max score AND RLS scored 2+
- Instant concerns: committed secrets, RLS missing/wrong, app doesn't run
### Red flags
- Service role key in the repo or in the app code
- No RLS, or RLS policies that allow `true` for everything
- README copied boilerplate with no project-specific setup
- Everything in one 800-line `App.tsx`
- Perfect code but can't explain it live (see Part 3)
---
 
## Part 3 — 30-Minute Live Follow-Up (screen share)
 
This is your AI-slop filter. Anyone can submit polished code in 2026; the question is whether they understand it.
 
1. **"Open your project and add X live"** — small change, e.g., "add a filter to show only pending items." Watch how they navigate their own code. (10 min)
2. **"Why did you do it this way?"** — pick one non-obvious decision from their code and ask them to defend it. (5 min)
3. **Break something** — ask them to intentionally break RLS and show what happens in the app, then fix it. (10 min)
4. **Their questions** — good candidates ask about the codebase, deploy process, or how you review PRs. (5 min)
Using Claude/Copilot during the take-home is fine (say so upfront — it's realistic). The live session is where you separate "used AI as a tool" from "AI did it, they can't drive."
 
---
 
## Optional: Senior-Level Add-On
 
If hiring for a senior/lead role, add ONE of these to the take-home:
 
- **EAS + OTA:** set up EAS Update with a `preview` channel and document the release flow
- **Native module touch:** integrate one config-plugin-requiring library (e.g., notifications) and explain the prebuild implications
- **Migration scenario (written):** "The items table needs a new required column with 50k existing rows in production. Write the migration plan — zero downtime."
