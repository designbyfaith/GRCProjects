# EU AI Act High-Risk Assessment

> **Fictional scenario.** Noordhaven Logistics B.V., Talvio GmbH, and Talvio Screen are invented for this portfolio. All figures are illustrative. See [scenario.md](../scenario.md).
>
> **Timing assumption.** This assessment assumes the AI Act's high-risk obligations for Annex III systems apply from 2 August 2026, as originally set. The ban on prohibited practices (Article 5), the AI literacy duty (Article 4), and the GDPR apply regardless.

## Document Information
| Field | Value |
|-------|-------|
| Organization | Noordhaven Logistics B.V. (deployer) |
| AI System Name | Talvio Screen, provided by Talvio GmbH |
| Assessment Date | October 7, 2026 |
| Assessor | Faith Olofintuyi, Risk & Compliance |
| Version | 0.1 (Draft) |

---

## 1. Executive Summary

Talvio Screen ranks job applicants and automatically rejects those who score below 35. It is a high-risk AI system under the EU AI Act, because it is used to filter applications and evaluate candidates (Annex III, point 4(a)). HR has been piloting it at two warehouses since June 2026 without a legal review, and about 4,000 real candidates have already gone through it.

The pilot does not meet the rules as it runs today. Rejections are automatic, recruiters spend under a minute per candidate, candidates are not told AI is involved, and nobody has checked whether the tool disadvantages people because of where they live, gaps in their work history, or their language. The video add-on HR wants to switch on would read candidates' emotions, which the AI Act bans in recruitment.

The tool can be used, but only after specific changes. The Risk & Compliance team recommends approval with conditions: stop automatic rejections now, put real human review in place, test for bias, tell candidates and give them a way to ask for a review, and never enable the video add-on.

**Recommendation:**
- [ ] APPROVE for deployment
- [x] APPROVE with conditions (Section 8.3)
- [ ] DO NOT APPROVE until remediated
- [x] PROHIBIT the video-interview add-on (Article 5(1)(f))

---

## 2. System Description

### 2.1 Purpose and Intended Use
Talvio Screen helps recruiters handle high-volume hiring for warehouse, forklift, and driver roles. It reads each application, scores job fit from 0 to 100, ranks candidates, flags a shortlist, and sends automatic rejections below a set score.

### 2.2 Technical Architecture

| Component | Description |
|-----------|-------------|
| Model Type | Machine-learning scoring model with text extraction from CVs (details held by Talvio) |
| Training Data | Several million past applications and hiring outcomes from Talvio's other clients. Not shared with us. |
| Input Data | CV, application form, work history, employment gaps, years of experience, language skills, certifications, home postcode |
| Output | Score (0 to 100), rank, shortlist flag, automatic rejection below 35 |
| Update Frequency | Retrained by Talvio "periodically." No notice given to clients. |

### 2.3 Deployment Context

| Aspect | Description |
|--------|-------------|
| Geographic Scope | Pilot: Venlo and Tilburg (NL). Proposed: all 8 sites in NL, BE, and DE. |
| User Base | One recruiter per site, who also handles onboarding and scheduling |
| Decision Impact | Decides who is shortlisted and who is rejected for a job |
| Integration Points | Careers site, applicant tracking system, candidate email |

---

## 3. Risk Classification

### 3.1 Classification Determination

| Classification | Selected |
|----------------|----------|
| Unacceptable Risk (Prohibited) | [x] Video-interview add-on only |
| High Risk | [x] Core screening tool |
| Limited Risk | [ ] |
| Minimal Risk | [ ] |

### 3.2 Applicable Category
Annex III, point 4(a): AI systems intended to be used for the recruitment or selection of natural persons, in particular to analyze and filter job applications and to evaluate candidates.

