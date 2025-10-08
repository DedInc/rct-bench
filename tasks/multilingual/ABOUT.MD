# 🌐 Multilingual Category

The real test of understanding vs. memorization: converting code between languages and libraries.

## Overview

This category tests whether AI models truly understand code logic and patterns, or just memorize syntax. Converting between languages and libraries requires:
- Deep understanding of both source and target paradigms
- Ability to maintain functionality across different environments
- Knowledge of idiomatic patterns in each language
- Understanding of ecosystem differences

## Subcategories

### 🔄 Language Rewrites (15 tasks)

**Focus:** Translating complete applications between programming languages

**Common Language Pairs:**
- Python ↔ JavaScript
- Python ↔ Go
- JavaScript ↔ TypeScript
- Go ↔ Rust
- Java ↔ Kotlin
- Python ↔ Rust
- Ruby ↔ Python
- C++ ↔ Rust

**High-Level to Low-Level:**
- Python → C++
- JavaScript → Rust
- Python → Go

**Low-Level to High-Level:**
- C → Python
- C++ → JavaScript
- Rust → Python

**What Must Be Preserved:**
- ✅ Core functionality
- ✅ Algorithm logic
- ✅ Error handling approach
- ✅ API/interface contracts

**What Should Change:**
- ✅ Idiomatic patterns (use language-specific idioms)
- ✅ Data structures (use appropriate types)
- ✅ Error handling mechanisms (exceptions vs Result types)
- ✅ Concurrency patterns (threads vs async/await vs goroutines)
- ✅ Package/module structure

**Example Scenarios:**
- Async Python bot → Event-driven Node.js bot
- Synchronous Python script → Concurrent Go application
- JavaScript REST API → Type-safe TypeScript with proper types
- Python data processor → Memory-efficient Rust tool

**Path:** `tasks/multilingual/language-rewrites/`

---

### 📦 Library Porting (15 tasks)

**Focus:** Migrating applications between different libraries/frameworks within the same or different languages

**Web Frameworks:**
- Express.js → Fastify (Node.js)
- Flask → FastAPI (Python)
- Django → FastAPI (Python)
- Express → Koa (Node.js)
- Ruby on Rails → Sinatra

**HTTP Clients:**
- requests → httpx (Python)
- axios → fetch API (JavaScript)
- request → got (Node.js)

**Testing Frameworks:**
- unittest → pytest (Python)
- Mocha → Jest (JavaScript)
- JUnit → TestNG (Java)

**Frontend Frameworks:**
- jQuery → Vanilla JS
- jQuery → React
- React → Vue
- Vue → Svelte
- AngularJS → Angular

**Database Libraries:**
- SQLAlchemy → asyncpg (Python)
- Mongoose → Prisma (Node.js)
- Sequelize → TypeORM (Node.js)

**Bot Frameworks:**
- python-telegram-bot → aiogram (Python)
- discord.js v13 → discord.js v14
- discord.py → hikari (Python)

**Key Challenges:**
- Different API styles (callback vs Promise vs async/await)
- Feature parity differences
- Performance characteristics
- Configuration approaches
- Middleware/plugin systems
- Type systems (if applicable)

**Path:** `tasks/multilingual/library-porting/`

---

## What These Tasks Test

✅ **True Understanding vs Memorization**
- Can the model understand the logic, not just syntax?
- Does it know when to use language-specific patterns?
- Can it adapt algorithms to different paradigms?

✅ **Language Proficiency**
- Idiomatic code in target language
- Proper use of standard library
- Understanding of language features
- Best practices and conventions

✅ **Ecosystem Knowledge**
- Package management differences
- Build system variations
- Testing approaches
- Dependency handling

✅ **Architectural Adaptation**
- Choosing appropriate patterns for target environment
- Handling concurrency differences
- Memory management considerations
- Error handling paradigms

## Why This Category Matters

Many benchmarks only test writing new code from scratch. But in the real world, developers often need to:
- Migrate legacy systems to modern languages
- Port applications to more suitable technologies
- Modernize outdated framework usage
- Translate proof-of-concepts to production languages

A model that can only write Python but can't translate it to Go when needed is limited in practical value.

## Difficulty Considerations

**Easier Translations:**
- Similar paradigms (Python → JavaScript)
- Higher abstraction level maintained
- Same async model

**Harder Translations:**
- Paradigm shifts (Python → Rust with ownership)
- High-level → Low-level (Python → C++)
- Different concurrency models (callbacks → async/await → goroutines)
- Major version migrations with breaking changes

## Task Structure

Each multilingual task directory contains:
- **prompt.md** - Task description with source code/project and conversion requirements
- **source/** - Original implementation to convert (when applicable)

**Evaluation:** Human reviewers evaluate both functional equivalence to the source and quality of the target language implementation. Special attention is paid to idiomatic code and appropriate use of target language features.

## Contributing

When adding multilingual tasks:
1. Choose meaningful, non-trivial applications (not toy examples)
2. Ensure source code is well-written and idiomatic
3. Provide clear requirements for target language
4. Consider what should be preserved vs adapted
5. Include tests that verify functional equivalence
6. Document any deliberate architectural changes

See [MINIMAL_PROMPTS_GUIDE.md](../../docs/MINIMAL_PROMPTS_GUIDE.md) for prompt guidelines.