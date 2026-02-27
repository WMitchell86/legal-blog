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

*Last updated: February 2026. Tax laws change frequently. Verify all figures with current НАП guidelines.*
