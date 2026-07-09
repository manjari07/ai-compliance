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

**In the checklist:**
```markdown
# New Items Added

- [ ] Training data de-identified and validated
- [ ] Re-identification risk < 0.04 (documented)
- [ ] Model sensitivity >= 95%
- [ ] Model specificity >= 90%
- [ ] Fallback process when confidence low
- [ ] Monthly review of missed cases
- [ ] Annual clinical validation study
```

**What they automated:**
```python
# Check fairness across demographics
def check_fairness(self):
    # Make sure sensitivity/specificity similar across:
    # - Age groups
    # - Gender
    # - Race (using de-identified indicators)
    # Return True if variance < 5%
    pass

# Check for HIPAA violations
def check_hipaa_compliance(self):
    # Scan model outputs for patient identifiers
    # Return False if any PII found
    pass
```

**How they use it:**
- Weekly: Run checklist on new model version
- Monthly: Clinical team reviews model performance
- Quarterly: Full fairness and safety assessment
- Yearly: Independent clinical validation

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

- Test for disparate impact across protected classes:
  - Age, gender, race, national origin, marital status
- Model must pass 4/5ths rule:
  - If approval rate for Group A = 80%
  - Then approval rate for Group B must be >= 64%
- Every loan denial must include reason
- Customers can request explanation

# Added Section: PCI-DSS Compliance

- No real credit card numbers in training data
- Model outputs encrypted at rest and in transit
- Access logs reviewed monthly
```

**In the checklist:**
```markdown
# New Items

- [ ] Disparate impact test shows 4/5ths compliance
- [ ] Denial explanations auto-generated
- [ ] Customers can request explanation (process exists)
- [ ] Monthly disparate impact report generated
- [ ] No real credit card data in training set
- [ ] Model outputs encrypted
```

**What they automated:**
```python
# Run monthly to check for violations
def check_4_5ths_rule(self):
    # Get approval rates by demographic group
    # Find group with highest approval rate
    # Check if all others are >= 80% of that rate
    # Return False if any group is lower
    pass
```

**How they use it:**
- Daily: Model runs on new loan applications
- Weekly: Check model performance, alert if degrading
- Monthly: Run fairness test, generate report for regulators
- Quarterly: Full compliance audit

### What Worked
- Involved legal/compliance early
- Built in fairness testing from day one
- Tracked and fixed bias issues quickly
- Transparent with regulators

### What Was Hard
- Getting historical data that wasn't biased
- Explaining fairness to business stakeholders
- Dealing with edge cases (what if someone has no credit history?)
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

**In the policy:**
```markdown
# Added Section: Safety-Critical Requirements

- All decisions must be deterministic (same input = same output)
- Dual redundancy for safety-critical functions
- Fallback to human driver if confidence < 99.5%
- Hardware watchdog timer (timeout if model doesn't respond)
- Graceful degradation (limp-home mode when sensors fail)

# Added Section: Real-Time Requirements

- Decision latency < 100ms
- Process 60+ frames per second
- CPU usage < 80% sustained
- Memory < 500MB
```

**In the checklist:**
```markdown
# New Items

- [ ] Model behavior reproducible (deterministic)
- [ ] Dual redundancy implemented for critical functions
- [ ] Fallback to human driver works
- [ ] Hardware watchdog configured and tested
- [ ] Latency < 100ms in all conditions
- [ ] Throughput >= 60 fps
- [ ] Tested in adverse weather (rain, snow, fog)
- [ ] Tested in night conditions
```

**What they automated:**
```python
# Real-time monitoring
def check_performance_metrics(self):
    # Measure latency, throughput, memory, CPU
    # Alert if any metric breaches threshold
    # Return False if any critical threshold hit
    pass

# Check sensor redundancy
def check_sensor_fusion(self):
    # Verify multi-modal data fusion working
    # Check cross-validation between sensors
    # Return False if sensor disagreement too high
    pass
```

**How they use it:**
- Continuous: Real-time monitoring during testing
- Daily: Check overnight test logs
- Weekly: Safety metrics review
- Monthly: Full safety assessment
- Quarterly: Third-party safety audit

### What Worked
- Invested heavily in simulation before real-world testing
- Built in redundancy from the start
- Conservative fallback thresholds
- Regular third-party review

### What Was Hard
- Edge cases (what about the unexpected situation?)
- Regulatory approval (very conservative)
- Cost (safety is expensive)
- Convincing people it's safe (public perception vs. actual safety)

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

**In the policy:**
```markdown
# Added Section: Research Ethics

- IRB approval obtained before use
- Data sources clearly documented
- Attribution to original researchers
- License compliance verified (CC-BY, etc.)

# Added Section: Reproducibility

- Code published on GitHub (MIT license)
- Training data publicly available
- Model checkpoints versioned
- Results reproducible within ±5% variance
- Random seeds fixed
- Hyperparameters documented

# Added Section: Open Science

- Model card published before production
- Uncertainty estimates provided
- Known limitations disclosed
- Potential harms discussed
```

**In the checklist:**
```markdown
# New Items

- [ ] IRB approval obtained
- [ ] Training data sources documented
- [ ] Code published under appropriate license
- [ ] Results reproducible by others
- [ ] Model card created and published
- [ ] Uncertainty estimates calculated
- [ ] Known limitations documented
```

**What they automated:**
```python
# Check reproducibility
def check_reproducibility(self):
    # Run model twice with same seed
    # Compare outputs
    # Return False if variance > ±5%
    pass

# Check code availability
def check_code_availability(self):
    # Verify GitHub repo exists and is public
    # Check for README and documentation
    # Return True if all present
    pass
```

**How they use it:**
- Before publication: Check all reproducibility items
- Quarterly: Update model card
- Yearly: Full reassessment

### What Worked
- Publish early, often
- Community feedback caught issues
- Open source made collaboration easier
- Transparent about limitations

### What Was Hard
- IP concerns from institution
- Data licensing complexity
- Computational reproducibility (floating point variance)
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