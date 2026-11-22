# FabBench results, slice 9 only

4 cases (2 positive, 2 negative).
Recall: positives flagged with any positive label. False flags: negatives given a positive label.
`rules` was written with every case visible, so its numbers are in-sample, not a held-out score.
Model judges: every run of a judge scores the same cases on identical input (command, date, CLI version and input hash in their JSON); the `cases` column says how many. A judge with N runs is pooled: k/(N x cases), the per-run range in brackets, and its label per case is the majority over runs (`split` when no label has more than half).

Held out: cases added after the judge's rules or prompt were frozen (added_in >= `held_out_from` in its JSON); the `cases` column says how many of the cases it scored were held out. A prompt with no held-out cases yet shows `-`: its whole score is in-sample.

| judge | runs | cases | recall | false flags | exact label | held out: false flags | held out: exact | fb-102 | fb-104 |
|---|---|---|---|---|---|---|---|---|---|
| claude-haiku-5-5_prompt-v3 | 3 | 4 (4 held out) | 6/6 (2/2 per run) | 0/6 (0/2 per run) | 11/12 (3-4/4 per run) | 0/6 (0/2 per run) | 11/12 (3-4/4 per run) | - | - |
| claude-haiku-5-5_prompt-v5 | 3 | 4 (4 held out) | 6/6 (2/2 per run) | 0/6 (0/2 per run) | 10/12 (3-4/4 per run) | 0/6 (0/2 per run) | 10/12 (3-4/4 per run) | - | - |
| claude-sonnet-5-5_prompt-v3 | 3 | 4 (4 held out) | 6/6 (2/2 per run) | 0/6 (0/2 per run) | 10/12 (3-4/4 per run) | 0/6 (0/2 per run) | 10/12 (3-4/4 per run) | - | - |
| claude-sonnet-5-5_prompt-v5 | 3 | 4 (4 held out) | 6/6 (2/2 per run) | 0/6 (0/2 per run) | 12/12 (4/4 per run) | 0/6 (0/2 per run) | 12/12 (4/4 per run) | - | - |

## claude-haiku-5-5_prompt-v3: true label (rows) by predicted label (columns), summed over 3 runs

| true \ predicted | fabricated | unsupported | verified |
|---|---|---|---|
| unsupported | 1 | 5 |  |
| verified |  |  | 6 |

Wrong majority label: none.

Label moved between runs (1 of 4): fb-017 (unsupported / fabricated / unsupported).

## claude-haiku-5-5_prompt-v5: true label (rows) by predicted label (columns), summed over 3 runs

| true \ predicted | fabricated | unsupported | verified |
|---|---|---|---|
| unsupported | 2 | 4 |  |
| verified |  |  | 6 |

Wrong majority label: fb-017 (unsupported → fabricated).

Label moved between runs (1 of 4): fb-017 (fabricated / fabricated / unsupported).

## claude-sonnet-5-5_prompt-v3: true label (rows) by predicted label (columns), summed over 3 runs

| true \ predicted | fabricated | unsupported | verified |
|---|---|---|---|
| unsupported | 2 | 4 |  |
| verified |  |  | 6 |

Wrong majority label: none.

Label moved between runs (2 of 4): fb-017 (fabricated / unsupported / unsupported), fb-018 (unsupported / unsupported / fabricated).

## claude-sonnet-5-5_prompt-v5: true label (rows) by predicted label (columns), summed over 3 runs

| true \ predicted | unsupported | verified |
|---|---|---|
| unsupported | 6 |  |
| verified |  | 6 |

Wrong majority label: none.

Label moved between runs (0 of 4): none.
