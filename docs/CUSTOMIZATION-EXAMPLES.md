# Customization: Real Examples

Not templates. Real examples of how different teams did this.

---

## Healthcare: Cancer Detection AI

### The System
```
Name: DiagnosticAI
What it does: Detects early-stage cancer from medical imaging
Data: Patient X-rays, CT scans, lab results
Risk: Misdiagnosis delays treatment
Who uses it: Radiologists at teaching hospitals
```

### What They Changed

**In the policy:**
```markdown
# Added Section: HIPAA Compliance

- All training data must be de-identified per HIPAA Safe Harbor
- Re-identification risk assessment required (< 0.04)
- Model outputs cannot contain patient names/IDs
- Audit logs track all PHI access

# Added Section: Clinical Safety

- Model must achieve 95%+ sensitivity (catch the cancer)
- Model must achieve 90%+ specificity (don't over-diagnose)
- When confidence < 85%, require human radiologist review
- Track all cases where model missed cancer
```

### What Worked
- Started with manual checklist
- Built relationships with radiologists early
- Made explainability a priority (doctors want to understand the model)
- Tracked adverse events seriously

### What Was Hard
- De-identification took longer than expected
- Getting clinical validation data
- Convincing radiologists the model was safe (took 6 months)
- Regulatory approval (required external validation)

---

## Finance: Credit Scoring AI

### The System
```
Name: CreditScore v2.0
What it does: Approve/deny loan applications
Data: Customer financial records, payment history
Risk: Discriminatory lending, customer harm
Who uses it: Banks deciding on loans
```

### What They Changed

**In the policy:**
```markdown
# Added Section: Fair Lending Compliance

- Test for disparate impact across protected classes
- Model must pass 4/5ths rule
- Every loan denial must include reason
- Customers can request explanation
```

### What Worked
- Involved legal/compliance early
- Built in fairness testing from day one
- Tracked and fixed bias issues quickly
- Transparent with regulators

### What Was Hard
- Getting historical data that wasn't biased
- Explaining fairness to business stakeholders
- Dealing with edge cases
- Managing expectations about approval rates

---

## Autonomous: Self-Driving Cars

### The System
```
Name: AutoDrive v5.0
What it does: Autonomous vehicle perception and decisions
Data: Camera, LIDAR, radar sensor feeds
Risk: Safety-critical decisions, accidents, deaths
Who uses it: Testing fleet, eventually customers
```

### What They Changed

**Safety-Critical Requirements:**
- All decisions must be deterministic
- Dual redundancy for critical functions
- Fallback to human driver if confidence < 99.5%
- Hardware watchdog timer
- Graceful degradation

### What Worked
- Invested heavily in simulation before real-world testing
- Built in redundancy from the start
- Conservative fallback thresholds
- Regular third-party review

### What Was Hard
- Edge cases
- Regulatory approval (very conservative)
- Cost (safety is expensive)
- Public perception vs. actual safety

---

## Research: Scientific Discovery AI

### The System
```
Name: ResearchAI v1.0
What it does: Protein structure prediction
Data: Public scientific datasets
Risk: Incorrect predictions mislead research
Who uses it: Research teams globally
```

### What They Changed

**Research Ethics:**
- IRB approval obtained before use
- Data sources clearly documented
- Attribution to original researchers
- License compliance verified

**Reproducibility:**
- Code published on GitHub
- Training data publicly available
- Model checkpoints versioned
- Results reproducible within ±5% variance
- Random seeds fixed
- Hyperparameters documented

### What Worked
- Publish early, often
- Community feedback caught issues
- Open source made collaboration easier
- Transparent about limitations

### What Was Hard
- IP concerns from institution
- Data licensing complexity
- Computational reproducibility
- Keeping up with rapidly evolving field

---

## How to Do Your Own

### Step 1: Understand Your System
```
- What is it?
- Who uses it?
- What data does it use?
- What could go wrong?
- Who cares about compliance?
```

### Step 2: Find Your Industry
```
- Healthcare → add patient protection
- Finance → add fairness/fraud
- Government → add security
- Research → add reproducibility
- Everything else → add security + data protection + bias
```

### Step 3: Customize the Policy
```
1. Copy AI-COMPLIANCE-POLICY.md
2. Add your system description
3. Add your industry-specific requirements
4. Update roles/approval authorities
5. Review with your team
```

### Step 4: Customize the Checklist
```
1. Copy AI-COMPLIANCE-CHECKLIST.md
2. Add items specific to your system
3. Remove items that don't apply
4. Make sure items are verifiable (not vague)
5. Use as your baseline
```

### Step 5: Use It
```
1. Weekly/monthly: Run the checklist
2. Track your score over time
3. Make progress on gaps
4. Show your team you're serious
```

---

**The examples show it's possible. Specific to your industry. Practical to implement. Not overwhelming.**

**Your situation is different. That's fine. Adapt what's here.**