> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · Kaspa Testnet-10 only. tKAS has no value. Counts only. What we observed in this run.

# Findings map, pre-run 47

One desk node. The clock is the controller: BASE 22:58:00Z–23:01:00Z, HOLD-1 23:01:00Z–23:13:00Z, HOLD-2 23:13:00Z–23:25:00Z, HOLD-3 23:25:00Z–23:37:00Z, HOLD-4 from 23:37:00Z. RETURN was not written. The controller log ends at 23:41:26Z on a pool reload. A run end was not written. The desk node was not restarted. The minute cells are [chain/TEMPLATE.md](chain/TEMPLATE.md).

The locked window is that clock through the guest stop at 00:11:18Z on 15 Nov. Guest loops that start at 08:05Z are a later stretch. Probe samples after about 10:30Z are a later run. Neither is this offer.

| Phase | What the logs say |
|---|---|
| BASE | Probe only. Fee cells 100 / 100 / 100. The 23:00 cell is size 7 and ready count 7. 22:57 is two samples, size 0 on both, ready count 0 and ready count 7 |
| HOLD-1 | Pay-100 submit-OK 713,595 over 12 minutes, the full minutes 60,307–61,367. The 1,000 slice is on 590–600 in the full minutes. The 50 slice is 0 submit-OK and stops at 23:01:15Z, reason=rate. Family submit-OK 1,767, rejects 752, and the rows stop after 23:04Z. Mint accepts 6. Guest matches 1–19 are 8 of 8 |
| HOLD-2 | Pay-100 submit-OK 1,459,395, every minute 120,805–122,485. The 1,000 slice stays on 590–600. Family submit rows 0. Accept stamps in this phase: 6. Mint accepts 6. Guest 20 matches, 155 carriers accepted. Match 38 is 3 of 8 |
| HOLD-3 | Pay-100 submit-OK 1,643,819. The first eight minutes are 180,640–183,137. From 23:33Z the minutes are 150,046, 17,383, 11,094 and 9,906. The 1,000 slice stops at 23:31:30Z, reason=pool. The 2,000 window on families 11–12 has no submit rows. Mint accepts 6. Guest 19 matches, 148 carriers. Match 42 is 4 of 8 |
| HOLD-4 | The clock step stays open. Pay-100 submit-OK 851,284 over the nine minutes that have lines. After the reload, 23:42Z and 23:43Z are 242,501 and 242,413. Six senders stop reason=rate. Three senders have no stop line. Mint accepts 2 and reaches its cap. Guest matches through 114. The stop line is 00:11:18Z |

## Genesis

Included: families 1 through 13. Thirteen. Dropped: none. The controller line reads included=13 dropped=0 at 23:01:10Z. The fee split line reads floor 1–4 at 100, 5–8 at 200, 9–10 at 500, 11–12 at 200, family 13 at 100, one builder, desk. The kit fee table was not edited.

## Payments

Nine senders at 100 sompi per gram, one at 50 with a fixed 30 a second, one at 1,000 with a fixed 10 a second. Pay-100 is the sum of the nine. The offers are 60,780, 121,620, 182,400 and 243,180 a minute. Submit-OK is not inclusion. The minute logs do not carry an inclusion count.

| Minute (UTC) | Step | Pay-100 submit-OK | Senders | Pay-50 | Pay-1000 |
|---|---|---:|---:|---:|---:|
| 23:01 | HOLD-1 | 44,986 | 9 | 0 | 440 |
| 23:02–23:12 | HOLD-1 | 60,307–61,367 | 9 | — | 590 or 600 |
| 23:13–23:24 | HOLD-2 | 120,805–122,485 | 9 | — | 590 or 600 |
| 23:25–23:32 | HOLD-3 | 180,640–183,137 | 9 | — | 590 or 600, then 52 at 23:31, then off |
| 23:33 | HOLD-3 | 150,046 | 9 | — | — |
| 23:34 | HOLD-3 | 17,383 | 9 | — | — |
| 23:35 | HOLD-3 | 11,094 | 9 | — | — |
| 23:36 | HOLD-3 | 9,906 | 9 | — | — |
| 23:37–23:40 | HOLD-4 | 8,918, 7,258, 9,345, 11,971 | 9 | — | — |
| 23:41 | HOLD-4 | 118,418 | 9 | — | 149 |
| 23:42 | HOLD-4 | 242,501 | 9 | — | 292 |
| 23:43 | HOLD-4 | 242,413 | 9 | — | 299 |
| 23:44 | HOLD-4 | 204,006 | 9 | — | 292 |
| 23:45 | HOLD-4 | 6,454 | 5 | — | 297 |

