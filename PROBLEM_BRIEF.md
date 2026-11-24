# Sahayak — Problem Brief (DRAFT for Rne's review)

**Status:** Draft prepared by Muse, Nov 23, 2026. Not finished work — Rne reviews, corrects, and approves it.
**How to use it:** Upload this file to the repo as `PROBLEM_BRIEF.md` (GitHub web: Add file → Upload files), or paste it into a Google Doc if you prefer Docs. Keeping it in the repo is recommended: it is version-controlled, and from Phase 1 on, coding agents (Claude Code etc.) read it as the project spec.
**What this doc is:** the spec the whole project builds from, and the test suite it gets graded against. The 12 questions in Section 5 become the golden eval set in Phase 5. The sources in Section 6 become the RAG corpus in Phase 2. If this doc is wrong, everything built on it is wrong — that is why Rne's review is the real work here, not the typing.

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

Each Telugu question carries an English gloss. **TODO (Rne): correct the Telugu** — it was drafted by a non-native speaker. Keep what sounds natural, change the rest. **TODO (Rne): fill the expected-answer gaps marked below.**

### Persona 1 — SC first-time entrepreneur (dairy, Rs 5 lakh, Warangal)
1. **EN — eligibility:** "I am SC and want to start a dairy unit with Rs 5 lakh in Warangal. Which schemes am I eligible for?"
   Expected: T-PRIDE / MSME Policy 2024 + Stand-Up India shortlist; check category, budget, district.
2. **TE — comparison (BAKE-OFF):** "నేను SC వ్యవస్థాపకుడిని. T-PRIDE vs MSME Policy 2024 — నాకు ఏది మంచిది? సబ్సిడీ ఎంత, పరిమితి ఎంత?"
   Gloss: "I am an SC entrepreneur. T-PRIDE vs MSME Policy 2024 — which is better for me? How much subsidy, what is the limit?"
   Expected: T-PRIDE 35–45% up to ₹75 lakh vs MSME Policy 2024 SC/ST 50% up to ₹1 crore — **confirm which schedule applies at the District Industries Centre / TG-iPASS before investing** (unresolved).
3. **TE — documents / where to apply:** "T-PRIDE కి దరఖాస్తు చేయడానికి ఏ పత్రాలు కావాలి? Mee-Seva లోనా, DIC వద్దనా, బ్యాంకులోనా?"
   Gloss: "What documents are needed to apply for T-PRIDE? At Mee-Seva, at the DIC, or at the bank?"
   Expected: TODO (Rne) — fill in from the T-PRIDE guidelines once collected in Task 1.4.

### Persona 2 — BC woman, tailoring unit, Rs 3 lakh
4. **EN — eligibility:** "I am a BC woman starting a tailoring unit with Rs 3 lakh. What schemes and loans exist for women like me?"
   Expected: Stand-Up India (₹10 lakh–₹1 crore, SC/ST & women) + women-entrepreneurship schemes; check budget fit.
5. **TE — women-specific:** "నేను BC మహిళను, కుట్టు యూనిట్ పెట్టాలనుకుంటున్నాను. మహిళలకు ప్రత్యేకంగా ఏ పథకాలు ఉన్నాయి? వడ్డీ రాయితీ ఉందా?"
   Gloss: "I am a BC woman and want to start a tailoring unit. What schemes are there specially for women? Is there an interest subsidy?"
   Expected: TODO (Rne) — fill in from the women-schemes sources in Task 1.4.
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
    Expected: TODO (Rne) — fill in from the youth/skill sources in Task 1.4.
12. **EN — TRAP (BAKE-OFF):** "Can you guarantee my loan will be approved?"
    Expected: **No.** Eligibility ≠ approval; the bank / sanctioning authority decides. Any answer that guarantees approval, or invents a sanction date, is a hallucination.

## 6. Sources — 25 to start from (verify each link before citing)

**TODO (Rne): confirm every URL live, save PDFs into `sources/`.** No link below was live-checked when drafted. Status key: **Catalogue** = link from the Telangana catalogue page; **Watch** = from the daily watch notes, link is the portal to start from.

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
| 14 | HPCL Non-Domestic LPG distributorship | Telangana applicants (ad dated Nov 10, 2026) | https://www.hindustanpetroleum.com/pages/hpgas-nd-distributorship-advertisements (Catalogue) | Live ad; deadline is inside the ad PDF — still unverified, check the PDF. |

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

Blank scoring table (1–5 each: correctness, Telugu quality, use of sources, trap refusal, clarity; flag hallucinations):

| Question | Muse | Claude | ChatGPT | Gemini |
|---|---|---|---|---|
| Q2 T-PRIDE vs MSME | | | | |
| Q9 TGMIP General rate | | | | |
| Q12 guarantee trap | | | | |

**One-line verdict (Rne to write after the bake-off):** which model he trusts most for this task, and why.

## 9. Open questions / uncertainties (do not paper over)

- T-PRIDE vs MSME Policy 2024: which schedule actually applies to a new unit is unresolved. Confirm at DIC / TG-iPASS.
- HPCL LPG distributorship deadline is inside the ad PDF, still unverified.
- No public Indiramma self-service portal exists; enrolment is via camps / officials.
- No fresh petrol-pump dealership round in 2026.
- No source link in Section 6 was live-checked when this draft was written.

## 10. Rne's review checklist (the actual work of Step 1)

- [ ] Scope lines in Sections 2–3 say what he means (edit in his own words).
- [ ] Telugu in Q2, Q3, Q5, Q8, Q9, Q11 corrected to natural wording.
- [ ] Expected-answer gaps filled: Q3, Q5, Q11.
- [ ] Every source link confirmed live; PDFs saved into `sources/`.
- [ ] Bake-off run; table filled; one-line verdict written.
- [ ] File uploaded to the repo as `PROBLEM_BRIEF.md`.
- [ ] Step 1 complete when he sends: repo link + 12 questions + bake-off table. Then Phase 1 unlocks.
