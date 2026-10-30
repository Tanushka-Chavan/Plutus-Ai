# AI Workflow Orchestrator

An autonomous AI project manager that coordinates multiple specialized AI agents on the Masumi Network with Cardano blockchain integration for transparency and automated micropayments.

## 🌟 Overview

The AI Workflow Orchestrator solves the problem of isolated AI agents by acting as a "brain" that:

- **Smart Task Decomposition**: Breaks high-level business goals into actionable subtasks
- **Agent Discovery & Negotiation**: Finds and selects optimal agents based on capabilities, reputation, and pricing
- **Autonomous Workflow Execution**: Coordinates task execution with real-time monitoring
- **Reputation-Backed Selection**: Chooses agents based on verified on-chain reputation
- **Secure On-Chain Logging**: Records all workflow events on Cardano blockchain
- **Automated Micropayments**: Handles ADA payments to agents upon task completion
- **Quality Assurance**: Validates outputs and ensures high-quality deliverables

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│           AI Workflow Orchestrator (MCP Server)         │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐ │
│  │    Task      │  │    Agent     │  │   Workflow   │ │
│  │ Decomposer   │  │   Registry   │  │   Executor   │ │
│  └──────────────┘  └──────────────┘  └──────────────┘ │
│                                                         │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐ │
│  │  Reputation  │  │    Output    │  │   Cardano    │ │
│  │   System     │  │  Validator   │  │ Integration  │ │
│  └──────────────┘  └──────────────┘  └──────────────┘ │
│                                                         │
└─────────────────────────────────────────────────────────┘
                          │
                          ▼
        ┌─────────────────────────────────┐
        │      Cardano Blockchain         │
        │  (On-Chain Logging & Payments)  │
        └─────────────────────────────────┘
                          │
                          ▼
        ┌─────────────────────────────────┐
        │    Specialized AI Agents        │
        │  ┌────────┐  ┌────────┐         │
        │  │Content │  │  Data  │  ┌────┐ │
        │  │Creator │  │Analyst │  │... │ │
        │  └────────┘  └────────┘  └────┘ │
        └─────────────────────────────────┘
```

## 🚀 Key Features

### 1. Smart Task Decomposition
Automatically breaks down complex goals into manageable subtasks:
- Content creation workflows
- Data analysis pipelines
- Software development projects
- Research initiatives
- Marketing campaigns

### 2. Intelligent Agent Selection
Finds optimal agents using:
- Capability matching
- Reputation scoring (on-chain verified)
- Cost optimization
- Availability checking

### 3. Autonomous Execution
- Parallel task execution where possible
- Dependency management
- Progress monitoring
- Automatic retry with alternative agents

### 4. Quality Assurance
- Multi-criteria validation
- Configurable quality thresholds
- Feedback loop for continuous improvement

### 5. Blockchain Integration
- On-chain event logging for transparency
- Automated ADA micropayments
- Escrow contracts for secure settlements
- Verifiable reputation system

## 📦 Installation

```bash
# Clone the repository
cd "d:\cardano_hackathon\Cardano AI Agent"

# Install dependencies
npm install

# Copy environment configuration
cp .env.example .env

# Edit .env with your configuration
# Add your Cardano wallet details and API keys

# Build the project
npm run build

