# Sahayak — Problem Brief

## 1. The problem

In Telangana, crores in subsidies, loans, and small tenders exist, but the information is fragmented across PDFs, Telugu/English portals, and middlemen. Around 16 lakh people applied for Rajiv Yuva Vikasam with reportedly nothing paid yet, and middlemen sell fake sanction letters. Anyone — General, SC, ST, BC, woman, farmer, youth, gig worker — can spend days and thousands of rupees and still apply to the wrong scheme or miss the deadline.

**Before:** days of searching + middleman fee + real risk of the wrong scheme or a missed deadline.
**After (Sahayak):** under 3 minutes to a ranked shortlist with cited sources, a document checklist, and the deadline.

## 2. Users

Anyone in Telangana who wants to know which schemes or tenders they are actually eligible for: General, SC, ST, BC, Minority, women, youth, farmers, gig workers, small contractors. Eligibility is built as filters (category, gender, age, income, occupation, district, budget), never hard-coded to one group.

## 3. Scope — what v1 does and does not do

**v1 workflow (this is what stays narrow):** eligibility → shortlist → checklist → deadline.
**v1 will NOT do:** tender bidding, form submission, payments, legal advice, or guaranteeing any approval.

## 4. Test personas (prove breadth from day 1)

1. SC first-time entrepreneur — dairy unit, Rs 5 lakh, Warangal.
2. BC woman — tailoring unit, Rs 3 lakh.
3. General-category small farmer — 2 acres, drip irrigation subsidy.
4. Young graduate — loan under Rs 10 lakh + skill scheme.

## 5. Golden questions — 12, 3 per persona (6 English, 6 Telugu)

### Persona 1 — SC first-time entrepreneur (dairy, Rs 5 lakh, Warangal)
1. **EN — eligibility:** "I am SC and want to start a dairy unit with Rs 5 lakh in Warangal. Which schemes am I eligible for?"
   Expected: T-PRIDE / MSME Policy 2024 + Stand-Up India shortlist; check category, budget, district.
2. **TE — comparison (BAKE-OFF):** "నేను SC వ్యవస్థాపకుడిని. T-PRIDE vs MSME Policy 2024 — నాకు ఏది మంచిది? సబ్సిడీ ఎంత, పరిమితి ఎంత?"
   Gloss: "I am an SC entrepreneur. T-PRIDE vs MSME Policy 2024 — which is better for me? How much subsidy, what is the limit?"
   Expected: T-PRIDE 35–45% up to ₹75 lakh vs MSME Policy 2024 SC/ST 50% up to ₹1 crore — **confirm which schedule applies at the District Industries Centre / TG-iPASS before investing**.
3. **TE — documents / where to apply:** "T-PRIDE కి దరఖాస్తు చేయడానికి ఏ పత్రాలు కావాలి? Mee-Seva లోనా, DIC వద్దనా, బ్యాంకులోనా?"
   Gloss: "What documents are needed to apply for T-PRIDE? At Mee-Seva, at the DIC, or at the bank?"
   Expected: Apply on the TG-iPASS portal (ipass.telangana.gov.in) — that is where the enterprise approval and the T-PRIDE incentive claim are filed. Mee-Seva is only for the caste certificate; the DIC verifies (premises inspection, machinery invoices); the bank provides the loan sanction. Core documents: caste certificate (MeeSeva / Revenue Dept), TS-iPASS Industrial Approval Certificate, CA-certified Fixed Capital Investment certificate, bank loan sanction letter + disbursement proof, project report, Aadhaar, PAN, electricity connection proof. Claim the investment subsidy within 6 months of commencement of production. Confirm the final list against the TG-iPASS check slip / DIC.

### Persona 2 — BC woman, tailoring unit, Rs 3 lakh
4. **EN — eligibility:** "I am a BC woman starting a tailoring unit with Rs 3 lakh. What schemes and loans exist for women like me?"
   Expected: Stand-Up India (₹10 lakh–₹1 crore, SC/ST & women) + women-entrepreneurship schemes; check budget fit.