The 50 slice: 30 attempts, 0 submit-OK, rate field 1, other field 29, fee field 0. PAY_STOP and PAY_EXIT at 23:01:15Z–23:01:16Z, reason=rate.

The 1,000 slice: 19,061 submit-OK, 20,555 attempts, other field 1,494, rate field 0, fee fields 322.13 tKAS. PAY_STOP reason=pool at 23:31:30Z. The reload at 23:41:26Z starts it again. It does not return to 600.

Pay-100 across the run: 4,668,093 submit-OK. The rate field sums to 6, one on each sender that wrote PAY_STOP reason=rate. The full field is 0. The other field sums to 15,618. Fee fields sum to 8,675.68 tKAS. Through 23:42Z every pay-100 minute line's fee field divided by its submit-OK is 0.001690 tKAS. The lines that leave that figure are in 23:43Z, 23:44Z and 23:45Z.

PAY_STOP reason=rate: sender 2.0 at 23:44:21Z, 1.2 at 23:44:37Z, 3.0 at 23:44:48Z, 3.2 at 23:44:57Z, 2.1 at 23:45:02Z, 1.1 at 23:45:03Z. Senders 1.0, 2.2 and 3.1 have a 23:45 minute line, no PAY_STOP line, and no stop file. Their 23:45 fee-per-OK reads 0.033772, 0.135306 and 0.190300.

The reload line is `REPAIR pool-reload reason=coins-crossed-0.5 payers=10` at 23:41:26Z. The PAY_START lines at that stamp are the nine pay-100 senders and the 1,000 slice. The 50 slice is not among them.

## Covenant hops

Submit rows 6,671. Submit-OK rows 2,007, all distinct. Reject rows 4,664. The reason field reads already_spent on 463, orphan on 479, and other on 3,722. Accept rows 2,025, all distinct, all with an accept time. 2,005 ids are in both the submit-OK set and the accept set. 20 accept ids have no submit row. 2 submit-OK ids have no accept row. Distinct ids on all submit rows, OK and reject, are 2,949. We do not explain the 20 or the 2.

| Phase | Submit-OK | Rejects | already_spent | orphan | Accept stamps |
|---|---:|---:|---:|---:|---:|
| HOLD-1 | 1,767 | 752 | 350 | 402 | 1,771 |
| HOLD-2 | 0 | 0 | 0 | 0 | 6 |
| HOLD-3 | 88 | 104 | 50 | 19 | 94 |
| HOLD-4 | 152 | 3,808 | 63 | 58 | 154 |

HOLD-1 is the stretch with a share to read, and it is short. Family rows for families 11 and 12 are in 23:01Z, 23:02Z, 23:03Z and 23:04Z, then they stop. The next family rows are 23:34Z.

| Family | Fee label | HOLD-1 submit-OK | HOLD-1 rejects | HOLD-1 share |
|---|---:|---:|---:|---:|
| 1 | 100 | 125 | 90 | 0.58 |
| 2 | 100 | 137 | 76 | 0.64 |
| 3 | 100 | 130 | 83 | 0.61 |
| 4 | 100 | 127 | 84 | 0.60 |
| 5 | 200 | 162 | 49 | 0.77 |
| 6 | 200 | 160 | 50 | 0.76 |
| 7 | 200 | 153 | 56 | 0.73 |
| 8 | 200 | 153 | 55 | 0.74 |
| 9 | 500 | 158 | 50 | 0.76 |
| 10 | 500 | 159 | 48 | 0.77 |
| 11 | 200 | 152 | 55 | 0.73 |
| 12 | 200 | 151 | 56 | 0.73 |

Grouped on that stretch: families 1–4, 519 of 852. Families 5–8, 628 of 838. Families 9–10, 317 of 415. Families 11–12, 303 of 414.