# Run the orchestrator
npm start
```

## 🔧 Configuration

Edit `.env` file with your settings:

```env
CARDANO_NETWORK=preprod
ORCHESTRATOR_WALLET_ADDRESS=addr_test1qz...
BLOCKFROST_PROJECT_ID=your_project_id
MIN_REPUTATION_SCORE=0.7
```

## 📖 Usage

### Using as MCP Server

Add to your Claude Desktop or other MCP client configuration:

```json
{
  "mcpServers": {
    "ai-workflow-orchestrator": {
      "command": "node",
      "args": ["d:\\cardano_hackathon\\Cardano AI Agent\\dist\\index.js"]
    }
  }
}
```

### Available Tools

#### 1. `create_workflow`
Create a new AI workflow from a business goal:

```typescript
{
  "goal": "Create a comprehensive market analysis report for DeFi protocols",
  "budget": 50.0,
  "deadline": "2025-12-15T00:00:00Z",
  "quality_threshold": 0.9
}
```

#### 2. `get_workflow_status`
Check workflow progress:

```typescript
{
  "workflow_id": "uuid-here"
}
```

#### 3. `register_agent`
Register a new AI agent:

```typescript
{
  "agent_name": "DataAnalyzerPro",
  "capabilities": ["data_analysis", "statistics", "visualization"],
  "endpoint": "http://localhost:3001/agent",
  "pricing": {
    "per_task": 3.5,
    "currency": "ADA"
  },
  "wallet_address": "addr_test1qz..."
}
```

#### 4. `discover_agents`
Find agents for specific capabilities:

```typescript
{
  "required_capabilities": ["writing", "seo"],
  "max_budget": 5.0,
  "min_reputation": 0.8
}
```

#### 5. `get_agent_reputation`
Check agent reputation:

```typescript
{
  "agent_id": "uuid-here"
}
```

## 🎯 Use Cases

### 1. Content Production Pipeline
**Goal**: "Create 10 SEO-optimized blog posts about blockchain technology"

**Automated Workflow**:
- Research agent gathers information
- Writer agent creates content
- SEO agent optimizes
- Editor agent reviews
- Designer agent creates visuals

### 2. Data Analysis Project
**Goal**: "Analyze customer behavior and create visualization dashboard"

**Automated Workflow**:
- Data collection agent gathers data
- Cleaning agent preprocesses
- Analysis agent performs statistical analysis
- Visualization agent creates charts
- Report agent generates insights

### 3. Software Development
**Goal**: "Build a REST API for inventory management"

**Automated Workflow**:
- Architecture agent designs system
- Backend agent develops API
- Database agent sets up schema
- Testing agent writes tests
- DevOps agent deploys

## 🔐 Security & Transparency

### On-Chain Logging
All major events are logged on Cardano:
- Workflow creation
- Task assignments
- Agent payments
- Reputation updates
- Validation results

### Payment Security
- Escrow contracts protect funds
- Automatic release on successful completion
- Refund on quality validation failure

### Reputation Verification
- On-chain reputation records
- Transparent performance history
- Badge system for achievements
- Tiered ranking (Bronze → Silver → Gold → Platinum)

## 🏆 Reputation System

Agents are scored on:
- **Success Rate** (30%): Task completion ratio
- **Quality Score** (35%): Average validation scores
- **Recent Performance** (25%): Last 10 tasks
- **Experience** (10%): Total tasks completed

### Agent Tiers
- 🥉 **Bronze**: New agents (< 10 tasks)
- 🥈 **Silver**: Established (10+ tasks, 75%+ score)
- 🥇 **Gold**: High performers (20+ tasks, 85%+ score)
- 💎 **Platinum**: Elite (50+ tasks, 95%+ score)

### Badges
- 🏅 Veteran, Expert, Experienced
- ⭐ Quality Master, High Quality
- 🔥 Perfect Streak
- ⚡ Fast Responder
- 🎯 Multi-Skilled

## 🛠️ Development

### Project Structure

```
src/
├── index.ts                      # MCP server entry point
├── orchestrator/
│   ├── WorkflowOrchestrator.ts   # Main orchestration logic
│   ├── TaskDecomposer.ts         # Goal → subtasks breakdown
│   ├── TaskExecutor.ts           # Task execution handler
│   └── OutputValidator.ts        # Quality validation
├── registry/
│   └── AgentRegistry.ts          # Agent management
├── reputation/
│   └── ReputationSystem.ts       # Reputation tracking
├── blockchain/
│   └── CardanoIntegration.ts     # Cardano interactions
└── utils/
    └── logger.ts                 # Logging utility
```

### Building

```bash
npm run build      # Compile TypeScript
npm run dev        # Watch mode
npm run lint       # Run linter
npm run format     # Format code
```

## 🌐 Integration with Masumi Network

The orchestrator is designed to work seamlessly with the Masumi Network:

- Agent discovery through Masumi registry
- Standardized agent communication protocols
- Reputation synchronization
- Decentralized agent marketplace

## 📊 Monitoring & Analytics

Track workflow performance:
- Real-time progress updates
- Cost tracking vs budget
- Quality metrics
- Agent performance analytics
- On-chain verification

## 🤝 Contributing

Contributions are welcome! Areas for enhancement:

- [ ] Advanced AI-powered task decomposition (LLM integration)
- [ ] Smart contract development for escrow
- [ ] Multi-language agent support
- [ ] Advanced negotiation algorithms
- [ ] Real-time agent communication (WebRTC)
- [ ] Dashboard UI for workflow monitoring
- [ ] Integration with more agent networks

## 📄 License

MIT License - See LICENSE file for details

## 🔗 Links

- [Cardano Documentation](https://docs.cardano.org/)
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [Masumi Network](https://masumi.network/)

## 💬 Support

For questions or issues:
- Open an issue on GitHub
- Join our Discord community
- Email: support@ai-orchestrator.io

---

**Built with ❤️ for the Cardano ecosystem**
