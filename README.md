# Project 3: Third-Party Risk Management (TPRM) Program & Vendor Scoring Rubric

##  Executive Summary
Modern enterprise operations rely heavily on third-party SaaS ecosystems, introducing significant supply chain, concentration, and data privacy risks. This project demonstrates the design of an end-to-end Vendor Security Assessment Framework implemented for a mock enterprise onboarding a critical cloud-based HR, Payroll, and Workforce Analytics platform ("TalentCloud SaaS").

The objective of this framework is to establish standard vendor security questionnaires, analyze external compliance documentation (SOC 2 Type II), evaluate emerging AI adoption security configurations, and issue formal Risk Scorecards to leadership with clear business-risk recommendations.

---

##  TPRM Assessment Lifecycle
Every high-risk vendor onboarding request goes through a rigorous four-phase vetting pipeline:
1. **Inherent Risk Triage:** Determining the types of corporate data the vendor will touch (e.g., PII, PHI, Financials, Intellectual Property).
2. **Artifact Collection:** Gathering the vendor's SOC 2 Type II reports, penetration testing summaries, privacy policies, and business continuity plans.
3. **Control Evaluation & Gap Scoring:** Reviewing collected materials against internal risk thresholds.
4. **Governance Decision:** Approving, conditionally approving with compensating controls, or rejecting the vendor.

---

##  Vendor Security Scorecard: "TalentCloud SaaS"

Below is the formal risk scoring evaluation and security rubric compiled following a detailed review of the vendor's security posture.

<table width="100%">
  <thead>
    <tr>
      <th width="15%">Assessment Domain</th>
      <th width="25%">Internal Security Requirement</th>
      <th width="35%">Vendor Actual State / Finding</th>
      <th width="15%">Domain Grade</th>
      <th width="10%">Risk Level</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Data Encryption</b></td>
      <td>Data must be encrypted using AES-256 at rest and TLS 1.3 in transit. Vendor must support customer-managed keys (BYOK) for high-sensitivity tiers.</td>
      <td>• Fully supports AES-256 and TLS 1.3.<br>• Customer-managed keys (BYOK) are supported but require an upgraded enterprise license tier.</td>
      <td><span style="color:green;"><b>Pass (Exceeds Baseline)</b></span></td>
      <td>🟢 <b>Low</b></td>
    </tr>
    <tr>
      <td><b>Identity & Access Management</b></td>
      <td>Mandatory integration with corporate Identity Providers (IdP) via SAML 2.0 / OIDC for Federated Single Sign-On (SSO) and enforced MFA.</td>
      <td>• SAML 2.0 integration verified.<br>• <b>Critical Finding:</b> Vendor does not natively enforce MFA for their internal sub-processors managing database environments.</td>
      <td><span style="color:orange;"><b>Conditional Pass</b></span></td>
      <td>🟡 <b>Medium</b></td>
    </tr>
    <tr>
      <td><b>Compliance Artifacts</b></td>
      <td>Provision of a clean SOC 2 Type II report spanning at least a 6-month testing window with no unmitigated material exceptions.</td>
      <td>• SOC 2 Type II report provided for the trailing 12 months.<br>• Minor exception noted in physical datacenter visitor logging (mitigated by cloud host AWS).</td>
      <td><span style="color:green;"><b>Pass</b></span></td>
      <td>🟢 <b>Low</b></td>
    </tr>
    <tr>
      <td><b>AI Governance & Privacy</b></td>
      <td>Proprietary corporate data input into the platform must be excluded from public LLM/AI model training pools. Opt-out parameters must be contractually guaranteed.</td>
      <td>• <b>Major Finding:</b> Platform features an opt-in "AI Resume Scoring" module. By default, user inputs are retained for proprietary model refinement.<br>• No clear technical kill-switch exists in the standard customer console.</td>
      <td><span style="color:red;"><b>Fail (High Risk)</b></span></td>
      <td>🔴 <b>High</b></td>
    </tr>
    <tr>
      <td><b>Business Continuity</b></td>
      <td>Documented Disaster Recovery (DR) plan with an RTO ≤ 4 hours and an RPO ≤ 1 hour. Evidence of annual simulation testing required.</td>
      <td>• DR plan provided.<br>• Verified RTO of 8 hours and RPO of 2 hours during their last tested tabletop simulation. Gaps exist against internal enterprise SLAs.</td>
      <td><span style="color:orange;"><b>Conditional Pass</b></span></td>
      <td>🟡 <b>Medium</b></td>
    </tr>
  </tbody>
</table>

---

##  Executive Recommendation & Risk Treatment Plan
Based on the data collected in the scorecard, **TalentCloud SaaS is approved with conditional security restrictions.** The platform cannot be fully integrated into production operations until the following compensating controls are legally and technically instituted:

1. **Contractual AI Data Addendum (Remediation for AI Governance):** Enterprise legal counsel must append a custom data protection rider to the Master Services Agreement (MSA). This rider must explicitly state that all corporate customer data is barred from vendor machine learning model training pipelines, overriding the platform's default opt-in settings.
2. **Technical Module Disablement:** The IT administration team must globally disable the "AI Resume Scoring" module via centralized service configuration policies until the legal addendum is fully executed by both entities.
3. **Sub-Processor SLA Enforcement (Remediation for IAM):** The vendor must supply a formal attestation or contractual commitment demonstrating that their database sub-processors will implement Multi-Factor Authentication (MFA) controls within 90 days. Failure to provide this artifact will result in an automatic review and termination of the software onboarding waiver.

---

##  Key Insights & Business Alignment
1. **The Evolution of Third-Party Risk:** TPRM is no longer just about reading traditional SOC 2 reports. The rapid integration of native AI utilities into popular SaaS platforms means modern GRC analysts must closely audit vendor AI data-retention frameworks to stop intellectual property and consumer PII leakage.
2. **Compensating Controls Enable Business Velocity:** A rigid compliance function simply says "No" to a vendor that fails a control check, slowing down business growth. A risk-focused GRC analyst designs strategic, legally binding compensating controls that protect corporate assets while safely enabling the business to leverage new technologies.
3. **Continuous Vendor Lifecycles:** Vendor risk management is a loop, not a linear project. High-risk platforms processing employee details require automated annual trigger reassessments, continuous dark-web leak monitoring, and immediate contractual updates whenever vendor data-sharing architectures shift.