### 3.3 Classification Justification
- **The core tool is high-risk.** It filters applications and evaluates candidates, which is exactly what Annex III, point 4(a) describes.
- **The "it only assists" exception does not apply.** Article 6(3) lets some Annex III systems escape the high-risk label if they only perform narrow or preparatory tasks. That exception never applies when a system profiles people, and scoring candidates on their work history and characteristics is profiling.
- **The video add-on is prohibited.** Article 5(1)(f) bans AI that infers emotions in the workplace, and the Commission's guidelines treat recruitment as part of the workplace. Scoring "engagement" and "confidence" from faces and voices is emotion recognition. Fines for prohibited practices reach EUR 35 million or 7% of worldwide turnover.
- **Our role is deployer, not provider.** Talvio is the provider. We would become a provider ourselves under Article 25 if we put our own name on the tool, changed its intended purpose, or substantially modified it. We should do none of these.

---

## 4. Requirements Analysis

Articles 9 to 15 are the provider's obligations. As deployer, we cannot fix them ourselves, but we must not use a tool that fails them, and our own duties under Article 26 depend on what Talvio gives us. Each table shows what we have, what is missing, and what we will require.

### 4.1 Provider Requirements (Articles 9 to 15)

| Article | What we have | Gap | What we require from Talvio |
|---------|--------------|-----|------------------------------|
| Art. 9 Risk management | Marketing claims only | No risk management documentation shared | Summary of its risk management system and known risks for high-volume hiring |
| Art. 10 Data governance | Statement that training data came from "other clients" | No information on data quality, representativeness, or bias examination | Description of training data and bias testing by gender, age, nationality, and disability |
| Art. 11 Technical documentation | None | Missing | Confirmation that technical documentation exists and is available to the market surveillance authority |
| Art. 12 Record-keeping | Usage logs exist (we used them to measure recruiter time) | Unknown whether logs capture inputs, scores, and overrides | Confirmation of what is logged and for how long |
| Art. 13 Instructions for use | Short user guide | No stated accuracy, limitations, or known risks of misuse | Full instructions for use, including accuracy metrics and limitations |
| Art. 14 Human oversight design | Recruiter can open any profile | No explanation of scores; automatic rejection by default | Score explanations and a setting that turns off automatic rejection |
| Art. 15 Accuracy, robustness, cybersecurity | No metrics shared | Unknown | Accuracy metrics for our job types and a security summary |
| Conformity (Arts. 43, 47, 48, 49) | None | No EU declaration of conformity, CE marking, or EU database registration seen | All three before any wider rollout |

### 4.2 Our Obligations as Deployer (Article 26 and related)

| Obligation | Current State | Gap | Remediation |
|------------|--------------|-----|-------------|
| Use according to instructions (26(1)) | No full instructions received | Cannot show compliant use | Obtain instructions; align configuration |
| Human oversight by trained, empowered staff (26(2)) | One stretched recruiter per site; no training | Oversight is symbolic (Section 6) | Named, trained reviewers with time and authority |
| Relevant input data (26(4)) | Postcode and gap data fed in by default | Inputs may not be relevant to job fit | Remove or justify each input feature |
| Monitoring and suspension (26(5)) | No monitoring | Missing | Monthly outcome monitoring; suspend if risk found |
| Keep logs at least six months (26(6)) | Unknown | Possibly missing | Confirm retention with Talvio |
| Inform workers' representatives (26(7)) | Works council not consulted | Missing | Inform the works council before any rollout. Legal to confirm whether Dutch co-determination rules also apply. |
| Tell candidates AI is used (26(11)) | Candidates not told | Missing | Notice on the careers site and in every application acknowledgment |
| Right to explanation (Art. 86) | No process | Missing | Process to explain the role AI played in a decision on request |
| AI literacy (Art. 4) | No training | Missing | Training for recruiters, HR managers, and hiring managers |
| GDPR DPIA (GDPR Art. 35; AI Act 26(9)) | Not done | Missing | Complete before any further use |

