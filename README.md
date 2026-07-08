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

#Using Claude/Copilot during the take-home is fine
## Part 3 — 30-Minute Live Follow-Up (screen share)
When you submit the test we will have a live follow-up about what you did.
