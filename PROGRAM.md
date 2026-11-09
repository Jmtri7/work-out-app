# Reg Park 5×5 Program

Source: <https://theworkoutmag.com/training/reg-park-5x5-workout-program-guide>
(Notes below were extracted from that article and reorganized. Check the original for the authoritative text.)

## Overview

- **Length:** three phases of about 3 months each (roughly 9 months total).
- **Progression between phases:** start at Phase 1 and move up only after you stall and then break through plateaus on the current phase. Phase 2 is typically added around months 3–4, once squat, bench and deadlift stall.
- **Frequency:** 3 full-body sessions per week with at least one rest day between sessions.
- **Schedule:** Monday, Wednesday, Friday, plus an optional Tuesday Zone 2 cardio session (20–30 min).
  - Monday prioritizes squat.
  - Wednesday prioritizes bench.
  - Friday prioritizes deadlift.
- **Session length:** 35–45 min in Phase 1, 50–60 min in Phase 2, 60–75 min in Phase 3.

## Phase 1: Foundation (about 3 months)

| Exercise   | Sets × Reps | Rest  | Tempo   |
|------------|-------------|-------|---------|
| Back Squat | 5 × 5       | 3 min | 2-1-1-0 |
| Bench Press| 5 × 5       | 3 min | 2-1-1-0 |
| Deadlift   | 5 × 5       | 3 min | 1-1-1-0 |

- **Tempo** is lowering / bottom pause / lifting / top pause, in seconds. Lowering takes 2 s, pause 1 s, lift 1 s, top pause 0 s. The deadlift uses a faster initial pull.
- **Warm-up:** two sets of 5 reps at 50% and 70% of working weight. These do not count toward the 5×5.

## Phase 2: Upper-Body Volume (about 3 months)

Add this phase once squat, bench and deadlift stall (typically around months 3–4).

| Exercise                | Sets × Reps | Rest    |
|-------------------------|-------------|---------|
| Back Squat              | 5 × 5       | 3 min   |
| Bench Press             | 5 × 5       | 3 min   |
| Deadlift                | 5 × 5       | 3 min   |
| Standing Overhead Press | 5 × 5       | 2–3 min |
| Barbell Row             | 5 × 5       | 2–3 min |
| Barbell Curl            | 3 × 5       | 2 min   |

## Phase 3: Full-Body Development (about 3 months)

| Exercise                | Sets × Reps | Rest    |
|-------------------------|-------------|---------|
| Back Squat              | 5 × 5       | 3 min   |
| Bench Press             | 5 × 5       | 3 min   |
| Deadlift                | 5 × 5       | 3 min   |
| Standing Overhead Press | 5 × 5       | 2–3 min |
| Barbell Row             | 5 × 5       | 2–3 min |
| Weighted Dips           | 3 × 5       | 2 min   |
| High Pulls              | 3 × 5       | 2 min   |
| Standing Calf Raise     | 5 × 10      | 90 sec  |

## Progression Rules

1. **Starting weight:** choose a load you can complete for 5 reps on all 5 sets with 1–2 reps in reserve, roughly 70–75% of your 1RM.
2. **Increase:** when you complete all 25 reps with clean form, add 2.5 kg (5 lb) to upper-body lifts or 5 kg (10 lb) to lower-body lifts next session. The key rule is to add weight every session you finish all 25 reps.
3. **Missed rep:** repeat the same weight next session. Up to three attempts are allowed at that load. After that, reduce the weight by 10% and rebuild.
4. **Stall (3+ sessions):** take a one-week deload at 60% of working weight, then resume progression.
5. **Periodic deload (from the article's mistakes table):** every 4th week, reduce all loads by 40% for one session, or take a full deload week after 3 consecutive stalls.

## Safety and Technique

- Use a squat rack with safety bars, and a spotter for bench.
- Brace before each rep.
- If you are new to barbell training, spend 2–4 weeks learning form at 50–60% of estimated 1RM first.

## Missed Training and Substitutions

- **Training only twice in a week:** do two sessions and resume the next week. Do not compress three sessions into two days.
- **Substitutions:** front squats or sumo deadlifts are acceptable if mobility requires it. Machines should not replace the barbell lifts.

## Cardio

Light Zone 2 cardio on rest days (about 60–70% of max heart rate) is fine. Avoid HIIT on rest days.

## Nutrition Targets

- Calories: TDEE + 300–500 kcal
- Protein: 1.6–2.2 g/kg
- Carbohydrates: 4–6 g/kg
- Fat: 0.8–1.0 g/kg (not below 0.5 g/kg)
- Aim for a gain of about 0.1–0.2 kg (0.25–0.5 lb) per week.

## Who It Is For

- **Ideal:** beginners to intermediates (0–2 years of consistent training), people rebuilding after a layoff, and anyone wanting a simple strength base.
- **Not ideal:** advanced lifters (3+ years), people with joint issues aggravated by heavy bilateral loading, pure hypertrophy seekers who prefer 8–12 reps, and people who can only train 1–2 days per week.

## How the app implements this

The app in `index.html` follows the tables and rules above, with these choices of its own:

- The priority lift goes first each day. The three main lifts rotate: squat day is squat → bench → deadlift, bench day is bench → deadlift → squat, deadlift day is deadlift → squat → bench. The lift that led last time goes last this time. The article only says which lift to prioritize; this ordering is the app's own choice. Accessory lifts (Phases 2–3) follow in table order. The rotation follows your workout count, not the weekday.
- Your 3 training days are configurable under "Phase & units" (default Mon/Wed/Fri). The setting only changes the planned days on the calendar; logged workouts are never moved.
- Rest for the 2–3 min exercises (overhead press, row) is set to 2:30.
- Warm-ups (50% and 70% × 5) are shown for squat, bench and deadlift only, rounded to the nearest loadable weight and never below the bar.
- Weights increase after a clean set of all reps: +5 lb / +10 lb (2.5 kg / 5 kg) for upper / lower body. Squat, deadlift and calf raise use the larger step.
- After 3 failed attempts at one weight, the app drops it by 10%.
- Deload weeks, the periodic 40% deload and moving to the next phase are left to you. The app only reminds you.
- Starting weights are placeholders; adjust them in the first workout.
