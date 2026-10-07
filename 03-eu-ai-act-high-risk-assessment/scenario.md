# Scenario: High-Risk AI Hiring Tool Assessment

> Author: Faith Olofintuyi
> Fictional scenario. The companies, people, products, and figures are invented for this portfolio.

## The Organization
Noordhaven Logistics B.V. (fictional) is a warehousing and transport company headquartered in Rotterdam, the Netherlands. It has about 2,000 employees across 8 sites in the Netherlands, Belgium, and Germany. Most roles are warehouse operatives, forklift drivers, and truck drivers, with high turnover. The company hires about 1,100 people a year from roughly 25,000 applications.

## The AI System
Talvio Screen (fictional), from Talvio GmbH in Berlin, is a candidate-screening tool sold as a service. It:
1. Reads each CV and application form
2. Scores the candidate's job fit from 0 to 100
3. Ranks candidates and flags a shortlist for recruiters
4. Sends an automatic rejection email to candidates below a set score

Features it uses include work history, gaps in employment, years of experience, language skills, certifications, and home postcode (to estimate commute distance). Talvio says the model was trained on several million past applications and hiring outcomes from its other clients.

Talvio also offers an optional video-interview add-on that scores candidates on "engagement" and "confidence" from their facial expressions and voice. It is switched off in the pilot, but HR wants to turn it on.

## The Gap
HR started a pilot in June 2026 at two warehouses (Venlo and Tilburg) without involving Legal or the Risk & Compliance team. By the time we found out in September 2026, about 4,000 applications had gone through the tool.

In the pilot setup:
- Candidates scoring below 35 receive an automatic rejection email after five days unless a recruiter steps in. Recruiters almost never do.
- Each site has one recruiter, who also handles onboarding and shift scheduling. Talvio's usage logs show they spend under a minute per candidate in the tool.
- Recruiters see the score and rank but not why a candidate scored low.
- Candidates are not told that AI is used, and there is no way to ask for a review.
- No data protection impact assessment (DPIA) was done.

## Why It Matters
- Hiring tools like this are classed as high-risk under the EU AI Act (Annex III, point 4(a)).
- Automatic rejections with little human input may count as solely automated decisions under GDPR Article 22.
- Postcode, employment gaps, and language skills can stand in for national origin, disability, or caring responsibilities, so the tool may discriminate without ever using a protected characteristic.
- The video add-on would analyze emotions in a recruitment setting, which the AI Act bans outright.

## The Stakeholders
- **HR** wants to roll the tool out to all 8 sites. Time-to-hire in the pilot fell from 19 days to 8.
- **Operations** supports HR because unfilled shifts cost money every week.
- **Legal** is concerned about the pilot already running without review.
- **Works council (ondernemingsraad)** has not been consulted.
- **Talvio** says the tool "only assists" and that "recruiters make every decision."
- **My role:** I lead the Risk & Compliance assessment. My job is to decide whether the tool can be used, under what conditions, and what happens to the pilot in the meantime.

## The Constraints
- The business case is real. Faster hiring means fewer empty shifts.
- Talvio controls the model and the training data. We can only use what they share.
- The pilot has already affected about 4,000 real candidates.
- Any decision must hold up in front of the Dutch Data Protection Authority (Autoriteit Persoonsgegevens), which also coordinates AI Act supervision in the Netherlands.
