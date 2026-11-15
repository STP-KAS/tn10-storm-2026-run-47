> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is a pre-run. Pre-run 47.** It is not the Wednesday run. It is not pre-run 1 to 46, and it does not edit their repos. A read does not start a runner.

# tn10-storm-2026-run-47

**Pre-run 47: the payment ladder at 1,013, then 2,027, then 3,040, then 4,053, with a 50 slice and a 1,000 slice, twelve covenant families on this run's fee split, one KCC-20 mint, and tic-tac-toe.** Opened as `tn10-storm-2026-11-11-prerun-47`. The series is numbered without the 11 November date. GitHub redirects the old name. The neuron stays [tn10-storm-2026-11-11](https://github.com/STP-KAS/tn10-storm-2026-11-11). This repo does not edit that repo.

> **Our own testing.** This is our own Kaspa Testnet-10 testing, run on our own machines and nodes. What these pages report is what we observed in this run; it is not a claim of how TN10 or Kaspa behave in general.

| Field | Value |
|---|---|
| Target | A table of what the payment ladder, the two fee slices, the covenant hops, the mint and the guest did, by phase, with the desk probe |
| The change | One package after pre-run 46. No heavy lane. The congestion is the payment ladder. Families 1–4 at 100, 5–8 at 200, 9–10 at 500, 11–12 at 200 except five minutes at 2,000 in the 3,040 step. The mint at 100, cap 20, gap 120 s. The guest keeps playing. The kit fee table is not edited |
| Met or not met | **filled** on the table. BASE 22:58–23:01Z: fee cells 100 / 100 / 100. The 23:00 cell is mempool size 7. HOLD-1 full minutes of pay-100 submit-OK are 60,307–61,367, against 60,780. HOLD-2 full minutes are 120,805–122,485, against 121,620. HOLD-3 minutes 23:25–23:32 are 180,640–183,137, against 182,400. At 23:33Z pay-100 submit-OK is 150,046, then 17,383, 11,094 and 9,906. A pool reload at 23:41:26Z, reason coins-crossed-0.5, payers 10. The 23:42 and 23:43 minutes are 242,501 and 242,413, against 243,180. Six senders then stop, reason=rate, from 23:44:21Z to 23:45:03Z. Senders 1.0, 2.2 and 3.1 have a 23:45 minute line and no PAY_STOP line. The 50 slice has 0 submit-OK and stops at 23:01:15Z, reason=rate. The 1,000 slice sits on 590–600 a minute through 23:30Z and stops at 23:31:30Z, reason=pool. Families 1–13 included at genesis. Family submit rows stop after 23:04Z. Twelve STALL lines at 23:05:25Z. The five minutes at 2,000 have no family submit rows. Mint 20 of 20, fees 0.82 tKAS, raw 0.82359398, stopped on the cap. Guest 114 matches, 902 submit-OK, 902 accepted. 111 matches are 8 of 8. Matches 38, 42 and 74 are 3, 4 and 7. The guest stops at 00:11:18Z. RETURN was not written. The controller log's last line is the reload at 23:41:26Z. Nothing wrote a run end |
| Retry count | 0. The next attempt is a new repo. This one is not resumed |
| Core tags | — |
| Status | done. Closed from the probe, the payment minute logs, the guest log, the mint log and the family submit log. The desk was told to stop on 15 Nov. The probe was stopped then. It was not restarted |

Plan, lock, and the prediction are in [plan/PLAN.md](plan/PLAN.md), [locks/LOCKED.md](locks/LOCKED.md), and [plan/PREDICTIONS.md](plan/PREDICTIONS.md). Written before any submit. Those pages are not edited.

Three stretches, kept apart. The locked window is the controller clock from 22:58Z on 14 Nov through the guest stop at 00:11:18Z on 15 Nov. The continuation is the guest loops that start at 08:05Z, and the probe gap from 08:57:16Z to 08:58:35Z. Samples after about 10:30Z are a later run. They are not this offer. The controller did not write STOP, and it did not write a run end. This close does not invent one.

The minute table is [counts/chain/TEMPLATE.md](counts/chain/TEMPLATE.md). The phase map is [counts/FINDINGS-MAP.md](counts/FINDINGS-MAP.md). The lessons are [logs/LESSONS.md](logs/LESSONS.md).
