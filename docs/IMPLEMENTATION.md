# Implementation Guide

Step-by-step instructions for implementing AI compliance in your organization.

## Phase 1: Planning & Assessment (Week 1-2)

### 1.1 Form Compliance Team
- **CISO**: Chief Information Security Officer (Sponsor)
- **Compliance Officer**: Policy and procedure owner
- **AI Lead**: Technical AI/ML expert
- **Data Steward**: Data governance and privacy
- **DevOps Lead**: Infrastructure and deployment
- **Legal/Procurement**: Vendor and contract management

### 1.2 Current State Assessment
```bash
# Use the compliance checker to assess current state
python code/compliance_checker.py --report > current_state.txt
```

### 1.3 Gap Analysis
- Review current controls vs. requirements
- Identify critical gaps
- Prioritize remediation efforts

## Phase 2: Security Controls Implementation (Week 3-6)

### 2.1 Access Control

**Implement MFA:**
```python
import pyotp

def setup_mfa(user_id):
    secret = pyotp.random_base32()
    totp = pyotp.TOTP(secret)
    return secret, totp.provisioning_uri(name=user_id)

def verify_mfa(secret, token):
    totp = pyotp.TOTP(secret)
    return totp.verify(token)
```

**Implement RBAC:**
```python
ROLES = {
    'admin': ['create_model', 'deploy_model', 'delete_model'],
    'developer': ['create_model', 'train_model', 'test_model'],
    'viewer': ['view_model', 'view_logs']
}

def check_permission(user_role, action):
    return action in ROLES.get(user_role, [])
```

### 2.2 Data Protection

**Implement Encryption at Rest:**
```python
from cryptography.fernet import Fernet

key = Fernet.generate_key()
cipher = Fernet(key)

def encrypt_data(data):
    return cipher.encrypt(data.encode())

def decrypt_data(encrypted_data):
    return cipher.decrypt(encrypted_data).decode()
```

### 2.3 Audit Logging

**Implement Centralized Logging:**
```python
import logging
import json

def setup_audit_logging():
    logger = logging.getLogger('audit')
    handler = logging.FileHandler('/var/log/audit/model-access.log')
    formatter = logging.Formatter(json.dumps({
        'timestamp': '%(asctime)s',
        'user': '%(user)s',
        'action': '%(action)s',
        'resource': '%(resource)s',
        'result': '%(result)s'
    }))
    handler.setFormatter(formatter)
    logger.addHandler(handler)
    return logger

audit_log = setup_audit_logging()

def log_model_access(user_id, model_id, action):
    audit_log.info(f'Model access',
        extra={
            'user': user_id,
            'action': action,
            'resource': model_id,
            'result': 'success'
        })
```

## Phase 3: AI-Specific Controls (Week 7-10)

### 3.1 Model Governance

**Create Model Inventory:**
```json
{
  "models": [
    {
      "id": "model-001",
      "name": "Risk Assessment Model",
      "version": "1.2.0",
      "owner": "john.doe@company.com",
      "training_data": "dataset-2024-001",
      "deployment_date": "2024-01-15",
      "environment": "production",
      "last_updated": "2024-07-09",
      "compliance_status": "compliant"
    }
  ]
}
```

### 3.2 Bias Detection

**Fairness Assessment:**
```python
from fairlearn.metrics import demographic_parity_difference

def check_fairness(y_true, y_pred, sensitive_attr):
    dpd = demographic_parity_difference(
        y_true, y_pred, 
        sensitive_features=sensitive_attr
    )
    
    bias_report = {
        'demographic_parity_difference': float(dpd),
        'status': 'compliant' if abs(dpd) < 0.1 else 'needs_remediation',
        'timestamp': datetime.now().isoformat()
    }
    
    return bias_report
```

## Phase 4: Continuous Monitoring (Ongoing)

### 4.1 Daily Tasks
- Monitor model performance metrics
- Review error logs
- Check system health

### 4.2 Weekly Tasks
- Fairness and bias metric reviews
- Security log analysis
- Compliance status check

### 4.3 Monthly Tasks
- Comprehensive compliance assessment
- Gap analysis
- Remediation plan review

### 4.4 Quarterly Tasks
- Full audit
- Policy review and updates
- Training and awareness sessions

## Checklist

- [ ] Compliance team formed
- [ ] Current state assessment completed
- [ ] Gap analysis documented
- [ ] Access control implemented
- [ ] Data encryption enabled
- [ ] Audit logging configured
- [ ] Model inventory created
- [ ] Validation testing implemented
- [ ] Bias detection enabled
- [ ] Monitoring dashboard deployed
- [ ] Incident response plan documented
- [ ] Staff training completed
- [ ] Compliance audit passed

---

**For questions or support, contact: compliance@company.com**