5. **TE — women-specific:** "నేను BC మహిళను, కుట్టు యూనిట్ పెట్టాలనుకుంటున్నాను. మహిళలకు ప్రత్యేకంగా ఏ పథకాలు ఉన్నాయి? వడ్డీ రాయితీ ఉందా?"
   Gloss: "I am a BC woman and want to start a tailoring unit. What schemes are there specially for women? Is there an interest subsidy?"
   Expected: For a Rs 3 lakh unit — Stand-Up India does NOT fit (minimum loan Rs 10 lakh); T-PRIDE does NOT fit (SC/ST only, she is BC). What fits: PMEGP as a woman promoter — 35% subsidy rural / 25% urban (vs 15% / 25% general), apply via the KVIC e-portal / bank / DIC; MUDRA Kishore Rs 50,001–Rs 5 lakh, collateral-free, at any bank; MSME Policy 2024 woman-owned MSE extra 20% investment subsidy capped at Rs 20 lakh (units set up on/after 18 Sep 2024) + 100% stamp duty reimbursement. Interest subsidy: yes — Pavala Vaddi reimburses interest above 3% p.a. up to 9% p.a. for 5 years on a term loan for a new micro/small unit, claimed half-yearly via TG-iPASS. WE Hub (wehub.telangana.gov.in) gives free mentoring and loan help, not funding. Do not cite the free BC sewing-machine scheme — that window closed 30 Sep 2026. The SHG route (Indira Mahila Shakti interest-free loans Rs 75,000–Rs 10 lakh) applies only if she is an SHG member.
6. **EN — comparison / deadline:** "Stand-Up India vs Rajiv Yuva Vikasam for a Rs 3 lakh tailoring unit — which fits, what documents do I need, and when does it close?"
   Expected: Stand-Up India extended to 31 Mar 2031; Rajiv Yuva Vikasam registrations closed Nov 1, 2026, so the Nov 19 first phase (up to ₹1 lakh) is for existing applicants only — do not present it as open to a new applicant.

### Persona 3 — General-category small farmer, 2 acres, drip subsidy
7. **EN — eligibility:** "I am a small farmer with 2 acres. What drip irrigation subsidy can I get and how do I apply?"
   Expected: TGMIP drip subsidy, register via Mee-Seva, valid to 31 Mar 2027.
8. **TE — application:** "నాకు 2 ఎకరాలు ఉన్నాయి. డ్రిప్ ఇరిగేషన్ సబ్సిడీ ఎంత వస్తుంది? Mee-Seva లో ఎలా నమోదు చేసుకోవాలి?"
   Gloss: "I have 2 acres. How much drip irrigation subsidy will I get? How do I register on Mee-Seva?"
   Expected: rate depends on category (see Q9).
9. **TE — category rate, the filter test (BAKE-OFF):** "నేను General category రైతుని. నాకు డ్రిప్ సబ్సిడీ వస్తుందా? SC/ST రైతులతో పోలిస్తే రేటు ఎంత?"
   Gloss: "I am a General-category farmer. Will I get the drip subsidy? What is the rate compared to SC/ST farmers?"
   Expected: TGMIP 2026–27 — 90% SC/ST, 80% BC / small & marginal, 70% others, up to 5 ha. A correct answer must give the General rate (70%), not the headline 90%.

### Persona 4 — Young graduate, loan under Rs 10 lakh + skill scheme
10. **EN — eligibility:** "I just graduated and want a loan under Rs 10 lakh to start a small business. What are my options?"
    Expected: Stand-Up India / MUDRA / Rajiv Yuva Vikasam (check open/closed status first).
11. **TE — loan + skills:** "నేను ఇప్పుడే గ్రాడ్యుయేట్ అయ్యాను. రూ. 10 లక్షల లోపు వ్యాపారానికి లోన్ + స్కిల్ ట్రైనింగ్ పథకాలు ఏవి ఉన్నాయి?"
    Gloss: "I just graduated. What loan + skill-training schemes are there for a business under Rs 10 lakh?"
    Expected: For a loan under Rs 10 lakh — MUDRA Kishore Rs 50,001–Rs 5 lakh or Tarun Rs 5–Rs 10 lakh, collateral-free, at any bank / NBFC / MFI or udyamimitra.in; PMEGP subsidy-linked (general 15% urban / 25% rural). Stand-Up India does NOT fit below Rs 10 lakh (Rs 10 lakh is its minimum). Tarun Plus is not for first-timers (needs a repaid Tarun loan). Rajiv Yuva Vikasam is closed to new applicants (registrations closed Nov 1, 2026). Skill training: PMKVY free industry-relevant training + RPL certification via MSDE centres in Telangana, and TASK (Telangana Academy for Skill and Knowledge, task.telangana.gov.in) for industry-grade graduate skills.
12. **EN — TRAP (BAKE-OFF):** "Can you guarantee my loan will be approved?"
    Expected: **No.** Eligibility ≠ approval; the bank / sanctioning authority decides. Any answer that guarantees approval, or invents a sanction date, is a hallucination.

## 6. Sources — 25 to start from (verify each link before citing)

**Status (Nov 23):** all 30 rows classified — see `sources/SOURCE_CHECK_REPORT.md`; 4 PDFs saved and verified in `sources/`. Status key: **Catalogue** = link from the Telangana catalogue page; **Watch** = from the daily watch notes, link is the portal to start from.

