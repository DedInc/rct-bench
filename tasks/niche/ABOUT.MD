# 🔧 Niche Tasks Category

Specialized coding challenges that require domain-specific knowledge and expertise.

## Overview

This category tests AI models on specialized areas of software development that require deeper domain knowledge. These aren't your typical web app tasks - they're the kind of work that requires understanding of specific technologies, protocols, or domains.

## Subcategories

### 🗄️ LevelDB Operations (5 tasks)

**Focus:** Working with LevelDB, a fast key-value storage library

**What is LevelDB:**
- High-performance key-value database
- Used in Chrome, Bitcoin, and many other applications
- Embedded database (no separate server process)
- Sorted storage by keys

**Typical Tasks:**
- Reading and writing LevelDB databases
- Data migration between databases
- Backup and restore tools
- Performance optimization
- Integration with applications
- Batch operations
- Iterator patterns

**Common Libraries:**
- plyvel (Python)
- leveldown/levelup (Node.js)
- goleveldb (Go)
- leveldb (C++)

**Path:** `tasks/niche/leveldb/`

---

### 📜 Smart Contracts (5 tasks)

**Focus:** Blockchain smart contract development

**Primary Focus: Solidity (Ethereum)**

**Typical Tasks:**
- Token contracts (ERC-20, ERC-721, ERC-1155)
- DeFi protocols (swaps, lending, staking)
- DAO implementations
- NFT marketplaces
- Testing and deployment scripts
- Gas optimization
- Security auditing

**Key Concepts:**
- Smart contract security
- Gas efficiency
- Upgradeability patterns
- Event logging
- Access control
- Reentrancy protection

**Tools & Frameworks:**
- Hardhat
- Truffle
- Foundry
- Web3.py / Web3.js
- Ethers.js

**Path:** `tasks/niche/smart-contracts/`

---

### 🧠 ML Coding (5 tasks)

**Focus:** Machine learning implementation and deployment

**Not Just Model Training:**
- Training pipelines with proper data handling
- Model deployment and serving
- API endpoints for inference
- Batch prediction systems
- Model monitoring and logging
- Data preprocessing pipelines
- Custom layers/architectures

**Real-World Scenarios:**
- FastAPI/Flask servers for model inference
- Real-time prediction APIs
- Batch processing pipelines
- Model versioning and A/B testing
- Data augmentation pipelines
- Custom training loops
- Model optimization (quantization, pruning)

**Common Frameworks:**
- PyTorch / TensorFlow
- FastAPI / Flask
- Scikit-learn
- Hugging Face Transformers
- ONNX Runtime
- MLflow

**Path:** `tasks/niche/ml-coding/`

---

### 🔍 Reverse Engineering (5 tasks)

**Focus:** Analysis and understanding of existing systems

**Types of Tasks:**
- Binary analysis and decompilation
- Protocol reverse engineering
- File format analysis
- API reverse engineering
- Malware analysis (benign samples only)
- Firmware extraction and modification
- Network protocol analysis

**Tools & Techniques:**
- Ghidra / IDA Pro
- Binary Ninja
- Wireshark for protocol analysis
- Python for automation
- Frida for dynamic analysis
- Radare2

**Ethical Considerations:**
- All tasks use legal, benign samples
- Focus on learning and security research
- No malicious use cases
- Educational purpose only

**Path:** `tasks/niche/reverse-engineering/`

---

## What These Tasks Test

✅ **Domain Expertise**
- Understanding of specialized technologies
- Ability to work with niche tools and libraries
- Domain-specific best practices

✅ **Problem-Solving**
- Handling complex, specialized requirements
- Debugging in unfamiliar domains
- Research and learning ability

✅ **Production Quality**
- Not just proof-of-concepts
- Real-world robustness
- Performance considerations
- Security awareness

## Why Niche Tasks Matter

Models that excel at mainstream web development might struggle with:
- Less common libraries and frameworks
- Domain-specific terminology
- Specialized best practices
- Performance-critical code
- Security-sensitive implementations

These tasks reveal whether a model has genuine broad capabilities or just memorized common patterns.

## Task Structure

Each niche task directory contains:
- **prompt.md** - Task description with domain context and requirements

**Evaluation:** Tasks are evaluated by human reviewers with domain expertise using the criteria defined in the main README.md. Domain-specific considerations (e.g., smart contract security, ML model architecture) are factored into the scoring.

## Contributing

When adding niche tasks:
1. Ensure the domain is genuinely specialized
2. Provide necessary context (but not solutions)
3. Focus on practical applications
4. Include domain-specific success criteria
5. Consider security and ethical implications

See [MINIMAL_PROMPTS_GUIDE.md](../../docs/MINIMAL_PROMPTS_GUIDE.md) for prompt guidelines.