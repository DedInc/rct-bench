# 💻 Web Development Category

Modern web applications, from beautiful interfaces to powerful automation.

## Overview

Web development is one of the most common tasks developers face. This category tests AI models on creating real, production-quality web applications - not toy examples or basic forms. These tasks cover both user-facing interfaces and behind-the-scenes automation.

## Subcategories

### 🎨 Modern Interfaces (15 tasks)

**Focus:** Building complex, beautiful, and functional user interfaces

**Modern Frameworks:**
- **React** - Component-based, hooks, context
- **Vue** - Composition API, reactivity
- **Svelte** - Compile-time framework
- **Solid.js** - Fine-grained reactivity
- **Next.js** - React with SSR/SSG
- **Nuxt.js** - Vue with SSR/SSG

**What Makes a Good UI Task:**
- Real design requirements (not "create a form")
- Multiple interactive components
- State management challenges
- Responsive design needs
- Accessibility considerations
- Performance optimization

**Typical Requirements:**
- Complex layouts (dashboards, admin panels)
- Interactive widgets (calendars, charts, editors)
- Real-time features (live updates, notifications)
- Form validation and submission
- Data visualization
- Animations and transitions
- Dark mode / theming
- Mobile responsiveness

**Key Technologies:**
- **Styling:** Tailwind CSS, CSS Modules, Styled Components, SASS
- **State Management:** Redux, Zustand, Pinia, Context API
- **Data Fetching:** React Query, SWR, Axios
- **Routing:** React Router, Vue Router
- **UI Libraries:** Material-UI, Chakra UI, shadcn/ui, Ant Design

**Real Examples:**
- Project management dashboard
- E-commerce product catalog with filters
- Real-time chat interface
- Data analytics dashboard with charts
- Content management interface
- Social media feed with infinite scroll
- Video player with custom controls

**Path:** `tasks/web/modern-interfaces/`

---

### 🤖 Browser Automation (15 tasks)

**Focus:** Automating browser interactions for testing and scraping

**Primary Tools:**
- **Selenium** - The classic, cross-browser
- **Playwright** - Modern, fast, powerful
- **Puppeteer** - Chrome/Chromium focused

**Types of Tasks:**

**1. Web Scraping:**
- E-commerce price monitoring
- News aggregation
- Data extraction from complex sites
- Handling pagination and infinite scroll
- Dealing with dynamic content
- Bypassing anti-bot measures (ethically)

**2. End-to-End Testing:**
- User flow testing
- Form submission testing
- Multi-page workflows
- Authentication flows
- Error scenario testing
- Cross-browser compatibility

**3. Automation:**
- Form auto-filling
- Bulk operations
- Report generation
- Screenshot/PDF generation
- Social media automation
- Job application automation

**Real Challenges:**
- Waiting for dynamic content
- Handling JavaScript-heavy sites
- Managing cookies and sessions
- Dealing with CAPTCHAs (when appropriate)
- Error recovery
- Rate limiting
- Proxy rotation
- Data parsing and cleaning

**Common Patterns:**
- Page Object Model (POM)
- Implicit vs Explicit waits
- Headless vs Headed mode
- Screenshot on failure
- Retry mechanisms
- Parallel execution

**Technologies:**
- Browser drivers (ChromeDriver, GeckoDriver)
- Selector strategies (CSS, XPath)
- Data storage (JSON, CSV, databases)
- Scheduling (cron, celery, node-cron)
- Notifications (email, webhooks)

**Ethical Considerations:**
- Respect robots.txt
- Reasonable request rates
- No credential theft
- No malicious automation
- Terms of service compliance

**Real Examples:**
- E-commerce price tracker with notifications
- Job board scraper with filters
- Social media post scheduler
- Automated form filling for applications
- Website health monitoring
- Competitor analysis tool
- Data migration from old system

**Path:** `tasks/web/browser-automation/`

---

## What These Tasks Test

✅ **Frontend Proficiency (Modern Interfaces)**
- Component architecture
- State management
- Event handling
- CSS and styling
- Responsive design
- Performance optimization
- Accessibility

✅ **Automation Skills (Browser Automation)**
- Tool selection and usage
- Handling dynamic content
- Robust waiting strategies
- Error handling
- Data extraction
- Code organization

✅ **Real-World Complexity**
- Not trivial "hello world" apps
- Production-ready code
- Edge case handling
- User experience considerations

✅ **Modern Best Practices**
- Current framework versions
- Modern JavaScript/TypeScript
- Clean, maintainable code
- Proper tooling (bundlers, linters)

## Why These Tasks Matter

**Modern Interfaces:**
Every business needs web interfaces. Models that can build real, complex UIs are immediately valuable. We're not testing "can you create a button" - we're testing "can you build a real application."

**Browser Automation:**
Automation saves countless developer hours. Whether it's testing, scraping, or automating workflows, these are real tasks that developers do daily. Models that can handle dynamic web pages and anti-bot measures are genuinely useful.

## Difficulty Levels

**Easy:**
- Simple single-page applications
- Basic scraping of static sites
- Straightforward component composition

**Medium:**
- Multi-component dashboards
- Scraping with pagination
- State management across components
- Handling authentication

**Hard:**
- Complex interactive applications
- Anti-bot bypassing
- Real-time features
- Advanced state management
- Performance optimization

## Task Structure

Each web task directory contains:
- **prompt.md** - Task requirements and specifications
- **assets/** - Design mockups, sample data (when applicable)

**Evaluation:** Human reviewers test the implementations manually (for interfaces: visual inspection, interaction testing; for automation: running scripts, checking output). Evaluation follows the standard criteria with emphasis on UI/UX quality for interfaces and robustness for automation tasks.

## Contributing

When adding web tasks:

**For Modern Interfaces:**
1. Provide clear design requirements (or mockups)
2. Specify target framework
3. Include realistic features
4. Consider responsive design
5. Think about accessibility

**For Browser Automation:**
1. Ensure target sites are appropriate for scraping
2. Respect rate limits and ToS
3. Focus on real use cases
4. Include error handling scenarios
5. Consider ethical implications

See [MINIMAL_PROMPTS_GUIDE.md](../../docs/MINIMAL_PROMPTS_GUIDE.md) for prompt guidelines.