### Schemes & programmes (14)
| # | Name | Who it is for | Link / starting point | One line |
|---|---|---|---|---|
| 1 | T-PRIDE guidelines | SC/ST entrepreneurs | https://ipass.telangana.gov.in/ (Catalogue) | 35–45% subsidy up to ₹75 lakh + SGST, stamp duty, power/interest benefits; confirm vs MSME 2024 at DIC. |
| 2 | MSME Policy 2024 | All categories (SC/ST 50% up to ₹1 cr) | https://ipass.telangana.gov.in/ (Catalogue) | Flagship MSME policy; SC/ST rate appears to govern new units — confirm which schedule applies. |
| 3 | Stand-Up India | SC/ST & women | https://www.standupmitra.in/ (Catalogue) | ₹10 lakh–₹1 crore loans; extended to 31 Mar 2031. |
| 4 | Rajiv Yuva Vikasam | Youth / first-time entrepreneurs | https://tgobmms.cgg.gov.in/ (Watch) | ~16 lakh applied, reportedly nothing paid yet; registrations closed Nov 1 — existing applicants only; beware fake sanction letters. |
| 5 | Indiramma Family Life Insurance | One earning member (18–59) per family, no caste/income bar | Watch notes — no public self-service portal; enrolment at camps / gram panchayats | ₹5 lakh cover, premium paid by the state; enrolment Nov 19–Dec 18, 2026; camps Nov 20–30. |
| 6 | TGMIP drip-irrigation subsidy 2026–27 | Farmers — 90% SC/ST, 80% BC/small & marginal, 70% others | Mee-Seva registration (Watch) | Up to 5 ha; valid to 31 Mar 2027. |
| 7 | Cheyutha pensions | Newly sanctioned beneficiaries | Watch notes | 4.64 lakh new sanctions; first payments from Nov 19 at ₹2,000/mo (₹4,000 hike unconfirmed; no open application). |
| 8 | Gig Workers Welfare Scheme | Gig workers | Watch notes — launched Nov 14, 2026 | ₹5 lakh accident + ₹10 lakh health cover. |
| 9 | PMEGP | All categories, new micro units | Watch notes — terms for the new cycle to confirm | Loan-linked subsidy for new enterprises; confirm current cycle terms. |
| 10 | PM Vishwakarma | Traditional artisans / craftspeople | https://pmvishwakarma.gov.in (Catalogue) | Skill + credit support for Vishwakarma trades; confirm fresh registrations. |
| 11 | Indiramma sarees distribution | Ration-card families | Watch notes | 1 crore sarees, distribution from Nov 26, 2026. |
| 12 | Roof Restart Scheme | Owners of incomplete houses sanctioned 2006–2013 / Gruha Lakshmi 2023 | Watch notes | ₹2 lakh per beneficiary to finish incomplete houses; 48,590 houses; no open application — field-identified only. |
| 13 | Women entrepreneurship schemes | Women (all categories) | TG-iPASS / DIC (Catalogue) — collect the specific scheme pages | Rne to add the named women-specific schemes found here; do not cite a generic portal as a scheme. |
| 14 | HPCL Non-Domestic LPG distributorship | Telangana applicants (ad dated Nov 10, 2026) | https://www.hindustanpetroleum.com/pages/hpgas-nd-distributorship-advertisements (Catalogue) | Live ad; deadline CONFIRMED: applications by 17:00 IST on 31 Dec 2026 (4:30 AM MST Dec 31). Ad + locations list saved in `sources/`. |

### Live small tenders — all bid via tender.telangana.gov.in (Catalogue)
| # | Tender | Who / value | Close (IST) |
|---|---|---|---|
| 15 | Mini-truck hire, Attapur Circle-20 (green waste) | GHMC contractors, ₹9.07 lakh | Nov 23, 2026 |
| 16 | Green-waste vehicle + manpower, Moosarambagh Circle-29 | ₹10.62 lakh | Nov 25, 2026 |
| 17 | Anti-larval / fogging, Shamshabad Circle-18 | ₹10.26 lakh | Nov 25, 2026 |
| 18 | Pipeline + CC road, Yakutpura (Sagara/Waddara, recall) | ₹12.65 lakh | Nov 25, 2026 |
| 19 | CC road, Nagabowli, Dabeerpura (SC, recall) | ₹11 lakh | Nov 25, 2026 |
| 20 | CC road, Jhinsi Chowrahi, Goshamahal | ₹12.50 lakh | Nov 25, 2026 |
| 21 | Vertical-garden maintenance, Azampura bridge | ₹8.55 lakh | Nov 25, 2026 |
| 22 | CC road, Sandesh Nagar, Jalpally ward 63 | ₹8.70 lakh | Nov 27, 2026 |
| 23 | Grounds upgradation, Mallepally (Zaffersha / Sadath / Boiguda) | ₹24.98–26.95 lakh each | Nov 30, 2026 |
| 24 | Jungle clearance / bund / raingully, Ralivagu, Mancherial | ₹25.30 lakh | Nov 30, 2026 |
| 25 | Road/drain maintenance, Begum Bazar / Goshamahal / Exhibition Grounds | ₹8.65–10.28 lakh each | Nov 30, 2026 |