### 4.3 GDPR Article 22: Automated Decisions
Automatic rejections below 35 are decisions based solely on automated processing with a significant effect on candidates, because losing a job opportunity is a significant effect. In SCHUFA (C-634/21, 2023), the Court of Justice held that even a score produced by one party counts as an automated decision when it plays a determining role in another party's decision. Here the score does more than that: it sends the rejection itself.

Article 22 allows this only in narrow cases. Contract necessity is sometimes argued for very high application volumes, but 25,000 applications a year across 8 sites is not that scale, and less intrusive options exist. Even where an exception applies, candidates must be able to get human review, express their view, and contest the decision. None of this exists today.

---

## 5. Fundamental Rights Impact Assessment

A formal fundamental rights impact assessment under Article 27 is required only for public bodies, private entities providing public services, and certain credit and insurance uses. Noordhaven is not required to do one. We do it anyway, because it is the clearest way to show the rights risks were considered, and it feeds the DPIA.

### 5.1 Rights Analysis

| Right (EU Charter) | Potential Impact | Severity | Mitigation |
|--------------------|------------------|----------|------------|
| Art. 1 Human dignity | Candidates rejected by a score with no person ever looking at them | Medium | End automatic rejection; human review of every rejection |
| Art. 8 Data protection | Personal data processed without notice, DPIA, or Article 22 safeguards | High | Notice, DPIA, Article 22 safeguards |
| Art. 15 Right to work | Qualified people denied entry-level jobs that are often their main route into work | High | Human review; bias testing; review of pilot rejections |
| Art. 21 Non-discrimination | Postcode, employment gaps, and language can act as proxies for national origin, disability, and caring responsibilities | High | Remove or test proxy features; outcome monitoring |
| Art. 47 Effective remedy | No way to learn AI was used or to ask for a review | High | Notice, explanation on request, review route |

### 5.2 Vulnerable Groups Impact
Entry-level logistics roles attract many applicants who are migrants, non-native speakers, returners after caring or illness, and people without formal qualifications. These are the groups most likely to be scored down by language, gaps, and postcode, and least likely to challenge a rejection. In the pilot, candidates with an employment gap of more than 12 months were automatically rejected at a noticeably higher rate than other candidates.

### 5.3 Mitigation Measures
See the conditions in Section 8.3. The most important are ending automatic rejection, removing or justifying proxy features, and offering a review route.

---

## 6. Human Oversight Evaluation

### 6.1 Current Oversight Mechanisms
Recruiters can open any profile and override a score. In practice, they review the shortlist, rarely look below it, and almost never stop an automatic rejection in the five-day window.

### 6.2 Effectiveness Assessment

| Factor | Assessment | Evidence |
|--------|------------|----------|
| Human reviews all outputs | No | Rejections below 35 go out automatically |
| Human can easily override | Partial | Possible, but must be done within five days and is rarely used |
| Human has sufficient time | No | Under a minute per candidate, alongside onboarding and scheduling work |
| Human sees uncertainty/confidence | No | Only the score and rank are shown |
| Human trained on limitations | No | No training given |
| Appeals process exists | No | None |

### 6.3 Overall Assessment
- [ ] Meaningful oversight
- [ ] Partially meaningful
- [x] Symbolic only

The vendor's claim that "recruiters make every decision" is not true in this setup. For rejected candidates, the tool makes the decision and the recruiter never sees it.

### 6.4 Recommendations for Improvement
1. Turn off automatic rejection. Every rejection is confirmed by a person.
2. Show recruiters why a candidate scored as they did, not just the score.
3. Have recruiters review a random sample of low-scoring candidates each week to check the tool.
4. Free up recruiter time or add reviewers during peak hiring.

---

## 7. Bias and Discrimination Analysis

### 7.1 Protected Characteristics Assessment

| Characteristic | Could Be Inferred From | Risk Level |
|----------------|----------------------|------------|
| Race/Ethnicity, national origin | Postcode, language skills, foreign work history, name of previous employers | High |
| Gender | Employment gaps (caring), part-time history | Medium |
| Age | Years of experience, graduation dates | Medium |
| Disability | Employment gaps (illness) | High |
| Religion | Unlikely from inputs used | Low |
| Sexual Orientation | Unlikely from inputs used | Low |
| Socioeconomic Status | Postcode, certifications | Medium |

