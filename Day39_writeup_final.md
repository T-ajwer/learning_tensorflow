# Day 39 — Writeup: Days 36–38 in One Narrative

## Why this day looks different

No new code today. Days 36–38 gave you three separate experiments — capacity, the overfitting demonstration, and the fix. Day 39 is the muscle of turning three separate notebooks into one argument, which is the exact muscle a paper's Discussion section, or a strong technical blog post, actually demands. Nobody reads three notebooks. People read the story that connects them.

This file is a scaffold, not a draft — the sentences are yours to write. What's below is your raw material pulled back together so you're not re-digging through three days of notebooks to find your own numbers.

---

## Your raw material

**Day 36 — capacity:**
- ThreeLayerModel: 177 params (hand-counted, correct)
- OverkillModel: 12,737 params (hand-counted, correct)
- Core distinction you landed on: *overparameterized* is a property of the model (it has far more capacity than the problem needs); *overfitting* is a behavior (it actually happens, or doesn't, depending on what you do next)

**Day 37 — the demonstration:**
- OverkillModel, trained with no regularization: Train 0.4565 / Test 0.9498 / **Gap 0.4933**
- A silent bug: `y_pred_test` was missing from the eval loop

**Day 38 — the fix, three ways:**
- Dropout only (p=0.5): Train 0.6512 / Test 0.7446 / Gap 0.0935
- Weight decay only (1e-3): Train 0.3667 / Test 0.9946 / Gap 0.6278
- All three combined (+ early stopping): Train 0.6944 / Test 0.6980 / **Gap 0.0036**
- Two more silent bugs caught in review: a missing `zero_grad()`/`backward()` pair (a model that looked like it was "early stopping" but was actually never training at all), and a missing `model.eval()` (test loss quietly measuring a dropout-corrupted network instead of the real one)

---

## Structure to write toward

**1. The Question (Day 36)**
What did comparing a 177-param model to a 12,737-param model actually teach you about capacity — not the definition, the *feeling* of watching it? Why does it matter that "overparameterized" and "overfitting" are two different kinds of claims (one about the model, one about what happens)?

**2. The Demonstration (Day 37)**
What happened when you let the overkill model just train, with nothing holding it back? Put the 0.4933 gap into a sentence a non-ML friend could understand. And: what does a silent bug like the missing `y_pred_test` teach you that a loud one (a crash, a traceback) never could?

**3. The Fix, Three Ways (Day 38)**
What did each regularizer do to that gap *alone* — and what changed when you stacked them? What's the one sentence that explains why 0.0036 needed all three, not just the strongest one? (Dropout did the heaviest lifting alone here — why do you think that was, on this particular problem?)

**4. The Throughline**
The single idea that ties Days 36, 37, and 38 into one argument, not three. Don't let me hand you this line — write your own and see if it survives being said out loud. If it helps to test it: does your sentence explain *why* 12,737 params didn't have to mean overfitting?

---

## Self-check before you call it done

A writeup earns the name if a stranger who never saw your notebooks could read it and understand:
- What capacity has to do with risk (not with certainty)
- Why the Day 37 gap was the *predictable* consequence of Day 36's setup, not a surprise
- Why no single regularizer in Day 38 was enough alone, and what that implies about how you'd approach a new overfitting problem in the future

---

## Journal

**Summary table (fill in the "what surprised me" column yourself):**

| Stage | Train | Test | Gap | What surprised me |
|---|---|---|---|---|
| OverkillModel, no reg (Day 37) | 0.4565 | 0.9498 | 0.4933 | |
| + Dropout only | 0.6512 | 0.7446 | 0.0935 | |
| + Weight decay only | 0.3667 | 0.9946 | 0.6278 | |
| + All three (Day 38 final) | 0.6944 | 0.6980 | 0.0036 | |

**In your own words** (physically, not conceptually — what it *does*, not what it *achieves*):
- What does an overparameterized model physically do differently at inference time once it's overfit, versus once it's regularized well?
- If you had to explain to someone why train loss going *up* was actually good news in this arc, what would you say?

**LinkedIn hook:**
Day 37 found a real gap. Day 38 closed it three ways. That's a "before → broke it down → fixed it → here's the number" post, which is exactly your Day 27 formula's shape. What's your two-line hook? (This is the open item from the Day 38 review — want help pressure-testing it once you've drafted one, or want to draft it solo first?)