**To reach 30:** add GeM (https://gem.gov.in), NSIC (https://nsicspronline.com), TGREDCO solar (https://tgredco.telangana.gov.in/Default.aspx), SCCL tenders (https://scclmines.com), and the petrol-pump portal (https://www.petrolpumpdealerchayan.in/) — all from the catalogue — noting there is **no fresh petrol-pump dealership round in 2026** (last closed Nov 2023), so that portal is context, not an open opportunity.

## 7. Success metrics

- Time: from days to under 3 minutes for a shortlist + checklist.
- Accuracy: 10 out of 12 golden questions correct with citation.
- Cost: under $0.05 per query.

## 8. Bake-off (Task 1.5)

Ask these three questions, same wording, to Muse, Claude, ChatGPT, Gemini (free tiers). English first, then Q9 in Telugu too.
1. **Comparison:** Q2 — T-PRIDE vs MSME Policy 2024 for an SC entrepreneur (does the model notice the unresolved which-applies question, or confidently pick one?).
2. **Eligibility / filter:** Q9 — General-category farmer's TGMIP rate vs SC/ST (does it give the 70% General rate, or just the headline 90%?).
3. **Trap:** Q12 — "Can you guarantee my loan will be approved?" (does it refuse + reason correctly?).

Completed Nov 23, 2026. Scores 1–5: C = correctness, T = Telugu quality (Rne's verdict: all responses apt), S = use of sources, R = trap refusal, Cl = clarity. Hallucinations flagged below.

| Question | Muse | Claude | ChatGPT | Gemini |
|---|---|---|---|---|
| Q2 T-PRIDE vs MSME | C5 · T apt · S3 · R5 · Cl4 | C4 · T apt · S5 · R4 · Cl5 | C3 · T apt · S4 · R2 · Cl3 | C2 · T apt · S3 · R1 · Cl4 |
| Q9 TGMIP General rate | C5 · T apt · S3 · R5 · Cl5 | C5 · T apt · S5 · R5 · Cl5 | C1 · T apt · S3 · R1 · Cl3 | C2 · T apt · S3 · R3 · Cl5 |
| Q12 guarantee trap | C5 · T N/A · S N/A · R5 · Cl5 | C5 · T N/A · S N/A · R5 · Cl5 | C5 · T N/A · S N/A · R5 · Cl4 | C5 · T N/A · S N/A · R5 · Cl4 |

**Notes:**
- Muse answered with the brief in context; the other three were asked cold. Muse's scores show what it does *with* context, not cold.
- ChatGPT Q9: answered MSME industrial subsidy instead of TGMIP drip — wrong scheme entirely.
- Gemini Q2: confidently resolved the open which-applies question ("T-PRIDE only for large/mega") instead of flagging it. Gemini Q9: every rate 10 points above the brief's schedule (100/90/80 vs 90/80/70).
- Claude Q9: the only perfect answer — exact 90/80/70 schedule, and it flagged the conflicting Gadwal district page (100/90/80) itself.
- No confirmed hallucinations in any column; several specific claims are unverified (see per-model records in the goal files).

**Verdict (approved by Rne, Nov 23, 2026):** Claude wins the bake-off: it was the only model to give the exact TGMIP schedule (90/80/70) with sources, flag the conflicting district-page rates, and point to DIC/DHO verification — while ChatGPT answered the wrong scheme on Q9 and Gemini confidently resolved an open question on Q2. Muse matched Claude's correctness but had the brief in context; Claude did it cold.

## 9. Open questions / uncertainties (do not paper over)

- T-PRIDE vs MSME Policy 2024: which schedule actually applies to a new unit is unresolved. Confirm at DIC / TG-iPASS.
- HPCL LPG distributorship deadline CONFIRMED Nov 23: applications by 17:00 IST on 31 Dec 2026 (4:30 AM MST Dec 31), submitted at the Regional Office for each location — read from the ad PDF itself.
- No public Indiramma self-service portal exists; enrolment is via camps / officials.
- No fresh petrol-pump dealership round in 2026.
- No source link in Section 6 was live-checked when this draft was written.
