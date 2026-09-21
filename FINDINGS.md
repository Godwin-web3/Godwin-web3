# Findings index

Public catalog of verified work. Full writeups on the [portfolio](https://godwinxbt.vercel.app/findings).
A row here is not a Foundry test file. It is the claim, the scope, and the link to the argument.

---

<a id="lemon-fun-bonding-curve-theft"></a>

## lemon.fun · Critical · Robinhood Chain

**LemonCurveFactory legacy bonding curve. Total buyer-fund theft.**

`launch()` takes caller-supplied DEX addresses. At graduation the curve approves the attacker-chosen manager for buyer ETH.

Verified with a working PoC against the live factory.

[Writeup](https://godwinxbt.vercel.app/findings/lemon-fun-bonding-curve-theft)

---

<a id="noon-redeemhandler-unratiod-drain"></a>

## Noon (USN) · Critical · Ethereum

**RedeemHandler.redeem() has no USN/collateral ratio check.**

Burns `usnAmount` and pays `collateralAmount` with no on-chain relationship. Live BURNER_ROLE holder is an EOA.

[Writeup](https://godwinxbt.vercel.app/findings/noon-redeemhandler-unratiod-drain)

---

<a id="noon-minterhandler-uncollateralized-mint"></a>

## Noon (USN) · Critical · Ethereum

**MinterHandlerV2 uncollateralized self-mint.**

Ratio checks skip when `user == msg.sender`. A MINTER_ROLE address that is also a whitelisted user can mint with zero collateral.

[Writeup](https://godwinxbt.vercel.app/findings/noon-minterhandler-uncollateralized-mint)

---

<a id="flex-lender-auction-self-deal"></a>

## Flex Finance · High · Ethereum

**Lender withdrawal shortfall enables free-collateral self-deal.**

Dutch auction receiver is the withdrawing depositor. Self-take costs zero. Remaining depositors eat the marked loss.

PoC on a real large depositor against live state. Net USDC cost 0.

[Writeup](https://godwinxbt.vercel.app/findings/flex-lender-auction-self-deal)

---

<a id="flex-borrower-auction-self-deal"></a>

## Flex Finance · High · Ethereum

**Direct-borrower path. Same auction self-deal.**

Second entry point through `open_trove()` / `borrow()`.

[Writeup](https://godwinxbt.vercel.app/findings/flex-borrower-auction-self-deal)

---

<a id="hydrex-minter-initializer-noop"></a>

## Hydrex · High · Ethereum

**MinterUpgradeableV4._initialize() one-time guard is a no-op.**

Guard checks nonzero. Both pre and post states are nonzero. Governor can re-run and mint a permanent ve lock for free.

[Writeup](https://godwinxbt.vercel.app/findings/hydrex-minter-initializer-noop)

---

<a id="ripe-sequencer-uptime"></a>

## Ripe Protocol · High · Base

**Missing L2 sequencer uptime validation in ChainlinkPrices.**

Traced against real source. No sequencer feed under any name. Stale prices stay valid through an outage window.

[Writeup](https://godwinxbt.vercel.app/findings/ripe-sequencer-uptime)

---

<a id="orvex-voterv5-stale-reward-index"></a>

## Orvex · High · Robinhood Chain

**VoterV5 stale reward-index lets a late voter capture skipped-epoch rewards.**

Fork PoC: 9 epochs of zero weight, then 0.1% weight, captured 10x fair entitlement.

[Writeup](https://godwinxbt.vercel.app/findings/orvex-voterv5-stale-reward-index)

---

<a id="orvex-protocoltoken-missing-burn-early-exit"></a>

## Orvex · High · Robinhood Chain

**ProtocolToken has no burn(). veORVX early-exit claims revert.**

Advertised exit path calls a function the deployed token never implemented. Funds stuck past the chosen duration.

[Writeup](https://godwinxbt.vercel.app/findings/orvex-protocoltoken-missing-burn-early-exit)

---

<a id="ellipsis-incentivevoting-reentrancy"></a>

## Ellipsis Finance · Medium · BSC

**IncentiveVoting.createTokenApprovalVote() reentrancy.**

Caller-controlled external call. State written after. Fork PoC reentered mid-call against live BSC length.

[Writeup](https://godwinxbt.vercel.app/findings/ellipsis-incentivevoting-reentrancy)

---

<a id="hyperfx-calldispatcher-drain"></a>

## HyperFX · Medium · Ethereum

**Unauthenticated dispatch() drains stranded tokens.**

Valid placeOrder can leave an undeclared ERC20 on CallDispatcher. Anyone can sweep it.

[Writeup](https://godwinxbt.vercel.app/findings/hyperfx-calldispatcher-drain)

---

<a id="monolith-phantom-collateral"></a>

## Monolith Market · Medium · Ethereum

**Phantom collateral via fee-on-transfer tokens.**

Ledger credits requested amount, not received amount. Live markets (sINV, XAUt) are not exploitable today. Systemic gap, not an active drain.

[Writeup](https://godwinxbt.vercel.app/findings/monolith-phantom-collateral)

---

<a id="orvex-optiontoken-exercisev-broken"></a>

## Orvex · Medium · Robinhood Chain

**oORVX.exerciseVe() reverts. Missing burnFrom.**

Same token-standard gap. Independent entry point.

[Writeup](https://godwinxbt.vercel.app/findings/orvex-optiontoken-exercisev-broken)

---

<a id="orvex-bveorvx-exercisev-abi-mismatch"></a>

## Orvex · Medium · Robinhood Chain

**bveORVX.exerciseVe() calls a selector that does not exist on live oORVX.**

[Writeup](https://godwinxbt.vercel.app/findings/orvex-bveorvx-exercisev-abi-mismatch)

---

<a id="orvex-minter-broken-initialize-latch"></a>

## Orvex · Medium · Robinhood Chain

**MinterUpgradeableV3 one-time latch never latches.**

Governor can rewind the emission week counter.

[Writeup](https://godwinxbt.vercel.app/findings/orvex-minter-broken-initialize-latch)

---

<a id="panoptic-collateraltracker-stale-liquidation"></a>

## Panoptic V2 · Medium · Ethereum

**Stale/fresh accounting mismatch in CollateralTracker.assetsAndInterest().**

Working PoC. Not currently exploitable under live usage frequency. Shortest stale window measured in hundreds of days at thinnest mintable margin.

[Writeup](https://godwinxbt.vercel.app/findings/panoptic-collateraltracker-stale-liquidation)

---

<a id="ramses-dlmm-composition-fee"></a>

## Ramses DLMM · Informational · Robinhood Chain

**LP share over-mint from a missing fee term in _updateBin().**

Real deviation from audited Trader Joe V2. Echidna: 100,213 txs, 0 profitable sequences. Not oversold.

[Writeup](https://godwinxbt.vercel.app/findings/ramses-dlmm-composition-fee)
