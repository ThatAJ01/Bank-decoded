# Bank Decoded — Content Spec for a Three-View Educational Website

**Scope:** EU banks using the Standardised Approach (SA) to credit risk.
**Audience:** ordinary, non-expert adults (target reading level: CEFR B1/B2, ~8th-grade).
**Status:** Draft for expert review. Numbers are illustrative; regulatory references are listed in Part 0.4 so a compliance reviewer can check each one before publication.

---

## PART 0 — SHARED FOUNDATIONS

### 0.1 Design principles (apply to all three views)

1. **One fictional customer, three lenses.** Meet **Mila** once. Every view re-uses her numbers, so users see the same person through a regulator's, a risk manager's and a lender's eyes.
2. **Define on first use.** Every technical term gets a one-line definition in the sentence where it first appears, plus a hover/tap tooltip and a glossary entry.
3. **Analogies first, numbers second, regulation third.** Order each concept: everyday picture → Mila's numbers → "the rule behind it" (collapsed by default, with article reference).
4. **Honest framing.** The bank does not hold a "score card with your name" for capital purposes. Under the SA, regulatory capital depends on *product type and risk-weight rules*, not on your personal credit score. Your personal profile matters for **approval, pricing, provisioning (IFRS 9) and monitoring**. Say this early and often; it is the most common misunderstanding.
5. **Show the trade-off, not the verdict.** Never say "banks like/dislike you". Say "this raises/lowers the bank's cost of serving you".
6. **Country caveat.** Many levers are national (LTV caps, income-multiple limits, consumer-credit rules, early-repayment fees). A country selector or a persistent "rules differ by country" banner is mandatory.

### 0.2 Meet Mila (fictional persona used in all views)

> **Mila, 34**, project coordinator, permanent contract (6 years). Net income **€2,800/month**. Lives in a home worth **€250,000**.

| Product | Details |
|---|---|
| Current account | Salary paid in. Average balance €2,500. €1,000 overdraft limit, **not used in last 12 months** |
| Instant-access savings | €12,000 |
| 12-month term deposit | €8,000, 9 months left |
| Credit card | €3,000 limit, €400 balance today, **paid in full every month** |
| Personal loan | €10,000 left, 5 years, 7% → payment ≈ **€198/month** |
| Mortgage | €175,000 left, 25 years, 3.5% fixed → payment ≈ **€876/month**; home worth €250,000 → **LTV 70%** |

**Mila in one line:** she has **€22,500 of deposits** but **€185,400 of borrowings** (175,000 + 10,000 + 400). She is a net *borrower*: the bank needs ~€163k from other sources to fund her.

Optional extra personas (for the persona switcher):
- **Jonas, 28** — first-time buyer, 90% LTV, one salary → shows how LTV and affordability change everything.
- **Aiko, 41** — freelancer, irregular income, savings above the deposit-guarantee limit → shows income verification and deposit-stability issues.

### 0.3 Disclaimer template (use site-wide footer + top of each view)

> **Educational information only — not financial, legal, tax or investment advice.**
> This website explains, in simplified form, how banks in the European Union that use the Standardised Approach may analyse customers, products and loans. It is **not** a description of any specific bank's internal models, policies or decisions, and **no bank is affiliated with or endorses this content**.
> All customers, figures, rates, ratios and outcomes shown are **fictional and illustrative**. Real outcomes depend on your bank, your country, your personal circumstances and current regulation, all of which change.
> Regulatory references (e.g. CRR, CRD, EBA guidelines, IFRS) are summarised and simplified; they are not a substitute for the official texts. Rules in your country may be stricter or different.
> Nothing here is a recommendation to buy, sell, borrow or save. For decisions about your finances, consult a qualified, independent adviser or your national consumer or financial authority.
> Last reviewed: **[DD/MM/YYYY]**. Regulation reviewed as of: **[DD/MM/YYYY]**. We do not collect or store the numbers you enter into the calculators on this site. *(Delete the last sentence if that is not true.)*

### 0.4 Regulatory map (one "Sources & rules" page; link from every view)

| Topic | Source (verify article numbers before launch) |
|---|---|
| Capital, RWA, SA risk weights, LCR/NSFR, large exposures, leverage ratio | **CRR3** — Regulation (EU) 2024/1623 amending CRR (EU) 575/2013. Applies since **1 Jan 2025** |
| Governance, buffers, Pillar 2, ESG risk, supervision, third-country branches | **CRD VI** — Directive (EU) 2024/1619. Member-state transposition by 10 Jan 2026; most rules apply from **11 Jan 2026**. *It does not change retail risk weights; those are in CRR3.* |
| LCR detail (run-off rates) | Commission Delegated Regulation (EU) 2015/61 |
| Deposit guarantee | Directive 2014/49/EU — **€100,000 per depositor per bank** |
| Consumer loans | **CCD2** — Directive (EU) 2023/2225; replaces Directive 2008/48/EC; applies from **20 Nov 2026** (national laws vary) |
| Mortgages | **MCD** — Directive 2014/17/EU |
| Loan origination, affordability | **EBA Guidelines on loan origination and monitoring** (EBA/GL/2020/06); EBA Guidelines on creditworthiness assessment (EBA/GL/2015/11); EBA Guidelines on arrears and foreclosure (EBA/GL/2015/12) |
| Definition of default | CRR Art. 178; EBA Guidelines on the application of the definition of default (EBA/GL/2016/07) |
| Interest-rate risk on deposits and loans | EBA Guidelines on IRRBB (EBA/GL/2022/14) |
| AML/KYC | AML Directives as transposed nationally; **AML Regulation (EU) 2024/1624** applies from **10 July 2027**; EBA ML/TF risk-factor Guidelines (EBA/GL/2021/02); AMLA (Regulation (EU) 2024/1620) |
| Accounting | **IFRS 9** (expected credit losses), as endorsed in the EU |

