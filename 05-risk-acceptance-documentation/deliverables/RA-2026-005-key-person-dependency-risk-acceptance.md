# Risk Acceptance Document

> **Fictional scenario.** Sierra Meridian Field Services, Inc. is an invented company created for this portfolio. Any resemblance to a real organization is coincidental. All figures are illustrative assumptions.
>
> **Companion document.** This risk is the reason RA-2026-004 (external access to draft invoices) cannot be fixed quickly. Company background, impact figures, and meeting minutes are in RA-2026-004 and are not repeated here.

## Document Header

| Field | Value |
|-------|-------|
| Risk ID | RA-2026-005 |
| System/Asset | InvoiceTrack (in-house AP workflow, built 2014) and its permission mapping to the ShareFile invoice folders |
| Risk Owner | Chief Information Officer |
| Prepared By | Faith Olofintuyi, Risk & Compliance |
| Date | October 7, 2026 |
| Review Date | March 22, 2027 (aligned with RA-2026-004) |
| Version | 0.1 (Draft) |
| Linked Risk | RA-2026-004: External access to draft invoices |

---

## 1. Executive Summary

Only one person understood how InvoiceTrack connects to the ShareFile folders that hold draft invoices, and that engineer was laid off in the last reduction in force without a handover. Nobody still at the company can safely change those permissions, and nothing is written down. This is why the invoice access gap in RA-2026-004 cannot be closed quickly, and it means any InvoiceTrack failure could stop vendor payments with no one able to fix it.

The Risk & Compliance team recommended Option B, a short contractor engagement to map and document the system and cross-train two internal staff. On August 19, 2026, alongside RA-2026-004, the executive team chose Option D instead: internal documentation using existing staff, with limited paid help from the former engineer if available.

This acceptance runs until March 22, 2027 and holds only if the Section 8 conditions are met.

**Recommendation:**
- [ ] Option A: Replace InvoiceTrack
- [x] Option B: Contractor mapping, documentation, and cross-training **(Risk & Compliance team recommendation)**
- [ ] Option C: Accept the risk as it stands
- [ ] Option D: Internal documentation with limited former-engineer help **(Executive decision)**

---

## 2. Risk Description

### 2.1 What Could Happen

| Scenario | Description |
|----------|-------------|
| Scenario 1: AP outage | InvoiceTrack breaks after a routine update, a ShareFile change, or an expired service account. Nobody knows how to restore it, and vendor payments stop. |
| Scenario 2: Fix causes harm | Staff try to close the RA-2026-004 gap by breaking permission inheritance and unknowingly break the AP workflow or lose vendor data. |
| Scenario 3: Blind incident response | During a suspected invoice fraud, nobody can explain who should have had access or how the system grants it, which slows the investigation. |

### 2.2 How It Could Happen
1. **No documentation.** The permission design, service accounts, and scripts were never written down.
2. **No backup person.** No one shadowed the engineer or reviewed their work.
3. **Unmanaged change.** ShareFile and Windows updates continue on their normal schedule, with no one able to judge whether they will affect InvoiceTrack.

### 2.3 Why We Might Not Know
- Nothing tracks InvoiceTrack's hidden dependencies, so a breaking change would surface only when AP stops working.
- The engineer's accounts and scripts may still be running under credentials nobody manages.

---

## 3. Risk Assessment

| Factor | Assessment |
|--------|------------|
| Likelihood | **High.** The knowledge is already gone, and the risk has already blocked the RA-2026-004 fix. |
| Impact | **High.** AP downtime costs about $25K to $40K per day (RA-2026-004, Section 3.2), and late payments delay field job sites. The bigger cost is indirect: this risk keeps RA-2026-004's exposure open. |
| Detection | **Low.** A problem would show up only as an outage. |

**Current Risk Position: HIGH**

---

## 4. Existing Controls Assessment

| Control | Effectiveness | Honest Assessment |
|---------|---------------|-------------------|
| Offboarding checklist | Weak | Removes access but does not capture knowledge |
| Backups of InvoiceTrack data | Adequate | Protects data, but nobody knows how to restore the full workflow |
| IT change approval | Weak | Approvers cannot judge InvoiceTrack impact without documentation |

**Missing:** system documentation, a trained backup person, knowledge transfer as part of offboarding, and an inventory of the engineer's service accounts and scripts.

**Rating:** [ ] Strong [ ] Adequate [ ] Weak [x] Insufficient

---

## 5. Options Analysis

