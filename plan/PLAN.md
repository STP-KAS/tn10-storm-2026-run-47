> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · Kaspa Testnet-10 only. Written before any submit.

# Plan

Pre-run 46 filled its table. Twelve families hopped at 2,000 sompi per gram (quiet submit-OK 5,956, congest submit-OK 3,330). The mint accepted 15 of 24, fees 0.6169 tKAS, and stopped because the phase ended. The heavy lane submitted 1,376, fees 3,385.81 tKAS, and stopped on an empty pile, with pending 0. Six samples while our class was present showed template heavy count 1, storage mass 266,752 to 484,443. Tic-tac-toe played 33 matches, each 8 of 8, and then the refill stopped. The run ended at 21:24Z. That congestion was the lane. This run does not repeat the lane.

The question is how those same lines behave under the standard payment ladder. Simple payments at one third, two thirds, and three thirds of the low edge of finding 1, then four thirds for as long as the pile pays. While that is happening, low fees and higher fees run together, and we write down which ones land. Finding 1 stays about 304 to 308 simple payments per block, about 3,040 to 3,080 a second. The offers are 1,013, then 2,027, then 3,040, then 4,053. We may be dividing it wrong. This run does not try to correct it.

## What we measured before this page

One simple payment, one input and one output, on the desk node, after pre-run 46. The unsigned draft was 1,624 grams at every size we tried, from 1 tKAS through 20 tKAS, and on the pile's real coins. The same payment after signing was 1,690 grams. This run's payment fee uses the signed mass. At 100 sompi per gram the fee is 169,000 sompi, which is 0.001690 tKAS. At 150 sompi per gram it is 0.002535 tKAS. At 50 it is 0.000845 tKAS. At 1,000 it is 0.016900 tKAS. The node's own estimate at that read was 100 / 100 / 100.

A covenant hop in pre-run 46's submit log had node mass 42,462 to 43,695. This plan budgets a hop at 44,000 grams. A hop at 100 sompi per gram is then 0.044 tKAS, at 200 it is 0.088, at 500 it is 0.220, and at 2,000 it is 0.880. The real mass moves a little with the coin. The log will show the mass this run actually built.

The same read, sums only:

- The funding key held 8,899.75 tKAS. Usable value, in the old sense, was 7,581.52. That is under the 18,000 line from the earlier payment runs. This run does not use that line as an arm check.
- The guest reserve held 2,422.04 tKAS, largest coin 6.04. It has no 100 tKAS coin left.
- The second reserve usable value was 819.49, against the floor of 800 this series has kept. It is not spent.
- The mint purse held 782.93 tKAS and 22 coins at or above 15 tKAS. It is not topped up.
- The payment pile held 3,140.58 tKAS across 1,308 coins. The largest coin was 13.29. No coin was above 10 tKAS, so the old payment filter would have seen an empty pile.
- The guest issuer held 1 coin and 40 tKAS. The operator held 4 coins and 608.21 tKAS.
- Twelve family keys have no coin at or above 15 tKAS.
- Fifteen further keys, outside the family set, held 591.63 tKAS together. The largest coin was about 9.97.
- Free space on the desk was 325 GB. The desk node is not restarted.

Twenty minutes at 1,013, at 2,027, and at 3,040, with every payment at 150 sompi per gram, is about 18,495 tKAS of fees. The payment bag below is about 12,352 tKAS. The same three steps at 100 sompi per gram, with no hops, no second fee, and no tail, are 12,330 tKAS. The margin against that bag is about 22 tKAS, which setup fees would eat.

The locked steps are 12 minutes. That is the shape that still pays the fee spread and leaves a four-thirds tail. The tail runs until the pile cannot fund one more minute. A longer equal step does not leave that tail.

## Setup, after this page is on origin, before the window

The guest reserve stays the guest reserve. It is joined into coins of 20 tKAS. The guest kit's gate is 2 to 4 issuer coins and a total of at least 40 tKAS, and 1 to 4 operator coins with a total of at least 20. Coins of 100 tKAS would buy about two dozen matches from this reserve. Coins of 20 tKAS let the line keep playing through the ladder. The issuer is brought to 4 coins. The operator is left as it is. Never a fifth issuer coin and never a fifth operator coin.

The refill script in this run adds another input when the change would go negative, until the inputs cover the fee or the reserve is empty. Pre-run 46 refused with "fee" once a flat 0.2 tKAS reserve could not cover mass times a high rate. The refill rate here is 1,000 sompi per gram. The match cap is the number of 20 tKAS coins the reserve actually holds at arm. That number is logged then. It is not chosen on this page.

Twelve family keys each receive one coin of 20 tKAS from the funding key. That is 240 tKAS. A setup fee reserve of 40 tKAS stays on the funding key and is not part of the pile. The log records the setup fees that were actually paid. They are a list. They are not folded into a total with the window.

