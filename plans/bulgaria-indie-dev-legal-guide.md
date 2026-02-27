# Legal, Accounting & Tax Guide for Bulgarian Indie Developer
## Selling NinjaTrader Indicators / Software Licenses Online

> **Case Study:** Solo developer based in Bulgaria, selling software licenses (NinjaTrader indicators) via a Next.js web app hosted on Cloudflare (free tier) + Supabase (free tier) + custom licensing system. Product is downloadable for free; users pay for a license key. 14-day free trial included.

---

## ⚠️ DISCLAIMER

*This content is for informational purposes only and does not constitute legal or tax advice. Laws change frequently. Always consult a licensed Bulgarian attorney and/or accountant before making decisions. The "gray area" scenarios described carry real legal and financial risk.*

---

## 1. Understanding What You Are Selling

Before choosing a legal structure, it is critical to correctly classify the product:

| What the customer receives | Legal classification |
|---|---|
| A license key to activate already-downloaded code | **License for intellectual property / software** |
| The right to use the software for a period | **Service / subscription** |
| A downloadable file | **Digital goods** |

**Key insight:** Under Bulgarian and EU law, selling a software license is treated as a **supply of electronically supplied services (ESS)**. This has direct VAT implications (see Section 5).

---

## 2. The Two Payment Models

### Option A — Direct Payment Processor (Stripe, PayPal, etc.)

You integrate a payment processor directly into your Next.js app. You collect money, you are the **Merchant of Record (MoR)**.

**Responsibilities fall on YOU:**
- VAT collection and remittance in each EU country where customers are located
- Compliance with EU VAT OSS (One-Stop Shop) rules
- Issuing invoices
- Handling refunds, chargebacks
- PCI-DSS compliance (partially handled by Stripe/PayPal)

**Pros:**
- Lower fees (typically 2.9% + fixed fee)
- Full control over checkout experience
- No revenue sharing beyond processor fees

**Cons:**
- You become responsible for EU VAT from the first sale to an EU customer
- Significant compliance burden
- Chargebacks handled by you

---

### Option B — Merchant of Record (Lemon Squeezy, Paddle, Gumroad, etc.)

A third-party MoR acts as the legal seller. They collect payment, handle VAT, issue invoices, and remit taxes. You receive a payout minus their fee.

**Responsibilities fall on the MoR:**
- EU VAT compliance
- Invoicing
- Refunds and chargebacks
- PCI-DSS

**Your responsibilities:**
- Declare income received from the MoR as your revenue
- Pay Bulgarian income tax on net income

**Pros:**
- Dramatically reduces your compliance burden
- No VAT registration needed (in most scenarios — see Section 5)
- Handles global tax complexity automatically
- Ideal for solo developers

**Cons:**
- Higher fees (Lemon Squeezy: 5% + $0.50; Paddle: 5% + $0.50; Gumroad: 10%)
- Less control over checkout
- You are dependent on the MoR's policies

**Recommended MoR Comparison:**

| Platform | Fee | Notes |
|---|---|---|
| **Lemon Squeezy** | 5% + $0.50 | Best for software/SaaS, excellent API |
| **Paddle** | 5% + $0.50 | More enterprise-focused, strong EU presence |
| **Gumroad** | 10% | Simpler but expensive at scale |
| **Payhip** | 5% | Good for digital products |
| **FastSpring** | ~8.9% | Enterprise, complex setup |

**Recommendation for this case:** **Lemon Squeezy** or **Paddle** — both are purpose-built for software license sales and handle all EU VAT automatically.

---

## 3. Phase 1 — The "Gray Area" Start (Natural Person, First Few Sales)

### What is legally possible?

Bulgarian law allows natural persons (физически лица) to earn **occasional income** without registering a business, subject to certain conditions and annual declaration.

### Scenario 3.1 — Declare as "Author's Rights" Income (Авторски права)

**Legal basis:** Article 35 of the Bulgarian Income Tax on Natural Persons Act (ЗДДФЛ — Закон за данъците върху доходите на физическите лица).

**How it works:**
- Income from intellectual property (software, music, books, etc.) can be declared as author's rights income
- A **40% standard deduction** is applied automatically (recognized expenses without proof)
- Effective tax rate: **60% of income × 10% flat tax = 6% effective tax rate**
- Social security contributions may also apply (see below)

**Example calculation:**
```
3 sales × $300 = $900 gross income
40% deduction = $360
Taxable base = $540
Income tax (10%) = $54
Effective tax = $54 on $900 = ~6%
```

**Requirements:**
- The work must qualify as a copyrighted work under Bulgarian Copyright Act (ЗАПСП)
- Software code **does qualify** as a copyrighted work under Bulgarian and EU law
- You must be the author (original creator)
- Income declared annually in **Annual Tax Return (Годишна данъчна декларация)** — Appendix 3 (not Appendix 6)

**Important nuance:** Author's rights income goes in **Appendix 3** of the annual tax return, NOT Appendix 6. Appendix 6 is for "other income" from occasional activities.

**Social security on author's rights:**
- If you are NOT employed elsewhere and NOT self-insured: you may owe social security contributions on this income
- If you ARE self-insured (самоосигуряващо се лице): contributions are paid separately
- If you are employed full-time elsewhere: your employer handles your social security; author's rights income may still require additional contributions depending on amount

**Risks of this approach:**
- ⚠️ Tax authority (НАП) may challenge classification if sales are regular/systematic
- ⚠️ "Occasional" vs. "systematic" activity is a gray area — no clear legal threshold
- ⚠️ If deemed systematic, you could be reclassified as self-employed with back taxes + penalties
- ⚠️ No VAT registration protection (see Section 5)

---

### Scenario 3.2 — Declare as "Other Income" (Appendix 6 — Други доходи)

**Legal basis:** Article 35, paragraph 1, item 6 of ЗДДФЛ.

