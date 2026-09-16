# Days 36–39: Capacity, Overfitting, and Regularization

Part of a self-directed 681-day PyTorch/ML roadmap.

## What's in here

| Day | File | Focus |
|---|---|---|
| 36 | `day36_.ipynb` | Hand-counting parameters across model sizes (177 vs 12,737); the distinction between "overparameterized" (a property of the model) and "overfitting" (a behavior that may or may not happen) |
| 37 | `DAy37_test_train_split.ipynb` | Letting the 12,737-parameter model train with no regularization on a task that needed 177 — train/test gap of 0.4933 |
| 38 | `Day38_regularization.ipynb` | Dropout, weight decay, and early stopping — applied individually, then combined — final gap: 0.0036 |
| 39 | `Day39_writeup_final.md` | Tying the three days into one narrative |

## Headline result

| Condition | Train | Test | Gap |
|---|---|---|---|
| No regularization | 0.4565 | 0.9498 | 0.4933 |
| Dropout only (p=0.5) | 0.6512 | 0.7446 | 0.0935 |
| Weight decay only (1e-3) | 0.3667 | 0.9946 | 0.6278 (worse than no regularization) |
| All three combined | 0.6944 | 0.6980 | 0.0036 |

## The finding

A model with 72× the parameters the task needed didn't overfit because it was a bad model — it overfit because nothing constrained it. Stacking three regularization mechanisms that work through different means (noise injection, weight-magnitude penalty, stopping before memorization) closed the gap by two orders of magnitude. No single technique alone got close, and weight decay alone made the gap *worse*, not just weaker than the others.

## Known limitation

The four conditions above were trained from different random initializations, not one controlled comparison — see `Day39_controlled_comparison.py` for the version that pins every condition to identical starting weights so only the regularization technique varies.
