# Getting Started With AI Compliance

How to actually use this framework for your AI system.

## Five Things to Know First

1. **This is a template.** You'll need to customize it for your situation.
2. **Start with the manual checklist.** Don't automate before you understand what you're doing.
3. **Pick the parts that matter.** You don't need all of this.
4. **Compliance is ongoing.** Not a box you check once.
5. **Talk to your auditors.** If you have them. If you don't, you probably should.

## The Three Documents You Need

### 1. The Policy
**File:** `policies/FEDRAMP-AI-POLICY.md`

**What it is:** Your rules for how AI systems should work. Write down what you're doing and why.

**What to do:**
- Read it once
- Change things that don't apply to your system
- Highlight things your team needs to do
- Share it with your team

**Time required:** 30 minutes to read, 1-2 hours to customize

### 2. The Checklist
**File:** `checklist/FEDRAMP-AI-CHECKLIST.md`

**What it is:** Weekly/monthly reality check. "Are we actually doing what we said we'd do?"

**What to do:**
- Print it or open in an editor
- Go through each item
- Mark yes/no based on your system
- Count the yes's and no's
- Figure out your score

**Time required:** 1-2 hours per use

### 3. Your Tracking Folder
**File:** `tracking/your-dates-here.md`

**What it is:** Copy the checklist every week/month and fill it out. Watch your compliance grow (or identify where you're stuck).

**What to do:**
```bash
# Week 1
cp checklist/FEDRAMP-AI-CHECKLIST.md tracking/2024-07-week1.md
# Fill it out, count score

# Week 2
cp checklist/FEDRAMP-AI-CHECKLIST.md tracking/2024-07-week2.md
# Fill it out, count score again
# Notice: did it go up? Stay the same? Go down?
```

**Time required:** 1-2 hours per week/month

## For Different Situations

### You Have 30 Minutes Right Now

1. Read the policy (skim it, 15 min)
2. Look at one example in `docs/CUSTOMIZATION-EXAMPLES.md` (10 min)
3. Read this section again (5 min)

Done. Now you know what you're looking at.

### You're Building One AI System

1. Read the policy (30 min)
2. Read examples for your industry (15 min)
3. Customize the policy for your system (1 hour)
4. Copy the checklist and try it (1 hour)
5. Make a list of what's missing
6. Fix the big stuff first
7. Check the list again in a week

### You're Running Multiple AI Systems

1. Read everything (a few hours)
2. Create a policy for each system (or one policy with multiple sections)
3. Create a checklist for each system
4. Assign someone to check them weekly
5. Collect results in a spreadsheet
6. Report to leadership monthly

### You Work in a Regulated Industry

1. Read `docs/CUSTOMIZATION-EXAMPLES.md` for your industry
2. Read the policy
3. Talk to your compliance team/auditors
4. Customize for your situation
5. Follow the same checklist process
6. Keep good records for audits

### You Don't Have a Compliance Team

1. Do this yourself, or
2. Assign to one smart person on your team, or
3. Use this to convince leadership you need a compliance person

The good news: one person can do this. Might take them 4-6 hours per week, but it's doable.

## How to Customize the Policy

The policy is pretty generic. Make it specific to your situation.

### Example 1: Credit Scoring AI

**Find this:**
```markdown
This policy applies to:
- AI/Machine Learning systems processing federal data
- Models trained on sensitive or classified information
```

**Change to:**
```markdown
This policy applies to:
- CreditScore v2.0 - Our lending decision model
- Customer financial records (income, debt, payment history)
- Used by lenders to approve/deny loans
```

### Example 2: Medical Imaging AI

**Find this:**
```markdown
This policy applies to:
- AI/Machine Learning systems processing federal data
- Models trained on sensitive or classified information
```

**Change to:**
```markdown
This policy applies to:
- DiagnosticAI v1.5 - Cancer detection in medical images
- De-identified patient imaging data (X-rays, CT scans)
- Used by radiologists in hospital networks
```

### What to Add

After the generic part, add sections for:

**Your industry rules:**
- Healthcare? Add HIPAA requirements
- Finance? Add Fair Lending requirements
- Government? Add specific agency requirements

**Your specific risks:**
- If bias is a concern, add bias testing requirements
- If safety matters, add safety testing requirements
- If privacy matters, add data protection requirements

**Who's responsible:**
- Model owner: who?
- Data steward: who?
- Security lead: who?
- Compliance officer: who?

## How to Use the Checklist

Simple.

1. Print it or open it in an editor
2. Go through each item
3. If you're doing it: check the box
4. If you're not doing it: leave it blank
5. Count the checkmarks
6. Divide by total items
7. That's your compliance percentage

**Example:**
- Total items: 100
- Checkmarks: 63
- Compliance: 63%

**What the percentage means:**
- 90%+: You're in good shape. Keep going.
- 70-89%: You have gaps. Make a plan.
- <70%: You have serious gaps. Start with the critical ones.

## What to Do When You Find Gaps

You will find gaps. Everyone does.

1. **Don't panic.** You're catching this now, not when an auditor shows up.
2. **Prioritize.** What's most important for your situation?
3. **Make a plan.** What needs to be fixed? By who? By when?
4. **Fix it.** Start with the highest priority.
5. **Check again.** Re-run the checklist in a week. Did your score go up?

## Common Gaps and Quick Fixes

### "We don't have logging"
- **Quick fix:** Enable cloud logging (AWS CloudTrail, Azure Audit Logs, etc.). Takes 1 hour.
- **Real fix:** Set up centralized logging and monitoring. Takes 1-2 weeks.

### "We don't have MFA"
- **Quick fix:** Enable MFA in your cloud provider. Takes 1 hour.
- **Real fix:** Make it mandatory for everyone. Takes 1-2 weeks.

### "We don't test for bias"
- **Quick fix:** Run one fairness test on your model. Takes 1-2 hours.
- **Real fix:** Add fairness testing to your development process. Takes 1-2 weeks.

### "We don't have an incident response plan"
- **Quick fix:** Write down what you'd do if something broke. Takes 2 hours.
- **Real fix:** Test the plan with a simulation. Takes 1 day.

## Examples

Look at `docs/CUSTOMIZATION-EXAMPLES.md` for real cases:

- **Healthcare:** Cancer detection AI
- **Finance:** Credit scoring AI
- **Autonomous:** Self-driving cars
- **Research:** Scientific discovery AI

Each one shows:
- What compliance means for that domain
- How to customize the policy
- How to customize the checklist
- Actual code examples

## The Optional Automation Part

See `code/compliance_checker.py`.

This is if you want to automate compliance checking. Don't start here. Understand the manual process first. Then, if you want, automate it.

**When to automate:**
- You have 3+ systems to track
- You want daily automated checks
- You have engineering resources
- You understand what you're checking

**When not to automate:**
- You have fewer than 3 systems
- You just started doing this
- You don't have eng time
- You don't understand it yet

## Next Week

Week 1 is reading and understanding.

Week 2:
1. Customize the policy for your system
2. Run the checklist once
3. See what your baseline is
4. Pick the top 3 gaps
5. Make a plan to fix them

## Month 1

1. Fix the top 3 gaps
2. Run the checklist again
3. Did you improve? Good.
4. Pick the next 3 gaps
5. Keep going

## After That

Check the list weekly or monthly.

Watch your score go up. That's how you know it's working.

---

**That's it. Not complicated. Just consistent.**

**Questions?** See `docs/FAQ.md`.