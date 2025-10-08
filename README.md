# RCT-bench: Real Coding Tasks Benchmark

## The Problem with Current AI Benchmarks

Tired of benchmarks testing AI on synthetic crap like "draw an SVG pelican" or "animate a bicycle"? Us too.

**RCT-bench** is a benchmark that actually matters. No more artificial toy problems. No more contrived scenarios. Just **real-world coding tasks** that developers face every day.

## Philosophy

Modern AI coding benchmarks test models on problems that don't reflect reality:
- ❌ Synthetic algorithmic puzzles
- ❌ Trivial "hello world" variations  
- ❌ Academic exercises disconnected from real development
- ❌ Problems designed to be "benchmark-friendly" rather than realistic

**RCT-bench is different:**
- ✅ Real projects with real complexity
- ✅ Multi-file, multi-dependency systems
- ✅ Tasks that require understanding actual frameworks and libraries
- ✅ Problems developers actually need to solve
- ✅ Testing both creation and refactoring/porting abilities

## Benchmark Categories

RCT-bench is organized into four main categories, each testing different aspects of real-world coding ability.

### 🤖 Bots (20 tasks)
Real bot implementations for Telegram and Discord with actual functionality.

**Includes:**
- 10 Telegram bot tasks (aiogram, python-telegram-bot, Telegraf, etc.)
- 10 Discord bot tasks (discord.py, discord.js, JDA, etc.)

**[→ See detailed Bots category documentation](tasks/bots/ABOUT.MD)**

---

### 🔧 Niche Tasks (20 tasks)
Specialized coding that requires domain-specific knowledge.

**Includes:**
- 5 LevelDB operations tasks
- 5 Smart Contracts (Solidity) tasks
- 5 ML Coding (deployment & pipelines) tasks
- 5 Reverse Engineering tasks

**[→ See detailed Niche category documentation](tasks/niche/ABOUT.MD)**

---

### 🌐 Multilingual (30 tasks)
The real test of understanding vs. memorization - converting between languages and libraries.

**Includes:**
- 15 Language Rewrites (Python ↔ JavaScript ↔ Go ↔ Rust, etc.)
- 15 Library Porting (Express → Fastify, Flask → FastAPI, etc.)

**[→ See detailed Multilingual category documentation](tasks/multilingual/ABOUT.MD)**

---

### 💻 Web Development (30 tasks)
Modern web applications from beautiful interfaces to powerful automation.

**Includes:**
- 15 Modern Interfaces (React, Vue, Svelte, complex UIs)
- 15 Browser Automation (Selenium, Playwright, Puppeteer)

**[→ See detailed Web Development category documentation](tasks/web/ABOUT.MD)**

## Task Structure

**Important:** Tasks use **realistic prompts** similar to what a developer might receive in actual work.

```
tasks/
  category/
    subcategory/
      task-XXX-name/
        └── prompt.md              # Task description and requirements
```

Currently, the benchmark focuses on prompt.md files that models will implement. Additional testing and evaluation infrastructure will be added in future versions.

### Prompt Philosophy

**Models should receive realistic prompts** - just like a real development task:
- Brief description of what to build
- Basic requirements (1-2 sentences)
- Framework/library specifications when relevant (real developers specify these)
- Architectural direction when needed (but not over-detailed implementation)
- Strategic guidance without excessive hand-holding

**Example good prompt:**
```
Create a Telegram bot using aiogram 3.x that renders LaTeX expressions to images.
Should handle errors gracefully and support custom preambles.
```

**Example bad prompt (too hand-holding):**
```
Create a Telegram bot using aiogram 3.x that renders LaTeX...
- Use async/await patterns with @router.message() decorators
- Implement rate limiting with Redis using redis-py, store user timestamps
- Clean up temporary files with context managers using the 'with' statement
- Use subprocess.run() to call pdflatex with these exact flags: -interaction=nonstopmode
- Convert PDF to PNG using Pillow's Image.open() and .save() methods
...(etc)
```

The goal is to test whether models can implement solutions given realistic requirements, just like real developers do.

## Evaluation Criteria

Each task should be evaluated by human reviewers across five critical dimensions that reflect real-world development standards:

### 1. Functionality (35 points)
- **Code runs without errors** (10 pts) - The solution executes successfully
- **Core features work** (15 pts) - All main functionality is operational
- **Integration works** (5 pts) - Components work together properly
- **No critical bugs** (5 pts) - Solution is stable and reliable

### 2. Completeness (20 points)
- **All requirements met** (8 pts) - Nothing missing from the specification
- **Features fully implemented** (6 pts) - No half-finished functionality
- **Dependencies included** (3 pts) - All necessary packages specified
- **Configuration provided** (3 pts) - Setup instructions and configs present

### 3. Code Quality (25 points)
- **Readability** (5 pts) - Clean, understandable code
- **Architecture** (8 pts) - Well-organized, logical structure
- **Best practices** (6 pts) - Follows SOLID principles, design patterns
- **Language idioms** (3 pts) - Uses language-specific patterns correctly
- **Maintainability** (3 pts) - Easy to modify and extend

