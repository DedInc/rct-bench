# Guide to Writing Minimal Prompts

## Philosophy

**Realistic prompts test real coding ability, not excessive hand-holding.**

Real developers receive clear requirements with specified technologies and strategic direction, then figure out implementation details. RCT-bench should do the same for AI models - provide context and constraints like a real task, but avoid step-by-step implementation instructions.

## What Makes a Good Realistic Prompt?

### ✅ DO Include:
- Brief task description (1-2 sentences)
- Core requirements (what it should do)
- Specific frameworks/libraries when relevant (real devs specify these)
- Architectural direction when it matters for the task
- Expected deliverables
- Critical constraints

### ❌ DON'T Include:
- Step-by-step implementation instructions
- Exact function/method names to use
- Code snippets or pseudo-code
- Overly detailed architectural blueprints
- Every single edge case spelled out
- Specific algorithms to implement (unless that's the point)
- Line-by-line guidance

## Examples

### ❌ BAD: Too Hand-Holding
```markdown
# Task: Telegram Bot

Create a Telegram bot using aiogram 3.x that processes images.

Requirements:
- Use async/await patterns with @router.message() decorators for each handler
- Create a handlers/ directory with separate files: start_handler.py, image_handler.py
- Use Pillow's ImageFilter.BLUR and ImageFilter.SHARPEN for filters
- Store temporary files in /tmp using tempfile.NamedTemporaryFile()
- Implement rate limiting with Redis using redis-py, check timestamps with SETEX
- Use logging.getLogger(__name__) with logging.basicConfig() at INFO level
- Wrap all operations in try-except blocks catching Exception
- Return processed images using bot.send_photo() with PNG format
```

**Problem:** This is basically a tutorial with implementation instructions, not a test of coding ability.

---

### ✅ GOOD: Realistic and Clear
```markdown
# Task: Image Processing Bot

Create a Telegram bot using aiogram 3.x that applies filters to images sent by users.

Users should be able to:
- Send an image and select a filter (grayscale, blur, sharpen)
- Receive the processed image back
- Get error messages if something goes wrong

Deliverables:
- Working bot with proper async handling
- Clean code architecture
- Error handling for invalid inputs
```

**Why it's good:** 
- Framework is specified (like a real task would)
- Model must pick image library
- Model must design the specific architecture
- Model must implement error handling strategy
- Model must figure out filter implementation
- Model must handle edge cases

---

### ❌ BAD: Vague and Unclear
```markdown
# Task: Bot

Make a bot that does stuff with data.
```

**Problem:** Too vague, no clear success criteria, no technology specification.

---

### ✅ GOOD: Specific Goal, Realistic Details
```markdown
# Task: Weather Bot

Create a Discord bot using discord.py that provides weather forecasts.

Commands:
- /weather [city] - Current weather
- /forecast [city] - 5-day forecast

Should handle invalid city names gracefully.

Deliverables:
- Working Discord bot with slash commands
- Error handling for API failures and invalid inputs
- Clean, maintainable code
```

**Why it's good:**
- Clear functionality and technology stack
- Testable requirements
- Model chooses weather API
- Model designs specific error handling approach
- Model implements command structure
- Model handles edge cases

---

## Template

Use this template for new prompts:

```markdown
# Task: [Name]

[1-2 sentence description of what to build]

## Requirements

[3-5 bullet points of what it should do]

## Deliverables

- Working [type of project]
- Error handling
- [Any specific critical features]
- Clean, production-ready code
```

## Real Examples from RCT-bench

### Example 1: LaTeX Bot
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

**What models must figure out:**
- How to render LaTeX (pdflatex? matplotlib? something else?)
- How to handle temporary files
- Security concerns (command injection)
- Specific async implementation patterns
- Rate limiting approach
- File cleanup strategy
- Error handling implementation

---

### Example 2: Price Tracker
```markdown
# Task: E-commerce Price Tracker

Build a web scraper that monitors product prices and sends notifications.

## Requirements

Track prices for user-specified products from e-commerce sites. When a 
price drops below a threshold, send an email notification. Should handle 
multiple users and multiple products per user.

## Deliverables

- Working scraper with scheduling
- Email notifications
- User/product management
- Error handling for unreachable sites
```

**What models must figure out:**
- Scraping library (Selenium? Playwright? BeautifulSoup?)
- Storage (database? which one?)
- Scheduling (cron? celery? apscheduler?)
- Email sending
- Anti-bot handling
- Data persistence

---

## Common Mistakes

### Mistake 1: Providing Step-by-Step Implementation
```markdown
❌ "Use Express.js with the following structure:
    1. Create app.js with express()
    2. Define routes in routes/api.js using router.get()
    3. Use middleware with app.use(express.json())
    4. Start server with app.listen(3000)"
✅ "Create a REST API using Express.js with proper routing and middleware"
```

### Mistake 2: Specifying Exact Implementation Details
```markdown
❌ "Create a handlers/ directory with these files: userHandler.js, 
    authHandler.js. Each should export a function that takes (req, res, next).
    Use res.status(200).json() for responses."
✅ "Create a well-organized REST API with clean separation of concerns"
```

### Mistake 3: Listing Every Single Edge Case
```markdown
❌ "Handle: empty input, input >10000 chars, special characters (@#$%), 
    null values, undefined values, network timeout after 5s, rate limit 
    exceeded (429), database connection lost, malformed JSON"
✅ "Handle errors gracefully including validation and network failures"
```

### Mistake 4: Giving Exact Method/Function Names
```markdown
❌ "Use async/await with try-catch blocks. Call await fetch() for HTTP 
    requests and use .json() to parse responses."
✅ "Implement async operations with proper error handling"
```

### Mistake 5: Providing Algorithm Pseudocode
```markdown
❌ "To implement caching: check if key exists in cache -> if yes return 
    cached value -> if no, fetch from DB -> store in cache with TTL -> 
    return value"
✅ "Implement caching to improve performance"
```

## Testing Your Prompt

Before finalizing a prompt, ask:

1. **Would a real developer receive this level of detail?**
   - If yes → Your prompt is realistic
   - If no → Adjust to match real-world communication

2. **Does it specify technologies like a real task?**
   - Real developers get told which frameworks/libraries to use
   - This is important context, not hand-holding

3. **Does it test implementation ability?**
   - Models should implement solutions, not follow tutorials
   - Avoid step-by-step instructions

4. **Can success be objectively measured?**
   - You need clear requirements for testing

5. **Are there multiple valid implementation approaches?**
   - If yes → Good! Tests decision-making
   - If only one way → You might be too prescriptive

## Prompt Difficulty Levels

### Easy Prompts
- Single main feature
- Well-known domain
- Obvious library choices
- Limited edge cases

Example: "Create a command-line calculator"

### Medium Prompts
- Multiple features
- Some complexity
- Multiple reasonable approaches
- Various edge cases

Example: "Create a Telegram bot for LaTeX rendering"

### Hard Prompts
- Complex features
- Less common domain
- Many valid approaches
- Significant edge cases
- Integration challenges

Example: "Create a Discord music bot with queue management"

### Expert Prompts
- Very complex systems
- Specialized knowledge required
- Security critical
- Performance critical
- Multiple integrations

Example: "Create a smart contract for an NFT marketplace"

---

## Summary

**The goal is to test coding ability with realistic constraints, not hand-hold through implementation.**

Good prompts are:
- Clear and concise
- Specific about goals and technology stack
- Provide architectural direction without implementation steps
- Testable with clear success criteria
- Realistic (like what developers actually receive)

Models that excel at RCT-bench should be able to:
- Implement solutions with specified technologies
- Design good architecture within given constraints
- Handle edge cases without explicit enumeration
- Write clean, production-quality code
- Make good engineering decisions
- Choose appropriate supporting libraries and patterns

---

**Remember:** Specify the "what" and "with what tools", but not the "exactly how". 
Implementation skill is what we're testing!
