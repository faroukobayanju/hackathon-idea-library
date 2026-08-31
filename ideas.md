# Hackathon Idea Library

This file is our permanent idea bank for hackathons. It records products worth studying, the design pattern each one proves, and the lesson we can reuse without copying the product.

## Scope

This is not an AI idea list and it is not tied to GhostMode, Starknet, or one sponsor. It covers any product with a painful problem, a visible demo, a defensible technical core, and a credible reason to exist after a hackathon. Useful territories include blockchains, payments, privacy, identity, security, games, public-interest software, offline systems, robotics, healthcare, media, developer tools, and consumer products. AI belongs only where removing it would break the core product.

## How projects enter this file

For the STRK20 Private Sprint snapshot on 2026-08-31:

- **Evidence-backed product:** live demo, mainnet status, and at least three verified STRK20 pool transactions.
- **Standout benchmark:** evidence-backed plus an unusually strong problem, technical route, product presentation, or reusable integration pattern.
- **Concept watchlist:** original idea worth remembering, but without enough live mainnet evidence to call it a working benchmark.

These are research labels, not official placements or judging results. The live catalogue is [STRK20 Private Sprint](https://strk20.starknet.io/hackathon), backed by its public [projects dataset](https://raw.githubusercontent.com/starkience/strk20-hackathon/refs/heads/main/projects.json).

## Standout benchmarks

### 1. Facet — unlinkable identity per application

- **One line:** One shielded balance funds a different unlinkable identity for every Starknet application.
- **Why it stands out:** It uses privacy for identity separation, not merely token transfer. Shadow accounts make STRK20 essential to the product.
- **Pattern to remember:** A shared private treasury can create separate public execution identities for different contexts.
- **Risk:** Shadow-account UX and protocol-specific helpers increase integration and audit complexity.
- [Repository](https://github.com/Jennycruzy/facet) · [Demo](https://usefacet.xyz)

### 2. Airlock — unlinkable cross-chain movement

- **One line:** Move value between chains without publishing a direct onchain link between the two sides.
- **Why it stands out:** Cross-chain privacy addresses a real graph-analysis weakness at bridge edges.
- **Pattern to remember:** Separate entry and exit identities, timing, and message handling rather than wrapping a normal bridge in a private-looking interface.
- **Risk:** Bridge trust, relayer metadata, timing correlation, and compliance boundaries remain difficult.
- [Repository](https://github.com/kenkomu/airlock) · [Demo](https://kenkomu.github.io/airlock/)

### 3. Aperture — private governance plus shielded treasury

- **One line:** A DAO can vote with sealed ballots and move treasury funds without exposing every participant's financial graph.
- **Why it stands out:** It combines two privacy surfaces—governance and treasury—into one understandable institutional use case.
- **Pattern to remember:** Privacy becomes more valuable when it protects both a decision and the financial action produced by that decision.
- **Risk:** Eligibility, anti-double-voting, result disclosure, and governance auditability must remain explainable.
- [Repository](https://github.com/OoJae/aperture-strk20) · [Demo](https://aperture-strk20.vercel.app)

### 4. Erebus — private negotiation for AI agents

- **One line:** AI agents negotiate privately and settle through STRK20 without publishing their commercial strategy.
- **Why it stands out:** It moves beyond “agents can pay” to the more valuable problem of hiding offers, counterparties, and settlement relationships.
- **Pattern to remember:** Private machine commerce needs negotiation confidentiality, payment privacy, replay protection, and delivery verification together.
- **Risk:** If negotiation happens on an ordinary server, network metadata and operator visibility can undermine the privacy story.
- [Repository](https://github.com/PoulavBhowmick03/Erebus) · [Demo](https://erebus-private-agents.vercel.app)

### 5. Tony-Strk — anonymous browsing and private agent payments

- **One line:** An AI agent can access paid web resources through Tor and settle the request privately with STRK20.
- **Why it stands out:** It joins network privacy, agent tooling, x402-style payments, a Cairo anonymizer, and real mainnet execution.
- **Pattern to remember:** A payment receipt can be produced by an anonymizer that pays a public merchant while concealing the pool user.
- **Risk:** Merchant, resource commitment, token, and price may still be public depending on the receipt route.
- [Repository](https://github.com/Aaronvern/Tony-Strk) · [Demo](https://tony-strk.vercel.app)

### 6. Envelope — private payments without recipient wallet setup

- **One line:** Send value as a sealed link that the recipient can claim without already having a configured privacy wallet.
- **Why it stands out:** It attacks the hardest consumer privacy problem: recipient onboarding.
- **Pattern to remember:** Claim links and escrow can bridge the gap created by STRK20's requirement that a private-transfer recipient be registered.
- **Risk:** Link theft, secret delivery, expiry, refund paths, and phishing must be handled rigorously.
- [Repository](https://github.com/0xrlawrence/envelope) · [Demo](https://0xrlawrence.github.io/envelope/)

### 7. MorokPay — reusable private donation identity

- **One line:** A creator publishes one QR code while supporters choose amounts and pay inside the privacy pool.
- **Why it stands out:** Clear consumer use case, mainnet evidence, Ready wallet support, and a route for MetaMask-only users.
- **Pattern to remember:** Reusable payment endpoints need recipient registration checks, live pool-fee reads, maturity handling, and careful channel-opening privacy.
- **Risk:** The first setup interaction can name the recipient or shrink the anonymity set if it is tightly coupled to payment.
- [Repository](https://github.com/ssadkov/morok-pay-starknet) · [Demo](https://morok-pay-starknet.vercel.app)

### 8. Aegis Rescue — privacy as incident response

- **One line:** Rescue funds from an exposed wallet into a private safe destination before an attacker drains them.
- **Why it stands out:** It reframes a privacy pool as security infrastructure rather than a payment product.
- **Pattern to remember:** Privacy can break an attacker's ability to follow rescued assets from a compromised public identity.
- **Risk:** Transaction ordering, attacker bots, key compromise, proof latency, and authorization safety are existential.
- [Repository](https://github.com/justbiar/aegis) · [Demo](https://aegis-peach-six.vercel.app)

### 9. Offbook — private bilateral OTC settlement

- **One line:** Two parties agree fixed trade terms and settle without publishing the trader relationship.
- **Why it stands out:** OTC trading has an obvious confidentiality need and visible commercial value.
- **Pattern to remember:** A strong privacy app protects negotiation, counterparty identity, and atomic settlement—not just the final transfer.
- **Risk:** Asset delivery, price commitments, expiry, disputes, and helper-contract custody require careful design.
- [Repository](https://github.com/Akinbola247/offbook) · [Demo](https://offbooks.vercel.app/)

### 10. ConditionalPay — programmable private settlement

- **One line:** Lock private value behind claim, refund, and condition rules.
- **Why it stands out:** It turns private transfers into programmable business workflows.
- **Pattern to remember:** Stateful anonymizer contracts can implement escrow when direct private transfer is impossible or premature.
- **Risk:** Stateful helpers hold funds across transactions and therefore need pinned pool callers, replay protection, and audit-quality recovery logic.
- [Repository](https://github.com/eugenennamdi/ConditionalPay) · [Demo](https://conditionalpay.vercel.app)

### 11. Stealth Checkout — drop-in private merchant acceptance

- **One line:** Add private checkout to a site with a hosted invoice and small integration surface.
- **Why it stands out:** Excellent distribution strategy and extremely easy product explanation.
- **Pattern to remember:** The fastest merchant route can unshield to a fresh invoice address and verify the public balance delta.
- **Risk:** This hides payer linkage but exposes destination and amount, so it offers less privacy depth than an encrypted seller note.
- [Repository](https://github.com/bongbongcrypto/stealth-checkout) · [Demo](https://bongbongcrypto.github.io/stealth-checkout/apps/demo-arcade/index.html)

### 12. Lacuna — developer workbench for private flows

- **One line:** Build, inspect, and verify STRK20 Wallet API flows from one developer tool.
- **Why it stands out:** Infrastructure can multiply the value of every downstream privacy application.
- **Pattern to remember:** Debugging tools should expose action construction, wallet capability, pool evidence, simulation, and privacy boundaries.
- **Risk:** A generic workbench is easy to imitate unless it owns a uniquely useful compiler, verifier, or deployment workflow.
- [Repository](https://github.com/dexarxbt/Lacuna) · [Demo](https://lacuna-strk.vercel.app/)

### 13. Limen — proof of capital without balance disclosure

- **One line:** Confirm that someone has enough capital without revealing their complete wallet balance.
- **Why it stands out:** It converts privacy into a reusable credential rather than a hidden payment.
- **Pattern to remember:** Selective financial disclosure can unlock lending, marketplaces, access control, and institutional workflows.
- **Risk:** The proof statement, freshness, replay prevention, and exact information leakage must be specified precisely.
- [Repository](https://github.com/winsznx/limen) · [Demo](https://limen.timjosh507.workers.dev)

### 14. Cutout — privacy-aware wallet signing guard

- **One line:** Warn users when a shield action creates a weak anonymity set before they sign it.
- **Why it stands out:** It improves privacy quality instead of merely enabling a privacy transaction.
- **Pattern to remember:** A privacy product can analyze public pool evidence and recommend safer amounts or timing.
- **Risk:** Heuristics must be presented as risk estimates, never as guarantees of anonymity.
- [Repository](https://github.com/dmetagame/cutout) · [Demo](https://cutout.rouma.online/)

### 15. Philoxenia — privacy for real-world hospitality

- **One line:** Discover and pay for peer-to-peer stays without exposing the guest-host financial relationship publicly.
- **Why it stands out:** It applies privacy to a surprising, human, real-world marketplace.
- **Pattern to remember:** The most memorable hackathon products combine a private financial edge with a socially visible application.
- **Risk:** Trust, identity, reputation, disputes, location privacy, and physical safety cannot be solved by payment privacy alone.
- [Repository](https://github.com/SergioSSantiago/philoxenia) · [Demo](https://philoxenia-iota.vercel.app)

## All evidence-backed STRK20 products

The following 43 projects had a live demo, mainnet status, and at least three verified pool transactions in the 2026-08-31 catalogue snapshot.

### Payments

| Product | Core idea | Pattern worth saving | Links |
|---|---|---|---|
| KudiRoll | Private payroll for Nigerian businesses | Batch operational payments with reusable teams and shielded USDC | [Code](https://github.com/Cyano88/kudiroll) · [Demo](https://kudiroll-production.up.railway.app) |
| MorokPay | Private creator donations through one reusable QR | Recipient onboarding, dynamic amounts, fee and maturity handling | [Code](https://github.com/ssadkov/morok-pay-starknet) · [Demo](https://morok-pay-starknet.vercel.app) |
| Sage | AI agent recruits and privately pays product testers | Private agent labor marketplace with task delivery | [Code](https://github.com/shariqazeem/sage) · [Demo](https://sagepays.xyz) |
| NIGHTSHIFT | Automated private subscriptions | Recurring private payments and scheduling | [Code](https://github.com/kshitij-hash/nightshift) · [Demo](https://nightshift-six-lilac.vercel.app) |
| WhisperPay | Turn a photographed receipt into private split-bill links | Computer vision plus payment-link distribution | [Code](https://github.com/bugsm/whisperpay) · [Demo](https://whisperpay.vercel.app) |
| Envelope | Sealed payment links without wallet prerequisites | Escrow/claim link solves unregistered-recipient onboarding | [Code](https://github.com/0xrlawrence/envelope) · [Demo](https://0xrlawrence.github.io/envelope/) |
| ShadowPay | Anonymous payroll for teams | Private recurring business payouts | [Code](https://github.com/A-Raphie/shadowpay) · [Demo](https://shadowpay-green.vercel.app) |

### Infrastructure

| Product | Core idea | Pattern worth saving | Links |
|---|---|---|---|
| Facet | Unlinkable identity per app from one shielded balance | Shadow-account application launcher | [Code](https://github.com/Jennycruzy/facet) · [Demo](https://usefacet.xyz) |
| Airlock | Cross-chain transfers without a direct onchain link | Decoupled entry and exit identities | [Code](https://github.com/kenkomu/airlock) · [Demo](https://kenkomu.github.io/airlock/) |
| Almoner | Private batch payments to many recipients | Claim/escrow fallback for recipient registration | [Code](https://github.com/leojay-net/almoner) · [Demo](https://strkprivacy.vercel.app) |
| Jalin | Arbitrary multi-step, multi-token execution in one transaction | Transaction-plan compiler within protocol limits | [Code](https://github.com/PugarHuda/jalin) · [Demo](https://jalin-five.vercel.app) |
| Limen | Prove capital availability without revealing a balance | Selective financial credential | [Code](https://github.com/winsznx/limen) · [Demo](https://limen.timjosh507.workers.dev) |
| Xence | Seal forecasts and score them later | Commit/reveal for private information markets | [Code](https://github.com/AustinChris1/xence) · [Demo](https://xence.vercel.app) |
| ConditionalPay | Private settlement with claims and refunds | Stateful privacy escrow | [Code](https://github.com/eugenennamdi/ConditionalPay) · [Demo](https://conditionalpay.vercel.app) |
| Cordon | Credential and policy layer for private payments | Compliance/policy gate attached to execution | [Code](https://github.com/RaYYeR220/cordon) · [Demo](https://rayyer220.github.io/cordon/) |
| Quorum | Campaign activates only after private commitments reach a threshold | Private coordination with a public outcome | [Code](https://github.com/iamdflame/quorum) · [Demo](https://quorum-strk20.vercel.app) |
| Aperture | Sealed DAO ballots and shielded treasury | Privacy across decision and execution | [Code](https://github.com/OoJae/aperture-strk20) · [Demo](https://aperture-strk20.vercel.app) |
| Cutout | Signing guard based on STRK20 anonymity evidence | Privacy-risk analysis before execution | [Code](https://github.com/dmetagame/cutout) · [Demo](https://cutout.rouma.online/) |

### DeFi

| Product | Core idea | Pattern worth saving | Links |
|---|---|---|---|
| Doom | Prediction market with public odds and hidden bettors | Public market state plus private participant positions | [Code](https://github.com/neromtoobad/doom) · [Demo](https://neromtoobad.github.io/doom/) |
| CipherBid | Vickrey auctions with private bids | Sealed bids and verifiable settlement | [Code](https://github.com/SourceSenseiTheRealOne/cipherbid) · [Demo](https://sourcesenseitherealone.github.io/cipherbid/auction/?id=1788040057342) |
| Offbook | Private bilateral OTC trades | Confidential negotiation plus atomic settlement | [Code](https://github.com/Akinbola247/offbook) · [Demo](https://offbooks.vercel.app/) |

### Consumer products

| Product | Core idea | Pattern worth saving | Links |
|---|---|---|---|
| strk20.run | Private account for value, swaps, chat, bets, launches, and voting | Consumer privacy superapp | [Code](https://github.com/Blockchain-Oracle/strk20-run) · [Demo](https://strk20.run) |
| Afterlight | Private recovery reserve for self-custody wallets | Privacy as disaster recovery | [Code](https://github.com/qdeeworld/afterlight) · [Demo](https://afterlight.dolepee.com) |
| Wrenchless | Flexible private STRK/USDC vault | Private savings and delayed return | [Code](https://github.com/Timidan/wrenchless) · [Demo](https://wrenchless.timidan.xyz) |
| Lumen | Private Bitcoin account on Starknet | Shielded BTC-oriented saving and staking | [Code](https://github.com/shariqazeem/lumen-strk20) · [Demo](https://lumen-strk20.vercel.app) |
| Mirage | Shielding and cross-chain privacy superapp | Unified privacy UX across assets and chains | [Code](https://github.com/YanYuanFE/mirage) · [Demo](https://mirage-beta-app.vercel.app) |
| Deadletter | Protected evidence exchange with encrypted reporting | Anonymous disclosure plus private incentive | [Code](https://github.com/ELLA0VICTOR/deadletter) · [Demo](https://deadletter.vercel.app/) |
| Lantern | Crowdfunding with public goals and anonymous donors | Public coordination, private participation | [Code](https://github.com/PhiBao/lantern) · [Demo](https://app-wine-seven-35.vercel.app) |
| Booty Bank | Financial tools for creators with private income handling | Vertical banking where confidentiality is commercially necessary | [Code](https://github.com/odinfree/booty-bank) · [Demo](https://bootybank.app/) |

### Developer tooling

| Product | Core idea | Pattern worth saving | Links |
|---|---|---|---|
| Aegis Rescue | Sweep exposed funds into privacy before an attacker wins | Security incident response using privacy rails | [Code](https://github.com/justbiar/aegis) · [Demo](https://aegis-peach-six.vercel.app) |
| Lacuna | STRK20 Wallet API workbench | Developer debugging, inspection, and verification | [Code](https://github.com/dexarxbt/Lacuna) · [Demo](https://lacuna-strk.vercel.app/) |
| Stealth Checkout | Drop-in hosted private checkout | Tiny merchant integration surface | [Code](https://github.com/bongbongcrypto/stealth-checkout) · [Demo](https://bongbongcrypto.github.io/stealth-checkout/apps/demo-arcade/index.html) |

### Other strong applications

| Product | Core idea | Pattern worth saving | Links |
|---|---|---|---|
| Stake Wars | Validator delegation becomes a territory strategy game | Hide economic strategy inside a visible game | [Code](https://github.com/broody/stake-wars) · [Demo](https://stakewars.gg) |
| Gigstark | Private payments to creators | Simple vertical payment UX | [Code](https://github.com/OGtev317/Gigstark) · [Demo](https://zeerostream.pages.dev) |
| Philoxenia | Private peer-to-peer hospitality | Privacy in a real-world marketplace | [Code](https://github.com/SergioSSantiago/philoxenia) · [Demo](https://philoxenia-iota.vercel.app) |
| Erebus | Encrypted negotiation and settlement for AI agents | Private machine commerce beyond payment | [Code](https://github.com/PoulavBhowmick03/Erebus) · [Demo](https://erebus-private-agents.vercel.app) |
| Tony-Strk | Anonymous browsing and private agent payments | Tor + MCP + x402-style settlement | [Code](https://github.com/Aaronvern/Tony-Strk) · [Demo](https://tony-strk.vercel.app) |
| Cloakra | Shielded grants and bounty allocation | Private capital allocation | [Code](https://github.com/mrnetwork0001/Cloakra) · [Demo](https://cloakra-k81ir4y3k-mrnetworks-projects.vercel.app) |
| Hidden | Shielded 1v1 wagering with hidden moves | Private game state plus private stakes | [Code](https://github.com/DevTest-me/hidden-starknet) · [Demo](https://hidden-starknet.vercel.app/) |
| Provah | Transferable capabilities derived from pool activity | Private activity as access credential | [Code](https://github.com/levithefirst/provah) · [Demo](https://provah.vercel.app) |
| GhostLine | Privacy intelligence before private transactions | Explain exposure before execution | [Code](https://github.com/Leequidice/GhostLine) · [Demo](https://ghostline-weld.vercel.app) |
| Before You Sign | Simulate the privacy implications of an STRK20 action | Pre-signing privacy report | [Code](https://github.com/Valorian0108/before-you-sign) · [Demo](https://before-you-sign-seven.vercel.app/) |
| Morrow | Privacy preflight for milestone grants | Route analysis attached to funding workflows | [Code](https://github.com/nftkingiii/Morrow) · [Demo](https://morrow-production.up.railway.app) |

## Concept watchlist

These ideas are memorable, but their catalogue entries did not meet the evidence-backed threshold at the snapshot time.

| Product | Idea worth remembering | Missing proof at snapshot | Links |
|---|---|---|---|
| Vickrey | Losing auction bids never become public | No verified mainnet pool transactions | [Code](https://github.com/Vickrey-Protocol/vickrey) · [Demo](https://vickrey.0xo.in) |
| VINSS | Encrypted deal room from negotiation through escrow | No verified mainnet pool transactions | [Code](https://github.com/DXJLabs/vinss) · [Demo](https://vinss-nu.vercel.app/) |
| Veyl | Private launch/trading terminal with unlinkable execution identities | No verified mainnet pool transactions | [Code](https://github.com/codeswithroh/veyl) · [Demo](https://veyl-tau.vercel.app/) |
| zkPayslip | Private payroll plus verifiable income | No verified mainnet pool transactions | [Code](https://github.com/EndPx/zkpayslip) · [Demo](https://zkpayslip.vercel.app) |
| Lens | Selectively disclose payment relationships without showing full history | No verified mainnet pool transactions | [Code](https://github.com/Techkeyy/lens) · [Demo](https://lens-beige-five.vercel.app) |
| Sealed | Unlinkable bidders and concealed bids until reveal | No verified mainnet pool transactions | [Code](https://github.com/tinoxbt/sealed) · [Demo](https://tinoxbt.github.io/sealed/) |
| Nexora Protocol | Cross-chain privacy router rather than a single bridge | No verified mainnet pool transactions | [Code](https://github.com/Gedion08/Nexora-Protocol) · [Demo](https://nexora-protocol.vercel.app) |
| StarkWhisper | End-to-end encrypted messaging with private payment memos | No verified mainnet pool transactions | [Code](https://github.com/dino1x/starkwhisper) · [Demo](https://starkwhisper.vercel.app) |
| Redpocket | Password-based private group fund claims shared through chat | Only two verified transactions | [Code](https://github.com/kevlau1/redpacket) · [Demo](https://redpocket-virid.vercel.app/) |
| Mosby Pass | Private event admission with QR credentials and shielded payments | No verified mainnet pool transactions | [Code](https://github.com/odinfree/mosby-pass) · [Demo](https://welttowelt.github.io/mosby-pass/) |
| GhostBounty | Anonymous vulnerability reports with private rewards | No live demo or verified mainnet pool transactions | [Code](https://github.com/daraijaola/ghostbounty) |

## Blockchain-wide and non-AI product blueprints

These concepts deliberately look beyond AI. Several are derived from strong mechanics found across the reviewed portfolios; others extend those mechanics into new product categories.

### 1. Wallet Inbox Zero — clean up years of onchain clutter safely

- **One line:** Scan many wallets, explain every stranded asset, and produce one reviewable plan to consolidate or dispose of the clutter.
- **Pain:** Users accumulate dust, forgotten tokens, NFTs, allowances, positions, and tiny balances across chains; existing sweepers are risky and opaque.
- **Why blockchain is indispensable:** The product reads live ownership and approval state, simulates a deterministic transaction plan, and lets the user sign each bounded batch without custody.
- **Showcase moment:** Turn five messy wallets into a clean destination while showing assets recovered, approvals revoked, gas spent, and suspicious tokens skipped.
- **Winning edge:** It solves a problem almost every long-term crypto user visibly has.
- **Main risk:** Malicious tokens and inaccurate valuations make blind automation dangerous; default to simulation and explicit review.
- **Inspired by:** [TIDYR](https://github.com/winsznx/tidyr).

### 2. Milestone Capital — crowdfunding where evidence unlocks each tranche

- **One line:** Fund a project once, but release money only when backers verify visible milestones.
- **Pain:** Traditional crowdfunding sends all funds before delivery, while fully manual escrow does not scale.
- **Why blockchain is indispensable:** Escrow, milestone votes, refunds, deadlines, and release rules remain transparent and enforceable without platform custody.
- **Showcase moment:** Fund a three-stage build, submit proof for stage one, release only that tranche, then trigger a refund on a missed deadline.
- **Winning edge:** The complete happy path and failure path fit into a three-minute demo.
- **Main risk:** Subjective milestones cause disputes; start with grants whose evidence can be checked mechanically.
- **Inspired by:** [Fundraiser](https://github.com/winsznx/fundraiser) and [FundotStacks](https://github.com/winsznx/FundotStacks).

### 3. FairPass — tickets that remain useful but cannot become scalper inventory

- **One line:** Sell event tickets with enforceable resale limits, fraud-proof entry, and optional privacy for attendees.
- **Pain:** Buyers face counterfeit tickets, screenshot reuse, price gouging, and platforms that control the entire resale market.
- **Why blockchain is indispensable:** A ticket has verifiable provenance, rotating entry credentials, and programmable resale or royalty rules that survive outside one marketplace.
- **Showcase moment:** Resell a ticket within its price cap, reject an overpriced resale, and rotate the QR credential after transfer so the old screenshot fails.
- **Winning edge:** Everyone understands the pain immediately and the live scan is highly visual.
- **Main risk:** Do not force users to understand wallets; recovery, transfer, and door throughput matter more than token jargon.
- **Inspired by:** [EventTicket](https://github.com/winsznx/eventticket) and the STRK20 event-credential projects.

### 4. Circle Treasury — group finance inside the chat people already use

- **One line:** Split bills, run a savings circle, collect dues, and settle the group without leaving Telegram or WhatsApp.
- **Pain:** Friends, families, guilds, and rotating savings groups rely on spreadsheets, screenshots, and one trusted collector.
- **Why blockchain is indispensable:** A shared treasury enforces contributions, payout order, limits, and auditable settlement while members retain direct ownership.
- **Showcase moment:** Create a group in chat, collect five contributions, pay one member, and display the updated obligations instantly.
- **Winning edge:** Distribution is built into the product instead of being an afterthought.
- **Main risk:** Social recovery and lost-device handling are existential for mainstream users.
- **Inspired by:** [TON Circle](https://github.com/winsznx/TonCircle), [Float](https://github.com/winsznx/float), and [Tally](https://github.com/winsznx/tally).

### 5. Atomic Freight — delivery-versus-payment across different chains

- **One line:** Release payment only when authenticated delivery is proven, even when the asset and money live on different chains.
- **Pain:** Cross-chain commerce usually introduces a bridge, custodian, or manual reconciliation step between delivery and payment.
- **Why blockchain is indispensable:** Assets stay on their issuance chains while authenticated state proofs coordinate an atomic or safely recoverable settlement.
- **Showcase moment:** Deliver a tokenized certificate on one chain and release stablecoin on another; then show the timeout/refund path when delivery never arrives.
- **Winning edge:** It solves a real interoperability problem without pretending every asset must be bridged.
- **Main risk:** The security model is only as strong as the cross-chain proof and finality assumptions.
- **Inspired by:** [Conduit](https://github.com/winsznx/conduit) and [Signet](https://github.com/winsznx/signet).

### 6. Programmable Treasury Streams — recurring money without a cron custodian

- **One line:** Encode salaries, subscriptions, grants, and budget limits directly into spendable payment schedules.
- **Pain:** Recurring crypto payments depend on bots, hot keys, or centralized services that can stop, duplicate, or exceed a mandate.
- **Why blockchain is indispensable:** The asset itself or its vault enforces cadence, cap, recipient, expiry, and revocation conditions.
- **Showcase moment:** Stream a weekly budget, attempt an early withdrawal, change the recipient through governance, and prove the cap cannot be exceeded.
- **Winning edge:** It turns treasury policy into money behavior instead of dashboard settings.
- **Main risk:** UTXO and account-based chains need different designs; avoid claiming one abstraction fits both perfectly.
- **Inspired by:** [FlowGuard](https://github.com/winsznx/flow-guard) and the recurring-payment projects in the STRK20 sprint.

### 7. Proof-of-Presence Rituals — make real-world participation composable

- **One line:** Prove you were present for a place, event, or daily ritual without publishing your complete location history.
- **Pain:** Attendance, loyalty, volunteering, and local community programs rely on forgeable screenshots or invasive tracking platforms.
- **Why blockchain is indispensable:** Time-bound attestations become portable credentials that other applications can verify without trusting the original app.
- **Showcase moment:** Complete a weather- or venue-bound ritual, receive a credential, and unlock a benefit in a separate application.
- **Winning edge:** It links an onchain primitive to a physical, visual action.
- **Main risk:** GPS alone is trivial to spoof; combine bounded attesters, device signals, or privacy-preserving proximity proofs.
- **Inspired by:** [Klock](https://github.com/winsznx/klock).

### 8. Public Media Notary — community evidence for manipulated media

- **One line:** Attach timestamped provenance, expert challenges, and community notes to a specific photo or video fingerprint.
- **Pain:** Deepfakes spread faster than fact-checks, while platforms can remove context or disagree about the original file.
- **Why blockchain is useful:** Content hashes, attestations, challenge history, and signer reputation remain portable across platforms and cannot be silently rewritten.
- **Showcase moment:** Upload an altered clip, trace it back to a signed original, and show competing notes with their supporting evidence.
- **Winning edge:** Strong public-interest problem with a concrete artifact-verification demo.
- **Main risk:** A blockchain proves who said what and when—not that a claim is true. The UI must preserve uncertainty.
- **Inspired by:** [Deepfake Notary](https://github.com/winsznx/deepfake-notary-dkgcon2025).

### 9. Verifiable Index Factory — transparent crypto portfolios anyone can reproduce

- **One line:** Write an index methodology in plain rules, compile it independently, and execute rebalances with a complete audit trail.
- **Pain:** Crypto indices and structured products can hide discretionary asset selection, pricing, and rebalance decisions.
- **Why blockchain is indispensable:** Constituents, weights, oracle snapshots, compiler outputs, and execution receipts are publicly reproducible.
- **Showcase moment:** Change one methodology rule, have two independent compilers reach the same portfolio, and execute the rebalance.
- **Winning edge:** It targets institutional credibility rather than another retail trading interface.
- **Main risk:** Transparent methodology does not eliminate oracle manipulation or liquidity risk.
- **Inspired by:** [Method](https://github.com/winsznx/method).

### 10. RWA Collateral Passport — finance an asset without selling it

- **One line:** Verify what a tokenized real-world asset represents, assign a conservative borrowing value, and lend against it safely.
- **Pain:** Tokenized assets remain isolated because lenders cannot consistently evaluate legal identity, freshness, liquidity, encumbrance, and jurisdiction.
- **Why blockchain is indispensable:** Attestations, haircuts, lien state, and financing positions form a shared clearing and risk layer across issuers and lenders.
- **Showcase moment:** Present two similar assets with different documentation freshness and watch their eligible collateral values diverge.
- **Winning edge:** It solves the missing risk layer between tokenization and actual capital use.
- **Main risk:** Legal enforceability and oracle responsibility cannot be replaced by code; choose one narrow asset class.
- **Inspired by:** [Usance](https://github.com/winsznx/usance).

### 11. Sats-Back Arcade — a reusable stake-to-play game layer

- **One line:** Let any small web game attach an escrowed entry, skill threshold, leaderboard, and automatic prize pool.
- **Pain:** Onchain games often build payment, escrow, scoring, and anti-cheat infrastructure from scratch while the actual game remains weak.
- **Why blockchain is useful:** Entry stakes and payout rules are transparent, portable, and resistant to a game operator withholding prizes.
- **Showcase moment:** Play a 30-second game, cross the threshold, and watch the daily pool settle to the verified winner.
- **Winning edge:** A fun game attracts attention while the reusable SDK gives the project technical depth.
- **Main risk:** Skill verification and gambling regulation need careful boundaries; use capped sponsor-funded prizes where appropriate.
- **Inspired by:** [Flap](https://github.com/winsznx/flap), [Snak](https://github.com/winsznx/snak), [Coil](https://github.com/winsznx/coil), and [Bull Rush](https://github.com/winsznx/bull-rush).

### 12. Crowd Referee — settle live community events without one trusted judge

- **One line:** Capture a disputed real-world moment, let the room attest, and automatically settle the agreed outcome.
- **Pain:** Informal sports, local competitions, and watch-party wagers depend on one organizer's word and messy payment collection.
- **Why blockchain is useful:** Signed peer attestations, dispute windows, and escrowed payouts make settlement portable and auditable.
- **Showcase moment:** Record a goal or match event, gather nearby attestations, challenge one false report, and settle the room.
- **Winning edge:** It combines a physical moment, social consensus, and instant settlement.
- **Main risk:** Collusion is easy in small groups; the product should expose confidence and participant relationships.
- **Inspired by:** [Whisl](https://github.com/winsznx/whisl).

### 13. Borderless Payroll Router — pay people and software through the right rail

- **One line:** Send payroll or contractor payments across stablecoins, local cash-out, and machine-payment rails from one instruction.
- **Pain:** Global teams manually choose chains, bridge assets, manage recipient preferences, and reconcile fiat exits.
- **Why blockchain is useful:** Stablecoin settlement and portable receipts unify human payroll, contractor invoices, and software-service payments.
- **Showcase moment:** Pay one worker to a local cash-out rail, one to a wallet, and one API through x402 from the same batch.
- **Winning edge:** It connects crypto infrastructure to a recurring real business operation.
- **Main risk:** Compliance, exchange partners, and failed payout recovery dominate the engineering; one corridor is enough for an MVP.
- **Inspired by:** [Remlo](https://github.com/winsznx/remlo).

### 14. Onchain Yearbook — turn wallet history into a shareable personal story

- **One line:** Convert a year of onchain activity into a beautiful, verifiable story users actually want to share.
- **Pain:** Explorers expose raw transactions but do not help ordinary users understand milestones, communities, risk, or progress.
- **Why blockchain is useful:** Every highlight links back to verifiable activity while private or sensitive interactions can be excluded locally.
- **Showcase moment:** Generate a personalized annual reel with first protocol, biggest learning moment, communities, fees saved, and privacy controls.
- **Winning edge:** Consumer virality can distribute the project far beyond judges.
- **Main risk:** Do not reduce identity to wallet wealth or leak sensitive positions through a share card.
- **Inspired by:** [Base Wrapped](https://github.com/winsznx/base-wrapped) and [Stacks Wrapped](https://github.com/winsznx/stacks-wrapped).

### 15. Portable Work Reputation — prove delivery history without platform lock-in

- **One line:** Carry verified jobs, deadlines, disputes, and client attestations from one work platform to another.
- **Pain:** Freelancers and contractors lose years of reputation when a marketplace closes or suspends them.
- **Why blockchain is useful:** Job receipts and signed attestations belong to the worker, while selective disclosure avoids exposing every client relationship.
- **Showcase moment:** Import two completed jobs, prove a reliability threshold to a new marketplace, and hide the client names.
- **Winning edge:** It treats identity as user-owned infrastructure with a clear economic benefit.
- **Main risk:** Reputation farming and retaliatory reviews require bilateral evidence and dispute processes.
- **Inspired by:** [IdentityBadge](https://github.com/winsznx/identitybadge), [BountyMesh](https://github.com/winsznx/bountymesh), and [Vestra](https://github.com/Enoch208/Vestra).

### 16. Allowance Radar — prevent wallet drains before they happen

- **One line:** Continuously map token approvals and operator permissions, explain the actual blast radius, and revoke safely in batches.
- **Pain:** Users approve contracts once and forget them, leaving dormant permissions that become dangerous after upgrades or compromises.
- **Why blockchain is indispensable:** The product reconstructs live allowance and operator state, contract upgradeability, asset exposure, and revocation transactions.
- **Showcase moment:** Connect a wallet, reveal the maximum assets each approval can move, simulate revocations, and prove risk disappears after signing.
- **Winning edge:** Security value is immediate and measurable in protected assets.
- **Main risk:** A simplistic “unlimited equals malicious” score creates noise; explain evidence and uncertainty.

### 17. Product Recall Graph — find every customer touched by a bad component

- **One line:** Trace a defective ingredient, chip, package, or batch through suppliers to the exact products and customers affected.
- **Pain:** Recalls are slow and overbroad because supply-chain records are fragmented and parties cannot reconcile identifiers.
- **Why blockchain may help:** Shared signed batch events create a neutral lineage trail across organizations that do not share one database operator.
- **Showcase moment:** Mark one batch defective and instantly produce the bounded recall list with every dependency path as evidence.
- **Winning edge:** It converts graph infrastructure into a visible real-world safety outcome.
- **Main risk:** Blockchain cannot repair false input; attester accountability and physical-digital binding are the actual product.

### 18. Consent Receipt Wallet — make data permissions visible and revocable

- **One line:** Give people one place to see who may use their data, for what purpose, until when, and revoke it.
- **Pain:** Consent is buried in legal text, duplicated across services, and impossible for users to audit after clicking accept.
- **Why decentralized identity may help:** Signed, purpose-bound consent receipts remain portable across services; revocation registries let processors check current authority.
- **Showcase moment:** Grant a clinic research access to one data category, use it successfully, revoke it, and show the next access fail.
- **Winning edge:** Privacy becomes an understandable control panel rather than a policy document.
- **Main risk:** Never store personal data onchain; store minimal commitments and revocation state only.

### 19. Offline Clinic Reference — medical knowledge that works when the network does not

- **One line:** Give low-connectivity clinics a searchable, updateable medical reference that never depends on a live cloud call.
- **Pain:** Clinicians in rural settings lose access to drug, dosage, interaction, and protocol information during outages.
- **Core technology:** A compressed local knowledge base, on-device semantic retrieval, signed update bundles, and source-linked answers.
- **Showcase moment:** Disconnect the machine, search a difficult drug interaction, open the exact source passage, then install a signed update by file.
- **Winning edge:** Clear public benefit and a powerful offline demonstration.
- **Main risk:** This is reference support, not diagnosis; clinical review, versioning, and provenance are mandatory.
- **Inspired by:** [LocalRx](https://github.com/winsznx/localrx).

### 20. Low-Resource Language Foundry — prove where every training example came from

- **One line:** Build high-quality datasets for underrepresented languages with human gates, contamination checks, and reproducible releases.
- **Pain:** Low-resource language models suffer from scraped noise, translated contamination, dialect collapse, and evaluation leakage.
- **Core technology:** Source lineage, contributor workflow, deduplication, quality adjudication, held-out evaluation, and tamper-evident dataset manifests.
- **Showcase moment:** Trace one model improvement back to accepted examples while proving the evaluation set never entered training.
- **Winning edge:** It creates lasting ecosystem infrastructure rather than a disposable chatbot.
- **Main risk:** Community ownership, licensing, dialect representation, and compensation matter as much as model scores.
- **Inspired by:** [Foundry-Y](https://github.com/Enoch208/Foundry-Y).

### 21. Desktop Macro Studio — record work once, replay it safely

- **One line:** Let nontechnical users record a desktop workflow, turn it into editable steps, and replay it with safety checkpoints.
- **Pain:** Repetitive legacy-software work remains manual because APIs do not exist and current macro tools are brittle or opaque.
- **Core technology:** Event capture, visual anchors, parameterized steps, drift detection, secrets handling, and human approval before destructive actions.
- **Showcase moment:** Record a cross-application report workflow, change one field, and replay it while the system pauses when the screen diverges.
- **Winning edge:** The time saved is instantly obvious and the product works outside trendy AI use cases.
- **Main risk:** Coordinate-only playback fails constantly; semantic and visual validation must accompany input replay.
- **Inspired by:** [EventMaster](https://github.com/Enoch208/EventMaster).

### 22. Community Compute Exchange — monetize idle hardware with verifiable jobs

- **One line:** Match bounded workloads to idle local GPUs or CPUs and settle only when reproducible checks pass.
- **Pain:** Small creators and researchers cannot afford cloud compute while gaming and office hardware sits unused.
- **Why blockchain may help:** Escrow, operator bonds, portable reputation, and permissionless settlement coordinate unknown buyers and workers.
- **Showcase moment:** Split a render or simulation across three community machines, detect one bad result, reassign it, and pay only valid workers.
- **Winning edge:** The demo makes decentralized infrastructure physically visible across devices.
- **Main risk:** Privacy, malware isolation, bandwidth, and heterogeneous hardware are harder than payment; constrain the first workload tightly.

### 23. Repair Passport — a portable maintenance history for physical goods

- **One line:** Give a phone, vehicle, appliance, or machine a verifiable history of repairs, parts, and warranties that survives resale.
- **Pain:** Buyers cannot verify maintenance claims, manufacturers fragment records, and independent repair shops are excluded.
- **Why blockchain may help:** Owners and authorized repairers append signed events to a portable asset identity without one manufacturer owning the history.
- **Showcase moment:** Scan a product, verify a replacement part and repair, transfer ownership, and preserve warranty eligibility.
- **Winning edge:** It joins right-to-repair, resale trust, and real-world identity in one product.
- **Main risk:** Physical tags can be cloned; tamper evidence and accountable issuers matter more than minting an NFT.

### 24. Civic Budget Explorer — follow public money from promise to outcome

- **One line:** Turn government or community budgets into a searchable graph linking allocations, contracts, payments, milestones, and evidence.
- **Pain:** Public spending data is fragmented across PDFs and portals, making it hard to determine whether funded work actually happened.
- **Core technology:** Document extraction, entity resolution, signed source snapshots, milestone evidence, and an auditable change history.
- **Showcase moment:** Search one road or school and trace its budget promise through contractor payment to timestamped completion evidence.
- **Winning edge:** Strong social value and an interface ordinary citizens can understand.
- **Main risk:** Avoid declaring fraud from incomplete data; show provenance, gaps, and uncertainty.

## Cross-hackathon product blueprints

This section was added after reviewing all 290 public repositories visible across [winsznx](https://github.com/winsznx) and [Enoch208](https://github.com/Enoch208) on 2026-08-31: 200 original repositories and 90 forks. Forks, tutorials, empty experiments, duplicate SDKs, and simple CRUD products were reviewed but excluded from the idea list. The blueprints below remix the strongest original product mechanics into new directions; they are inspiration, not instructions to clone a repository.

### 1. Agent Circuit Breaker — a wallet an AI cannot drain

- **One line:** Give any AI agent spending power with limits that remain enforceable even when the agent is compromised.
- **Pain:** One prompt injection, hallucinated loop, or leaked key can empty an ordinary agent wallet.
- **Technology that must be indispensable:** Smart-account validation plus an onchain vault independently enforce target allowlists, per-action caps, daily caps, expiry, deduplication, and emergency revocation.
- **Showcase moment:** Ask a compromised demo agent to overspend; the exact same action succeeds below the limit and is visibly blocked above it without moving value.
- **Why it can win:** Immediate danger, one-sentence explanation, and a dramatic adversarial demo.
- **Why it can fail:** A UI-only policy or server-side guard is not credible; enforcement must survive a hostile agent and sponsor.
- **Inspired by:** [BOTSpend](https://github.com/winsznx/botspend), [Limen](https://github.com/Enoch208/Limen), and [MANDATE](https://github.com/winsznx/mandate).

### 2. Truth Market — agents buy facts and prove every conclusion

- **One line:** Launch a research swarm where agents pay for sources, challenge claims, and deliver a proof-carrying answer.
- **Pain:** Research agents produce confident summaries without proving who supplied each fact or whether a paid source was worth buying.
- **Technology that must be indispensable:** Machine payments purchase data; attestations and content hashes bind every conclusion to verified source artifacts; reputation rewards agents whose evidence survives challenges.
- **Showcase moment:** Enter a question and watch scout, skeptic, and synthesizer agents transact, disagree, and produce a clickable evidence graph.
- **Why it can win:** AI coordination, payments, provenance, and a visual live workflow reinforce one another.
- **Why it can fail:** If the verifier merely asks another language model for an opinion, the proof claim collapses.
- **Inspired by:** [AetherSwarm](https://github.com/winsznx/aetherswarm), [Strata](https://github.com/Enoch208/Strata), and [Cairn](https://github.com/Enoch208/cairn).

### 3. Agent Workbench Exchange — escrowed jobs for autonomous workers

- **One line:** Post a job that an AI agent can claim, prove it completed, and settle without platform custody.
- **Pain:** Agent marketplaces are controlled by private ledgers and have weak delivery evidence, dispute handling, and crash recovery.
- **Technology that must be indispensable:** Contract escrow defines the job state machine; delivery envelopes are content-addressed; acceptance, timeout, refund, and reputation are independently verifiable.
- **Showcase moment:** Two agents discover a job, one claims it, submits a hashed artifact, and receives payment after an automated acceptance test passes.
- **Why it can win:** It makes the “agent economy” tangible rather than speculative.
- **Why it can fail:** General freelance work is too subjective; the first vertical needs machine-verifiable acceptance criteria.
- **Inspired by:** [BountyMesh](https://github.com/winsznx/bountymesh) and [Metrx](https://github.com/winsznx/metrx).

### 4. Agent Flight Recorder — block dangerous behavior changes before release

- **One line:** Catch when an AI agent gives the same answer but secretly skips safety checks or repeats side effects.
- **Pain:** Output evaluations miss dangerous changes in the tools, retries, policies, and execution paths behind a plausible answer.
- **Technology that must be indispensable:** Distributed traces compile into deterministic behavioral contracts; source control and CI evidence prove what changed; releases fail on missing guards, unknown paths, or duplicate writes.
- **Showcase moment:** Compare two refund agents with identical text output while the tool graph exposes that one issued two refunds and skipped fraud checks.
- **Why it can win:** It solves a new, high-value production failure that ordinary evals miss.
- **Why it can fail:** Trace instrumentation must be real and the detection rules must avoid noisy false positives.
- **Inspired by:** [FlightRules](https://github.com/winsznx/flightrules), [LENS](https://github.com/Enoch208/lens), and [Sigil](https://github.com/Enoch208/Sigil).

### 5. Proof-of-Compute Escrow — pay only for verified work

- **One line:** Fund a compute job, verify its output against a committed rubric, then automatically pay, refund, or slash.
- **Pain:** Buyers cannot confidently purchase model training, rendering, inference, or data processing from unknown operators.
- **Technology that must be indispensable:** Job specification, rubric, output hash, and verifier identity are committed before judgment; a signed verdict is bound to one order and directly controls escrow settlement.
- **Showcase moment:** Submit one correct and one corrupted result; one pays the operator while the other refunds the buyer and slashes the bond.
- **Why it can win:** The AI is a settlement participant, not a chatbot decoration.
- **Why it can fail:** Open-ended quality is impossible to judge reliably; start with bounded jobs and deterministic checks around the model verdict.
- **Inspired by:** [Metrx](https://github.com/winsznx/metrx) and [Pact](https://github.com/winsznx/pact).

### 6. PayRoute — one payment call for every machine-payment protocol

- **One line:** Let an agent call `pay(url)` while the SDK safely selects the cheapest supported payment rail.
- **Pain:** Agents must hard-code separate x402, charge, streaming-channel, and chain-specific payment clients for every service.
- **Technology that must be indispensable:** A signed provider manifest advertises supported modes; a policy router validates it, chooses a rail, enforces spend limits, and emits a normalized receipt.
- **Showcase moment:** Fifty paid API calls automatically switch between per-call settlement and a payment channel while using only two onchain transactions.
- **Why it can win:** Tiny developer surface, measurable savings, and ecosystem-wide usefulness.
- **Why it can fail:** “Universal” becomes shallow quickly; ship two or three rails that genuinely work rather than ten mocked adapters.
- **Inspired by:** [RouteDock](https://github.com/winsznx/routedock), [STXact](https://github.com/winsznx/stxact), and [RelayCore](https://github.com/winsznx/relaycore).

### 7. Embargo Engine — publish now, reveal automatically later

- **One line:** Seal research, predictions, disclosures, or media now and make early access paid while public reveal is unavoidable.
- **Pain:** Paywalls cannot prove authorship before an event, stop operators from silently editing a claim, or guarantee eventual disclosure.
- **Technology that must be indispensable:** Encrypted storage protects content, a timestamped commitment proves authorship, license tokens control early access, and a permissionless time condition forces public reveal.
- **Showcase moment:** Publish a prediction, sell early access, then accelerate the demo clock and watch the same committed content become public automatically.
- **Why it can win:** The before/after reveal is visually obvious and the business model is built into the primitive.
- **Why it can fail:** A server-held decryption key makes the “forced reveal” and “cannot reveal early” promises untrue.
- **Inspired by:** [Hatch](https://github.com/winsznx/usehatch).

### 8. Memory Passport — every AI answer proves what it remembered

- **One line:** Give users portable AI memory where every answer shows exactly which authorized memories were used.
- **Pain:** Persistent memory can leak health, billing, work, or identity data across agents and model providers.
- **Technology that must be indispensable:** Access policy runs before retrieval; encrypted content-addressed memory remains portable; answer receipts prove permitted sources, blocked namespaces, and artifact availability.
- **Showcase moment:** Revoke one agent's health-memory access and show it refuse while another authorized model recalls the same portable memory with a verifiable receipt.
- **Why it can win:** Privacy, interoperability, and AI trust meet in a feature everyone immediately understands.
- **Why it can fail:** A receipt created after generation proves nothing; unauthorized memory must never enter the model context.
- **Inspired by:** [Cairn](https://github.com/Enoch208/cairn) and [Cordon](https://github.com/winsznx/cordon).

### 9. Encrypted Game Engine — shared worlds with secrets nobody administers

- **One line:** Build onchain games whose hidden state can be computed on but cannot be read by players or the operator.
- **Pain:** Poker, Battleship, treasure hunts, strategy fog, and sealed moves become trivial to cheat when contract storage is public.
- **Technology that must be indispensable:** Encrypted state supports computation, wallet-specific decryption, sealed actions, and permissionless reveal without an admin holding the answer.
- **Showcase moment:** Every player's move is public, but only the acting wallet can decrypt its clue until the round opens.
- **Why it can win:** Privacy becomes playful, visual, and impossible to replace with a normal database without changing the trust model.
- **Why it can fail:** A clever cryptographic demo without a fun game loop will not retain attention.
- **Inspired by:** [Azimuth](https://github.com/Enoch208/azimuth), [Chickenz](https://github.com/winsznx/chickenz), and [DarkOdds](https://github.com/winsznx/darkodds).

### 10. Robot Release Gate — prove a physical policy is safer before deployment

- **One line:** Find how a robot fails, repair it, and produce a qualification bundle anyone can verify on a laptop.
- **Pain:** Robotics teams compare demos instead of matched trials and often cannot reproduce success claims or audit their own success metrics.
- **Technology that must be indispensable:** GPU simulation runs matched failure experiments; virgin-seed qualification prevents overfitting; tamper-evident manifests let third parties recompute every reported result.
- **Showcase moment:** Show the same failed seed before and after repair, then independently verify the statistical release decision.
- **Why it can win:** A strong physical demo plus rigorous evidence is rare and memorable.
- **Why it can fail:** Scope explodes easily; one contact-rich task and one meaningful repair are enough.
- **Inspired by:** [CRUX](https://github.com/Enoch208/Crux) and [SlipZero](https://github.com/Enoch208/slipzero).

### 11. Disaster Ledger — offline aid distribution that reconciles without losing truth

- **One line:** Record relief handouts without internet, merge field devices later, and expose conflicts instead of silently overwriting them.
- **Pain:** Disaster and rural aid teams lose connectivity precisely when duplicate claims, scarce inventory, and auditability matter most.
- **Technology that must be indispensable:** Offline-first signed events, deterministic conflict surfacing, content-addressed evidence, and independently verifiable export bundles.
- **Showcase moment:** Disconnect two devices, issue overlapping aid, reconnect them, and show a transparent conflict-resolution audit.
- **Why it can win:** Real human impact and a powerful live failure/recovery demo.
- **Why it can fail:** Adding blockchain without improving offline reconciliation would only make the product slower.
- **Inspired by:** [Erilog](https://github.com/Enoch208/Erilog) and [LocalRx](https://github.com/winsznx/localrx).

### 12. Private Edge Sentinel — anomaly detection that never uploads raw footage

- **One line:** Give a camera a private visual memory that detects unusual events entirely on-device.
- **Pain:** Clinics, factories, homes, and critical sites need visual monitoring without continuously exporting sensitive video to a cloud model.
- **Technology that must be indispensable:** Local embeddings, encrypted vector memory, adaptive anomaly scoring, and signed incident summaries prove alerts without sharing the raw stream.
- **Showcase moment:** Teach the device a normal scene, introduce an anomaly, and verify the alert while the network is physically disconnected.
- **Why it can win:** The privacy claim is concrete and demonstrable by pulling the cable.
- **Why it can fail:** Generic object detection is not enough; the product needs temporal memory and a target vertical with meaningful anomalies.
- **Inspired by:** [Sentinel](https://github.com/Enoch208/sentinel).

### 13. Evidence Reel — an investigator that cannot make uncited claims

- **One line:** Ask a video archive a question and receive a timeline whose every sentence opens the exact supporting footage.
- **Pain:** Long-form video investigations require hours of manual search, while AI summaries hide source omissions and contradictions.
- **Technology that must be indispensable:** Typed claim extraction, chronological comparison, evidence gates, counter-evidence retrieval, timestamp-locked citations, and exportable evidence packets.
- **Showcase moment:** Ask why an event happened, challenge the answer, and watch unused footage qualify or overturn the first conclusion.
- **Why it can win:** The citations are visible, playable, and much stronger than a conventional RAG chat.
- **Why it can fail:** A transcript search with decorative citations is not an investigation engine.
- **Inspired by:** [Strata](https://github.com/Enoch208/Strata).

### 14. BuildGraph for Generative Media — regenerate only what changed

- **One line:** Turn an AI media campaign into a dependency graph so one copy edit rebuilds four assets instead of eighteen.
- **Pain:** Generative production pipelines waste money, time, and human approvals by recreating every asset after small changes.
- **Technology that must be indispensable:** Deterministic recipes and content fingerprints prove safe reuse; idempotency prevents double charges; recovery policies switch providers; release manifests re-hash every shipped byte.
- **Showcase moment:** Change one legal sentence and display exactly which assets rebuild, which remain valid, the calls avoided, and the release proof.
- **Why it can win:** The savings are measurable in money and minutes, and the graph makes them visually obvious.
- **Why it can fail:** Without real provider calls and measured reuse, it looks like a task graph mockup.
- **Inspired by:** [TAKEGRAPH](https://github.com/Enoch208/takegraph).

### 15. Savings-to-Credit Agent — make tiny habits financially portable

- **One line:** Turn daily micro-savings into a portable credit history without letting the savings agent custody the principal.
- **Pain:** Informal savers build years of financial discipline but no record a lender can use.
- **Technology that must be indispensable:** A guarded vault limits collection amount and frequency; onchain reputation records contributions and repayments; savings back small advances.
- **Showcase moment:** Save a small amount, see the portable score improve, then unlock and repay a savings-backed advance.
- **Why it can win:** It solves a large emerging-market problem with a simple human story and real financial rails.
- **Why it can fail:** Sybil resistance, missed-payment handling, and responsible lending must be honest; do not present a toy score as universal creditworthiness.
- **Inspired by:** [Vestra](https://github.com/Enoch208/Vestra).

### 16. Confidential Credit Desk — negotiate loans without publishing strategy

- **One line:** Let lenders submit private rates and borrowers request private terms while only the accepted deal becomes executable.
- **Pain:** Public fixed-income quotes expose balance sheets, urgency, risk appetite, and negotiation strategy.
- **Technology that must be indispensable:** Confidential compute matches terms; commitments bind offers; one authorized quote settles through existing lending markets without revealing the losing book.
- **Showcase moment:** Several lenders compete privately, a borrower receives the best executable quote, and losing terms never appear publicly.
- **Why it can win:** Strong institutional pain and sponsor technology that is clearly load-bearing.
- **Why it can fail:** Confidential matching is meaningless if the operator, logs, or frontend can read every offer.
- **Inspired by:** [Kyrve](https://github.com/winsznx/kyrve), [Vellum](https://github.com/winsznx/vellum), and [BlindMarkets](https://github.com/winsznx/blindmarkets).

### 17. Agent Warranty — rent an agent whose track record its sealed model signs

- **One line:** Rent a trading or operations agent with a tamper-evident performance history and rules that travel with it.
- **Pain:** Agent marketplaces sell prompts and screenshots, not independently verifiable capability, risk limits, or execution history.
- **Technology that must be indispensable:** A sealed runtime signs decisions; identity binds releases; outcome receipts build portable reputation; escrow and warranty bonds compensate rule violations.
- **Showcase moment:** Compare two rentable agents, verify one historic decision against its sealed runtime, then watch a policy violation trigger the warranty.
- **Why it can win:** It turns agent reputation from a rating into a verifiable product guarantee.
- **Why it can fail:** Historical returns never prove future performance, and a TEE signature does not prove a strategy is good.
- **Inspired by:** [Fief](https://github.com/winsznx/fief), [Pact](https://github.com/winsznx/pact), and [Warrant](https://github.com/winsznx/warrant).

### 18. Dependency Blast-Radius Navigator — show what a compromised package actually reached

- **One line:** Name a vulnerable dependency and instantly reveal every service, data path, and customer capability it could have touched.
- **Pain:** Security teams know a package is compromised but cannot quickly determine which production systems and data are truly exposed.
- **Technology that must be indispensable:** A live lineage graph joins packages, builds, deployments, services, datasets, and owners; every path is returned as evidence rather than a risk score alone.
- **Showcase moment:** Mark one npm package compromised and watch the system trace the exact path to affected services while excluding unaffected ones.
- **Why it can win:** It answers the first executive question during a supply-chain incident: “What is actually at risk?”
- **Why it can fail:** A manually seeded graph is not credible; integrate a real repository, build system, and deployment inventory.
- **Inspired by:** [Lazaret](https://github.com/winsznx/lazaret).

### 19. Live Warrant for ML — no model serves without current data authorization

- **One line:** Stop a production model the moment its training data, consent, jurisdiction, or policy warrant becomes invalid.
- **Pain:** ML deployments remain live after source data is revoked, moved, expired, or discovered to violate policy.
- **Technology that must be indispensable:** Data lineage continuously evaluates authorization policy and issues short-lived serving warrants checked at the inference gateway.
- **Showcase moment:** Revoke a source dataset and watch only the dependent model deployment lose its warrant while unrelated models stay live.
- **Why it can win:** It joins AI governance to an enforceable production control rather than a dashboard.
- **Why it can fail:** If serving continues when the policy service is unavailable, the warrant is decorative.
- **Inspired by:** [Licet](https://github.com/winsznx/licet).

### 20. Private Rules, Public Money — prove a payment obeyed a secret policy

- **One line:** Let money move only when a zero-knowledge proof shows it obeys private spending rules the chain never learns.
- **Pain:** Families, funds, businesses, and regulated users need enforceable financial controls without publishing salaries, beneficiaries, or internal risk rules.
- **Technology that must be indispensable:** A proof binds hidden policy, exact action, nonce, and expiry; a smart account verifies it before public settlement.
- **Showcase moment:** Execute an allowed payment, reject a subtly noncompliant one, and show that observers learn neither the hidden limit nor the private eligibility facts.
- **Why it can win:** It is a clean “could not exist without ZK” product with broad applicability.
- **Why it can fail:** Vague privacy claims are fatal; document every public input, leaked field, trusted setup, and replay boundary.
- **Inspired by:** [Nulth](https://github.com/winsznx/nulth), [Nullis](https://github.com/Enoch208/nullis), and [Writ](https://github.com/winsznx/writ).

### 21. Settlement SRE — autonomous recovery for programmable payments

- **One line:** Monitor financial obligations, diagnose failed settlement, cure them automatically, and prove the final state.
- **Pain:** Stablecoin payroll, invoices, subscriptions, and cross-chain delivery fail for mundane reasons that still trigger costly manual reconciliation.
- **Technology that must be indispensable:** Obligations are explicit state machines; bonded providers attempt settlement; bounded recovery agents apply approved cures; independent receipts prove completion or breach.
- **Showcase moment:** Inject a failed payment route and watch the system detect, reroute, cure, and produce a verifiable closure receipt.
- **Why it can win:** It treats programmable money as production infrastructure with reliability guarantees.
- **Why it can fail:** An unconstrained “autonomous cure agent” can create larger losses; actions need hard policy bounds.
- **Inspired by:** [Syrty](https://github.com/winsznx/syrty), [Resurv](https://github.com/winsznx/resurv), and [KeeperHub FlightCheck](https://github.com/winsznx/keeperhub-flightcheck).

### 22. No-Loss Private Prize Pool — public winner, hidden balances

- **One line:** Save privately, keep your principal, and let encrypted time-weighted balances select a verifiable prize winner.
- **Pain:** Prize savings can motivate saving, but public deposits reveal wealth and deterministic public balances invite targeting and gaming.
- **Technology that must be indispensable:** Homomorphic computation keeps balances encrypted while calculating weights and winner selection; yield funds the prize; users retain principal.
- **Showcase moment:** Run a draw whose math verifies while no participant balance is revealed.
- **Why it can win:** “Lottery without losing your savings or exposing your balance” is instantly understandable.
- **Why it can fail:** Exactness, randomness, withdrawal liquidity, and jurisdictional treatment need careful design.
- **Inspired by:** [Serein](https://github.com/winsznx/serein).

### 23. Mutual-Aid Covenant for Protocols — collective cyber insurance without a custodian

- **One line:** Protocols sharing a dependency pre-commit resources and automatically coordinate when a private incident is certified.
- **Pain:** Projects depending on the same bridge, oracle, sequencer, or package respond to incidents separately and too late.
- **Technology that must be indispensable:** Members ratify a bounded covenant, incidents are privately assessed, adapters execute pre-approved safeguards, and contributions or payouts are auditable.
- **Showcase moment:** Simulate an oracle compromise and watch member protocols pause exposure, route liquidity, and fund response from a shared covenant.
- **Why it can win:** It turns ecosystem interdependence into visible coordination rather than another insurance pool.
- **Why it can fail:** Certification and adapter authority are dangerous; the covenant must make false positives recoverable and powers narrowly scoped.
- **Inspired by:** [Vinct](https://github.com/winsznx/vinct) and [Cordon](https://github.com/winsznx/cordon).

### 24. Obligation Net — settle relationships, not every tiny payment

- **One line:** Keep a shared ledger of who owes whom, continuously net it, and settle only the remaining balance.
- **Pain:** Groups, marketplaces, games, and agent swarms create hundreds of tiny reciprocal payments that are expensive and interruptive to settle individually.
- **Technology that must be indispensable:** Signed obligations update a netting graph; limits prevent uncontrolled credit; periodic settlement clears only net exposure.
- **Showcase moment:** Simulate 100 reciprocal obligations across ten participants and settle them with a handful of transfers.
- **Why it can win:** The before/after transaction count and cost reduction are immediately measurable.
- **Why it can fail:** Netting creates credit exposure; caps, expiry, dispute proofs, and insolvency handling must be first-class.
- **Inspired by:** [Tally](https://github.com/winsznx/tally) and [FlowGuard](https://github.com/winsznx/flow-guard).

### 25. Healthcare Treatment Preflight — compare plans before touching a patient

- **One line:** Let a clinician branch treatment plans on a patient-specific digital twin and require evidence before approving one.
- **Pain:** Clinical AI often produces recommendations without showing alternative outcomes, source evidence, or the limits of its simulation.
- **Technology that must be indispensable:** Clinician-controlled branching, patient-state provenance, supported simulations, evidence-bound model output, and an explicit human approval gate.
- **Showcase moment:** Compare two interventions, show how assumptions change predicted outcomes, and refuse a plan whose evidence coverage falls below policy.
- **Why it can win:** High-impact, visually demonstrable, and far more responsible than an AI diagnosis chatbot.
- **Why it can fail:** Never imply clinical validity from a hackathon simulation; use synthetic cases and make the decision-support boundary explicit.
- **Inspired by:** [Silico](https://github.com/Enoch208/Silico) and [Overture](https://github.com/Enoch208/Overture-web).

### 26. Agent Due-Diligence Firewall — inspect deliverables before they enter another agent

- **One line:** Hire specialist agents, quarantine their output, and return a verifiable go/caution/no-go verdict before downstream use.
- **Pain:** Multi-agent systems blindly pass untrusted text and files between agents, allowing prompt injection, poisoned artifacts, and fabricated evidence to propagate.
- **Technology that must be indispensable:** Delivery hashes, sandboxed inspection, provenance checks, policy gates, and signed verdict receipts bind the review to the exact artifact.
- **Showcase moment:** One specialist returns a clean report and another hides an injection; only the clean artifact reaches the buyer agent.
- **Why it can win:** It solves the security problem created by agent marketplaces themselves.
- **Why it can fail:** A language-model-only reviewer can be attacked by the same content; deterministic scanners and isolation must surround it.
- **Inspired by:** [Ward](https://github.com/winsznx/ward) and [BountyMesh](https://github.com/winsznx/bountymesh).

### 27. Private Prediction Exchange — public market, encrypted conviction

- **One line:** Keep outcomes and odds public while bet sizes, trader identity, and strategy remain confidential.
- **Pain:** Transparent prediction positions reveal conviction, wealth, hedging strategy, and information before resolution.
- **Technology that must be indispensable:** Encrypted positions update aggregate market state; eligibility and solvency are proven; selective disclosure supports disputes or compliance.
- **Showcase moment:** Place several hidden bets, watch public odds move, then reveal only the winning settlement after resolution.
- **Why it can win:** It preserves the useful public signal while protecting the participants who create it.
- **Why it can fail:** If timing or exact odds movements trivially deanonymize a trader, encrypted amounts alone do not provide meaningful privacy.
- **Inspired by:** [DarkOdds](https://github.com/winsznx/darkodds), [Regista11](https://github.com/winsznx/regista11), and [TheEleven](https://github.com/winsznx/theeleven).

### 28. Verified Release Page — make every hackathon claim self-checking

- **One line:** Turn a project's README claims into a live page that independently re-verifies deployments, transactions, tests, hashes, and demo state.
- **Pain:** Judges cannot distinguish real integrations from seeded dashboards, dead contracts, copied addresses, or screenshots.
- **Technology that must be indispensable:** A machine-readable claim ledger maps each statement to a verifier; live probes reproduce evidence; failures degrade the claim visibly instead of being hidden.
- **Showcase moment:** Click “verify all” and watch the page re-read the chain, APIs, object storage, and test artifacts without requiring a wallet.
- **Why it can win:** It improves trust in every technical submission and demonstrates extreme engineering honesty.
- **Why it can fail:** It is only valuable if verification is independent and reproducible rather than a server returning `true`.
- **Inspired by:** the evidence discipline across [Metrx](https://github.com/winsznx/metrx), [CRUX](https://github.com/Enoch208/Crux), [Azimuth](https://github.com/Enoch208/azimuth), and [TAKEGRAPH](https://github.com/Enoch208/takegraph).

## Sui Overflow 2026 winner mechanics

The official 2026 field contained 747 projects from 58 countries and named 26 winners. These are the most reusable product mechanics from that cohort, not copies of the winning products.

- **Intent-to-transaction compilation:** turn a sentence into one previewable, atomic transaction rather than making users assemble calls manually. Inspired by Sprout.
- **Human protocols for machines:** translate websites and APIs into structured instructions agents can understand and pay for. Inspired by Rill.
- **Hardware as a verifiable service:** discover a device, pay it, execute a physical job, and receive evidence of completion. Inspired by Aether.
- **Any-token merchant acceptance:** let the buyer pay with what they hold while the merchant receives the stablecoin they chose. Inspired by Quay.
- **Invisible crypto account:** Google login, names instead of addresses, sponsored gas, and normal-looking dollar payments. Inspired by Talise.
- **Tap-to-pay with productive float:** NFC checkout plus automatic yield on money that is not currently needed for settlement. Inspired by Brisk.
- **Programmable invoice lifecycle:** encode the steps from invoice creation through local payout and audit evidence. Inspired by Splash.
- **User-owned cloud storage:** an S3-compatible layer where users own the data and can revoke an application's access. Inspired by Kraterion.
- **Verifiable one-call deployment:** deploy a site to decentralized storage and prove every served byte matches the release. Inspired by Deploy by Suize.
- **Markets people can feel:** turn an order book or volatility surface into an explorable visual object instead of another trading table. Inspired by PIPS and Skew.
- **Prediction as a social game:** package markets as quick head-to-head choices rather than a professional trading terminal. Inspired by Flicky.
- **Autonomous risk reduction:** automatically reduce leverage before liquidation rather than merely sending a warning. Inspired by Guardian.
- **Merchant-locked cards:** issue virtual cards backed by onchain funds that can only be spent with an approved merchant. Inspired by PayPerCard.
- **Recurring payments without repeated signing:** install a bounded payment permission once, then execute only within its limits. Inspired by Paystreamer.
- **Community-owned physical infrastructure:** coordinate satellite ground stations and other scarce hardware as an open network. Inspired by Azimuth.

Source: [Sui Overflow 2026 winners](https://www.sui.io/blog/sui-overflow-2026-winners).

## Additional portfolio-derived product blueprints

### 29. Citation Rail — every reused fact pays its original publisher

**One line:** A pay-per-read gateway that automatically shares revenue with every source cited in the purchased answer.

- **Pain:** AI products consume reporting while the publisher who created the fact receives neither attribution nor money.
- **Why blockchain is indispensable:** a programmable payment can atomically split one purchase across a verifiable citation graph.
- **Showcase:** buy one research answer, inspect its sources, and watch micropayments reach the original publishers.
- **Why it could win:** it joins x402-style machine payments to a visible, urgent content-economics problem.
- **Main risk:** determining provenance is harder than moving the money; reward only sources the seller can prove were used.
- **Source mechanics:** mrnetwork0001/Inktoll.

### 30. VeilHire — private salary matching with an interview bounty

**One line:** Candidates and employers discover salary compatibility without revealing either side's number, then escrow a bounty for a serious interview.

- **Pain:** candidates anchor low, employers harvest salary data, and both sides waste time on incompatible ranges.
- **Why privacy tech is indispensable:** encrypted comparison reveals only whether the ranges overlap; public software cannot honestly promise that.
- **Showcase:** enter two hidden ranges, reveal a match/no-match result, and release the interview bounty after attendance.
- **Why it could win:** the privacy benefit is instantly understandable and tied to a real economic action.
- **Main risk:** confidential-compute or FHE integration can overwhelm a hackathon; prove one comparison and one escrow path.
- **Source mechanics:** mrnetwork0001/VeilPay and SeventhOdyssey71/meeting-escrow.

### 31. Salary Stream Note — income that can be split, insured, or financed

**One line:** Turn a verified salary stream into a programmable asset without selling the worker's identity.

- **Pain:** payroll is periodic and rigid even though workers have continuous expenses and predictable future income.
- **Why blockchain is indispensable:** a live payment stream can become a transferable claim with enforceable splits and settlement.
- **Showcase:** stream wages by the second, split tax automatically, and use a bounded portion as collateral.
- **Why it could win:** it makes streaming payments feel like infrastructure rather than a visual gimmick.
- **Main risk:** transferable wage claims have legal and consumer-protection implications; prototype with opt-in test funds.
- **Source mechanics:** mrnetwork0001/Sluice, Rheon, and Fluenci.

### 32. Vendor Change Firewall — confidential approval before treasury payout

**One line:** A treasury refuses a changed vendor wallet until hidden reviewers approve the evidence behind the change.

- **Pain:** invoice fraud often starts with a convincing request to replace a supplier's payout address.
- **Why privacy tech is indispensable:** reviewers can attest that checks passed without exposing internal procurement evidence or identities.
- **Showcase:** submit a wallet-change request, collect private approvals, and show the multisig payment remain blocked until policy passes.
- **Why it could win:** it applies privacy to stopping theft, not merely hiding transfers.
- **Main risk:** the approval ceremony must be simpler than the fraud it prevents.
- **Source mechanics:** Mystiquemide/Qeltrun.

### 33. Parametric Warranty Reserve — claims backed before the product ships

**One line:** Every product sale funds a visible reserve that pays automatically when objective warranty evidence is met.

- **Pain:** warranties are promises from companies that may delay, dispute, or lack money when claims arrive.
- **Why blockchain is indispensable:** reserves, coverage, trigger evidence, and payout rules remain independently verifiable.
- **Showcase:** sell a covered device, trigger a simulated failure oracle, and pay the buyer from its dedicated reserve.
- **Why it could win:** “a warranty you can see is funded” is a sharp, consumer-friendly story.
- **Main risk:** oracles determine fairness; start with a narrow machine-verifiable trigger.
- **Source mechanics:** Mystiquemide/Resvyn, Arca Protocol, and Nyalthe.

### 34. EffectProof — prove what a transaction actually accomplished

**One line:** A transaction verifier that checks balance changes and recipient outcomes instead of trusting a success badge.

- **Pain:** a successful transaction can still deliver the wrong token amount, send to the wrong party, or execute a deceptive token implementation.
- **Why blockchain is indispensable:** pre-state, post-state, calls, and events provide deterministic evidence of the real effect.
- **Showcase:** feed it a normal payment and an adversarial token transfer; receive a plain-language pass/fail certificate.
- **Why it could win:** it turns confusing chain data into a security primitive every wallet and agent needs.
- **Main risk:** token semantics vary; support a small audited rule set and label unknown behavior honestly.
- **Source mechanics:** Mystiquemide/Veyctum and Dervyx.

### 35. MergePay — merged code is the payment authorization

**One line:** A GitHub action pays contributors only after the agreed pull request merges, with replay-safe receipts.

- **Pain:** open-source bounties and contractor payments are manually reconciled and easy to dispute.
- **Why blockchain is indispensable:** a signed merge event can authorize transparent, programmable settlement without a payout operator.
- **Showcase:** merge a PR, watch the action validate the repository and commitment, then issue a public payment receipt.
- **Why it could win:** developers understand it immediately and judges can reproduce the full flow during the demo.
- **Main risk:** GitHub credentials and webhooks are trusted inputs; bind signatures to repository, commit, amount, and nonce.
- **Source mechanics:** Mystiquemide/Skirwith.

### 36. Collision Lab — make race conditions reproducible evidence

**One line:** Two real browser sessions intentionally collide on shared state, then produce a proof, repair suggestion, and exact rerun.

- **Pain:** concurrency bugs disappear under debugging and return in production because teams cannot reproduce the timing.
- **Why the product needs special infrastructure:** synchronized actors, immutable traces, and deterministic replay are the core value—not a dashboard around ordinary tests.
- **Showcase:** reproduce a double-booking bug, apply the proposed guard, and rerun the identical collision successfully.
- **Why it could win:** the failure is dramatic, visual, and resolves inside a three-minute demo.
- **Main risk:** avoid claiming formal verification; it is a high-quality evidence and regression system.
- **Source mechanics:** Mystiquemide/Collision-Canary.

### 37. Device SLA Market — hardware earns only while it proves service

**One line:** Physical devices publish signed heartbeats and receive payment only for verifiable uptime and completed jobs.

- **Pain:** buyers of decentralized infrastructure cannot distinguish real capacity from registered but unavailable hardware.
- **Why blockchain is indispensable:** capability claims, service evidence, escrow, slashing, and payment share one auditable state machine.
- **Showcase:** take a device offline, stop its earnings, bring it back, execute a paid job, and verify the result.
- **Why it could win:** it connects tokens to observable physical work rather than speculative rewards.
- **Main risk:** a heartbeat alone does not prove useful work; pair it with challenge-response or output attestations.
- **Source mechanics:** Mystiquemide/Zoetra and Sui Overflow's Aether/Azimuth.

### 38. Trade Corridor OS — player-owned infrastructure inside games

**One line:** Players build trade routes, toll gates, depots, and markets that other players actually use and pay for.

- **Pain:** game economies call assets “owned” while the useful infrastructure and rules remain entirely publisher-controlled.
- **Why blockchain is indispensable:** durable ownership, shared state, composable market rules, and revenue rights can survive any one client.
- **Showcase:** create a route, stock a depot, move an item through a toll, and settle fees to the builders.
- **Why it could win:** it demonstrates ownership through live gameplay rather than NFT inventory screens.
- **Main risk:** without a compelling game loop it becomes infrastructure nobody wants; design the route conflict first.
- **Source mechanics:** SeventhOdyssey71/eve-hackathon (FEN).

### 39. Sealed Model Bazaar — buy model access without downloading the model

**One line:** Owners sell metered access to encrypted models and datasets while buyers receive attested outputs, not the secret asset.

- **Pain:** creators cannot monetize valuable models or datasets without handing buyers a copy that can leak.
- **Why privacy tech is indispensable:** encrypted storage plus attested execution separates usable access from possession.
- **Showcase:** purchase one inference, execute it in an attested environment, and verify payment and output provenance.
- **Why it could win:** it solves the core contradiction in AI marketplaces: try the intelligence without giving it away.
- **Main risk:** the trust boundary of the execution environment must be explicit and independently checkable.
- **Source mechanics:** SeventhOdyssey71/Satya and mrnetwork0001/Nodea.

### 40. Intent Auction — solvers compete to execute what the user meant

**One line:** Users state an outcome, bonded solvers bid on execution, and one atomic receipt proves delivery.

- **Pain:** users must understand routes, bridges, slippage, gas, and failure recovery just to express a simple financial goal.
- **Why blockchain is indispensable:** solver bonds, bid selection, atomic execution, and receipts need shared enforceable settlement.
- **Showcase:** request a target outcome, compare solver bids, execute the winner, and slash a deliberately invalid bid.
- **Why it could win:** it showcases programmability and market design while making crypto visibly simpler.
- **Main risk:** a chatbot that merely generates calls is not enough; the competitive solver and settlement loop must work.
- **Source mechanics:** SeventhOdyssey71/sui-intents, Iwetan77/Vektor, and Sui Overflow's Sprout.

### 41. Safe Route Compiler — swaps that explain partial and adversarial outcomes

**One line:** A headless router simulates token behavior, builds the safest atomic route, and reports partial execution honestly.

- **Pain:** routers optimize headline price while integrations, token behavior, and non-atomic steps create hidden failure modes.
- **Why blockchain is indispensable:** route construction must reason about exact onchain state, transaction effects, and settlement boundaries.
- **Showcase:** compare a safe token with a hostile one, preview the state changes, and reject the dangerous route before signing.
- **Why it could win:** it improves an everyday DeFi action with security judges can see.
- **Main risk:** do not list integrations that are not active; label supported liquidity sources and fallback behavior precisely.
- **Source mechanics:** Iwetan77/Routex and zip-swap.

### 42. Corridor State Machine — cross-border payments that never hide limbo

**One line:** A payment system that tells sender and recipient exactly which leg completed, who owns the funds, and how recovery works.

- **Pain:** cross-border products present a single spinner over several non-atomic providers, making failures opaque and support-heavy.
- **Why blockchain is indispensable:** durable receipts and programmable escrow can make every handoff independently auditable.
- **Showcase:** interrupt a payment between conversion and payout, show the orphaned state, then recover without double-paying.
- **Why it could win:** resilience is more credible than another “instant global payment” claim.
- **Main risk:** real fiat rails need partners; demo the state machine with stablecoin corridors and mocked external acknowledgements.
- **Source mechanics:** Iwetan77/Conduit.

### 43. StreamLane — pub/sub where one slow consumer cannot freeze everyone

**One line:** A QUIC-native event broker that gives every subscriber an isolated stream and proves the noisy neighbor cannot block the room.

- **Pain:** one stalled consumer can create head-of-line blocking and tail-latency spikes in real-time systems.
- **Why the technology is indispensable:** QUIC stream isolation is the actual product mechanism; this cannot be reproduced with a UI over a conventional queue.
- **Showcase:** throttle one subscriber while the others continue at full speed, with an on-screen latency comparison.
- **Why it could win:** the benchmark is visual, falsifiable, and relevant to games, trading, agents, and collaboration.
- **Main risk:** infrastructure projects need reproducible measurements and a simple hosted demo to avoid becoming a README-only entry.
- **Source mechanics:** Iwetan77/Flume.

### 44. ComfortRoute — navigation optimized for the body, not distance

**One line:** A walking route planner chooses shade, temperature, air quality, accessibility, and safety—not merely the shortest path.

- **Pain:** standard navigation treats two equally long streets as equivalent even when one is physically punishing or unsafe.
- **Why the product is defensible:** it combines hyperlocal sensors, forecasts, street geometry, and personal constraints into a route objective maps usually ignore.
- **Showcase:** compare the shortest route with the coolest or safest route and visualize the exposure avoided.
- **Why it could win:** the difference is immediately visible and applies to climate adaptation, disability, and public health.
- **Main risk:** sparse sensor data can create false precision; display confidence and degrade gracefully to public datasets.
- **Source mechanics:** mrnetwork0001/Cryonav.

### 45. Private Cart Settlement — one checkout, many merchants, selective failure

**One line:** A multi-merchant cart settles privately while quarantining or refunding only the seller that fails policy.

- **Pain:** marketplace checkouts either expose the full buyer graph or make one bad merchant fail the entire purchase.
- **Why privacy and programmability are indispensable:** shielded payment hides commercial relationships while conditional settlement isolates non-compliant legs.
- **Showcase:** purchase from three merchants, fail one compliance condition, and privately settle the other two.
- **Why it could win:** it pushes private payments beyond transfers into a realistic commerce workflow.
- **Main risk:** atomicity and selective rollback conflict; define the commitment and refund boundaries before coding.
- **Source mechanics:** mrnetwork0001/Splitrail.

### 46. Data Lineage Gate — block a release when its blast radius is unknown

**One line:** A pull request cannot merge until the system proves which dashboards, models, and customers its data change will affect.

- **Pain:** a tiny schema or metric change silently corrupts downstream decisions across an organization.
- **Why the product needs a graph:** lineage and impact are relational facts that ordinary test coverage does not capture.
- **Showcase:** change one field, display the downstream blast radius, block the merge, then approve a complete migration plan.
- **Why it could win:** it turns invisible operational risk into a concrete, testable release gate.
- **Main risk:** lineage graphs go stale; fail closed when evidence is missing rather than inventing certainty.
- **Source mechanics:** Mystiquemide/Threxa and mrnetwork0001/Radix.

## Portfolio lessons worth preserving

1. **Build the failure demo first.** “Allowed succeeds; forbidden fails” is more convincing than a happy-path dashboard.
2. **Make the sponsor load-bearing.** Removing the sponsor technology should destroy the core guarantee, not merely remove a payment button.
3. **Commit before judgment.** Specifications, rubrics, policies, inputs, and identities should be fixed before an AI or verifier sees the answer.
4. **Gate before exposure.** Private memory, confidential data, and untrusted artifacts must be filtered before they reach a model or downstream agent.
5. **Bind every signature narrowly.** Include action, chain, contract, nonce, expiry, inputs, and output hash so a valid receipt is useless elsewhere.
6. **Design crash recovery and idempotency.** Agents, indexers, payment providers, and testnets fail; recovery is part of the product.
7. **Publish an honesty table.** Clearly separate live, seeded, mocked, simplified, and future components.
8. **Give judges a walletless proof path.** A read-only evidence page should demonstrate the core claim in under 60 seconds.
9. **Measure the headline.** Transactions avoided, calls saved, failures caught, money protected, time reduced, or evidence coverage should be numerical.
10. **Ship a reusable primitive.** A small SDK, CLI, verifier, manifest format, policy language, or contract interface makes the project valuable after judging.

## Reusable idea patterns

When brainstorming a new hackathon product, start with one of these patterns rather than a technology buzzword:

1. **Private edge + visible outcome:** anonymous donations with a public campaign total, sealed votes with a public result, or hidden bettors with public odds.
2. **Unlinkable identities:** one private balance funds separate identities for apps, suppliers, campaigns, or agent tasks.
3. **Private coordination:** participants commit privately and reveal only when a threshold or condition is reached.
4. **Selective proof:** prove enough balance, income, membership, or prior action without exposing complete history.
5. **Security recovery:** use privacy to break an attacker's ability to follow rescued assets or identify a safe destination.
6. **Recipient onboarding:** claim links or escrow let someone receive before they have completed privacy setup.
7. **Privacy compiler:** inspect an intended action, select a reviewed route, state residual leakage, and refuse unsupported promises.
8. **Private machine commerce:** protect negotiation, supplier selection, payments, receipts, and delivery—not payment alone.
9. **Vertical privacy:** choose a domain where public financial relationships cause obvious harm: payroll, creators, OTC trading, procurement, grants, healthcare, legal work, research, or hospitality.
10. **Developer multiplier:** make privacy integration, testing, debugging, verification, or deployment dramatically easier for every other builder.

## Standard for adding future ideas

For every future hackathon project saved here, record:

- the one-line explanation;
- the painful real-world problem;
- why the sponsor technology is indispensable;
- what is genuinely private and what remains public;
- live product, repository, contract, and transaction evidence;
- the strongest reusable design pattern;
- the reason it may win;
- the reason it may fail;
- how our next idea can be meaningfully different.
