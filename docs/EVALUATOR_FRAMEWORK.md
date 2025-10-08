# Evaluator Competency Framework

**Status:** Planning / Future Implementation

This document outlines the framework for verifying evaluator qualifications to ensure high-quality, competent assessments of AI model implementations.

## Purpose

Prevent unqualified evaluations by ensuring evaluators only assess tasks within their demonstrated competency areas. This maintains benchmark integrity and fairness.

## Experience Levels

### Junior Developer (0-2 years)
**Can Evaluate:**
- ✅ Basic implementations in their primary language(s)
- ✅ Simple bot tasks
- ✅ Straightforward web interfaces
- ✅ Basic CRUD applications

**Should NOT Evaluate:**
- ❌ Complex architectural decisions
- ❌ Performance-critical systems
- ❌ Niche domains (smart contracts, ML, reverse engineering)
- ❌ Cross-language porting tasks

**Evaluation Focus:** Functionality, basic code quality

---

### Middle Developer (3-5 years)
**Can Evaluate:**
- ✅ Medium complexity tasks across multiple categories
- ✅ Framework-specific implementations
- ✅ Multi-component systems
- ✅ Language rewrites (if proficient in both languages)
- ✅ Most bot and web development tasks

**Should NOT Evaluate:**
- ❌ Highly specialized domains without specific expertise
- ❌ Tasks requiring deep performance optimization knowledge
- ❌ Technologies/frameworks they haven't used

**Evaluation Focus:** All criteria, emphasis on architecture and best practices

---

### Senior Developer (5+ years)
**Can Evaluate:**
- ✅ All task categories (if technology proficient)
- ✅ Complex architectural implementations
- ✅ Performance-critical systems
- ✅ Niche domains (if they have domain expertise)
- ✅ Cross-paradigm translations

**Additional Responsibilities:**
- ✅ Can review controversial scoring decisions
- ✅ Can mentor junior evaluators
- ✅ Can contribute to evaluation criteria refinement

**Evaluation Focus:** All criteria with nuanced understanding

---

## Technology Competency Matrix

### Self-Declaration
Evaluators declare their proficiency in:

#### Programming Languages
**Proficiency Levels:** None / Basic / Intermediate / Expert

Examples:
- Python: Expert
- JavaScript: Expert
- Go: Intermediate
- Rust: Basic
- Java: Intermediate

#### Frameworks & Libraries
**Proficiency Levels:** None / Used / Proficient / Expert

Examples:
- React: Expert
- aiogram: Proficient
- FastAPI: Expert
- discord.py: Used
- Selenium: Proficient

#### Domains
**Proficiency Levels:** None / Familiar / Experienced / Expert

Examples:
- Web Development: Expert
- Bot Development: Expert
- Smart Contracts: None
- ML/AI: Familiar
- Reverse Engineering: None
- Browser Automation: Experienced

### Task Matching Rules

**Required Minimum:**
- Primary language: Intermediate+ proficiency
- Framework (if specified): Used+ proficiency
- Domain: Familiar+ proficiency

**Examples:**

✅ **Valid Assignment:**
- Task: Telegram bot with aiogram 3.x (Python)
- Evaluator: Python (Expert), aiogram (Proficient), Bot Dev (Expert)

❌ **Invalid Assignment:**
- Task: Telegram bot with aiogram 3.x (Python)
- Evaluator: Python (Expert), aiogram (None), Bot Dev (None)

❌ **Invalid Assignment:**
- Task: Solidity smart contract
- Evaluator: Solidity (None), Smart Contracts (None)
- Reason: Zero domain knowledge

✅ **Valid with Caveat:**
- Task: Discord bot with discord.js (JavaScript)
- Evaluator: JavaScript (Expert), discord.js (Used), Bot Dev (Familiar)
- Note: Acceptable for basic/medium tasks, senior should review complex ones

---

## Verification Process (Future Implementation)

### Initial Registration
1. Evaluator creates profile
2. Declares experience level
3. Lists technology proficiencies
4. Provides LinkedIn/GitHub/portfolio for verification

### Verification Methods

**Option A: Peer Verification**
- 2-3 senior developers review claims
- Check portfolio/GitHub for evidence
- Approve or request adjustments

**Option B: Sample Task Evaluation**
- Evaluator scores a pre-evaluated reference task
- Scoring compared against expert consensus
- Demonstrates competency and calibration

**Option C: GitHub Activity Analysis**
- Automated scan of public repositories
- Confirms claimed language/framework usage
- Provides evidence for proficiency claims

### Ongoing Calibration
- Regular spot-checks of evaluation quality
- Comparison with other evaluators' scores on same tasks
- Feedback loop for improvement

---

## Anti-Gaming Measures

### Prevent "Works/Doesn't Work" Only Evaluations

**Problem:** Low-effort evaluators just test if code runs without deeper analysis.

**Solution:**
- Require written justification for each score
- Flag evaluations with generic/minimal justifications
- Review pattern: All 100s or all 50s = suspicious
- Cross-check: Multiple evaluators per task, outliers reviewed

### Prevent Over-Rating Own Language/Framework
**Problem:** Python experts might be too lenient on Python code.

**Solution:**
- Mix evaluators (Python + Go experts both review Python task)
- Track evaluator bias patterns
- Normalize scores if systematic bias detected

### Prevent Collusion
**Problem:** Groups of evaluators coordinating scores.

**Solution:**
- Anonymous evaluator assignments
- Stagger evaluation timing
- Statistical analysis for correlation patterns

---

## Task Assignment Algorithm (Conceptual)

```
def can_assign_evaluator(task, evaluator):
    # Check experience level
    if task.difficulty == "Hard" and evaluator.level == "Junior":
        return False
    
    # Check primary language
    if evaluator.proficiency[task.language] < "Intermediate":
        return False
    
    # Check framework (if specified)
    if task.framework and evaluator.proficiency[task.framework] < "Used":
        return False
    
    # Check domain
    if evaluator.proficiency[task.domain] < "Familiar":
        return False
    
    # Check niche domains require higher proficiency
    if task.category == "Niche":
        if evaluator.proficiency[task.domain] < "Experienced":
            return False
    
    return True
```

---

## Evaluation Quality Metrics

Track evaluator performance:
- **Agreement Rate:** % agreement with consensus (when multiple evaluators)
- **Justification Quality:** Length and depth of scoring rationale
- **Response Time:** Balance between thorough and timely
- **Calibration Score:** How close to expert evaluators
- **Feedback Rating:** From benchmark administrators

Poor performers:
- Receive feedback and guidance
- Assigned simpler tasks for recalibration
- May be suspended if quality doesn't improve

---

## Benefits of This System

✅ **Quality Assurance:** Only competent evaluators assess each task
✅ **Fairness:** Models evaluated by qualified reviewers
✅ **Credibility:** Benchmark results trusted by community
✅ **Scalability:** Clear rules enable community participation
✅ **Transparency:** Evaluator qualifications visible for each assessment

---

## Implementation Timeline

**Phase 1 (Current):** Manual selection of trusted evaluators
**Phase 2:** Basic self-declaration system
**Phase 3:** Verification and calibration system
**Phase 4:** Automated task assignment based on competency matrix
**Phase 5:** Quality tracking and continuous improvement

---

## Notes

- System should be transparent but not bureaucratic
- Balance between quality control and evaluator experience
- Community feedback will shape final implementation
- May need adjustment based on participation levels
- Trust but verify approach
