# AI Compliance Checklist

**Version**: 1.0  
**Last Updated**: 2026-07-09

Use this checklist to verify your AI system's compliance with requirements.

## Security Controls

### Access Control (AC)
- [ ] **AC-2.1**: MFA enabled for all system access
- [ ] **AC-2.2**: Active user account audit log maintained
- [ ] **AC-2.3**: Privileged account management implemented
- [ ] **AC-3.1**: RBAC defined and enforced
- [ ] **AC-3.2**: Least privilege principle enforced
- [ ] **AC-3.3**: Dev/Test/Prod environments separated
- [ ] **AC-6.1**: Privileged access restrictions enforced
- [ ] **AC-6.2**: Session timeouts implemented

### Audit & Accountability (AU)
- [ ] **AU-2.1**: Audit events defined and logged
- [ ] **AU-3.1**: Audit records contain required fields
- [ ] **AU-4.1**: Audit log storage capacity sufficient
- [ ] **AU-5.1**: Audit failure procedures documented
- [ ] **AU-6.1**: Audit logs reviewed regularly
- [ ] **AU-12.1**: Auditing enabled for all systems
- [ ] **AU-12.4**: Model inference predictions logged

### System & Communications Protection (SC)
- [ ] **SC-2.1**: Application partitioning implemented
- [ ] **SC-7.1**: Boundary protection enforced
- [ ] **SC-7.8**: Physical/logical network segmentation
- [ ] **SC-7.12**: Permitted outbound connections monitored
- [ ] **SC-8.1**: Transmission confidentiality (TLS 1.2+)
- [ ] **SC-8.2**: Transmission integrity (HMAC/signatures)
- [ ] **SC-13.1**: Cryptographic module validated
- [ ] **SC-28.1**: Data at rest encrypted (AES-256 minimum)
- [ ] **SC-28.3**: Sensitive information encrypted in storage

### Identification & Authentication (IA)
- [ ] **IA-2.1**: Multi-factor authentication required
- [ ] **IA-2.2**: User identification before authentication
- [ ] **IA-4.1**: Unique user identifiers assigned
- [ ] **IA-5.1**: Password requirements enforced
- [ ] **IA-5.2**: Password strength requirements (minimum 12 chars)
- [ ] **IA-6.1**: Obscure feedback during authentication
- [ ] **IA-8.1**: Authentication for external connections

## AI-Specific Controls

### Model Governance (AI-MOD)
- [ ] **AI-MOD-01.1**: Model inventory created and maintained
- [ ] **AI-MOD-01.2**: Model version control implemented
- [ ] **AI-MOD-01.3**: Model lineage documented
- [ ] **AI-MOD-02.1**: Pre-deployment validation testing required
- [ ] **AI-MOD-02.2**: Adversarial testing performed
- [ ] **AI-MOD-02.3**: Robustness analysis documented
- [ ] **AI-MOD-03.1**: Explainability methods documented (LIME/SHAP)
- [ ] **AI-MOD-03.2**: Model decision logic documented
- [ ] **AI-MOD-03.3**: Prediction audit trails maintained
- [ ] **AI-MOD-04.1**: Fairness assessment completed before deployment
- [ ] **AI-MOD-04.2**: Disparate impact testing performed
- [ ] **AI-MOD-04.3**: Bias mitigation strategies implemented
- [ ] **AI-MOD-04.4**: Production bias monitoring enabled

### Data Governance (AI-DATA)
- [ ] **AI-DATA-01.1**: Data classification scheme defined
- [ ] **AI-DATA-01.2**: Training data classified by sensitivity
- [ ] **AI-DATA-01.3**: Data lineage tracked
- [ ] **AI-DATA-02.1**: Data quality validation before training
- [ ] **AI-DATA-02.2**: Data integrity checksums implemented
- [ ] **AI-DATA-02.3**: Data anomalies documented
- [ ] **AI-DATA-03.1**: Feature minimization applied
- [ ] **AI-DATA-03.2**: Unnecessary features removed
- [ ] **AI-DATA-03.3**: Differential privacy considered
- [ ] **AI-DATA-04.1**: PII detection implemented
- [ ] **AI-DATA-04.2**: PII redaction procedures documented
- [ ] **AI-DATA-04.3**: Consent records maintained

