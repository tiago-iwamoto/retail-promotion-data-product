# Business Framing

## 1. Business Context

A newly launched grocery store is operating in a competitive area and needs to evaluate the real impact of its promotion strategy.

Current reporting lacks standardized definitions and reliable availability timing, leading to uncertainty in decision-making.

Leadership requires a structured and trusted data foundation to:

- Understand the real impact of promotions on revenue
- Compare store performance under consistent metric definitions
- Ensure daily revenue numbers are stable and finalized

---

## 2. Primary Stakeholders

- **Executive Leadership**  
  Uses standardized revenue and promotion metrics to evaluate commercial performance and strategic direction.

- **Commercial / Store Operations Teams**  
  Analyze promotion impact and store-level performance under consistent metric definitions.

- **Finance**  
  Relies on finalized and reconciled revenue data for financial tracking and validation.

- **Data & Analytics Teams**  
  Consume this dataset as the official source for dashboards and reporting without redefining business logic.

- **IT / Data Engineering**  
  Responsible for ingestion, pipeline reliability, and availability of source data, in alignment with the defined data contracts and quality expectations.

---

## 3. Key Decisions Enabled

This data product supports the following decisions:

- Evaluate whether current promotion strategies generate measurable revenue impact.
- Determine if discount policies should be adjusted based on store-level performance.
- Compare store performance under standardized metric definitions.
- Monitor reporting SLA compliance to ensure daily decision reliability.

---

## 4. Data Product Scope

- 24 months of historical transaction data
- Three daily ingestion batches
- Daily aggregated performance metrics (revenue, discount value, basket size, promotion rate)
- Transaction-level promotion tracking
- Standardized definitions for revenue and discount-related metrics

---

## 5. Definition of "Good Data"

### Business Contract

- Daily revenue numbers are considered final after the 07PM 3rd batch.
- Revenue figures are consistent across all official reports.
- No active store is excluded from reporting.
- Aggregated performance metrics reconcile with transaction-level detail.

### Technical Enforcement

- `Transaction_ID` is unique and non-null.
- `Store_ID` is unique and non-null in the store dimension.
- Daily aggregated revenue reconciles with transaction-level totals within zero tolerance.
- ≥95% on-time availability of finalized daily revenue.
- ≤1 SLA breach per month.

---

## 6. Ownership & Accountability

- Data Manager owns the data product lifecycle and defined guarantees.
- Data Engineers are responsible for ingestion, transformation, and pipeline reliability.
- Source system owners are accountable for upstream transactional data correctness.
- Business stakeholders and Data Manager jointly define and approve metric definitions.
- Data team monitors SLA compliance and escalates incidents when guarantees are breached.

---

## 7. Success Metrics

- Dataset is formally adopted as the official single source of truth for revenue and promotion reporting.
- Measurable reduction in metric definition disputes across reporting teams.
- ≥95% on-time availability of finalized daily revenue.
- ≤1 SLA breach per month.

---

## 8. Key Risks

- Rapid store expansion exceeding current SLA capacity assumptions.
- Technical failures impacting batch schedules.
- Business teams bypassing official metric definitions.
- Changes in promotion logic implemented without alignment with the data product contract.