**How it works:**
- Income from occasional activities not covered by other categories
- **No standard deduction** (unlike author's rights)
- Full amount taxed at **10% flat rate**
- Declared in **Appendix 6** of annual tax return

**Example calculation:**
```
3 sales × $300 = $900 gross income
No deduction
Income tax (10%) = $90
```

**When to use this vs. Author's Rights:**
- Use Author's Rights (Appendix 3) if you can clearly establish you are the software author
- Use Appendix 6 only if you cannot establish author's rights claim
- Author's Rights is almost always more favorable (40% deduction)

**Risks:** Same as Scenario 3.1, plus higher effective tax rate.

---

### Scenario 3.3 — Using a MoR to Reduce Exposure in Gray Area

**Creative approach:** If you use Lemon Squeezy or Paddle as your MoR:

1. The MoR collects payment from customers
2. The MoR pays YOU as a "vendor payout" — this is income from a foreign company
3. You declare this as **income from abroad** (Appendix 8 of annual tax return)
4. The income is still taxable in Bulgaria, but the **VAT obligation is entirely on the MoR**
5. You avoid Article 97a VAT registration (see Section 5)

**This is the most legally defensible gray-area path** because:
- You are not directly collecting payments from customers
- The MoR handles all VAT
- Your income is clearly from a foreign business entity (the MoR)
- Easier to classify as occasional income or author's rights

---

## 4. Phase 2 — Registering as Self-Employed (Свободна Професия / ЕТ)

### Option A — Freelancer / Free Profession (Свободна Професия)

**Best for:** Software developers, consultants, creative professionals.

**Registration steps:**
1. Register with **Bulstat Register** (Агенция по вписванията) — obtain BULSTAT number
2. Register with **НАП (National Revenue Agency)** as self-employed
3. Register as **self-insured person** (самоосигуряващо се лице) with НОИ (National Social Security Institute)
4. Open a business bank account (optional but recommended)
5. Start issuing invoices

**Monthly obligations:**
- Pay **social security contributions** by the 25th of the following month
  - Minimum base: ~933 BGN/month (2024 figure, changes annually)
  - Contribution rate: ~32.7% (pension + health)
  - Minimum monthly contribution: ~305 BGN (~€155)
- File monthly/quarterly VAT returns IF VAT registered
- Keep accounting records

**Annual obligations:**
- Annual tax return by **April 30**
- Annual financial statement (simplified for sole traders)
- Declare all income in Appendix 2 (income from self-employment)

**Tax calculation for self-employed:**
```
Gross income: $X
Minus: documented expenses (hosting, software, equipment, etc.)
Minus: 25% standard deduction (if no documented expenses exceed this)
= Taxable base
Income tax: 15% (for ET — Едноличен търговец) OR 10% (for freelancer)
```

**Note:** "Свободна Професия" (free profession) pays **10% income tax** on net income. This is more favorable than ET (15%).

---

### Option B — Sole Trader (Едноличен Търговец — ЕТ)

**Registration:** Through Commercial Register (Търговски регистър) — more formal than freelancer registration.

**Tax rate:** 15% on profit (after expenses).

**Not recommended** for this use case — more paperwork, higher tax rate, no significant advantages over freelancer status for a solo developer.

---

### Self-Insurance Costs (Critical for Budget Planning)

As a self-insured person with NO other employment:

| Contribution type | Rate | On minimum base (933 BGN) |
|---|---|---|
| Pension (ДОО) | 19.8% | ~185 BGN |
| Health (НЗОК) | 8% | ~75 BGN |
| **Total minimum** | **~27.8%** | **~260 BGN/month** |

**Annual minimum social security cost: ~3,120 BGN (~€1,600)**

This is a fixed cost regardless of income. If your income is low, this can be a significant burden.

**Important:** You can choose a higher contribution base (up to the maximum of ~3,750 BGN/month), which increases your future pension but also your current costs.

---

## 5. The VAT Question — Article 97a and How to Navigate It

### What is Article 97a?

Article 97a of the Bulgarian VAT Act (ЗДДС) requires registration for VAT purposes when:
- You are a Bulgarian person (natural or legal)
- You receive services from **foreign suppliers** (e.g., Stripe, Cloudflare, Supabase, Google, etc.)
- The value of such services exceeds **0 BGN** (yes, from the first lev/euro)

**This means:** If you pay for ANY foreign digital service (even $1 to Stripe or Cloudflare), you technically must register under Article 97a.

**Consequences of Article 97a registration:**
- You must file **monthly VAT returns** (VIES declarations)
- You must self-assess VAT on foreign services received (reverse charge mechanism)
- You do NOT collect VAT from customers (limited registration)
- You cannot reclaim input VAT
- Significant monthly paperwork burden

### The Main Question: Can You Avoid Article 97a?

**The honest answer:** If you use ANY paid foreign service, you cannot legally avoid Article 97a. However, there are creative approaches:

---

### Strategy 1 — Stay on Free Tiers Only (Most Effective)

**The insight:** Article 97a is triggered by **receiving taxable services from abroad**. If all your foreign services are **free**, there is no taxable supply to trigger registration.

**Your current stack is already optimized for this:**
- ✅ Cloudflare (free plan) — no payment = no taxable service
- ✅ Supabase (free plan) — no payment = no taxable service
- ✅ Custom licensing system (self-built) — no cost

**Additional free tools to consider:**
- GitHub (free) for code hosting
- Vercel (free tier) as alternative to Cloudflare
- PlanetScale (free tier) as alternative to Supabase
- Resend (free tier) for transactional email

**Critical:** Do NOT upgrade to any paid tier of any foreign service until you have proper VAT registration or a legal structure that handles this.

**Risk:** If you accidentally use a paid foreign service (even a $1 charge), you are technically in violation from that moment.

---

### Strategy 2 — Route Payments Through a Bulgarian Entity

**The insight:** If you use a Bulgarian payment processor or a Bulgarian intermediary, the service is domestic and does not trigger Article 97a.

**Options:**
- Use a Bulgarian bank's payment gateway (e.g., DSK Bank, UniCredit Bulbank — they offer payment processing)
- Use a Bulgarian accounting software that handles invoicing

**Limitation:** Bulgarian payment processors are not well-suited for international software sales. This approach is impractical for a global product.

---

### Strategy 3 — Use a MoR That Pays You as a Vendor (Most Practical)

**The insight:** When Lemon Squeezy or Paddle pays you, they are paying you for your **product/license rights**, not providing you a service. The payment flow is:

```
Customer → MoR (Lemon Squeezy) → You (vendor payout)
```

**You are receiving income, not purchasing a service.** This does NOT trigger Article 97a.

**However:** If you use Lemon Squeezy's platform (their dashboard, API, etc.), they ARE providing you a service. The question is whether their service is "free" (included in their commission) or a separate paid service.

**Lemon Squeezy's model:** They take a commission (5% + $0.50) from each sale. There is no separate monthly fee. Their service is effectively "free" — you pay only when you sell.

**Legal argument:** The commission is deducted from the customer's payment before it reaches you. You never "pay" Lemon Squeezy — they simply pass through a reduced amount. This is similar to a marketplace model.

**This is a gray area argument** — tax authorities could disagree. But it is a reasonable position, especially for small volumes.

---

### Strategy 4 — Restructure as B2B Sales Only

**The insight:** Article 97a and EU VAT OSS rules apply primarily to **B2C** (business-to-consumer) sales. If all your customers are **businesses** (B2B), different rules apply:

- B2B sales: VAT is handled by the customer via reverse charge
- You do not need to register for VAT in the customer's country
- Simpler compliance

**How to implement:**
- Require customers to provide a VAT number at checkout
- Only sell to registered businesses
- Use Lemon Squeezy/Paddle's B2B checkout flow

**Limitation:** NinjaTrader indicators are primarily used by individual traders, not businesses. Forcing B2B-only sales would exclude most of your market.

**Partial implementation:** Offer a B2B option with a discount for businesses that provide VAT numbers. This reduces your B2C exposure without eliminating it.

---

### Strategy 5 — Threshold-Based Approach (EU OSS)

**The insight:** Under EU VAT rules, there is a **€10,000 annual threshold** for cross-border B2C digital services. Below this threshold, you can apply your home country's VAT rules (or no VAT if not registered).

**For Bulgaria:** If your total annual B2C sales to EU customers are below €10,000, you can:
- Apply Bulgarian VAT rules (or no VAT if not registered)
- Avoid registering for EU VAT OSS

**This means:** For your first ~€10,000 in EU sales, you have simplified obligations.

**Non-EU customers (US, UK, etc.):** Different rules apply. Generally, you do not charge EU VAT to non-EU customers.

---

## 6. Scenario Comparison Matrix

| Scenario | Income Tax | VAT Obligation | Social Security | Paperwork | Risk Level |
|---|---|---|---|---|---|
| Natural person, Author's Rights, MoR | ~6% effective | None (MoR handles) | Possible | Annual return only | Low-Medium |
| Natural person, Other Income, MoR | ~10% | None (MoR handles) | Possible | Annual return only | Low-Medium |
| Natural person, Direct payment | ~6-10% | Article 97a risk | Possible | Monthly VAT returns | High |
| Self-employed freelancer, MoR | 10% on profit | None (if free tiers) | ~260 BGN/month | Monthly + Annual | Low |
| Self-employed freelancer, Direct | 10% on profit | Article 97a + OSS | ~260 BGN/month | Monthly VAT + Annual | Medium |
| ET (Sole Trader), MoR | 15% on profit | None (if free tiers) | ~260 BGN/month | Monthly + Annual | Low |

---

## 7. Recommended Path — Step by Step

### Phase 1: Test the Market (0–3 sales, up to ~$900)

**Recommended approach:** Natural person + Lemon Squeezy as MoR + Author's Rights declaration

**Steps:**
1. Set up Lemon Squeezy account (free, no monthly fee)
2. Configure your product as a software license
3. Keep ALL foreign services on free tiers (Cloudflare free, Supabase free)
4. Make your first sales
5. Keep records of all income received from Lemon Squeezy
6. At year end, declare income in **Annual Tax Return, Appendix 3** (Author's Rights)
7. Pay 10% tax on 60% of income (40% deduction)
8. No monthly obligations

**Total tax on $900:** ~$54 (6% effective rate)
**Monthly obligations:** None
**Registration required:** None

---

### Phase 2: Growing Business (After Proof of Concept)

**Recommended approach:** Register as self-employed freelancer (Свободна Професия)

**Registration steps:**
1. **Obtain BULSTAT number:**
   - Visit Агенция по вписванията (Registry Agency) office OR apply online at brra.bg
   - Bring: national ID, completed application form
   - Cost: ~10 BGN
   - Time: 1-3 business days

2. **Register with НАП (National Revenue Agency):**
   - Visit local НАП office or use e-services at nap.bg
   - Bring: BULSTAT certificate, national ID
   - Declare start of self-employed activity
   - Cost: Free
   - Time: Same day

3. **Register as self-insured with НОИ:**
   - Submit OKd-5 form to НОИ
   - Choose contribution base (minimum recommended to start)
   - Cost: Free
   - Time: 1-2 business days

4. **Open business bank account (optional but recommended):**
   - Any Bulgarian bank
   - Required for: issuing invoices, receiving payments professionally

5. **Consider VAT registration (Article 97a):**
   - Only if you start using paid foreign services
   - Register at НАП
   - Monthly VIES declarations required

**Monthly obligations after registration:**
- Pay social security by 25th of each month (~260 BGN minimum)
- File monthly/quarterly income declarations if required
- Keep income/expense records

**Annual obligations:**
- Annual tax return by April 30
- Annual social security reconciliation

---

## 8. The Author's Rights Path — Deep Dive

### Can Software Licenses Be Declared as Author's Rights?

**Yes, with important nuances:**

**What qualifies:**
- The software code itself (the NinjaTrader indicator code) is a copyrighted work
- Income from licensing the right to USE the code = author's rights income
- This is explicitly recognized under Bulgarian Copyright Act (ЗАПСП, Article 3)

**What does NOT qualify:**
- Income from providing a service (e.g., custom development)
- Income from selling the code outright (transfer of copyright)
- Income from support/maintenance services

**Your model fits:** You are licensing the right to use your copyrighted code. This is classic author's rights income.

**Documentation to keep:**
- Records showing you are the original author
- Git commit history (proves creation timeline)
- License agreements (even if automated)
- Records of income received

**Potential challenge from НАП:**
- If sales are frequent and systematic, НАП may argue this is a business activity
- Counter-argument: Authors regularly license their works; frequency does not change the nature
- Risk is higher if you have many customers and high revenue

---

## 9. Creative Alternative Routes

### Alternative 1 — Sell Through a Marketplace (Not Your Own Store)

**Idea:** Instead of your own webapp, list your indicator on an established marketplace (NinjaTrader's own ecosystem, CodeForTraders, etc.)

**Benefits:**
- The marketplace may act as MoR
- Reduces your direct sales obligations
- Established trust with NinjaTrader users

**Drawbacks:**
- Less control over pricing and customer relationship
- Marketplace takes a cut
- May not support your custom licensing system

---

### Alternative 2 — Sell as a Subscription (SaaS Model)

**Idea:** Instead of a one-time license, offer a monthly subscription.

**Benefits:**
- Recurring revenue
- Easier to classify as service income
- Better cash flow predictability

**Drawbacks:**
- Customers may prefer one-time purchase
- More complex licensing system needed
- Monthly revenue may trigger earlier VAT registration thresholds

---

### Alternative 3 — Incorporate in a Low-Tax EU Jurisdiction

**Idea:** Register a company in Estonia (e-Residency), Cyprus, or Ireland, and operate through that entity.

**Benefits:**
- Estonia: 0% corporate tax on retained earnings, excellent e-Residency program
- Cyprus: 12.5% corporate tax, EU member
- Clear separation between personal and business income

**Drawbacks:**
- Significant setup cost (€500–€2,000+)
- Annual accounting and compliance costs
- Substance requirements (you must actually operate from there)
- Bulgarian tax residency rules still apply to your personal income
- Complex for small operations

**Verdict:** Overkill for initial testing phase. Consider after reaching €20,000+ annual revenue.

---

### Alternative 4 — Partner with a Bulgarian IT Company

**Idea:** Find a Bulgarian IT company willing to act as your "employer" or "contractor" for a fee. They handle invoicing and VAT; you receive a salary or contractor payment.

**Benefits:**
- Company handles all compliance
- You receive clean income

**Drawbacks:**
- Company takes a cut (typically 10-20%)
- Loss of independence
- Company must trust you and your product
- Unusual arrangement that may raise questions

---

### Alternative 5 — Donate the Code, Sell Support

**Idea:** Make the indicator code completely free and open source. Sell "support packages" or "premium support" instead.

**Benefits:**
- No software license sales = different tax treatment
- Support income is clearly service income
- Builds community and trust

**Drawbacks:**
- Anyone can use the code without paying
- Harder to monetize
- Requires excellent support to justify payment

---

## 10. Risk Assessment Summary

### Gray Area Risks (Natural Person Phase)

| Risk | Probability | Impact | Mitigation |
|---|---|---|---|
| НАП reclassifies income as business activity | Low (for <$1,000) | Medium | Keep sales occasional, document author's rights |
| Article 97a violation (paid foreign services) | Medium | Medium | Stay on free tiers |
| Undeclared income discovered | Low | High | Always declare, even small amounts |
| VAT OSS non-compliance | Low (if using MoR) | Medium | Use MoR to eliminate this risk |

### Self-Employed Phase Risks

| Risk | Probability | Impact | Mitigation |
|---|---|---|---|
| Social security costs exceed income | Medium (early stage) | High | Only register when income justifies it |
| Article 97a triggered by paid services | Medium | Low | Register proactively if using paid services |
| Incorrect income classification | Low | Medium | Consult accountant annually |

---

## 11. Frequently Asked Questions

**Q: Do I need to register for VAT if I use Lemon Squeezy?**
A: If you stay on free tiers for all other foreign services, and Lemon Squeezy's commission is treated as a deduction from sales (not a service fee), you may avoid Article 97a. This is a defensible position for small volumes. Consult a tax advisor before scaling.

**Q: What is the minimum income that requires declaration?**
A: In Bulgaria, ALL income must be declared, regardless of amount. There is no minimum threshold for declaration (though there is a threshold below which no tax is owed, currently 780 BGN/year for employed persons).

**Q: Can I deduct my laptop, internet, and software costs?**
A: Yes, if registered as self-employed. As a natural person declaring author's rights, you use the standard 40% deduction instead of itemized expenses.

**Q: What happens if I don't declare?**
A: НАП can audit you for up to 5 years back. Penalties include the unpaid tax + interest (currently ~10% per year) + administrative fines (up to 100% of unpaid tax for intentional evasion).

**Q: Is the 14-day free trial a problem?**
A: No. Free trials are a standard business practice. They do not create tax obligations until a paid conversion occurs.

**Q: What currency should I use for declarations?**
A: Convert to BGN at the BNB (Bulgarian National Bank) exchange rate on the date of receipt.

---

## 12. Recommended Action Plan

### Immediate (Before First Sale)
- [ ] Set up Lemon Squeezy account
- [ ] Configure product as software license
- [ ] Ensure ALL services remain on free tiers
- [ ] Create simple spreadsheet to track all income

### After First 3 Sales (~$900)
- [ ] Consult a Bulgarian accountant (one-time consultation, ~100-200 BGN)
- [ ] Prepare annual tax return with Appendix 3 (Author's Rights)
- [ ] Evaluate whether to continue as natural person or register

### After Proof of Concept (Consistent Sales)
- [ ] Register as self-employed freelancer (Свободна Професия)
- [ ] Obtain BULSTAT
- [ ] Register as self-insured
- [ ] Consider whether income justifies social security costs
- [ ] Evaluate Article 97a registration if upgrading any foreign services

### At €10,000+ Annual Revenue
- [ ] Consult accountant for full compliance review
- [ ] Consider EU VAT OSS registration
- [ ] Evaluate company formation (Bulgarian OOD or Estonian e-Residency)

---

## 13. Key Bulgarian Tax Contacts and Resources

- **НАП (National Revenue Agency):** nap.bg — tax registration, declarations
- **Агенция по вписванията (Registry Agency):** brra.bg — BULSTAT registration
- **НОИ (National Social Security Institute):** noi.bg — social security registration
- **BNB Exchange Rates:** bnb.bg — for currency conversion

---

## 14. DEEP DIVE — Is Using a MoR (Lemon Squeezy / Paddle) Truly Safe for Article 97a?

> **Short answer:** Probably yes for Lemon Squeezy's commission-only model, with meaningful caveats. Paddle's model has a slightly stronger argument. Neither is 100% guaranteed without a formal ruling. Here is the full legal reasoning.

---

### 14.1 What Article 97a Actually Says

Article 97a of the Bulgarian VAT Act (ЗДДС) reads (paraphrased):

> *A taxable person established in Bulgaria who receives services with a place of supply in Bulgaria from a supplier established outside Bulgaria is obliged to register under this Act before the date on which the tax for the respective supply becomes chargeable.*

**Key elements that must ALL be present to trigger registration:**

1. You are a **taxable person** (физическо или юридическо лице, извършващо независима икономическа дейност)
2. You **receive a service** (получавате услуга)
3. The service is supplied by a **foreign supplier** (доставчик, установен извън България)
4. The **place of supply** is Bulgaria (under the general B2B rule: where the recipient is established)
5. The supply is **taxable** (not exempt)

**The critical question for MoR platforms:** Does using Lemon Squeezy or Paddle constitute "receiving a service" from a foreign supplier?

---

### 14.2 The Legal Structure of MoR Platforms — What Actually Happens

#### Lemon Squeezy (now part of Stripe)

**Legal structure:**
- Lemon Squeezy acts as the **reseller** of your product. They buy your license from you and resell it to the customer.
- The contractual chain is: **You → Lemon Squeezy (reseller) → Customer**
- You grant Lemon Squeezy a non-exclusive right to sell your product
- Lemon Squeezy pays you a **vendor payout** (the sale price minus their commission)
- There is **no separate service agreement** — no monthly fee, no SaaS subscription

**What this means for Article 97a:**
- The relationship is: you are the **supplier** of a license; Lemon Squeezy is the **buyer/reseller**
- You are **not receiving a service** from Lemon Squeezy — you are **selling** to them
- The commission (5% + $0.50) is not a fee you pay — it is a deduction from the resale price
- **Argument: No "service received" = Article 97a is not triggered**

**The counter-argument НАП could make:**
- Lemon Squeezy provides you with a platform, dashboard, API, analytics, payment infrastructure, and customer support tools
- These are clearly "services" in the economic sense
- The commission IS the price for these services, just structured as a deduction rather than an invoice
- Economic substance over legal form: you ARE receiving services, just paying for them indirectly

**Assessment of НАП's counter-argument:**
- This argument has merit but is weaker than it appears
- Bulgarian VAT law follows EU VAT Directive (2006/112/EC), which defines a "supply of services" as any transaction that is not a supply of goods
- The EU VAT Committee and ECJ case law distinguish between **agency/commission arrangements** and **service supplies**
- In a true reseller model (which Lemon Squeezy uses), the platform is not providing a service to the vendor — it is acting as a commercial intermediary
- The commission is consideration for the **resale activity**, not for a service to the vendor

**Verdict for Lemon Squeezy: LOW-MEDIUM RISK**
- The reseller model provides a defensible legal argument
- No formal НАП ruling exists on this specific question (as of 2026)
- Risk is higher if you use Lemon Squeezy's paid add-ons or if they change their model
- Risk is lower if you have zero other paid foreign services

---

#### Paddle

**Legal structure:**
- Paddle operates as a **Merchant of Record** — they are the legal seller to the customer
- Paddle's Terms of Service explicitly state they are the seller; you are the "software vendor"
- Paddle pays you a **reseller revenue share** after deducting their fee
- Like Lemon Squeezy, there is no separate monthly service fee for basic use

**Paddle's additional argument:**
- Paddle is incorporated in the UK (post-Brexit, not EU)
- Paddle has a stronger contractual separation between "reseller relationship" and "service provision"
- Paddle's legal documentation more explicitly frames the relationship as a resale arrangement

**Verdict for Paddle: LOW-MEDIUM RISK (slightly stronger than Lemon Squeezy)**
- Similar analysis to Lemon Squeezy
- Slightly stronger contractual documentation of the reseller relationship
- UK incorporation means different treaty considerations

---

### 14.3 The "Taxable Person" Threshold — A Critical Nuance

Article 97a only applies to **taxable persons** (данъчно задължени лица). Under Bulgarian VAT law (Article 3 ЗДДС), a taxable person is someone who **independently carries out economic activity**.

**If you are a natural person declaring occasional author's rights income:**
- You may NOT qualify as a "taxable person" for VAT purposes
- Occasional, non-systematic activity may fall below the threshold of "independent economic activity"
- **This means Article 97a may not apply to you at all** during the natural person / gray area phase

**The catch:**
- If НАП determines your activity IS systematic (and therefore you ARE a taxable person), Article 97a applies retroactively
- This creates a circular risk: the same determination that makes you a taxable person also triggers Article 97a

**Practical implication:**
- During Phase 1 (natural person, occasional sales), Article 97a risk is LOW because you may not be a taxable person
- Once you register as self-employed (Свободна Професия), you ARE definitively a taxable person, and Article 97a analysis becomes critical

---

### 14.4 The "Free Service" Argument — Does It Hold?

The existing guide mentions that free-tier services don't trigger Article 97a. This is correct but needs precision:

**Why free services don't trigger Article 97a:**
- Article 97a requires a **taxable supply** — a supply made for consideration
- A genuinely free service (no payment, no obligation, no future commitment) is not a taxable supply
- Therefore, using Cloudflare free tier, Supabase free tier, GitHub free tier = no taxable supply = no Article 97a trigger

**The nuance with "freemium" models:**
- Some "free" tiers include implicit obligations (data sharing, usage limits that push you to upgrade)
- These are still generally considered non-taxable for VAT purposes
- The key test: **is there monetary consideration?** If no money changes hands, no VAT supply

**Applying this to Lemon Squeezy/Paddle:**
- If the commission is treated as a deduction from the resale price (not a fee you pay), then you are not paying for a service
- The "free service" argument and the "reseller model" argument converge: either way, you are not paying for a service from a foreign supplier

---

### 14.5 Practical Risk Matrix for MoR + Article 97a

| Scenario | Article 97a Risk | Reasoning |
|---|---|---|
| Natural person + Lemon Squeezy, no other paid foreign services | Very Low | May not be taxable person; reseller model argument |
| Natural person + Lemon Squeezy + paid Cloudflare | High | Paid foreign service clearly triggers Art. 97a |
| Self-employed + Lemon Squeezy, no other paid foreign services | Low-Medium | Taxable person confirmed; reseller argument still applies |
| Self-employed + Lemon Squeezy + paid Stripe directly | High | Stripe is clearly a service provider, not a reseller |
| Self-employed + Paddle, no other paid foreign services | Low-Medium | Same as Lemon Squeezy; slightly stronger reseller docs |
| Self-employed + Paddle + paid add-ons | Medium-High | Paid add-ons = clear service receipt |

---

### 14.6 What Would Make This 100% Safe?

**Option 1: Obtain a written ruling from НАП (Данъчно-осигурително процесуален кодекс, Art. 17)**
- You can request a binding written opinion from НАП on your specific situation
- Cost: Free (but requires detailed written request)
- Time: 30-60 days
- НАП is bound by their own ruling if you follow the described facts
- **This is the gold standard for certainty**

**Option 2: Register under Article 97a proactively**
- Register, file monthly VIES returns (even if zero)
- Eliminates all risk
- Cost: ~2-4 hours/month of paperwork
- No financial cost (you don't pay VAT, just report)

**Option 3: Use a Bulgarian accountant's written opinion**
- Not binding on НАП, but demonstrates good faith
- Reduces penalty risk if НАП later disagrees
- Cost: ~200-500 BGN for a formal written opinion

---

### 14.7 Final Verdict on MoR + Article 97a

**For Lemon Squeezy and Paddle specifically:**

✅ **The reseller model argument is legally sound and defensible**
✅ **No separate monthly fee = no clear "service received"**
✅ **During natural person phase, you may not even be a taxable person**
⚠️ **No formal НАП ruling exists — this remains a gray area**
⚠️ **If НАП audits and disagrees, penalties apply retroactively**
⚠️ **Risk increases if you use ANY other paid foreign service simultaneously**

**Recommended approach:**
1. Use Lemon Squeezy or Paddle with zero other paid foreign services → proceed with confidence
2. If you add any paid foreign service → register under Article 97a immediately
3. If you want certainty → request a written ruling from НАП before scaling

---

## 15. DEEP DIVE — Can Author's Rights Be Used for Extended/Ongoing Periods?

> **Short answer:** Yes, legally there is no time limit on author's rights income. But in practice, НАП becomes increasingly likely to challenge the classification as sales become regular and systematic. Here is the full analysis.

---

### 15.1 The Legal Framework — No Time Limit in the Law

**Bulgarian Copyright Act (ЗАПСП, Закон за авторското право и сродните му права):**
- Copyright in software lasts for the **author's lifetime + 70 years** (Article 27 ЗАПСП)
- There is **no provision** limiting how long you can license your copyrighted work
- An author can license their work for decades and still receive author's rights income

**Bulgarian Income Tax Act (ЗДДФЛ, Article 35):**
- Article 35 defines author's rights income as income from "transfer of rights of intellectual property"
- There is **no time limit** or **frequency limit** in the statute
- The law does not say "only for the first year" or "only for occasional sales"

**Conclusion from the law itself:** Author's rights income classification has no statutory time limit. You could theoretically declare software license income as author's rights for 10 years.

---

### 15.2 The "Systematic Activity" Problem — Where It Breaks Down

Despite the lack of a statutory time limit, there is a practical limit driven by a different legal concept: **systematic economic activity**.

**The key distinction in Bulgarian law:**

| Concept | Legal basis | Tax treatment |
|---|---|---|
| Occasional author's rights income | ЗДДФЛ Art. 35 | 10% tax on 60% of income (40% deduction) |
| Systematic self-employment activity | ЗДДФЛ Art. 29 | 10% tax on 75% of income (25% deduction) |
| Business activity (ET/OOD) | ЗКПО / ЗДДФЛ | 10-15% on profit after expenses |

**The "systematic" threshold:**
- Bulgarian law does not define "systematic" with a specific number of transactions or revenue amount
- НАП uses a facts-and-circumstances test
- Factors НАП considers:

| Factor | Suggests "Occasional" | Suggests "Systematic/Business" |
|---|---|---|
| Frequency of sales | Rare, irregular | Regular, predictable |
| Number of customers | Few | Many |
| Revenue amount | Small | Large |
| Marketing activity | None/minimal | Active marketing, website, ads |
| Infrastructure | None | Dedicated website, payment system |
| Duration | Short period | Ongoing for years |
| Primary income source | Secondary income | Primary income |

**Your situation (NinjaTrader indicator with a dedicated Next.js webapp):**
- You have a dedicated website → suggests systematic activity
- You have a custom licensing system → suggests systematic activity
- You have a 14-day trial → suggests systematic activity (marketing infrastructure)
- These factors push toward "systematic" even from the first sale

---

### 15.3 НАП's Practical Enforcement — What Actually Happens

**Reality check on НАП enforcement:**

НАП's audit capacity is limited. In practice:
- Small amounts (under ~5,000 BGN/year) are rarely audited
- НАП focuses on larger undeclared income
- If you **declare** the income (even as author's rights), you are in a much better position than if you don't declare at all
- НАП is more likely to accept a reasonable classification than to challenge a declared return for small amounts

**When НАП is more likely to challenge:**
- Revenue exceeds ~10,000-20,000 BGN/year from the same source
- You have been declaring author's rights for 3+ consecutive years from the same product
- The activity clearly looks like a business (website, marketing, customer support)
- You have not registered as self-employed despite obvious systematic activity

**НАП's typical response to a challenge:**
1. Issue a notice requesting clarification of income classification
2. If you cannot justify author's rights classification, reclassify as self-employment income
3. Assess additional tax (difference between 6% effective and 10% on 75%)
4. Add interest (currently ~10%/year on unpaid tax)
5. Administrative fine (typically 10-100% of additional tax)

**The financial impact of reclassification:**
```
Example: $5,000/year declared as author's rights for 3 years
Author's rights tax paid: $5,000 × 60% × 10% = $300/year × 3 = $900 total

If reclassified as self-employment:
Self-employment tax: $5,000 × 75% × 10% = $375/year × 3 = $1,125 total

Additional tax: $1,125 - $900 = $225
Interest (3 years at 10%): ~$67
Fine (50% of additional tax): ~$112
Total additional cost: ~$404 on $15,000 of income

This is manageable — not catastrophic
```

---

### 15.4 The "Author" vs. "Entrepreneur" Distinction — The Core Legal Argument

The strongest argument for maintaining author's rights classification over time:

**The nature of the income does not change based on frequency:**
- A musician who licenses their song 1,000 times still receives author's rights income
- A photographer who sells 500 stock photos still receives author's rights income
- A software developer who licenses their code to 100 customers still receives author's rights income

**The key is the NATURE of the transaction, not the frequency:**
- You are licensing the right to use a copyrighted work
- You are NOT providing a service
- You are NOT selling goods
- The transaction is always: "I grant you a license to use my copyrighted software"

**Supporting legal argument:**
- ЗАПСП (Copyright Act) Article 36: "The author has the exclusive right to use the work and to authorize its use by other persons"
- This right is perpetual (subject to copyright term)
- Exercising this right repeatedly does not transform it into a "business activity"

**The counter-argument НАП uses:**
- The systematic exploitation of intellectual property for commercial gain IS a business activity
- The existence of a commercial website, payment system, and marketing infrastructure demonstrates business intent
- The author's rights provision was designed for occasional, non-commercial licensing — not for running a software business

---

### 15.5 Year-by-Year Risk Assessment

| Year | Revenue Level | Risk of Challenge | Recommended Action |
|---|---|---|---|
| Year 1 | Under $3,000 | Very Low | Declare as author's rights, Appendix 3 |
| Year 2 | Under $5,000 | Low | Continue author's rights; consult accountant |
| Year 3 | Under $10,000 | Low-Medium | Consider registering as self-employed |
| Year 3+ | Over $10,000 | Medium | Register as self-employed; author's rights becomes risky |
| Any year | Over $20,000 | High | Must register; author's rights not defensible at this scale |

**The inflection point:** Around Year 2-3 with consistent sales, the risk/reward calculation shifts. The tax savings from author's rights (6% vs. 10%) become less valuable than the legal certainty of proper self-employment registration.

---

### 15.6 The Social Security Dimension — A Hidden Trap

**Critical issue with long-term author's rights classification:**

If you declare author's rights income for multiple years WITHOUT registering as self-employed, you may face a social security problem:

**The rule:** Natural persons who earn income from "independent economic activity" (including author's rights in some interpretations) may owe social security contributions.

**НОИ's position:**
- If your author's rights income is your primary income source
- And you are not insured elsewhere (not employed)
- You may be required to pay social security contributions retroactively

**The trap:**
- You save on income tax by using author's rights (6% vs. 10%)
- But you may owe social security contributions that exceed the tax savings
- НОИ can assess contributions for up to 5 years back

**Mitigation:**
- If you are employed full-time elsewhere, your employer covers your social security — author's rights income does not create additional social security obligations (up to certain limits)
- If you are NOT employed elsewhere, consult a social security specialist before year 2

---

### 15.7 The "Hybrid" Strategy — Best of Both Worlds

**Recommended approach for extended periods:**

**Phase 1 (Year 1, under $3,000):**
- Natural person + author's rights + MoR
- Declare in Appendix 3
- No registration required
- Effective tax: ~6%

**Phase 2 (Year 2-3, $3,000-$15,000):**
- Register as self-employed (Свободна Професия)
- Continue using MoR (Lemon Squeezy/Paddle)
- Declare income in Appendix 2 (self-employment income)
- Deduct 25% standard deduction OR actual expenses
- Effective tax: ~7.5% (10% on 75%) + social security
- **BUT:** Social security contributions are now fixed and predictable

**Why this is better than extending author's rights:**
- Legal certainty: no risk of reclassification
- Social security is paid and accounted for
- You can deduct actual expenses (hosting, software, equipment)
- If actual expenses exceed 25%, you pay even less tax
- Professional credibility with customers and banks

**The math comparison at $10,000/year:**

| Approach | Income Tax | Social Security | Total Cost | Risk |
|---|---|---|---|---|
| Author's rights (natural person) | $600 (6%) | Uncertain/possible | $600-$1,500 | Medium |
| Self-employed freelancer | $750 (7.5%) | ~$1,600/year fixed | $2,350 | Low |
| Self-employed with actual expenses | $500-$700 | ~$1,600/year fixed | $2,100-$2,300 | Low |

**Conclusion:** At $10,000/year, the social security cost dominates. Author's rights saves ~$150 in income tax but carries reclassification risk and uncertain social security exposure. Self-employment is cleaner.

---

### 15.8 Special Case — What If You Are Employed Full-Time Elsewhere?

**This changes the analysis significantly:**

If you have a full-time job in Bulgaria:
- Your employer pays your social security (up to the maximum contribution base)
- Author's rights income does NOT trigger additional social security (up to the annual maximum base)
- You can declare author's rights income for years without social security concerns
- The 6% effective tax rate is genuinely achievable with low risk

**In this scenario, author's rights classification is MORE defensible for longer periods:**
- You are clearly not relying on software sales as your primary income
- The "occasional" nature is more credible
- НАП is less likely to challenge a secondary income source

**Practical limit even in this scenario:**
- If software income exceeds your employment income, НАП may question the "secondary" characterization
- If software income exceeds ~30,000 BGN/year, registration becomes advisable regardless

---

### 15.9 Final Verdict on Author's Rights for Extended Periods

**Can you use author's rights for multiple years?**

✅ **Legally: Yes — no statutory time limit**
✅ **Practically: Yes for 1-2 years at low revenue**
✅ **If employed elsewhere: Yes for longer, with higher revenue tolerance**
⚠️ **Risk increases significantly after Year 2-3 with consistent sales**
⚠️ **Social security exposure is the hidden risk, not just income tax**
❌ **Not advisable as primary income source beyond Year 2 without registration**
❌ **Not defensible at $20,000+/year regardless of duration**

**The bottom line:**
- Author's rights is a legitimate, legal classification for software license income
- It is not a "hack" or "loophole" — it is the correct classification for what you are doing
- The risk is not that the classification is wrong, but that НАП may disagree about whether your activity is "occasional" or "systematic"
- The longer you use it and the more revenue you generate, the more that risk grows
- The smart strategy is to use it for Phase 1, then transition to self-employment registration before the risk becomes significant

---

## 16. COMPREHENSIVE DEFENSIBLE STRATEGY — Traffic-Light Risk Classification

> This section synthesizes everything in the guide, fills gaps not covered elsewhere, and gives you a clear GREEN / AMBER / RED classification for every decision point. It also covers what to do with your website, domain, bank account, and MoR when transitioning between phases.

---

### 16.1 The Master Traffic-Light Table

| Decision / Action | Risk Level | Classification | Notes |
|---|---|---|---|
| Use Lemon Squeezy as MoR, no other paid foreign services | 🟢 GREEN | OK | Reseller model; no service received |
| Use Paddle as MoR, no other paid foreign services | 🟢 GREEN | OK | Same as above; slightly stronger docs |
| Stay on all free tiers (Cloudflare, Supabase, GitHub) | 🟢 GREEN | OK | No taxable foreign service supply |
| Declare income as Author's Rights, Year 1, under $3,000 | 🟢 GREEN | OK | Correct legal classification; low audit risk |
| Declare income as Author's Rights, Year 2, under $5,000 | 🟢 GREEN | OK | Still defensible; document everything |
| Receive MoR payouts to personal Bulgarian bank account | 🟢 GREEN | OK | No legal requirement for business account in Phase 1 |
| Use a .com domain registered in your personal name | 🟢 GREEN | OK | Domain registration alone does not create tax obligations |
| Have a public website selling your product | 🟡 AMBER | Gray | Website is evidence of systematic activity; acceptable if income is low |
| Declare income as Author's Rights, Year 3+, $5,000-$15,000 | 🟡 AMBER | Gray | Increasing НАП challenge risk; consider registering |
| Use Lemon Squeezy + one paid foreign service (e.g., paid email) | 🟡 AMBER | Gray | Paid service triggers Art. 97a obligation |
| Receive payouts to a foreign bank account (Wise, Revolut) | 🟡 AMBER | Gray | Legal but may complicate declaration; use BNB rate on receipt date |
| Not declaring income at all | 🔴 RED | Too Risky | НАП can audit 5 years back; criminal exposure above certain thresholds |
| Using Stripe directly (you are MoR) without VAT registration | 🔴 RED | Too Risky | You become responsible for EU VAT from first sale |
| Upgrading to paid Cloudflare/Supabase without Art. 97a registration | 🔴 RED | Too Risky | Clear Art. 97a violation; monthly returns required retroactively |
| Declaring author's rights income for 5+ years as primary income | 🔴 RED | Too Risky | НАП will reclassify; social security exposure compounds |
| Operating as natural person with $20,000+/year revenue | 🔴 RED | Too Risky | Scale makes "occasional" classification indefensible |

---

### 16.2 Gaps in the Existing Guide — Addressed Here

#### Gap 1: Appendix 3 vs. Appendix 8 — Which One for MoR Payouts?

**The conflict:** The guide mentions both Appendix 3 (Author's Rights) and Appendix 8 (Foreign Income) for MoR payouts. Which is correct?

**The answer depends on how you frame the relationship:**

**Option A — Appendix 3 (Author's Rights):**
- You frame the MoR payout as income from licensing your copyrighted software
- The MoR is just the collection mechanism; the underlying income is author's rights
- **Argument:** The economic substance is a software license; the MoR is just the payment channel
- **Risk:** НАП may question why you're using Appendix 3 for income from a foreign company

**Option B — Appendix 8 (Income from Abroad):**
- You frame the payout as income received from a foreign company (Lemon Squeezy/Paddle)
- The income is from a foreign source, regardless of its underlying nature
- **Argument:** The payer is a foreign entity; Appendix 8 is the correct form for foreign-source income
- **Risk:** Appendix 8 income does not automatically get the 40% author's rights deduction

**The correct approach:**
- **Use Appendix 3 AND note the foreign source** — the 40% deduction applies to author's rights income regardless of whether the payer is Bulgarian or foreign
- The key is the **nature of the income** (author's rights), not the **source** (foreign company)
- Consult your accountant on the specific form layout, but the 40% deduction should be preserved

**Practical documentation:**
- Keep the Lemon Squeezy/Paddle payout statements showing the underlying product sales
- These prove the income is from software license sales (author's rights), not from providing services to the MoR

---

#### Gap 2: Bulgarian Customers — Domestic VAT Implications

**The guide focuses on EU/international customers. What about Bulgarian customers?**

**If you sell to a Bulgarian customer:**
- As a natural person (not VAT registered): no VAT obligation — you are below the Bulgarian VAT registration threshold (100,000 BGN/year for domestic sales)
- As a self-employed person (not VAT registered): same — no VAT on domestic sales until you hit the 100,000 BGN threshold
- The EU VAT OSS rules do NOT apply to domestic Bulgarian sales

**The threshold difference:**
- EU cross-border B2C digital services: €10,000 threshold (EU OSS)
- Bulgarian domestic sales: 100,000 BGN (~€51,000) threshold
- **You are far more likely to hit the EU threshold first**

**Practical implication:** Bulgarian customers are not a special problem. Treat them the same as other customers through your MoR.

---

#### Gap 3: Invoice/Receipt Obligations as a Natural Person

**The guide doesn't address whether you need to issue invoices.**

**As a natural person (not registered as self-employed):**
- You are NOT required to issue VAT invoices (you are not VAT registered)
- You are NOT required to issue commercial invoices (you are not a trader)
- The MoR (Lemon Squeezy/Paddle) issues invoices to customers on your behalf
- **You only need to keep records of income received** (bank statements, MoR payout reports)

**As a self-employed person (Свободна Професия):**
- You ARE required to issue invoices for services/licenses you provide
- However, if the MoR is the legal seller, the MoR issues invoices — you issue an invoice to the MoR for your "vendor payout"
- In practice, many self-employed developers using MoR platforms do not issue formal invoices to the MoR; the payout statement serves as documentation
- **Consult your accountant** on whether a formal invoice to the MoR is required

---

#### Gap 4: GDPR and Data Protection

**Selling to EU customers means GDPR applies to you.**

**Minimum GDPR obligations for a solo developer:**
- **Privacy Policy** on your website (required — describes what data you collect and why)
- **Cookie consent** if you use analytics or tracking cookies
- **Data Processing Agreement (DPA)** with your MoR (Lemon Squeezy/Paddle provide these)
- **Right to erasure** — if a customer asks you to delete their data, you must comply

**What data do you actually collect?**
- Email addresses (for license delivery)
- Payment data (handled entirely by MoR — you never see card numbers)
- Usage data (if your licensing system phones home)

**GDPR risk for a solo developer:**
- Low for small operations
- The main risk is not having a Privacy Policy
- Fines are theoretically up to 4% of global annual turnover, but enforcement against small operators is rare
- **Action:** Add a Privacy Policy page to your website before first sale

**GDPR does NOT affect your tax situation** — it is a separate compliance area.

---

#### Gap 5: The Website and Domain as Evidence

**Does having a professional website hurt your "occasional activity" argument?**

**The honest answer: Yes, somewhat. But it's manageable.**

**What a website signals to НАП:**
- You have invested time/money in infrastructure → suggests systematic intent
- You have a checkout flow → suggests commercial activity
- You have a 14-day trial system → suggests ongoing business operation
- You have a custom domain → suggests professional/commercial intent

**Counter-arguments:**
- Many authors have websites to distribute their works (musicians, writers, photographers)
- Having a website does not automatically make you a "trader" under Bulgarian law
- The website is the distribution mechanism for a copyrighted work, not evidence of a business

**Practical mitigation:**
- Do NOT put "business" language on your website in Phase 1 (avoid "company," "enterprise," "business")
- DO use "author," "creator," "developer" language
- Keep the website simple — a landing page, not a full e-commerce operation
- Avoid running paid ads (Google Ads, Facebook Ads) in Phase 1 — this is strong evidence of systematic commercial activity

**Domain registration:**
- Register the domain in your personal name (not a company name)
- Use a personal email for domain registration
- This is consistent with "individual author" framing

---

#### Gap 6: Bank Account Strategy

**Which bank account should you use for MoR payouts?**

**Phase 1 (Natural Person):**
- **Personal Bulgarian bank account** — completely legal and appropriate
- MoR payouts to a personal account are normal for individual vendors
- No requirement for a business account
- **Recommended:** Use a separate personal account (not your main salary account) to keep income clearly separated for declaration purposes

**Alternative: Wise or Revolut (foreign e-money accounts):**
- Legal to use
- Payouts in USD/EUR before converting to BGN
- **Complication:** You must convert to BGN at the BNB rate on the date of receipt for tax declaration purposes
- Wise/Revolut provide transaction history — keep this for your records
- **Risk:** НАП may scrutinize foreign accounts more carefully; not a legal problem but adds complexity

**Phase 2 (Self-Employed):**
- A dedicated business bank account is strongly recommended (not legally required for Свободна Професия, but practically important)
- Keeps business and personal finances separate
- Required if you want to issue formal invoices
- **Recommended Bulgarian banks for freelancers:** DSK Bank, Fibank, UniCredit — all offer accounts for self-employed persons

**Phase 3 (OOD/Company):**
- A company bank account is legally required
- Must be in the company's name
- Cannot use personal accounts for company transactions

---

#### Gap 7: The Lemon Squeezy / Stripe Acquisition

**Lemon Squeezy was acquired by Stripe in 2024. Does this change the analysis?**

**What changed:**
- Lemon Squeezy is now a Stripe product
- The underlying legal entity may have changed
- Terms of Service may be updated

**What did NOT change:**
- The MoR model — Lemon Squeezy still acts as the reseller/MoR
- The commission structure (5% + $0.50)
- The fundamental legal relationship between vendor and platform

**Practical implication:**
- Check Lemon Squeezy's current Terms of Service to confirm they still operate as MoR
- If they have shifted to a "payment facilitator" model (like Stripe itself), the analysis changes — you would become the MoR
- As of early 2026, Lemon Squeezy continues to operate as MoR

**Paddle as the safer alternative:**
- Paddle is independent (not acquired by a payment processor)
- Paddle's MoR model is more explicitly documented
- Paddle has a longer track record as MoR for software vendors
- **If uncertain about Lemon Squeezy's post-acquisition status, use Paddle**

---

#### Gap 8: What Happens at the "Free Trial Converts to Paid" Moment?

**When does the tax obligation arise?**

**The rule:** Tax obligation arises when you receive income (cash basis for natural persons in Bulgaria).

**For a 14-day free trial:**
- During the trial: no income, no tax obligation
- When the customer pays for a license: income arises on the date of payment
- The MoR collects payment; you receive a payout (typically monthly or weekly)
- **Tax obligation arises on the date you receive the payout from the MoR**, not the date the customer paid

**Practical implication:**
- If a customer pays in December but you receive the MoR payout in January, the income is in January (next tax year)
- Keep records of payout dates, not customer payment dates

---

#### Gap 9: Bulgarian OOD — The Underanalyzed Option

**The guide mentions OOD briefly but doesn't analyze it as a viable path.**

**What is an OOD (Дружество с ограничена отговорност)?**
- Bulgarian equivalent of a Limited Liability Company (LLC)
- Separate legal entity from you personally
- Limited liability: your personal assets are protected

**Tax treatment of OOD:**
- Corporate income tax: **10%** (one of the lowest in the EU)
- Dividend tax when you pay yourself: **5%**
- Combined effective rate: **14.5%** (10% corporate + 5% dividend on remaining 90%)
- Compare to self-employed: **10%** income tax + social security (~27.8%)

**When OOD becomes attractive:**
- Revenue exceeds ~€15,000-20,000/year
- You want liability protection
- You want to retain earnings in the company (0% tax on retained earnings until distributed)
- You want to hire employees or contractors

**OOD setup costs:**
- Registration: ~500-1,000 BGN (lawyer + state fees)
- Minimum capital: 2 BGN (yes, two leva)
- Annual accounting: ~1,500-3,000 BGN/year (mandatory for OOD)
- Annual financial statement: required, filed with Commercial Register

**OOD and Article 97a:**
- An OOD is definitively a "taxable person" — Article 97a applies from the first paid foreign service
- However, an OOD can register for full VAT (not just Art. 97a limited registration) and reclaim input VAT
- This makes paid foreign services less painful — you pay VAT but get it back

**OOD and MoR:**
- The OOD signs the vendor agreement with Lemon Squeezy/Paddle
- Payouts go to the OOD's bank account
- The OOD declares the income as corporate revenue
- You pay yourself a salary or dividends

**Verdict:** OOD is the right structure for €15,000+/year. Below that, the accounting costs eat into the tax savings.

---

#### Gap 10: Crypto Payments — Should You Accept Them?

**Some traders prefer crypto. Should you accept it?**

**Short answer: No, not in Phase 1 or 2.**

**Why crypto is problematic:**
- Crypto income is taxable in Bulgaria (НАП has issued guidance)
- Each crypto transaction creates a taxable event
- You must track the BGN value at the time of receipt
- Crypto-to-fiat conversion is another taxable event
- No MoR handles crypto payments with the same legal protection as fiat MoRs
- Significantly increases accounting complexity

**If you want to accept crypto eventually:**
- Only after registering as self-employed or forming an OOD
- Use a dedicated crypto accounting tool (Koinly, CoinTracker)
- Consult a Bulgarian accountant with crypto experience
- Consider using a crypto payment processor that converts to fiat immediately (BitPay, Coinbase Commerce)

---

### 16.3 The "Easily Defensible" Strategy — Concrete Implementation

This is the strategy that minimizes risk while maximizing simplicity. Every element is chosen for defensibility.

#### Phase 1: The Defensible Gray Zone (Year 1, under $5,000)

**Legal structure:** Natural person (no registration)
**Payment:** Paddle as MoR (slightly stronger MoR documentation than Lemon Squeezy post-acquisition)
**Website:** Simple landing page, personal domain, "author" language
**Bank account:** Separate personal Bulgarian bank account
**Foreign services:** ALL on free tiers — zero exceptions
**Income declaration:** Appendix 3 (Author's Rights), 40% deduction, ~6% effective tax
**Documentation to maintain:**
- Git commit history showing you are the original author
- Paddle payout statements (monthly)
- Simple spreadsheet: date received, amount in USD, BNB rate, amount in BGN
- Screenshot of your Paddle vendor agreement

**Why this is defensible:**
- Paddle is the legal seller — you are not collecting payments
- No paid foreign services — Article 97a cannot be triggered
- Author's rights is the correct legal classification for software license income
- You are declaring all income — no evasion argument
- The 40% deduction is statutory — НАП cannot challenge it

**What to avoid in Phase 1:**
- ❌ Running paid ads (Google Ads, Facebook Ads, Twitter/X Ads)
- ❌ Upgrading ANY foreign service to a paid tier
- ❌ Accepting payments directly (bypassing MoR)
- ❌ Registering a company name or trademark in Phase 1
- ❌ Hiring anyone (employees, contractors)

---

#### Phase 2: The Clean Transition (Year 2-3, $5,000-$20,000)

**Trigger for transition:** When you have consistent monthly sales (3+ consecutive months of sales), OR when annual income exceeds $5,000, whichever comes first.

**What changes:**
1. **Register as self-employed (Свободна Професия)**
   - Obtain BULSTAT
   - Register with НАП
   - Register as self-insured with НОИ
   - Open a dedicated business bank account

2. **Update your Paddle account** to reflect your BULSTAT number (business registration)

3. **Update your website** — you can now use more professional/business language

4. **Income declaration changes** — from Appendix 3 to Appendix 2 (self-employment income)

5. **Consider upgrading services** — once registered, you can upgrade to paid tiers and register under Article 97a if needed

**What does NOT need to change:**
- Your domain — keep the same domain
- Your website — same site, just update the legal footer
- Your MoR — keep Paddle (or switch to Lemon Squeezy if preferred)
- Your product — same NinjaTrader indicator

**The transition is invisible to customers** — they see no change.

---

#### Phase 3: The Professional Structure ($20,000+/year)

**Legal structure:** Bulgarian OOD
**Payment:** Paddle or Lemon Squeezy (MoR agreement in OOD's name)
**Bank account:** OOD business account
**VAT:** Register for full VAT (not just Art. 97a) — allows input VAT reclaim
**Accounting:** Hire a Bulgarian accountant (~150-250 BGN/month)

**What changes from Phase 2:**
- New legal entity (OOD) — requires new Paddle/Lemon Squeezy vendor account
- New bank account in OOD's name
- New domain registration (optional — can keep personal domain, just update legal footer)
- New Privacy Policy and Terms of Service reflecting the OOD

**What does NOT need to change:**
- Your website content
- Your product
- Your customer relationships

---

### 16.4 The "What Is Really Gray" Classification

#### Genuinely Gray (Defensible but Uncertain)

1. **MoR commission as "not a service received"** — legally sound argument, but no НАП ruling
2. **Author's rights for Year 2-3 with consistent sales** — correct classification, but "systematic" risk grows
3. **Using Wise/Revolut for payouts** — legal, but adds complexity and НАП scrutiny
4. **Appendix 3 vs. Appendix 8 for MoR payouts** — both have arguments; Appendix 3 is more favorable

#### Clearly OK (Green Light)

1. **Paddle/Lemon Squeezy as MoR with zero paid foreign services** — defensible and practical
2. **Author's rights for Year 1, under $3,000** — correct classification, low audit risk
3. **Personal bank account for Phase 1 payouts** — completely normal
4. **Free tier foreign services** — no taxable supply, no Article 97a
5. **14-day free trial** — standard practice, no tax implications until conversion
6. **Declaring all income** — always the right move, even if classification is uncertain

#### Too Risky (Red Light)

1. **Not declaring income** — НАП audit risk + criminal exposure above ~5,000 BGN undeclared
2. **Being your own MoR (Stripe direct) without VAT registration** — EU VAT liability from first sale
3. **Upgrading to paid foreign services without Art. 97a registration** — clear violation
4. **Author's rights as primary income for 5+ years** — social security trap + reclassification risk
5. **Accepting payments to a foreign company you control** — substance requirements, CFC rules
6. **Crypto payments in Phase 1** — complexity far exceeds benefit

---

## 17. WORST-CASE SCENARIO ANALYSIS

> What actually happens if everything goes wrong? Understanding the worst case helps you calibrate how much risk is acceptable.

---

### 17.1 Scenario: НАП Audits You After 3 Years of Author's Rights Declarations

**Trigger:** НАП receives information about your income (bank reports, Paddle/Lemon Squeezy reporting, or random audit selection).

**НАП's process:**
1. Issue a notice (Акт за установяване на задължение) requesting documentation
2. You have 14 days to respond with documentation
3. НАП reviews your documentation and income classification
4. If they disagree with your classification, they issue a revised assessment

**Worst case outcome:**
```
3 years of income: $15,000 total ($5,000/year)
Declared as author's rights: $15,000 × 60% × 10% = $900 tax paid

НАП reclassifies as self-employment income:
Revised tax: $15,000 × 75% × 10% = $1,125
Additional income tax: $225

Social security (if not insured elsewhere):
3 years × ~3,120 BGN/year = ~9,360 BGN (~$5,000)
Interest on social security: ~$1,500
Fine on social security: ~$500-$2,500

Total worst-case additional cost: ~$7,000-$9,000 on $15,000 of income
```

**This is painful but not catastrophic.** You would still have kept ~$6,000-$8,000 after all costs.

**Mitigating factors:**
- If you are employed elsewhere, social security is already covered — the worst case drops to ~$500-$1,000
- If you cooperate with НАП and pay promptly, fines are typically at the lower end
- If you have good documentation (git history, license agreements, payout statements), the income tax reclassification is less likely

---

### 17.2 Scenario: Article 97a Violation Discovered

**Trigger:** You accidentally upgraded to a paid Cloudflare plan and forgot to register under Article 97a.

**НАП's process:**
1. НАП discovers the paid foreign service (typically through bank records or VAT information exchange)
2. НАП issues a notice of non-registration
3. You must register retroactively and file all missing monthly returns

**Worst case outcome:**
```
1 year of paid Cloudflare ($20/month = $240/year)
VAT on foreign services received: $240 × 20% = $48 (self-assessed VAT)
Fine for late registration: 500-5,000 BGN
Fine for each missing monthly return: 100-500 BGN × 12 = 1,200-6,000 BGN
Interest on unpaid VAT: minimal (VAT amount is small)

Total worst-case: ~2,000-11,000 BGN (~$1,000-$5,500)
```

**This is disproportionate to the underlying tax amount.** The fines for non-registration are much larger than the actual VAT owed.

**Key insight:** Article 97a violations are punished more harshly than income tax misclassification. The fines for non-registration are fixed administrative penalties, not proportional to the tax amount.

**Mitigation:** Register under Article 97a BEFORE upgrading any foreign service. The registration itself is free and takes one day.

---

### 17.3 Scenario: You Never Declare Anything

**This is the true worst case.**

**НАП's tools for discovering undeclared income:**
- Bank account monitoring (НАП has access to Bulgarian bank data)
- Foreign bank/payment processor reporting (EU DAC7 directive requires platforms to report vendor income)
- Customs and border control data
- Anonymous tips
- Cross-referencing with social media / website presence

**DAC7 — The Game Changer:**
The EU DAC7 directive (implemented in Bulgaria from 2023) requires digital platforms (including Lemon Squeezy, Paddle, and similar) to report vendor income to tax authorities. This means:
- Lemon Squeezy/Paddle MUST report your income to Bulgarian tax authorities
- НАП will know about your income even if you don't declare it
- **There is no hiding income from MoR platforms**

**Worst case for 3 years of undeclared income ($15,000):**
```
Income tax owed: ~$900-$1,125
Interest (3 years at 10%/year): ~$270-$340
Administrative fine (intentional evasion): up to 100% of tax = ~$900-$1,125
Social security (if not insured): ~$5,000
Criminal threshold: 3,000 BGN (~$1,500) undeclared tax triggers criminal investigation

Total worst case: ~$7,000-$8,000 + potential criminal charges
```

**Criminal exposure:**
- Under Bulgarian Criminal Code (НК), tax evasion above 3,000 BGN is a criminal offense
- Penalty: up to 3 years imprisonment (suspended sentence typical for first offense)
- Criminal record affects future employment, travel, banking

**This is the scenario to avoid at all costs.** Declaring income — even with an imperfect classification — is always better than not declaring.

---

### 17.4 Scenario: You Use Stripe Directly (No MoR) Without VAT Registration

**What happens:**
- You are the Merchant of Record
- You are responsible for EU VAT on all B2C sales to EU customers
- EU VAT rates vary: 17-27% depending on country
- You must register for EU VAT OSS (One-Stop Shop) in Bulgaria

**Worst case for $10,000 in EU sales:**
```
Average EU VAT rate: ~21%
VAT owed on EU sales: $10,000 × 21% = $2,100
Fine for non-registration: 500-5,000 BGN
Fine for each missing quarterly OSS return: 100-500 BGN × 4 = 400-2,000 BGN
Interest: ~$630

Total worst case: ~$3,500-$5,000 on $10,000 of sales
```

**Plus:** Each EU country where you have customers could theoretically audit you separately. In practice, OSS centralizes this, but the theoretical exposure is significant.

**This is why using a MoR is so important.** The MoR absorbs all of this risk for 5% + $0.50 per transaction.

---

### 17.5 Risk-Adjusted Summary

| Scenario | Worst Case Cost | Probability | Expected Cost |
|---|---|---|---|
| Author's rights for 3 years, employed elsewhere | ~$500-$1,000 | Low | ~$100 |
| Author's rights for 3 years, not employed | ~$7,000-$9,000 | Low-Medium | ~$1,500 |
| Art. 97a violation (one paid service) | ~$1,000-$5,500 | Medium | ~$1,000 |
| No declaration at all | ~$7,000-$8,000 + criminal | High (DAC7) | ~$5,000 |
| Stripe direct without VAT registration | ~$3,500-$5,000 | High | ~$3,000 |

**The clear winner:** Declare everything, use a MoR, stay on free tiers. Expected cost: near zero.

---

## 18. TRANSITION PLAYBOOK — Moving from Gray Zone to Registered

> This section gives you the exact steps to transition from Phase 1 (natural person) to Phase 2 (self-employed) without disrupting your business. Every element — website, domain, bank account, MoR account — is covered.

---

### 18.1 When to Trigger the Transition

**Trigger conditions (any one of these):**
- [ ] 3+ consecutive months of sales (consistent revenue pattern)
- [ ] Annual income exceeds $5,000 from software sales
- [ ] You want to upgrade any foreign service to a paid tier
- [ ] You want to run paid advertising
- [ ] You want to hire a contractor or employee
- [ ] You want to open a business bank account for professional credibility

**Do NOT wait for:**
- A specific revenue threshold (there is none in the law)
- НАП to contact you
- Your accountant to tell you to register

---

### 18.2 The Transition Checklist — Step by Step

#### Week 1: Preparation

- [ ] Consult a Bulgarian accountant (one-time, ~200-400 BGN) — get their opinion on your specific situation
- [ ] Gather all income records from Phase 1 (Paddle/Lemon Squeezy payout statements)
- [ ] Calculate total Phase 1 income in BGN (using BNB rates)
- [ ] Confirm you have filed (or will file) your Phase 1 annual tax return correctly

#### Week 2: Registration

- [ ] **Step 1:** Visit Агенция по вписванията (or apply online at brra.bg) — obtain BULSTAT number
  - Bring: national ID, completed application form (available on brra.bg)
  - Cost: ~10 BGN
  - Time: 1-3 business days

- [ ] **Step 2:** Visit local НАП office (or use e-services at nap.bg) — register as self-employed
  - Bring: BULSTAT certificate, national ID
  - Declare start date of self-employed activity
  - Cost: Free
  - Time: Same day

- [ ] **Step 3:** Submit OKd-5 form to НОИ — register as self-insured
  - Choose minimum contribution base to start
  - Cost: Free
  - Time: 1-2 business days

- [ ] **Step 4:** Open a dedicated business bank account
  - Any Bulgarian bank
  - Bring: BULSTAT certificate, national ID, НАП registration certificate
  - Cost: Varies (typically free or ~10 BGN/month)

#### Week 3: Update Your Business Infrastructure

- [ ] **Update Paddle/Lemon Squeezy account:**
  - Add your BULSTAT number to your vendor profile
  - Update payout bank account to your new business account
  - Update your business address/details

- [ ] **Update your website:**
  - Add legal footer: "Operated by [Your Name], BULSTAT [number], registered self-employed person"
  - Update Privacy Policy to reflect your new legal status
  - Update Terms of Service if you have them

- [ ] **Domain:** No change needed — keep the same domain in your personal name (or transfer to business name if preferred, but not required)

- [ ] **Email:** No change needed — keep the same email

#### Week 4: Ongoing Obligations Setup

- [ ] Set up a system for monthly social security payments (bank standing order by 25th of each month)
- [ ] Set up a simple accounting spreadsheet or use accounting software (e.g., Bulgarian-compatible: Microinvest, Счетоводна програма)
- [ ] Schedule annual tax return reminder (April 30 deadline)
- [ ] Decide whether to register under Article 97a (only if you plan to use paid foreign services)

---

### 18.3 What Customers See During Transition

**Nothing.** The transition is completely invisible to customers:
- Same website
- Same domain
- Same product
- Same checkout (Paddle/Lemon Squeezy)
- Same license keys
- Same support email

The only change is in your legal footer and internal accounting.

---

### 18.4 The Phase 3 Transition (Self-Employed to OOD)

**When to trigger:**
- Annual revenue exceeds €15,000-20,000 consistently
- You want liability protection
- You want to retain earnings in a company
- You want to hire employees

**What changes:**
1. **Incorporate OOD** — through a lawyer or online (e-Registrar at brra.bg)
   - Cost: ~500-1,000 BGN (lawyer fees + state fees)
   - Time: 3-7 business days
   - Minimum capital: 2 BGN

2. **Open OOD bank account** — in the company's name

3. **Transfer vendor agreements** — create new Paddle/Lemon Squeezy account in OOD's name
   - Note: You cannot simply "transfer" an existing account; you create a new one
   - Old account (personal) can be closed or kept for legacy payouts

4. **Transfer domain** (optional) — can transfer domain to OOD's name, or keep in personal name with a license to the OOD

5. **Update website** — new legal footer with OOD details (company name, UIC number, registered address)

6. **Deregister as self-employed** — once OOD is operational, deregister your Свободна Професия status with НАП

7. **Hire an accountant** — mandatory for OOD; budget ~150-250 BGN/month

**What does NOT change:**
- Your website content
- Your product
- Your customers
- Your domain (if kept in personal name)

---

### 18.5 The "Clean Slate" Option — If You Want to Start Fresh

**If you have been operating in the gray zone and want to clean up:**

1. **File any missing annual tax returns** — НАП allows voluntary disclosure with reduced penalties
2. **Pay any outstanding tax** — with interest but without the maximum fine
3. **Register as self-employed** going forward
4. **Do NOT try to hide past income** — DAC7 means НАП likely already knows

**Voluntary disclosure process:**
- Contact НАП directly or through an accountant
- Declare the income you should have declared
- Pay the tax + interest
- НАП typically reduces or waives fines for voluntary disclosure
- This closes the exposure for past years

---

## 19. DEEP DIVE — DAC7: Does Lemon Squeezy (US/Stripe) or Paddle (UK) Actually Report Your Income to НАП?

> **The short answer:** Lemon Squeezy/Stripe almost certainly reports your income to EU tax authorities (via Ireland). Paddle's reporting status is genuinely uncertain due to the UK's post-Brexit position. Neither platform is a safe harbor from НАП discovering your income. Here is the full legal analysis.

---

### 19.1 What is DAC7?

**EU Council Directive 2021/514** (commonly called "DAC7") amends the EU Directive on Administrative Cooperation in Taxation (2011/16/EU). It was adopted in March 2021 and required EU member states to implement it by January 1, 2023.

**What DAC7 does:**
- Requires "platform operators" (digital marketplaces, app stores, gig economy platforms, software distribution platforms) to **collect, verify, and report** information about sellers/vendors who earn income through their platform
- The platform reports to the tax authority of the EU member state where it is registered
- That tax authority then **automatically shares the data** with the tax authorities of all other EU member states where the sellers are resident
- **Result:** НАП receives a report about your income from Lemon Squeezy/Paddle without you doing anything

**What information is reported:**
- Your full name
- Your primary address
- Your tax identification number (Bulgarian EGN or BULSTAT)
- Your date of birth (for natural persons)
- Your bank account number (where payouts are sent)
- Total consideration paid to you per quarter
- Number of transactions

**Reporting timeline:**
- Platforms report annually, by January 31 of the following year
- First reporting period: calendar year 2023 (reported by January 31, 2024)
- НАП receives the data and can cross-reference with your tax return

---

### 19.2 Does DAC7 Apply to Non-EU Platforms?

**This is the critical question for Lemon Squeezy (US) and Paddle (UK).**

**The DAC7 scope rule:**

DAC7 applies to "platform operators" defined as any entity that:
1. Contracts with sellers to make available all or part of a platform, AND
2. The platform facilitates the carrying out of "relevant activities" (which includes selling software licenses)

**The geographic scope:**

| Platform type | DAC7 obligation |
|---|---|
| EU-resident platform (incorporated or managed in EU) | Must report in their EU member state |
| Non-EU platform with EU sellers OR EU buyers | Must register in ONE EU member state and report there |
| Non-EU platform from a "qualifying" country with equivalent rules | May be exempt if home country rules are deemed equivalent |

**The "equivalent third country" exemption (Article 8ac(7) DAC7):**
- A non-EU platform can be exempt from EU DAC7 registration IF:
  1. Their home country has "equivalent" reporting rules, AND
  2. The EU Commission has formally recognized those rules as equivalent, AND
  3. The platform actually reports under those home country rules

---

### 19.3 Lemon Squeezy / Stripe — US-Based Analysis

**Corporate structure:**
- Lemon Squeezy LLC was a US company (Delaware)
- Acquired by Stripe, Inc. in 2024
- Stripe, Inc. is a US company (Delaware)
- **However:** Stripe has a major EU subsidiary: **Stripe Payments Europe, Ltd.** (incorporated in Ireland)
- Stripe's EU operations are run through the Irish entity

**Does the US have "equivalent" DAC7 rules?**
- **No.** The US has FATCA (Foreign Account Tax Compliance Act) and FBAR, but these cover financial accounts, not platform income reporting
- The US does not have a DAC7-equivalent regime for platform operators
- The EU Commission has NOT recognized the US as a qualifying country for the DAC7 exemption

**What this means for Lemon Squeezy/Stripe:**
- Stripe cannot claim the "equivalent third country" exemption
- Stripe MUST register in an EU member state and report under DAC7
- Stripe has registered in **Ireland** (where Stripe Payments Europe, Ltd. is based)
- Stripe reports EU seller income to the **Irish Revenue Commissioners**
- Irish Revenue then shares this data with **НАП (Bulgaria)** under the automatic exchange mechanism

**Practical conclusion for Lemon Squeezy:**
- ✅ **Lemon Squeezy/Stripe IS subject to DAC7**
- ✅ **Your income from Lemon Squeezy IS being reported to НАП** (via Ireland)
- ✅ **НАП has your name, address, EGN/BULSTAT, bank account, and income amount**
- ✅ **This reporting started for 2023 income** (reported January 2024)

**One nuance:** Lemon Squeezy may report under Stripe's DAC7 registration (since the acquisition). The exact reporting entity may be Stripe Payments Europe, Ltd. rather than "Lemon Squeezy" specifically. But the data flows to НАП either way.

---

### 19.4 Paddle — UK-Based Analysis

**Corporate structure:**
- Paddle.com Market Ltd — incorporated in **England and Wales** (UK)
- Paddle is NOT an EU company
- Paddle has no major EU subsidiary (unlike Stripe)
- Paddle operates from the UK

**Does the UK have "equivalent" DAC7 rules?**

**The UK's position is complex and evolving:**

The UK implemented its own equivalent reporting rules: **The Platform Operators (Due Diligence and Reporting Requirements) Regulations 2023** (SI 2023/817), which came into force on **January 1, 2024**.

These UK rules are modeled on DAC7 and require UK-based platforms to report seller income to **HMRC (UK tax authority)**.

**The EU-UK equivalence question:**
- For Paddle to be exempt from EU DAC7 registration, the EU Commission must formally recognize UK rules as "equivalent"
- As of early 2026, the EU Commission has **not yet issued a formal equivalence decision** for the UK
- This is a post-Brexit complication — the UK is no longer in the EU, and equivalence decisions take time

**Three possible scenarios for Paddle:**

**Scenario A — EU Commission grants UK equivalence (most likely eventually):**
- Paddle reports to HMRC under UK rules
- HMRC shares data with EU tax authorities (including НАП) under a separate UK-EU tax information exchange agreement
- Your income reaches НАП, but via a different route (UK-EU exchange, not DAC7 directly)

**Scenario B — EU Commission has NOT granted equivalence (current situation as of early 2026):**
- Paddle must register in an EU member state and report under DAC7
- Paddle may have registered in Ireland, Netherlands, or another EU state
- OR Paddle may be non-compliant (not yet registered) — this is a risk for Paddle, not for you

**Scenario C — Paddle is non-compliant with DAC7:**
- Paddle has not registered in the EU
- Your income is NOT being reported to НАП via DAC7
- However, НАП can still discover your income through other means (bank records, your own declaration, etc.)

**What Paddle actually says:**
- Paddle's documentation acknowledges DAC7 obligations
- Paddle has stated they comply with applicable reporting requirements
- Paddle likely registered in an EU member state (most likely Ireland or Netherlands) to cover EU sellers

**Practical conclusion for Paddle:**
- ⚠️ **Paddle's DAC7 reporting status is less certain than Stripe/Lemon Squeezy**
- ⚠️ **Paddle likely reports your income to EU authorities, but the exact mechanism is unclear**
- ⚠️ **Even if Paddle doesn't report via DAC7, UK-EU tax information exchange may still result in НАП receiving data**
- ✅ **Assume your income IS being reported — do not rely on Paddle's uncertainty as a reason not to declare**

---

### 19.5 The Information Exchange Chain — How НАП Gets the Data

```
Lemon Squeezy/Stripe (US operations)
    ↓ reports to
Stripe Payments Europe Ltd (Ireland)
    ↓ files DAC7 report with
Irish Revenue Commissioners
    ↓ automatic exchange under DAC7/EU Directive
НАП (Bulgaria)
    ↓ cross-references with
Your Bulgarian tax return
```

```
Paddle (UK)
    ↓ reports to (under UK DAC7 equivalent)
HMRC (UK)
    ↓ exchange under UK-EU Tax Information Exchange Agreement
НАП (Bulgaria)
    [OR]
Paddle (UK)
    ↓ registers in EU member state (e.g., Ireland)
    ↓ files DAC7 report with
Irish/Dutch Revenue
    ↓ automatic exchange
НАП (Bulgaria)
```

**Timeline:**
- Platforms collect data throughout the year
- Report to their home/registered tax authority by **January 31** of the following year
- Tax authorities exchange data within **2 months** (by March 31)
- НАП has the data before the Bulgarian tax return deadline (April 30)
- **НАП can compare your declared income against the DAC7 report before you even file**

---

### 19.6 What НАП Does With DAC7 Data

**НАП's process:**
1. Receive DAC7 data from EU partner authorities (including Irish Revenue for Stripe/Lemon Squeezy)
2. Match the data against Bulgarian tax identification numbers (EGN or BULSTAT)
3. Cross-reference with filed tax returns
4. If income is declared: no action (or minor verification)
5. If income is NOT declared: issue a notice requesting explanation

**НАП's matching capability:**
- НАП matches by EGN (personal ID number) or BULSTAT
- If you provided your EGN to Lemon Squeezy/Paddle (required for tax purposes), НАП can match you
- If you provided a foreign address or fake details, НАП may not match immediately — but this is tax fraud

**What if you didn't provide your EGN to the platform?**
- Lemon Squeezy/Paddle are required to collect and verify your tax identification number
- If you refuse to provide it, they may withhold payouts or close your account
- Providing false information is a separate legal offense

---

### 19.7 DAC7 and the "Natural Person" Phase — Does It Apply?

**Yes, DAC7 applies regardless of your legal status.**

DAC7 covers "sellers" — defined as any person (natural or legal) who uses the platform to sell. There is no minimum threshold below which reporting is not required.

**However, there is a de minimis exception:**
- Platforms are NOT required to report sellers who:
  - Had fewer than **30 transactions** in the year, AND
  - Received less than **€2,000** in total consideration

**What this means for you:**
- If you have fewer than 30 sales AND less than €2,000 in a year: Lemon Squeezy/Paddle may not report you
- If you exceed either threshold: they MUST report you
- **At $300/sale, you hit the €2,000 threshold at approximately 7 sales**

**Practical implication:**
- In your very first year with only 3 sales ($900): you may be below the reporting threshold
- From year 2 onwards with consistent sales: you are almost certainly above the threshold and WILL be reported

---

### 19.8 The "Paddle is UK, Not EU" Argument — Does It Help You?

**Some people argue:** "Paddle is UK-based, not EU. DAC7 is an EU directive. Therefore Paddle doesn't have to report to EU authorities."

**This argument is WRONG for two reasons:**

**Reason 1 — DAC7 explicitly covers non-EU platforms:**
DAC7 Article 8ac(1) states that the reporting obligation applies to platform operators "regardless of where they are established." Non-EU platforms with EU sellers must register in the EU and report.

**Reason 2 — UK-EU tax information exchange:**
Even if Paddle reports only to HMRC (under UK rules), the UK and EU have a Tax Information Exchange Agreement (TIEA) and the UK is a signatory to the OECD Common Reporting Standard (CRS). HMRC shares financial information with EU tax authorities, including НАП.

**The bottom line:** Whether Paddle reports via DAC7 directly or via UK-EU exchange, the information can reach НАП. The route is different; the destination is the same.

---

### 19.9 Practical Implications — What You Should Do

**Given DAC7 reporting:**

1. **Always declare your income** — НАП will have the data. Non-declaration is easily detected.

2. **Provide accurate tax information to your MoR** — Give Lemon Squeezy/Paddle your correct EGN or BULSTAT. This is legally required and ensures the DAC7 report matches your tax return.

3. **Declare in the same year the income is received** — DAC7 reports are annual. If you receive income in 2024, it will be reported in January 2025. Your 2024 tax return (due April 30, 2025) must include this income.

4. **The de minimis exception is not a strategy** — Do not deliberately keep sales below 30 transactions or €2,000 to avoid reporting. This is artificial behavior that НАП can challenge.

5. **DAC7 does NOT change your tax obligations** — It only changes НАП's ability to discover undeclared income. Your tax obligations are the same whether or not DAC7 exists.

6. **DAC7 actually helps honest taxpayers** — If you declare correctly, DAC7 data confirms your declaration. НАП is less likely to audit you if your return matches the DAC7 report.

---

### 19.10 Summary Table — DAC7 Reporting by Platform

| Platform | Jurisdiction | DAC7 Status | Reports to | НАП Receives Data? |
|---|---|---|---|---|
| Lemon Squeezy (pre-Stripe) | US (Delaware) | Must register in EU | Irish Revenue (via Stripe EU) | Yes — high confidence |
| Lemon Squeezy (post-Stripe acquisition) | US (via Stripe) | Reports via Stripe Payments Europe Ltd | Irish Revenue | Yes — high confidence |
| Paddle | UK (England and Wales) | Must register in EU OR qualify for UK equivalence exemption | Irish/Dutch Revenue OR HMRC | Yes — medium-high confidence |
| Stripe (direct) | US (via EU entity) | Reports via Stripe Payments Europe Ltd | Irish Revenue | Yes — high confidence |
| Gumroad | US | Must register in EU | Unknown EU member state | Likely yes |
| PayPal | US/Luxembourg | Reports via PayPal Europe S.a.r.l. (Luxembourg) | Luxembourg Revenue | Yes — high confidence |

**Key takeaway:** There is no major payment platform or MoR that is outside the DAC7 reporting net. Assume all income from these platforms is reported to НАП.

---

*Last updated: February 2026. Tax laws change frequently. Verify all figures with current НАП guidelines.*