| Factor | Option A: Replace InvoiceTrack | Option B: Contractor mapping (Recommended) | Option C: Accept | Option D: Internal documentation (Selected) |
|--------|-------------------------------|--------------------------------------------|------------------|---------------------------------------------|
| What it involves | Same as RA-2026-004 Option A | Contractor maps permissions and dependencies, writes a runbook, and cross-trains two IT staff | Do nothing | IT staff document what they can; up to 40 paid hours from the former engineer if willing; inventory service accounts |
| Cost | $450K to $650K | $40K to $60K (part of RA-2026-004 Option B's $70K to $110K) | $0 | About $8K plus staff time |
| Timeline | 9 to 12 months | 60 to 90 days | None | 90 days |
| Residual Risk | Low | Medium | High | Med-High |
| Main drawback | Not budgeted | Small unbudgeted spend | Leaves both risks open | Depends on staff with no spare capacity, and on the former engineer agreeing to help |

---

## 6. Recommendation

**Risk & Compliance team recommendation:** Option B
**Executive decision (August 19, 2026):** Option D

**The Risk & Compliance team recommends Option B because:**
1. It produces documentation and two trained people in 90 days, using outside capacity the business does not have internally.
2. It is the prerequisite for closing RA-2026-004 safely.
3. It does not depend on the former engineer's goodwill.

**The executive team selected Option D because:**
1. No budget is set aside for outside help this fiscal year.
2. Some knowledge may be recovered cheaply from the former engineer.

**Risk & Compliance team position:** Option D is not a fix. It relies on the same overloaded staff whose lack of capacity created this problem, and on a former employee who has no obligation to help. If the Section 8 conditions slip, this risk should go back to the executive team.

### 6.1 Immediate Actions (within 30 days)
- [ ] Inventory every service account, scheduled task, and script the former engineer created, and assign each an owner (Owner: IT Director)
- [ ] Rotate credentials on those accounts (Owner: Director of IT Security)
- [ ] Ask Legal to review the former engineer's separation agreement before any contact (Owner: General Counsel)
- [ ] Freeze non-urgent changes to InvoiceTrack and the invoice folders until documentation exists (Owner: CIO)

### 6.2 Future Commitments
| Action | Timeline | Owner |
|--------|----------|-------|
| Written InvoiceTrack and permission documentation | Within 90 days (matches RA-2026-004, Section 6.4) | IT Director |
| Name and train one backup person | Within 90 days | CIO |
| Add knowledge transfer to the offboarding procedure for critical roles | Within 60 days | HR with CIO |
| Submit Option B with RA-2026-004 Option B in the FY2027 budget | Q1 FY2027 planning cycle | CIO |

---

## 7. Residual Risk Acknowledgment

| Residual Risk | Why Accepted |
|---------------|--------------|
| Internal documentation may be incomplete or wrong | Executive decision based on budget |
| Only one backup person, with limited time | Staffing limits |
| RA-2026-004 cannot be safely fixed until documentation is done | Accepted, with the 90-day documentation deadline |

---

## 8. Conditions and Validity

### 8.1 This Acceptance is Valid Only If:
- [ ] Section 6.1 actions are completed within 30 days of signature
- [ ] Documentation is delivered within 90 days and reviewed by the Risk & Compliance team
- [ ] Option B is submitted in the FY2027 budget process

If any condition is not met, this acceptance lapses and the risk returns to the executive team.

### 8.2 This Acceptance Expires On:
March 22, 2027, the same date as RA-2026-004, so both are reviewed together.

### 8.3 Re-evaluation Triggers
- [ ] Any unplanned InvoiceTrack outage
- [ ] The named backup person leaves or changes role
- [ ] The former engineer declines to help or is unavailable
- [ ] RA-2026-004 is re-evaluated for any reason

---

## 9. Compliance Implications

| Framework | Requirement | Impact of Acceptance |
|-----------|-------------|---------------------|
| SOC 2 (CC1.4) | Commitment to competence, including succession planning | No backup person and no documented knowledge for a critical system. Likely observation. |
| SOC 2 (CC3.4) | Changes that could significantly affect internal control are identified and assessed | The layoff removed critical knowledge without an assessment. This document is the late assessment. |
| SOC 2 (CC8.1) | Changes are authorized, tested, and approved | Changes to InvoiceTrack cannot be properly assessed without documentation. The change freeze in Section 6.1 is the interim control. |

### 9.1 Legal Considerations
- **Former engineer's separation agreement.** Before any contact, Legal should check the agreement for confidentiality, cooperation, and non-disparagement terms. Any paid help needs a new written agreement covering confidentiality and the return of company information.
- **Worker classification.** Rehiring a former employee as a contractor to do the same work can raise misclassification issues under California's ABC test (Labor Code §2775). Keep the engagement short, scoped, and documented. **Legal to confirm.**
- **Access for the former engineer.** Any access must be temporary, limited to what the work needs, monitored, and removed when the work ends.

---

## 10. Signatures

### Risk Owner (Business)
By signing, I acknowledge that I understand the risk described above and accept responsibility for this risk on behalf of the organization.

| Field | Value |
|-------|-------|
| Name | |
| Title | Chief Information Officer |
| Date | |
| Signature | |

### Security Review
| Field | Value |
|-------|-------|
| Name | |
| Title | Director of IT Security |
| Date | |
| Signature | |

### Compliance Review
| Field | Value |
|-------|-------|
| Name | |
| Title | General Counsel |
| Date | |
| Signature | |

### Executive Approval
| Field | Value |
|-------|-------|
| Name | |
| Title | Chief Executive Officer |
| Date | |
| Signature | |

---

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | October 7, 2026 | Faith Olofintuyi | Initial draft |
