# 🤖 Bots Category

Real bot implementations with actual functionality that developers build every day.

## Overview

This category focuses on testing AI models' ability to create functional bots for popular messaging platforms. These are real-world applications that require understanding of:
- Platform-specific APIs and frameworks
- Async/event-driven programming patterns
- State management
- User interaction flows
- Error handling and edge cases

## Subcategories

### 🔵 Telegram Bots (10 tasks)

**Focus:** Building bots for Telegram using various frameworks

**Common Frameworks:**
- aiogram 3.x (Python)
- python-telegram-bot (Python)
- Telegraf (Node.js)
- telebot (Python)
- And others

**Typical Features:**
- Message handlers and commands
- Inline keyboards and callback handling
- File processing (images, documents, etc.)
- State machines for complex interactions
- Database integration
- Payment processing
- Custom keyboards
- Webhook vs polling

**Real Use Cases:**
- LaTeX rendering bots
- Database interface bots
- File converter bots
- Payment processing bots
- Notification bots
- Admin/moderation bots
- Interactive quiz/game bots

**Path:** `tasks/bots/telegram/`

---

### 🟣 Discord Bots (10 tasks)

**Focus:** Building bots for Discord with rich functionality

**Common Libraries:**
- discord.py (Python)
- discord.js (Node.js)
- JDA (Java Discord API)
- discord.py-interactions
- hikari (Python)

**Typical Features:**
- Slash commands and context menus
- Message embeds and rich formatting
- Role and permission management
- Voice channel handling
- Event listeners and handlers
- Database integration
- Moderation tools
- Custom emojis and reactions

**Real Use Cases:**
- Moderation and admin tools
- Music bots with queue management
- Game integration bots
- Custom command systems
- Leveling/XP systems
- Welcome/goodbye messages
- Logging and audit bots
- Poll and survey bots

**Path:** `tasks/bots/discord/`

---

## What These Tasks Test

✅ **Framework Proficiency**
- Proper use of platform-specific libraries
- Understanding of async patterns
- Event-driven architecture

✅ **Real-World Integration**
- API interaction
- External service integration
- Database operations
- File handling

✅ **User Experience**
- Clear interaction flows
- Error messages and feedback
- State management
- Input validation

✅ **Production Readiness**
- Error handling
- Logging
- Configuration management
- Resource cleanup

## Task Structure

Each bot task directory contains:
- **prompt.md** - The task description with requirements that models will implement

**Evaluation:** Tasks are evaluated by human reviewers using the criteria defined in the main README.md (Functionality, Completeness, Code Quality, Edge Case Handling, Performance).

## Contributing

When adding new bot tasks:
1. Choose a realistic use case
2. Specify the platform and framework
3. Focus on practical functionality
4. Ensure testability
5. Follow the realistic prompt philosophy

See [MINIMAL_PROMPTS_GUIDE.md](../../docs/MINIMAL_PROMPTS_GUIDE.md) for detailed guidelines.