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

*Last updated: February 2026. Tax laws change frequently. Verify all figures with current НАП guidelines.*