### 4. Edge Case Handling (15 points)
- **Input validation** (4 pts) - Checks for invalid inputs
- **Error handling** (6 pts) - Graceful failure with meaningful messages
- **Edge cases covered** (3 pts) - Handles unusual but valid scenarios
- **Defensive programming** (2 pts) - Anticipates potential issues

### 5. Performance (5 points)
- **Efficient algorithms** (2 pts) - Appropriate complexity
- **Resource management** (2 pts) - Proper use of memory, connections
- **Optimization** (1 pt) - Critical paths are optimized

**Note:** Performance is weighted lower unless critical to the specific task (e.g., real-time systems, high-throughput services). For performance-critical tasks, this category may be weighted higher.

**Total: 100 points per task**

### Evaluation Process

Human evaluators should:
1. Read the task prompt carefully
2. Review the submitted implementation
3. Test the code (run it, try different inputs)
4. Score each dimension based on the criteria above
5. Provide brief justification for scores

### Evaluator Qualifications

**Current:** Evaluators should be experienced developers familiar with the technologies used in each task category.

**Future Enhancement:** To ensure evaluation quality and prevent unqualified assessments, we plan to implement evaluator verification:

**Experience Level Verification:**
- **Junior** (0-2 years) - Can evaluate basic tasks in their known languages/frameworks
- **Middle** (3-5 years) - Can evaluate medium complexity tasks across multiple categories
- **Senior** (5+ years) - Can evaluate all tasks including complex and niche domains

**Technology Competency Matrix:**
- Evaluators declare their proficiency in specific languages, frameworks, and domains
- Task assignments match evaluator competencies
- Prevents evaluation by those unfamiliar with the technology stack

**Examples:**
- A Python expert shouldn't evaluate Rust smart contracts
- A frontend specialist shouldn't score ML deployment tasks
- A junior developer shouldn't assess complex architectural decisions

This verification system will be implemented when the benchmark reaches the community evaluation phase.

See [EVALUATOR_FRAMEWORK.md](docs/EVALUATOR_FRAMEWORK.md) for detailed planning and implementation considerations.

## Example Task: #001 - LaTeX Telegram Bot

**Category:** Bots → Telegram  
**Difficulty:** Medium  
**Location:** `tasks/bots/telegram/task-001-latex-renderer/prompt.md`

**What the model receives:**
```markdown
# Task: LaTeX Telegram Bot

Create a Telegram bot using aiogram 3.x that renders LaTeX mathematical 
expressions to PNG images.

## Requirements

Users should be able to send LaTeX code to the bot and receive a rendered 
image back. The bot should support custom preambles for including additional 
LaTeX packages and handle errors gracefully when the LaTeX code is invalid.

## Deliverables

- Working Telegram bot
- Error handling for invalid LaTeX
- Support for custom preambles
- Clean, production-ready code
```

**What the model must figure out:**
- How to render LaTeX (pdflatex, matplotlib, etc.)
- Error handling implementation
- File cleanup strategy
- Async implementation patterns
- Security considerations (command injection)
- State management approach

This tests real implementation ability with realistic constraints.

## Contributing

We need your help to reach 100+ tasks! See [CONTRIBUTING.md](docs/CONTRIBUTING.md) for guidelines.

### What Makes a Good RCT-bench Task?

✅ **Real-world utility** - Someone would actually build this  
✅ **Non-trivial** - Requires multiple files/concepts  
✅ **Testable** - Clear success criteria  
✅ **Framework knowledge** - Tests actual library usage  
✅ **Current** - Uses modern, maintained dependencies  

❌ **Avoid:**  
- Toy problems
- Academic exercises
- Deprecated technologies
- Purely algorithmic challenges

## Roadmap

### Phase 1: Core Task Collection (Current)
- [x] Initial structure and philosophy
- [x] Documentation and evaluation criteria
- [x] Creating some tasks for example

### Phase 2: Community & Results (Future)
- [ ] Public leaderboard for model comparisons
- [ ] Community contributions and task submissions
- [ ] Evaluator verification system (experience level + technology competency)
- [ ] Evaluation templates and guidelines for reviewers
- [ ] Example evaluations and scoring references

## Why This Matters

Current benchmarks don't predict real-world coding ability. A model might ace HumanEval but fail to:
- Use a real framework correctly
- Handle async/await patterns
- Manage dependencies
- Write production-ready error handling
- Follow language-specific best practices
- Port code between paradigms

**RCT-bench tests what matters: Can the model help with actual development work?**

## License

MIT License - See [LICENSE](LICENSE) for details

## Citation

If you use RCT-bench in research or evaluation:

```bibtex
@misc{rctbench2025,
  title={RCT-bench: Real Coding Tasks Benchmark for AI Models},
  author={Vladislav Zenkevich},
  year={2025},
  url={https://github.com/DedInc/rct-bench}
}
```

---

**Let's build a benchmark that actually matters.** 🚀