### Operational Security (AI-OPS)
- [ ] **AI-OPS-01.1**: Training activity logging implemented
- [ ] **AI-OPS-01.2**: Model deployment logging enabled
- [ ] **AI-OPS-01.3**: Performance monitoring active
- [ ] **AI-OPS-01.4**: Alert thresholds configured
- [ ] **AI-OPS-02.1**: Change approval process defined
- [ ] **AI-OPS-02.2**: Model version control in place
- [ ] **AI-OPS-02.3**: Rollback procedures tested
- [ ] **AI-OPS-03.1**: Incident response plan documented
- [ ] **AI-OPS-03.2**: RCA procedures established
- [ ] **AI-OPS-03.3**: Incident logs maintained

## Data Protection

### Information Security (IS)
- [ ] **IS-1.1**: Security classification scheme defined
- [ ] **IS-2.1**: Security requirements documented
- [ ] **IS-3.1**: Security controls selected and tailored
- [ ] **IS-6.1**: Information flow control policies
- [ ] **IS-7.1**: Information system partitioning

### System & Information Integrity (SI)
- [ ] **SI-2.1**: Flaw remediation process established
- [ ] **SI-3.1**: Malware protection mechanisms deployed
- [ ] **SI-4.1**: System monitoring implemented
- [ ] **SI-4.2**: System-generated alerts configured
- [ ] **SI-5.1**: Security alerts and advisories subscribed
- [ ] **SI-7.1**: Information system monitoring enabled
- [ ] **SI-10.1**: Information input validation implemented
- [ ] **SI-11.1**: Error handling procedures documented
- [ ] **SI-12.1**: Information handling procedures documented

## Vendor & Third-Party Management

- [ ] **VM-1.1**: Third-party AI services assessed
- [ ] **VM-1.2**: Compliance requirements in contracts
- [ ] **VM-1.3**: Data handling agreements signed
- [ ] **VM-2.1**: Vendor compliance audits scheduled
- [ ] **VM-2.2**: Audit results documented
- [ ] **VM-3.1**: Vendor incidents tracked
- [ ] **VM-3.2**: Remediation actions documented

## Documentation & Training

- [ ] **DOC-1.1**: Security plan maintained
- [ ] **DOC-1.2**: Risk assessment completed
- [ ] **DOC-2.1**: Procedures documented and accessible
- [ ] **DOC-2.2**: Procedures regularly reviewed and updated
- [ ] **DOC-3.1**: Personnel security training completed
- [ ] **DOC-3.2**: AI governance training provided
- [ ] **DOC-3.3**: Training records maintained

## Incident Response

- [ ] **IR-1.1**: Incident response plan established
- [ ] **IR-2.1**: Incident response team defined
- [ ] **IR-3.1**: Incident detection procedures
- [ ] **IR-4.1**: Incident containment procedures
- [ ] **IR-6.1**: Incidents reported to appropriate parties
- [ ] **IR-7.1**: Incident handling assistance available
- [ ] **IR-8.1**: Post-incident reviews conducted

## Compliance Assessment

### Scoring
- **Total Items**: Count total checkboxes
- **Checked Items**: Count checked items
- **Compliance Score**: (Checked / Total) × 100%

### Target Scores
- 🔴 **Below 70%**: Critical compliance gaps - immediate remediation required
- 🟡 **70-89%**: Compliance gaps - remediation plan needed
- 🟢 **90-99%**: Good compliance - monitor and maintain
- 🟢 **100%**: Full compliance - continue monitoring

## Next Steps

1. **Complete Checklist**: Go through each item and verify status
2. **Document Gaps**: List any non-compliant items
3. **Create Remediation Plan**: For each gap, assign owner and deadline
4. **Schedule Review**: Quarterly compliance reviews recommended
5. **Audit Trail**: Keep completed checklists for audit records

---

**Last Compliance Assessment**: ___________
**Assessed By**: ___________
**Next Assessment Date**: ___________