What remains of the funding key, the whole payment pile, and the fifteen further keys, are joined onto the payment pile. The aimed bag is 8,899.75 minus 240 minus 40, plus 3,140.58, plus 591.63, which is 12,351.96 tKAS. The join makes coins of 2 tKAS, so a chained payment has a coin to spend and a few thousand coins remain if chaining stops. The old filter of "above 10 tKAS" is not this run's filter. A coin must clear its own fee plus 0.01 tKAS.

The second reserve is not touched. The mint purse is not touched. The heavy pile is this same payment pile. There is no heavy lane.

The window is not armed if, after setup, any hopping family still has no coin at or above 15 tKAS, or the issuer is outside 2 to 4 coins, or the pile holds under 4,000 coins or under 10,000 tKAS, or the second reserve usable value has fallen under 800, or free space is under 160 GB. A payment sender does not stop because the funding key is under 18,000.

## Window

One controller. The desk node is not restarted. No heavy lane.

| Phase | Clock | What is on |
|---|---|---|
| BASE | 3 min | Probe only |
| HOLD-1 | 12 min | Simple payments at 1,013 a second, all of them at 100 sompi per gram. Beside that, 30 a second at 50, and 10 a second at 1,000. Twelve covenant families. Tic-tac-toe, one match at a time. The mint, one at a time, rate 100, accept cap 20, 120 seconds after the previous accept |
| HOLD-2 | 12 min | The same lines. The standard offer moves to 2,027 a second |
| HOLD-3 | 12 min | The same lines. The standard offer moves to 3,040 a second. For five minutes in the middle, or until those two families have paid 200 tKAS extra, whichever the log hits first, families 11 and 12 move from 200 to 2,000. Then they return to 200 |
| HOLD-4 | until the pile, the disk, or the clock | The standard offer moves to 4,053 a second. Everything else stays. This phase ends when the pile's remaining value is under one minute of the budgeted fee at this offer, or free space is under 150 GB, or the clock reaches 22:00 UTC on 15 Nov 2026 (23:00 Brussels) |
| RETURN | 3 min | All off |

The clock lengths are the lock. The absolute start is chosen at arm, and the log records it.

Launch paths are new: `launch::storm-2026-10-30-p47-f1` through `f12`, and `launch::storm-2026-10-30-p47-kcc1`. Pre-run 46's paths are not reused. The fee table below lives in this run. The kit fee table is not edited.

Preflight checks the candidate list the earlier payment ladder used. Kept nodes are unique kaspads that answer synced on testnet-10. The standard offer is split across them, three senders on each. The 50 slice and the 1,000 slice are one sender each, on the first kept node. Families, the mint, and tic-tac-toe stay on the desk node. If no candidate passes, every payment sender uses the desk node and the log says so. Hosts are not written in this repo.

A payment spends a coin back to the same pile, amount equal to the coin minus the fee, and the change is the next coin in that chain. A reject of "fee" or "mass" stops that fee class only. The other classes keep their offer. "Mempool full" returns the coin to the pool and is counted. The old stop, funding-key usable under 18,000, is not in this sender.

Families attempt 0.4 a second each. That rate is what the bag can pay across these steps. Pre-run 46's 1.2 would spend the tail.

| Families | Node rate, sompi per gram | When |
|---|---|---|
| 1 to 4 | 100 | The whole window |
| 5 to 8 | 200 | The whole window |
| 9 and 10 | 500 | The whole window |
| 11 and 12 | 200, then 2,000, then 200 | The 2,000 stretch is the five minutes in HOLD-3, capped at 200 tKAS extra |
| 13, the mint | 100 | The whole window, cap 20 accepts |

The guest prices each carrier at the node's priority estimate. No recompile. Each match logs the quote the gate saw. The guest stops on its own stop file at RETURN, or when the reserve cannot fund another coin, or when a match fails the gate twice. The rest of the window still counts.

Disk abort under 150 GB free. A read under 160 GB does not start the window. New submits also stop at 22:00 UTC on 15 Nov 2026 if the pile has not already stopped them.

## What is logged

The probe samples the desk, and each kept public node, through the window. Each sample has the mempool size, the low / normal / priority estimate, the ready count, the ready mass, and the template count and mass. Payment logs are per class and per minute: submit-OK, attempts, rejects by reason, fees, and the pile's coin count and value. Hop logs have the family's rate, the node mass, the fee, and submit-OK or the reject text. The mint log has the wait before each accept. The guest log has the quote and the carriers. A findings map in this repo, written at the close from those logs, says what landed in each phase.

The count is the desk node's. Submit-OK is not inclusion. Same-minute inclusion is counted from the desk for the payments whose ids were logged. We will not publish a cost total we have not summed.

While the offer is above what a block can hold, lower fees on our node have a smaller chance of being chosen. That is the competition this window is for. We do not guess, on this page, which class gets poor.
