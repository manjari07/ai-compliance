# Template Structure & File Organization

This document explains the directory structure and how to customize each file.

## Directory Structure

```
ai-compliance/
├── README.md                          # Project overview
├── QUICKSTART.md                      # Getting started guide
├── .gitignore                         # Git ignore file
├── policies/
│   └── AI-COMPLIANCE-POLICY.md        # Main policy (customize)
├── checklist/
│   └── AI-COMPLIANCE-CHECKLIST.md     # Tracking tool (customize)
├── code/
│   ├── compliance_checker.py          # Automation template
│   └── requirements.txt               # Python dependencies
├── docs/
│   ├── QUICKSTART.md                  # 5-minute primer
│   ├── CUSTOMIZATION-EXAMPLES.md      # Real examples
│   ├── IMPLEMENTATION.md              # Step-by-step
│   ├── TEMPLATE-STRUCTURE.md          # This file
│   └── FAQ.md                         # Frequently asked questions
└── tracking/                          # Your weekly snapshots (create)
```

## File Customization Guide

### 1. README.md - Project Overview

**What to change:**
```markdown
# BEFORE
# AI Compliance Framework
A comprehensive framework for ensuring AI systems meet compliance.

# AFTER  
# [Your Company Name] AI Compliance Framework
Framework for ensuring [Your AI System] meets compliance.
```

### 2. AI-COMPLIANCE-POLICY.md - Main Policy Document

**This is your governance document. Customize heavily.**

**Section 1: Executive Summary**
```markdown
# BEFORE
"This policy establishes compliance requirements for Artificial Intelligence systems."

# AFTER
"This policy establishes compliance requirements for [Your AI System Name] v[X.Y], used by [Your Department]."
```

### 3. AI-COMPLIANCE-CHECKLIST.md - Compliance Checklist

**This is your tracking tool. Make it specific to YOUR systems.**

**Customize Items:**
```markdown
# BEFORE (Generic)
- [ ] **AC-2.1**: MFA enabled for all system access

# AFTER (Specific)
- [ ] **AC-2.1**: MFA enabled for YourModel admin access
       Evidence: Screenshot of AWS IAM MFA configuration
```

## Next Steps

1. Read QUICKSTART.md
2. Customize README.md
3. Customize AI-COMPLIANCE-POLICY.md
4. Customize AI-COMPLIANCE-CHECKLIST.md
5. Start tracking compliance

---

**This is a framework, not gospel. Use what works. Skip what doesn't.**