### 7.2 Training Data Bias Assessment
The model learned from other clients' past hiring decisions. If those decisions favored certain groups, the model will repeat that pattern and present it as "job fit." Talvio has not shared enough to rule this out.

### 7.3 Fairness Testing Results
Talvio shared a one-page summary covering gender and age only. It does not cover national origin or disability, which are the highest risks here. Our own review of pilot outcomes found the employment-gap pattern in Section 5.2. Testing by national origin is limited, because we do not and should not collect that data. We will test using proxies such as postcode and language, with the DPIA setting the limits.

---

## 8. Deployment Decision

### 8.1 Decision Matrix

| Factor | Assessment | Weight | Notes |
|--------|------------|--------|-------|
| Technical compliance | Not met today; achievable | High | Depends on Talvio providing documentation |
| Fundamental rights protection | Not met today | High | Proxy features and no remedy |
| Human oversight effectiveness | Symbolic | High | Fixable with process changes |
| Bias risk | High, partly unknown | High | Needs testing before rollout |
| Business benefit | Strong | Medium | Time-to-hire fell from 19 to 8 days |

The business benefit is real, and most gaps can be fixed with process changes and vendor documentation. That supports conditional approval rather than refusal. The video add-on cannot be fixed by any condition, so it is prohibited.

### 8.2 Recommendation
- [x] APPROVE with conditions (below)
- [x] PROHIBIT the video-interview add-on

### 8.3 Conditions for Approval

**Immediately (pilot sites):**
1. Turn off automatic rejection today.
2. Do not enable the video-interview add-on, now or later.
3. Review the candidates automatically rejected during the pilot, starting with those with employment gaps, and invite those wrongly rejected to reapply.
4. Add an AI notice to the careers site and application acknowledgments.

**Before any rollout beyond the two pilot sites:**
5. Complete a DPIA.
6. Receive from Talvio the full instructions for use, the EU declaration of conformity, CE marking, and confirmation of EU database registration.
7. Remove postcode, employment gaps, and language as inputs, or justify each in the DPIA, and test for bias by gender, age, and proxies for national origin and disability.
8. Name trained reviewers with time to review every rejection, and set up a way for candidates to request an explanation and a human review.

### 8.4 Monitoring Requirements
- Monthly: selection and rejection rates by employment gap, postcode band, and language, reviewed by HR and Risk & Compliance.
- Quarterly: sample review of low-scoring candidates by a second reviewer.
- Suspend use and inform Talvio if monitoring shows a risk to health, safety, or fundamental rights (Article 26(5)).
- Re-assess after any Talvio model update, any complaint alleging discrimination, or any regulator inquiry.
- Full review in six months.
- Inform the works council before rollout and share monitoring results with it.
- AI literacy training for everyone who uses or manages the tool, refreshed yearly.
- Contract terms requiring Talvio to notify us before retraining or changing the model, and to cooperate with audits and regulator requests.

---

## 9. Appendices

### A. Technical Documentation Reference
Requested from Talvio on October 7, 2026. Not yet received.

### B. Testing Results
Pilot outcome review (employment-gap pattern): Risk & Compliance working file. Talvio bias summary: gender and age only.

### C. Stakeholder Consultation Record

| Stakeholder | Position |
|-------------|----------|
| HR | Wants rollout to all 8 sites; accepts ending automatic rejection |
| Operations | Supports faster hiring |
| Legal | Concerned about the pilot running without review |
| Works council | Not yet consulted |
| Talvio | Says the tool "only assists"; reluctant to share training data details |

---

## Approval

| Role | Name | Date | Signature |
|------|------|------|-----------|
| Data Protection Officer | | | |
| General Counsel | | | |
| Head of IT | | | |
| HR Director (Business Owner) | | | |
