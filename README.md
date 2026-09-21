# Godwin Mbah

**GodwinXbt.** Smart contract auditor at SMC Audits.
Researcher first. Builder second.

A protocol can look safe on the dashboard and still fail in its accounting.
I follow the settlement path. Contract code. Forked live state. Working proofs.

[Portfolio](https://godwinxbt.vercel.app) · [Findings](https://godwinxbt.vercel.app/findings) · [Finding index](./FINDINGS.md) · [X](https://x.com/GodwinXbt) · [Telegram](https://t.me/GodwinXbt) · godwinxbt@gmail.com

---

## Hire me for

- Protocol research on live EVM and Solana systems
- Smart contract review with PoCs against forked state
- Payments and settlement-path work where the hop is the bug

If the claim cannot be checked on-chain or in a fork, I am the wrong person.

## Record

| | |
| --- | ---: |
| Findings with PoC or traced root cause | **17** |
| Protocols | **11** |
| Critical + High | **9** |

Numbers are only as good as the writeups. Each row in [FINDINGS.md](./FINDINGS.md) links to the full argument.

## How a claim dies or survives

1. Start from a real problem. A vault that looks solvent. A payment that dies at settlement.
2. Read the mechanism. Storage, roles, the hop the dashboard hides.
3. Prove it on a fork. Valid calls. Live chain data.
4. Scope it honestly. If it is not exploitable today, I say so.

## Selected work

| Project | Problem | Link |
| --- | --- | --- |
| [Blast Radius](https://github.com/Godwin-web3/blast-radius) | Approvals stay live after the app is gone | [live](https://blast-radius-pearl.vercel.app) |
| [Assay](https://github.com/Godwin-web3/assay) | A ticker on Solana is not proof of what the token is | [live](https://assay-gold.vercel.app) |
| [Paidline](https://github.com/Godwin-web3/paidline) | An invoice that dies at the settlement hop is not paid | [live](https://paidline.vercel.app) |
| [Ragnarok](https://github.com/Godwin-web3/ragnarok) | A finding is not a finding until a fork proves it | repo |
| [Keel](https://github.com/Godwin-web3/keel) | A public guess is worthless if it can be copied | [live](https://keel-black-phi.vercel.app) |
| [NoGhosts](https://github.com/Godwin-web3/noghosts) | Agent hire with a logo and no evidence is noise | [live](https://noghosts.vercel.app) |

## Findings (critical and high first)

| Sev | Protocol | Finding | Writeup |
| --- | --- | --- | --- |
| Critical | lemon.fun | Legacy bonding curve. Total buyer-fund theft | [index](./FINDINGS.md#lemon-fun-bonding-curve-theft) · [full](https://godwinxbt.vercel.app/findings/lemon-fun-bonding-curve-theft) |
| Critical | Noon (USN) | RedeemHandler pays collateral with no USN ratio | [index](./FINDINGS.md#noon-redeemhandler-unratiod-drain) · [full](https://godwinxbt.vercel.app/findings/noon-redeemhandler-unratiod-drain) |
| Critical | Noon (USN) | MinterHandlerV2 uncollateralized self-mint | [index](./FINDINGS.md#noon-minterhandler-uncollateralized-mint) · [full](https://godwinxbt.vercel.app/findings/noon-minterhandler-uncollateralized-mint) |
| High | Flex Finance | Lender withdrawal auction self-deal | [index](./FINDINGS.md#flex-lender-auction-self-deal) · [full](https://godwinxbt.vercel.app/findings/flex-lender-auction-self-deal) |
| High | Flex Finance | Borrower path. Same auction self-deal | [index](./FINDINGS.md#flex-borrower-auction-self-deal) · [full](https://godwinxbt.vercel.app/findings/flex-borrower-auction-self-deal) |
| High | Hydrex | Minter one-time guard is a no-op | [index](./FINDINGS.md#hydrex-minter-initializer-noop) · [full](https://godwinxbt.vercel.app/findings/hydrex-minter-initializer-noop) |
| High | Ripe Protocol | No L2 sequencer uptime check on Base | [index](./FINDINGS.md#ripe-sequencer-uptime) · [full](https://godwinxbt.vercel.app/findings/ripe-sequencer-uptime) |
| High | Orvex | Stale voter reward-index capture | [index](./FINDINGS.md#orvex-voterv5-stale-reward-index) · [full](https://godwinxbt.vercel.app/findings/orvex-voterv5-stale-reward-index) |
| High | Orvex | Missing burn(). Early-exit claims revert | [index](./FINDINGS.md#orvex-protocoltoken-missing-burn-early-exit) · [full](https://godwinxbt.vercel.app/findings/orvex-protocoltoken-missing-burn-early-exit) |

The rest of the 17, including the ones that were not exploitable once run, live in [FINDINGS.md](./FINDINGS.md).

## Stack

Solidity and Foundry for proofs. TypeScript, Next.js, and viem for live surfaces. Solana when the mint and the authority are the question. Python for monitors.

## Currently

Full-time auditor at SMC Audits (Sir Mapy & Co). Remote. Sep 2026 to present.
Still packaging the work so the receipts speak louder than the replies.