**Reviewer checklist (things I could not confirm from primary text):**
1. CRR3 Art. 125 wording for the part of a residential loan above 55% of property value (I use the counterparty risk weight, 75% for a retail individual; web sources support the 55%/20% split and "counterparty weight on the rest" but I did not read the Official Journal text).
2. The NSFR "risk weight ≤ 35%" test for the lower 65% required-funding factor and whether CRR3 changed its reference.
3. LCR run-off rates and the "stable deposit" conditions (Delegated Reg. 2015/61, Arts. 24–25).
4. CCD2 national transposition status in each country you target.
5. Current CCyB, O-SII, P2R values if you quote a real bank.

---
---

# VIEW 1 — REGULATORY VIEW
### *"How regulators' numbers see you"*

## 1(a) Plain-language summary

Every product you hold changes some numbers the bank must report to regulators. Think of the bank as a **water system**:

- Your **deposits** are water coming *in*. They fund the bank, but regulators ask: *how fast could it leak out in a crisis?* (**liquidity**)
- Your **loans** are water going *out* into pipes that might burst. Regulators ask: *how risky are those pipes, and how much of the bank's own money (a "safety tank") must sit behind them?* (**risk-weighted assets and capital**)

Three families of numbers result:

1. **Liquidity** — can the bank pay depositors if many want money back? (LCR, NSFR)
2. **Risk-weighted assets (RWA)** — each loan is counted at a "risk-adjusted size". A safer loan counts for less.
3. **Capital ratios** — the bank's own money divided by RWA must stay above legal minimums.

> **Key honesty box:** Under the Standardised Approach, these numbers are driven by *what product you have* (mortgage? card? deposit?) and a few simple facts (loan-to-value, whether you pay on time) — **not** by a personal credit score. Two people with the same type of loan get the same regulatory treatment.

## 1(b) Key concepts glossary (View 1)

