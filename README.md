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
      <td><b>Geopolitical & Data Sovereignty</b></td>
      <td>All corporate PII and operational datasets must reside and be processed within continental U.S. boundaries (CONUS) to satisfy regulatory criteria.</td>
      <td>• Primary cloud infrastructure is hosted in AWS US-East.<br>• <b>Finding:</b> Secondary, non-production testing environments and customer support desks operate out of high-risk offshore jurisdictions.</td>
      <td><span style="color:orange;"><b>Conditional Pass</b></span></td>
      <td>🟡 <b>Medium</b></td>
    </tr>
    <tr>
      <td><b>API & Integration Security</b></td>
      <td>External API integrations must utilize secure OAuth 2.0 authentication tokens, restrict permissions to least privilege, and undergo annual penetration testing.</td>
      <td>• OAuth 2.0 token architecture verified.<br>• <b>Finding:</b> Vendor API documentation reveals a lack of automated rate-limiting, increasing susceptibility to Denial of Service (DoS) or bulk data scraping attacks.</td>
      <td><span style="color:orange;"><b>Conditional Pass</b></span></td>
      <td>🟡 <b>Medium</b></td>
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