ESC rate=2000 at 23:29:00Z and ESC back=200 at 23:34:00Z. Families 11–12 have no submit row and no reject row in 23:28Z through 23:33Z. The five minutes at 2,000 were not submitted. The family log shows POOL_LOW at 23:03:12Z and NODE_MEMPOOL_HIGH at 23:26:38Z, mempool 93,220. The family sender's restart log starts at 23:34:55Z with a FEE_SPLIT line, and at 23:34:57Z the next line is NODE_MEMPOOL_HIGH, mempool 245,000. Later family lines: POOL_LOW at 23:41:56Z, NODE_MEMPOOL_HIGH at 23:43:33Z mempool 91,447, NODE_MEMPOOL_BACK at 23:46:17Z mempool 89,183. STALL lines: 36, three for each family 1–12.

## KCC-20 mint

Family 13. Cap 20. Gap 120,000 ms. Rate 100. Coins on the line at the start: 53. Started 23:01:12Z.

| n | Accept (UTC) | Accept, ms | Phase |
|---|---|---:|---|
| 1 | 23:01:16Z | 3,452 | HOLD-1 |
| 2 | 23:03:17Z | 1,008 | HOLD-1 |
| 3 | 23:05:18Z | 1,022 | HOLD-1 |
| 4 | 23:07:19Z | 1,011 | HOLD-1 |
| 5 | 23:09:20Z | 1,021 | HOLD-1 |
| 6 | 23:11:20Z | 511 | HOLD-1 |
| 7 | 23:13:21Z | 1,016 | HOLD-2 |
| 8 | 23:15:25Z | 3,555 | HOLD-2 |
| 9 | 23:17:29Z | 3,567 | HOLD-2 |
| 10 | 23:19:30Z | 1,541 | HOLD-2 |
| 11 | 23:21:33Z | 2,540 | HOLD-2 |
| 12 | 23:23:35Z | 2,043 | HOLD-2 |
| 13 | 23:25:38Z | 3,067 | HOLD-3 |
| 14 | 23:27:40Z | 2,044 | HOLD-3 |
| 15 | 23:29:42Z | 2,572 | HOLD-3 |
| 16 | 23:31:44Z | 1,533 | HOLD-3 |
| 17 | 23:33:48Z | 3,578 | HOLD-3 |
| 18 | 23:35:49Z | 1,533 | HOLD-3 |
| 19 | 23:37:50Z | 508 | HOLD-4 |
| 20 | 23:39:53Z | 3,718 | HOLD-4 |

End line: accepted 20, tries 20, rejects 0, timeouts 0, fees 0.82359398 tKAS, why cap. We publish 0.82 tKAS. Node rate on the accept lines is 100.01 to 100.30.

## Tic-tac-toe

Aimed 114. Played 114. Submit-OK 902. Accepted on the desk 902. The stop line at 00:11:18Z says the same. 111 matches are 8 of 8. Three are short.

| Match | Confirm (UTC) | Carriers | Quote |
|---|---|---:|---:|
| 38 | 23:24:23Z | 3 | 181.20 |
| 42 | 23:26:39Z | 4 | 252.64 |
| 74 | 23:46:50Z | 7 | 211.20 |

Quotes by phase, on the confirm rows: HOLD-1, 19 matches, 100 to 206.63, 10 of them at 100. HOLD-2, 20 matches, 157.78 to 240.14, none at 100. HOLD-3, 19 matches, 181.94 to 254.71, none at 100. HOLD-4, 56 matches, 100 to 262.85, 43 of them at 100.

The 114 refill lines in this window send 111 coins. Their fee fields sum to 3.33 tKAS. The first line reads issuer 4 coins, 80 tKAS, operator 608.21 tKAS. The last line, 00:10:49Z, reads issuer 2 coins, 40 tKAS, operator 376.78 tKAS.

Guest loops that start at 08:05:11Z are not this count. Their stop lines read 48, 296, 240, 48, 56, 0 and 8 submit-OK, and the same accepted counts. The totals file left on disk is the last of those loops. The locked count is the 00:11:18Z line and the 114 confirm rows before 08:00Z.

## After the guest stop

From 00:16:05Z through 08:04:41Z: 1,400 probe samples, priority fee 100 on every sample, mempool size 0 to 59, ready mass 0 to 1.22 blocks, 251 samples with size above 0.

The probe file has one gap above a minute in the later stretch: 08:57:16Z to 08:58:35Z. The probe was started again. The controller was not. No stop file was written.

From 10:30Z the same probe file leaves that quiet range. Size reaches 107,031. Priority fee reaches 230.83. That is a later run. It is not scored here. The last sample in the file when this page was written is 18:47:47Z. The probe was stopped when the desk was told to stop.