| Term | Plain-language definition |
|---|---|
| **Standardised Approach (SA)** | The "ready-made rulebook" for measuring credit risk. Regulators fix the risk weights; the bank does not use its own statistical models to set them. |
| **Liquidity** | Having cash, or things that turn into cash quickly, when needed. |
| **HQLA** | *High-quality liquid assets*: e.g. cash at the central bank, government bonds. The bank's emergency cash cushion. |
| **LCR (Liquidity Coverage Ratio)** | HQLA ÷ cash that could leave in a **30-day stress**. Must be **at least 100%**. Analogy: *a bank's 30-day emergency fund.* |
| **Run-off rate** | The % of a deposit regulators assume could leave in the 30-day stress. 5% = "very sticky"; higher = "flightier". |
| **Stable deposit** | Insured by a deposit guarantee scheme **and** held by someone with an established relationship or in an account where their salary arrives. Assumed run-off: **5%**. |
| **Less-stable deposit** | Everything else retail (e.g. not insured, or an online-only rate-chaser). Assumed run-off: **10% or more**. |
| **Deposit guarantee scheme** | State-backed protection of up to **€100,000 per person per bank** if a bank fails. |
| **NSFR (Net Stable Funding Ratio)** | A **one-year** test: is long-term lending (mortgages) funded by long-term money (capital, long-dated debt, sticky deposits)? Must be **at least 100%**. Analogy: *don't pay a 25-year mortgage with a 1-month credit card.* |
| **ASF / RSF** | *Available* and *Required* Stable Funding: the supply and demand sides of the NSFR. Each product gets a % factor (e.g. stable deposit 95% ASF; mortgage ~65% RSF). |
| **Risk weight (RW)** | A percentage that scales a loan to reflect its riskiness. **€100 loan × 35% RW = €35 of RWA.** Analogy: *a crash-test rating that shrinks or grows the loan on paper.* |
| **RWA (Risk-weighted assets)** | Sum of all loans × risk weights. The "denominator" of capital ratios. |
| **LTV (Loan-to-value)** | Loan ÷ property value. €175k loan on €250k home = **70%**. |
| **Regulatory retail** | Small loans to individuals, spread over many borrowers → **75% RW** (45% for "transactors"). |
| **Transactor** | A card or overdraft user who **repays in full each cycle** (or hasn't drawn the overdraft for 12 months) → lower RW (**45%**). A revolver (carries a balance) stays at 75%. |
| **CCF (Credit conversion factor)** | How much of an *unused* limit counts as if drawn. Cancellable credit-card/overdraft limits: **10%**. |
| **CET1 capital** | Common Equity Tier 1: the best-quality loss-absorbing money (shareholders' equity + retained profits). |
| **Tier 1 / Total capital** | CET1 + extra loss-absorbing instruments (AT1) = Tier 1; + subordinated debt (Tier 2) = Total capital. |
| **Capital ratio** | Capital ÷ RWA. |
| **CRR / CRD** | EU **Regulation** (directly applicable rules; "CRR3" = 3rd version, applies since 2025) / EU **Directive** (national laws: governance, buffers, supervision; "CRD VI"). |
| **Pillar 2 / buffers** | Extra, bank-specific capital requirements and cushions on top of the minimum. |
| **Leverage ratio** | Tier 1 ÷ *total* exposure with **no** risk weighting; minimum **3%**. A safety net against models/weights being too kind. |
| **Output floor** | CRR3 rule capping how low banks using *internal models* can go vs. SA numbers (phased to 72.5% by 2030). SA banks already use SA, so it mostly affects model users — but it is why SA weights act as the system's reference point. |

## 1(c) Worked example — Mila through the regulatory lens

### Step 1: Liquidity (LCR) — what leaves in a 30-day stress?

| Item | Balance | Regulator's assumption | Assumed outflow |
|---|---|---|---|
| Current account (salary paid in, insured) | €2,500 | Stable, 5% | €125 |
| Savings (insured; she's an established customer with a mortgage) | €12,000 | Stable, 5% | €600 |
| 12-month term deposit (can't be withdrawn within 30 days, or only with a heavy penalty) | €8,000 | 0% in the 30-day window | €0 |
| Unused card limit | €2,600 | Retail undrawn facility, 5% | €130 |
| Unused overdraft | €1,000 | Retail undrawn facility, 5% | €50 |
| **Total** | | | **≈ €905** |

**Contrast:** if the bank judged her current and savings accounts "less stable" (10%), deposit outflow would be ~€1,450 (+ €180 undrawn) = **€1,630** — about 80% more. The bank must hold more emergency cash against less-stable money, which makes such money *more expensive* for the bank.

*Caveats to show on the page:* (1) LCR is computed for the **whole bank**, not per customer; this is a "slice" illustration. (2) Mila's loan repayments are inflows (counted at 50% when performing, with an overall cap), which partly offset outflows — not shown to keep it simple.

### Step 2: Stable funding (NSFR) — is long-term lending funded by long-term money?

| Supply (ASF) | Balance | Factor | Counts as |
|---|---|---|---|
| Current account (stable) | €2,500 | 95% | €2,375 |
| Savings (stable) | €12,000 | 95% | €11,400 |
| Term deposit (<1 year left) | €8,000 | 95% | €7,600 |
| **Total ASF** | | | **€21,375** |

| Demand (RSF) | Balance | Factor | Needs |
|---|---|---|---|
| Mortgage (RW ≤35%, >1 year left) | €175,000 | 65% | €113,750 |
| Personal loan (>1 year, RW 75%) | €10,000 | 85% | €8,500 |
| Card balance (<1 year) | €400 | 50% | €200 |
| **Total RSF** | | | **≈ €122,450** |

**Reading it:** Mila's deposits cover only **~17%** (21,375 ÷ 122,450) of the stable funding her loans need. The bank fills the gap with capital, long-term bonds (e.g. covered bonds) and *other customers'* deposits. **Lesson:** a household with big deposits and a small loan helps the bank's ratios; a household with a big mortgage uses them up — both are normal, banks need both.

### Step 3: Risk-weighted assets (SA)

**Mortgage — loan-splitting by LTV.** The SA treats the part of a residential mortgage up to **55% of the property value** as very safe (**20%** RW). The rest gets the borrower's ordinary weight (**75%** for a retail individual).

- Property value €250,000 → 55% = **€137,500** at 20% → **€27,500** RWA
- Remaining €175,000 − 137,500 = **€37,500** at 75% → **€28,125** RWA
- **Mortgage RWA = €55,625** → *average* RW **31.8%**

**Other products:**

| Product | Exposure | Treatment | RWA |
|---|---|---|---|
| Personal loan | €10,000 | Regulatory retail, 75% | €7,500 |
| Card (drawn) | €400 | Transactor, 45% | €180 |
| Card (unused €2,600) | €2,600 × 10% CCF = €260 | Transactor, 45% | €117 |
| Overdraft (unused €1,000) | €1,000 × 10% = €100 | Transactor, 45% | €45 |
| **Mila's total RWA** | | | **≈ €63,467** |

(A revolver who carries a card balance would be weighted 75% instead of 45% on the card lines.)

**Interactive widget idea — "LTV slider" (per property value 100):**

| LTV | Average RW | Capital tied up per €100,000 loan at a 15% CET1 ratio |
|---|---|---|
| 50% | 20.0% | €3,000 |
| 60% | 24.6% | €3,688 |
| 70% | 31.8% | €4,768 |
| 80% | 37.2% | €5,578 |
| 90% | 41.4% | €6,208 |
| 100% | 44.8% | €6,713 |

Formula shown on page: *RWA = 20% × (loan up to 55% of value) + 75% × (loan above that).* (Add the footnote: "Rules for specific property types, income-producing property, past-due loans and unfinished buildings differ.")

*Past-due note:* if a loan is in default (typically 90+ days late and over materiality thresholds), the SA risk weight rises (typically 100%–150% depending on provisions and loan type).

### Step 4: Capital — how much of the bank's own money sits behind Mila?

EU minimums (CRR Art. 92), as a % of RWA:

| Layer | Minimum | For Mila's €63,467 RWA |
|---|---|---|
| CET1 | 4.5% | €2,856 |
| Tier 1 | 6.0% | €3,808 |
| Total capital | 8.0% | €5,077 |
| + Capital conservation buffer (CET1) | 2.5% | €1,587 |
| **A real bank targets more** — fictional bank's CET1 ratio **15%** | 15% | **€9,520** |

On top of these minimums, supervisors add **Pillar 2** (bank-specific) requirements, and national authorities set buffers (countercyclical, systemic). The **leverage ratio (3%)** is checked separately and ignores risk weights.

**Reading it:** against Mila's roughly €185k of borrowing, the bank keeps roughly **€9,500 of its own money** (~5%). That is the "safety tank" behind her loans.

### Step 5: The accounting lens (IFRS 9) — a one-box sidebar

Separately from capital rules, the bank's *accounts* (IFRS 9) require **expected-loss provisions** from day one (see View 2 for Mila's numbers). Provisions reduce profit and therefore, over time, capital. So regulatory capital and accounting provisions *both* rise when loans get riskier.

## 1(d) What this means for you — practical tips

1. **Deposits that stay put are valued.** Being a long-standing customer with a salary account and an insured balance is what makes your money "stable" (5% run-off). Moving large sums between banks chasing rates tends to be classified less stable.
2. **Stay under the guarantee limit if safety matters to you.** Above €100,000 per bank, money is not insured *and* is treated as less stable.
3. **A bigger deposit (down payment) lowers the bank's capital need on your mortgage.** Dropping from 90% to 70% LTV cuts the average risk weight from ~41% to ~32%. That often shows up as a better rate tier (see View 3).
4. **Pay cards in full each cycle.** Under the SA, a "transactor" gets a lower risk weight (45% vs 75%). Banks may reward behaviour that costs them less capital. (Whether they pass it on varies.)
5. **Unused credit limits are not free for the bank.** They count as potential exposure. Cancelling unused limits can reduce the bank's costs — but check with your own situation first, as available credit also affects your own credit file.

## 1(e) Suggested page/section layout — View 1

**URL:** `/regulatory-view`

| # | Section | Component | Notes |
|---|---|---|---|
| 1 | Hero: "Your bank has three dials" | Water-system illustration with three labelled dials: **Liquidity / Risk / Capital** | One-sentence promise, "5-min read" |
| 2 | "What changes with each product?" | **Product grid** (current account, savings, term deposit, card, loan, mortgage); click → shows which dial moves | Colour-coded: *adds liquidity* / *uses liquidity* / *adds RWA* |
| 3 | Mila's profile | Sticky sidebar card on desktop; collapsible on mobile | Persona switcher (Mila/Jonas/Aiko) |
| 4 | Dial 1: Liquidity | Run-off bar chart; toggle "stable / less stable"; LCR & NSFR explainers in tabs | Show the 30-day emergency-fund analogy |
| 5 | Dial 2: Risk-weighted assets | **LTV slider** → live risk weight & capital; transactor toggle on the card | Pop-up: "what a risk weight means" |
| 6 | Dial 3: Capital | Stacked bar of minimum → buffers → bank target for Mila's RWA | Plain note: CRR vs CRD |
| 7 | "Putting it together" | Single table: Mila's liquidity / RWA / capital contributions | Net funding user vs provider |
| 8 | IFRS side box | Collapsed card | Links to View 2 |
| 9 | "What this means for you" | 5 tip cards | Each with an icon |
| 10 | Glossary + sources + disclaimer | Footer block | Link to Part 0.4 map |

Navigation: bottom-of-page card → "Next: How the bank sees your risk →".

---
---

# VIEW 2 — RISK VIEW
### *"How the bank sees you as a source of risk"*

## 2(a) Plain-language summary

If View 1 is what the regulator *counts*, View 2 is what the bank *watches*. Banks sort customer-related risk into a few boxes:

1. **Credit risk** — will you pay it back? If not, how much does the bank lose?
2. **Behavioural and concentration risk** — how do you *act* (overdrafts, early repayments, withdrawals), and does the bank have too many eggs in one basket?
3. **Operational, conduct and financial-crime risk** — mistakes, fraud, unfair treatment, money laundering.

> **Honesty box:** The SA does not use *your* personal default probability to set capital. But the bank **does** estimate it, for approval, pricing, monitoring and **IFRS 9 provisions**. The regulator's weights are a blunt average; the bank's own view is sharper.

## 2(b) Key concepts glossary (View 2)

| Term | Plain-language definition |
|---|---|
| **Credit risk** | The risk that a borrower doesn't repay as agreed. |
| **PD (Probability of Default)** | How likely you are to stop paying within a given time (usually 12 months). 1% PD = 1 in 100. |
| **Default** | In EU rules, usually **90 days overdue** (above small materiality thresholds) **or** the bank judges you "unlikely to pay" (CRR Art. 178). |
| **EAD (Exposure at Default)** | How much you would owe at the moment of default (including part of any unused limit). |
| **LGD (Loss Given Default)** | The share of EAD the bank loses *after* selling collateral and collecting costs. Mortgage: low (house sells). Unsecured loan: high. |
| **Expected loss (EL)** | **PD × LGD × EAD**. The "normal cost of doing business". |
| **SA context** | In the SA, regulators *pre-set* a risk weight that bundles typical PD and LGD together. No bank model is used for capital. External credit ratings apply to *companies, banks, governments* — **not to individuals**. |
| **Collateral** | An asset pledged to the lender (e.g. the home). Reduces LGD. Real estate has its own SA rules; cash or financial collateral and guarantees can lower risk weights via *credit risk mitigation*. |
| **Credit bureau / credit register** | A national database of borrowers' loans and repayment history. Banks check it. |
| **Scorecard** | A statistical points system that turns your data into a risk grade. |
| **IFRS 9 / ECL** | Accounting rule: banks set aside **expected credit losses**. **Stage 1** (normal): 12-month expected loss. **Stage 2** (credit risk up significantly, e.g. 30+ days late): *lifetime* expected loss. **Stage 3** (credit-impaired, e.g. 90+ days late): full loss estimate. |
| **Behavioural risk** | Risk from *how customers behave*: repaying early, withdrawing suddenly, using overdrafts. |
| **Prepayment risk** | You repay early, so the bank loses the interest it planned to earn and may have to unwind hedges. |
| **Concentration risk** | Too much exposure to one customer, sector, region, or product (e.g. one country's housing market). |
| **Operational risk** | Loss from failed processes, people, systems, fraud, or outside events (e.g. cyberattack). Capital is computed under CRR3's single standardised method based on the bank's income, not on individual customers. |
| **Conduct risk** | Risk of treating customers unfairly (mis-selling, poor information, bad arrears handling). |
| **KYC / CDD** | *Know Your Customer / Customer Due Diligence*: proving who you are, where money comes from, and why you bank here. |
| **AML** | *Anti-money-laundering*: detecting and reporting criminal money. |
| **PEP** | *Politically exposed person*: someone in a prominent public role (and close family/associates) → extra checks by law. |
| **Forbearance** | Concessions (e.g. payment holiday, term extension) to help a borrower in difficulty. |

## 2(c) Worked example — Mila through the risk lens

### Step 1: Credit risk — expected loss and IFRS 9 allowance (illustrative, Stage 1)

| Product | PD (12-mo) | LGD | EAD | Expected loss = PD × LGD × EAD |
|---|---|---|---|---|
| Mortgage | 0.5% | 10% (house worth €250k vs. loan €175k) | €175,000 | **€88** |
| Personal loan | 3% | 65% (no collateral) | €10,000 | **€195** |
| Card + unused limit | 1% | 80% | €1,700 (€400 + 50% of €2,600, bank's own estimate) | **€14** |
| **Total allowance (IFRS 9 Stage 1)** | | | | **≈ €297** |

**What happens if Mila slips?**

| Scenario | IFRS 9 stage | Provision on personal loan (EAD €9,000) |
|---|---|---|
| Pays on time | Stage 1 | ~€195 (12-month ECL; EAD simplified) |
| 35 days late once | **Stage 2** — credit risk significantly increased | lifetime PD ~12% × LGD 65% × €9,000 ≈ **€700** |
| 90+ days late | **Stage 3** — credit-impaired | ~65% × €9,000 ≈ **€5,850** |

*SA link:* once defaulted, the SA risk weight changes (e.g. 150% if provisions are under 20% of the loan, 100% if above — for unsecured retail), so a missed payment costs the bank *twice*: higher provisions **and** higher capital. That is why banks act early.

**Why isn't Mila's EL used for capital?** Under the SA it isn't; her PD feeds **pricing, approval, limits and provisions**.

### Step 2: How the bank "sees" Mila — an illustrative internal risk grade

| Signal | What the bank sees | Effect |
|---|---|---|
| Payment history | 0 late payments in 24 months | ↓ risk |
| Income stability | Permanent contract, 6 years | ↓ risk |
| Debt service ÷ net income | 40% (see View 3) | neutral/amber |
| Savings buffer | €22,500 ≈ 8 months of income | ↓ risk |
| Credit use | Card paid in full; overdraft unused | ↓ risk |
| Relationship | Salary account for 5 years, multiple products | ↓ risk (and stable deposits) |
| Recent credit searches | 1 in 12 months | neutral |
| **Illustrative result** | **Grade 4 of 10 ("good")** | |

*Design note:* show this as a **stylised dashboard**, not a "credit score", and state that grades, weights and thresholds vary by bank.

### Step 3: Collateral & LGD — why the house matters

| LTV | Rough LGD (illustrative) | Why |
|---|---|---|
| 50% | ~5% | Property can fall 50% and the loan is still covered |
| 70% (Mila) | ~10% | Large cushion after fire-sale discount and costs |
| 90% | ~20% | Small cushion |
| 100%+ | 30%+ | Likely loss if prices drop |

Banks usually assume a distressed sale price **below** market value (and collection costs and time), so even a 70% LTV is not "zero risk".

### Step 4: Behavioural and concentration risk

| Behaviour | What the bank worries about | What it may do |
|---|---|---|
| Regular overdraft use / hitting limits | Cash-flow stress | Lower limits, offer help, tighter lending |
| Card carried at the limit; minimum payments | Revolving debt rising | Monitor, contact, adjust limit |
| Salary stops arriving; balance falls fast | Job loss | Early-warning flag; outreach |
| Cluster of new credit applications | "Credit hunger" | Higher risk grade |
| Early repayment of fixed-rate mortgage | Lost interest; hedge unwinding | May charge a **fair** fee (MCD: must not exceed the bank's financial loss; national caps apply). Consumer loans (CCD2): early-repayment compensation generally capped at 1% of the amount repaid early (0.5% if under a year remains) |
| Large, sudden withdrawals; rate-chasing | Deposit instability (View 1 run-off) | Treated as "less stable" funding |

**Concentration** (customers don't control it but should understand it):
- *Retail portfolios must be **diversified*** to qualify for the 75% weight: no single borrower is allowed to dominate.
- A bank with mostly mortgages in one country is exposed to *that housing market*. When it worries, it may tighten LTV limits or raise rates, even if you personally are fine.
- On the deposit side, a few very large depositors raise liquidity risk; many small insured depositors lower it.

### Step 5: Operational, conduct and AML/KYC — what you see and what you don't

| Risk | What the bank checks or does | Signals on your side |
|---|---|---|
| **Identity & KYC** | Verify ID and address; understand your employment and why you need the product | Consistent documents; honest answers |
| **Source of funds / wealth** | For large deposits or down payments: "where did this money come from?" | Keep proof (payslips, sale contract, gift letter) |
| **Transaction monitoring** | Software looks for unusual patterns: sudden large cash deposits, splitting transfers just under limits, quick in-and-out flows, payments to high-risk countries | Large cash is the most common trigger; say what it's for |
| **Risk rating** | Low / medium / high customer risk (higher for PEPs, complex structures, high-risk countries) → more frequent checks | Mila: **low** (salaried, transparent flows) |
| **Fraud** | Is the account being used by scammers (as victim or "money mule")? | Never lend your account to others |
| **Conduct** | Does the bank explain products properly, avoid mis-selling, and treat borrowers in arrears fairly? | MCD/CCD2 give you pre-contract information, time to think, and forbearance rights |
| **Operational** | Outages, cyber, process errors. Not about you individually, but it affects service | — |

**Important:** if a bank reports suspicious activity to the authorities, it is **forbidden** to tell you ("no tipping off"). Banks can also say "no" or close accounts after AML checks. Explain this neutrally; it can feel unfair but it is law.

## 2(d) What this means for you — practical tips

1. **Your payment history is your strongest signal.** Set up direct debits. A single 30-day delay can move you into "higher risk" (IFRS 9 Stage 2) at many banks.
2. **A savings cushion matters.** 3–6 months of expenses visibly lowers risk, even if you never touch it.
3. **Use credit as a tool, not as a lifeline.** Persistent overdraft use is one of the earliest stress signals.
4. **Talk early if you struggle.** Banks are expected to offer forbearance and fair arrears handling; waiting until you are 90 days late costs both sides more.
5. **Be ready for KYC questions.** Keep documents showing where large sums came from. Questions are routine, not accusations.

## 2(e) Suggested page/section layout — View 2

**URL:** `/risk-view`

| # | Section | Component | Notes |
|---|---|---|---|
| 1 | Hero: "The bank's three risk questions" | Three icons: *Will you repay? How do you behave? Is everything above board?* | |
| 2 | "Capital vs. risk: what's the difference?" | 2-column explainer (SA fixed weights vs. bank's own view) | Prevents the biggest misunderstanding |
| 3 | Credit risk | **PD × LGD × EAD** calculator with sliders; Mila's table | Analogy: *lend a bike to a friend (PD), how much would you lose if it's stolen (LGD), value of the bike (EAD)* |
| 4 | "Slip-up simulator" | Timeline: day 0 → day 35 → day 90 with IFRS 9 stage badges and provision amounts | Strongest "aha" |
| 5 | Collateral & LGD | LTV bar with LGD overlay | Links to View 1 LTV slider |
| 6 | Behaviour & concentration | Traffic-light signal board (green/amber/red behaviours) | Click each signal → bank's reaction |
| 7 | Operational, conduct, AML | 3 tabs; "Why am I being asked this?" FAQ | Neutral tone; mention tipping-off rule |
| 8 | "Your bank's view of Mila" | Stylised internal dashboard with grade | Disclaimer: illustrative |
| 9 | What this means for you | 5 tips | |
| 10 | Glossary, sources, disclaimer | | |

---
---

# VIEW 3 — LENDING VIEW
### *"What it takes to get a loan, and how your rate is set"*

## 3(a) Plain-language summary

Getting a loan has two questions:

1. **Can you afford it, and is the paperwork right?** (approval)
2. **What does it cost the bank to lend to you, plus profit?** (pricing)

EU law requires banks to check you can *realistically* repay (not just that the house is worth enough). Your rate then comes from a **building-block formula**: what the bank pays for the money, plus a charge for the risk you might not repay, plus the cost of holding capital against the loan, plus running costs and profit. The SA matters because it fixes **how much capital the loan needs**, and that capital is expensive.

> **Analogy:** pricing a loan is like pricing a taxi ride: the fuel (funding), the risk of a breakdown (credit risk), the car's purchase cost tied up (capital), the driver's wage (operating cost), and a small profit — all affected by what rival taxis charge.

## 3(b) Key concepts glossary (View 3)

| Term | Plain-language definition |
|---|---|
| **Creditworthiness assessment** | The bank's legal duty to check you can repay, based on income, expenses and debts. |
| **DSTI / DTI** | *Debt-service-to-income*: monthly debt payments ÷ monthly income. *Debt-to-income*: total debt ÷ annual income. |
| **Affordability stress test** | Checking you could still pay if interest rates rose (e.g. +2 percentage points) or your income fell. |
| **Residual income** | What's left after taxes, debt payments and basic living costs. |
| **LTV limit** | The maximum % of the property value the bank (or national rules) will lend. Set nationally and by banks; **not** one EU-wide number. |
| **ESIS / SECCI** | The standard European info sheet banks must give you before a mortgage (**ESIS**) or consumer loan (**SECCI**, under CCD2 "standard consumer credit information"). Lets you compare offers. |
| **APR / APRC** | *Annual percentage rate (of charge)*: interest **plus** fees, as one yearly percentage. Compare this, not just the headline rate. |
| **Reference rate (Euribor / swap rate)** | Market interest rates banks use as a base: Euribor for variable rates, swap rates for fixed rates over several years. |
| **Funding cost** | What the bank pays to get the money it lends (deposits, bonds). |
| **Liquidity premium** | An extra charge for holding long-term loans funded by money that might leave sooner (links to LCR/NSFR). |
| **Risk premium** | Charge to cover expected losses (**PD × LGD**). |
| **Cost of capital** | The return shareholders expect on the bank's own money (e.g. 10–12%). Equity is costlier than deposits. |
| **Margin** | The bank's profit and competitive adjustment on top of all costs. |
| **RAROC / ROE** | Return on risk-adjusted capital / return on equity: profit relative to the capital the loan uses. Banks set a minimum target. |
| **Fixed vs. variable rate** | Fixed: set for a period. Variable: moves with Euribor + margin. |
| **Cooling-off / reflection period** | Time to think (mortgages: a reflection period or withdrawal right of at least 7 days, depending on the country; consumer loans: 14-day withdrawal right). |

## 3(c) Part 1 — What the bank needs from you (step by step)

| Step | What happens | What you provide | Legal anchor |
|---|---|---|---|
| **1. Decide & pre-check** | Estimate budget; compare offers | Your own budget, desired amount and term | Pre-contract info (**ESIS**, **SECCI**) |
| **2. Documents** | Bank collects evidence | ID; proof of address; **payslips** (last 3 months) or, if self-employed, tax returns/accounts for 2–3 years; employment contract; 3–6 months bank statements; list of existing debts; for a mortgage: purchase contract, property valuation, proof of down payment, buildings insurance | MCD Art. 18; CCD2; EBA/GL/2020/06 |
| **3. Identity & checks** | KYC and AML; credit-register search | Consent to check credit registers; explain source of funds | AML rules; national credit registers |
| **4. Affordability** | Income vs. expenses vs. debts; interest-rate stress test | Honest, complete information (omissions can void the loan or lead to refusal) | MCD Art. 18; CCD2 creditworthiness; EBA/GL/2020/06 |
| **5. Collateral & LTV** (mortgage) | Independent valuation; check LTV against bank and national limits | Access to the property | MCD (valuation standards); national macroprudential rules |
| **6. Decision & offer** | Approve/decline; offer with APR/APRC; you can ask for **human review** of an automated decision (CCD2) | Time to read ESIS/SECCI | MCD; CCD2 |
| **7. Signing & after** | Funds released; monitoring; early-repayment rights; help if you struggle | Keep paying; tell the bank early if things change | MCD; CCD2; EBA Guidelines on arrears |

**Scope notes to put in a callout:**
- **CCD2** applies to consumer credit up to **€100,000** (check national law), from **20 Nov 2026**.
- **Responsible lending principle:** the assessment must be mainly about whether *you can repay from income*, **not** whether the house is worth enough.
- **LTV and income limits** (e.g. maximum LTV, income multiples) are generally set **nationally**. Example: some countries cap LTV at 100% or lower; others use income-based limits. Show a "check your country" link, don't hard-code numbers.

## 3(c) Worked example A — Mila's affordability check (at mortgage application)

| Item | Monthly |
|---|---|
| Net income | €2,800 |
| Existing personal loan | €198 |
| Card (bank assumes 2% of €3,000 limit) | €60 |
| **New mortgage payment** (€175,000, 3.5%, 25 yrs) | **€876** |
| **Total debt payments** | **€1,134** |
| **DSTI** | **40.5%** |
| Living-cost benchmark (single adult; national benchmark) | €1,100 |
| **Residual income** | **€566** ✅ |

**Stress test (rate +2 pp → 5.5%):** mortgage payment ≈ **€1,075** → debts €1,333 → DSTI **47.6%**, residual **€367** — still positive ✅.

Illustrative bank policy: DSTI ≤ 42% at the offered rate and ≤ 50% under stress → **Mila passes**. Also: **LTV 70%** (down payment €75,000) and a permanent contract → **approved** (illustration only; real limits vary).

**Compare — Jonas** (income €2,400, 90% LTV, no existing debts): the stress-test DSTI and the higher LTV may lead to a smaller loan, a longer term, a co-borrower, or a refusal.

## 3(c) Part 2 — How the bank builds your interest rate

### The building blocks (formula for the site)

> **Rate = Funding cost + Liquidity premium + Expected loss + Capital cost + Operating cost + Margin/competition**

| Block | What it means | Mila's mortgage (3.5% fixed, LTV 70%) |
|---|---|---|
| 1. **Funding cost** | What the bank pays for matched-term money (swap rate / deposits / bonds) | **2.30%** |
| 2. **Liquidity premium** | Cost of holding emergency cash and stable long-term funding (LCR/NSFR) | **0.25%** |
| 3. **Expected loss (risk premium)** | PD × LGD = 0.5% × 10% | **0.05%** |
| 4. **Capital cost** | Capital held × the extra cost of equity over debt (see Part 3) | **0.40%** |
| 5. **Operating cost** | Staff, IT, servicing, distribution | **0.35%** |
| 6. **Margin & competition** | Profit target, adjusted for what rivals charge | **0.15%** |
| **Customer rate** | | **3.50%** |

### Same bank, different LTV (mortgage)

| LTV | Risk weight | Capital (15% CET1) | Expected loss (PD × LGD) | Capital cost | **Indicative rate** |
|---|---|---|---|---|---|
| 50% | 20.0% | 3.0% of loan | 0.3% × 5% = 0.02% | 0.25% | **≈ 3.32%** |
| 70% (Mila) | 31.8% | 4.8% | 0.5% × 10% = 0.05% | 0.40% | **≈ 3.50%** |
| 90% | 41.4% | 6.2% | 0.8% × 20% = 0.16% | 0.52% | **≈ 3.73%** |

### Product matters: Mila's €10,000 personal loan (5 years)

| Block | Value |
|---|---|
| Funding cost | 2.00% |
| Liquidity premium | 0.25% |
| Expected loss (3% × 65%) | 1.95% |
| Capital cost (RW 75% → 11.25% capital × 8.75% extra cost) | 0.98% |
| Operating cost (small loans cost more per €) | 1.20% |
| Margin | 0.60% |
| **Rate** | **≈ 7.0%** |

**Key SA insight:** if Mila had a lower PD of 1% (EL 0.65%), the rate would be ~5.7% — but the **capital cost would not change**, because the SA gives the same **75% weight** to all regulatory-retail borrowers. The SA is blunt, so banks add their own risk view **in the price**.

## 3(c) Part 3 — How the SA framework influences pricing

### The capital cost formula

1. **Capital needed** = loan × risk weight × CET1 ratio
   *Mila's mortgage:* €175,000 × 31.8% × 15% ≈ **€8,344** (4.8% of the loan)
2. **Extra cost of using equity instead of debt** = cost of equity − cost of debt-type funding
   *Illustration:* 11% − 2.55% = **8.45%**
3. **Capital cost, per € of loan per year** = 4.8% × 8.45% ≈ **0.40%** → built into the rate

### Three practical consequences

1. **Risk weight → price.** Higher LTV → higher RW → more capital → higher rate (table above). 20% RW loans are the cheapest for the bank to hold; unsecured at 75% and revolvers at 75% (or 100% in some cases) cost more.
2. **Capital is rationed.** A bank has a finite pool. It lends first where the return per unit of capital is highest. Loans using lots of capital for thin margins (high-LTV, small unsecured) may be priced up or rationed, especially when capital is scarce.
3. **Deposits can lower your price.** Stable deposits (View 1) are cheap funding that also helps LCR/NSFR, so banks may reward customers who bring salary and savings (relationship pricing, say −0.10 pp). It does not violate rules — it reflects real cost differences.

### Other factors beyond the formula

| Factor | Effect |
|---|---|
| **Competition** | Banks match market rates to win business; margins can be squeezed |
| **Fixed vs. variable** | Fixed rates track swap rates for the fixed period and include a charge for rate risk; variable tracks Euribor + margin |
| **Fees and IFRS 9** | Upfront fees are spread over the loan's life in the accounts (effective interest rate method), so banks may trade fee vs. rate |
| **Early repayment** | Fixed-rate loans may carry a fee reflecting the bank's cost of unwinding funding (MCD: not above financial loss) |
| **Energy efficiency / ESG** | Some banks offer lower margins for efficient homes due to expected lower risk and ESG goals. This is *a bank decision*, not an automatic SA capital discount |
| **Regulation changes** | New rules (e.g. CRR3 recalibrated residential weights from 35% to 20% on the secured part, with loan-splitting retained) change costs for all banks over time |

## 3(d) What this means for you — practical tips

1. **Do your own affordability stress test first.** Ask: "Can I pay if the rate is 2 points higher?" Banks do.
2. **Gather documents before applying.** Missing documents are the most common cause of delay.
3. **Bigger down payment = lower LTV = cheaper loan.** The step from 90% to 70% LTV can reduce the rate in the example by ~0.2 pp. Over 25 years on €175,000, that's real money — calculate it with the APRC, not just the rate.
4. **Compare the APR/APRC and the ESIS/SECCI side by side.** Fees, insurance and early-repayment terms matter.
5. **Ask what you gain from your relationship.** Salary account, savings, or insurance may cut your rate. Ask for it in writing, and check what you would lose if you cancel one product.
6. **Don't hide debts or income issues.** Misstatements can lead to refusal, withdrawal of the loan or legal consequences, and it's more likely to be caught than not (credit registers).
7. **You may request human review** of an automated loan decision (CCD2) and an explanation in many cases. Use that right.

## 3(e) Suggested page/section layout — View 3

**URL:** `/lending-view`

| # | Section | Component | Notes |
|---|---|---|---|
| 1 | Hero: "From 'yes' to your rate" | Two-step journey graphic: *Approval → Pricing* | |
| 2 | Journey stepper | **7-step horizontal stepper** (mobile: accordion) with "documents checklist" printable | Each step = what bank does / what you provide / law |
| 3 | "Can I afford it?" | **Affordability calculator** (income, debts, loan, rate, stress slider) with traffic-light result | Runs locally in the browser, no data stored |
| 4 | LTV explainer | LTV bar linking to View 1 slider | Country selector with link-outs to national rules |
| 5 | "How your rate is built" | **Stacked bar chart** (6 blocks) with hover definitions; toggle product (mortgage / personal loan) and LTV | Core visual of the whole site |
| 6 | "Where the SA comes in" | 3-line formula strip: *Loan × Risk weight × Capital ratio × Extra cost = Capital cost* | Animate with Mila's numbers |
| 7 | "Why the same risk weight, different price?" | Callout on SA blunt weights vs. internal PD | |
| 8 | "Other price factors" | Accordion (competition, fixed vs. variable, fees, early repayment, ESG) | |
| 9 | What this means for you | 7 tip cards + "Questions to ask your bank" checklist (downloadable) | |
| 10 | Glossary, sources, disclaimer | | |

---
---

# PART 4 — SITE-WIDE STRUCTURE & UX

## 4.1 Information architecture

```
Home — "How does your bank see you?"
├── Meet Mila (persona + switcher)
├── View 1: Regulatory   /regulatory-view
├── View 2: Risk         /risk-view
├── View 3: Lending      /lending-view
├── Compare the three lenses (one-page table of Mila)
├── Glossary (A–Z, searchable, same definitions as tooltips)
├── Rules & sources (Part 0.4 map, links to EUR-Lex / EBA)
└── About, methodology & disclaimer
```

## 4.2 "Compare the three lenses" summary table (a good home-page teaser)

| | Regulator's view | Risk manager's view | Lender's view |
|---|---|---|---|
| **Looks at** | Product type and rules | Your behaviour and ability to repay | Your affordability and what the loan costs |
| **Mila's mortgage** | RWA €55,625; NSFR RSF €113,750 | PD 0.5%, LGD 10%, EL €88 | Rate 3.50%; 70% LTV; DSTI 40.5% |
| **Mila's deposits** | 5% run-off; 95% ASF | Stable behaviour | Relationship pricing |
| **Question answered** | "Is the bank safe?" | "Will she pay?" | "At what price do we lend?" |

## 4.3 Interactive elements (ranked by value)

1. **LTV slider** (Views 1 & 3) — shows risk weight, capital and rate together.
2. **Rate build-up stacked bar** (View 3).
3. **Slip-up simulator** (View 2).
4. **Stable / less-stable deposit toggle** (View 1).
5. **Persona switcher** (Mila / Jonas / Aiko) — everything recalculates.

## 4.4 Plain-language & accessibility rules

- Short sentences (<20 words), active voice, no unexplained acronyms; spell out **LCR, NSFR, RWA, CET1, LTV, DSTI, PD, LGD, EAD** at first use in each view.
- Every number in a table has a one-line "how we got it" expansion.
- WCAG 2.2 AA: colour is never the only signal (traffic-light needs icons/text), keyboard-operable sliders, captions/alt text for diagrams.
- Mobile-first: tables collapse to cards; sticky Mila card becomes a bottom sheet.
- Localise: language, currency formats, national rules panel. Keep a single "regulation as of" date in the footer.

## 4.5 Content governance (small but important)

1. **Owner and review cycle:** assign a compliance/regulatory reviewer; review at least twice a year and after any CRR/CRD/CCD/AML change. Keep a visible "last reviewed" date.
2. **Every number traces to a source:** keep a hidden "assumptions" sheet (swap rates, cost of equity, PD/LGD, benchmarks) so figures can be updated in one place.
3. **No real bank names or real customer data.** Label every illustration as fictional.
4. **Privacy:** run calculators client-side; no cookies beyond what's necessary; link to a privacy notice (GDPR).

---

## Sources used while drafting (secondary; verify against primary EU texts)

- [Advisense — Credit Risk Framework, Standardised Approach (transactors 45%)](https://advisense.com/2024/06/05/credit-risk-framework-standardised-approach/)
- [CRR Art. 125, German text — 20% on part up to 55% of property value](https://gesetze.legal/eu/vo_eu_2013_575/125)
- [European Commission — Consumer Credit Directive, financial services](https://commission.europa.eu/topics/consumers/consumer-rights-and-complaints/consumer-financial-products-and-services/consumer-protection-financial-services_et) (CCD2 applies from 20 Nov 2026)
- [Abreu Advogados — New rules on consumer credit in the EU, Directive 2023/2225](https://abreuadvogados.com/en/?p=67548)
