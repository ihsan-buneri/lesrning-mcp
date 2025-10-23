# Visual Diagrams for Lesson 01

This document contains visual representations of MCP concepts to help you understand the architecture and workflow better.

## MCP Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────┐
│                         MCP Ecosystem                                │
└─────────────────────────────────────────────────────────────────────┘

┌──────────────────┐         ┌──────────────────┐         ┌──────────────────┐
│                  │         │                  │         │                  │
│   MCP CLIENT     │         │   MCP SERVER     │         │   YOUR SYSTEMS   │
│                  │         │                  │         │                  │
│  ┌────────────┐  │         │  ┌────────────┐  │         │  ┌────────────┐  │
│  │            │  │         │  │            │  │         │  │ Databases  │  │
│  │  Claude    │  │◄───────►│  │   Your     │  │◄───────►│  │            │  │
│  │  Desktop   │  │  JSON   │  │   Code     │  │   API   │  └────────────┘  │
│  │            │  │  -RPC   │  │            │  │  Calls  │                  │
│  └────────────┘  │         │  └────────────┘  │         │  ┌────────────┐  │
│                  │         │                  │         │  │   Files    │  │
│  ┌────────────┐  │         │  Implements:     │         │  │            │  │
│  │  Other AI  │  │         │  • Resources     │         │  └────────────┘  │
│  │   Apps     │  │         │  • Tools         │         │                  │
│  │            │  │         │  • Prompts       │         │  ┌────────────┐  │
│  └────────────┘  │         │                  │         │  │ External   │  │
│                  │         │                  │         │  │ APIs       │  │
└──────────────────┘         └──────────────────┘         │  └────────────┘  │
                                                           │                  │
     You use these           You build this               └──────────────────┘
                                                              Your data sources
```

## MCP Communication Flow

```
Step 1: DISCOVERY
┌──────────┐                                    ┌──────────┐
│          │  "What can you do?"                │          │
│  Client  │──────────────────────────────────► │  Server  │
│          │                                    │          │
└──────────┘                                    └──────────┘

┌──────────┐                                    ┌──────────┐
│          │  "I can provide:                   │          │
│  Client  │  • Resources: X, Y, Z              │  Server  │
│          │◄ • Tools: A, B, C                  │          │
│          │  • Prompts: P, Q"                  │          │
└──────────┘                                    └──────────┘


Step 2: REQUEST
┌──────────┐                                    ┌──────────┐
│          │  "Get resource X"                  │          │
│  Client  │──────────────────────────────────► │  Server  │
│          │  OR "Call tool A(params)"          │          │
└──────────┘  OR "Use prompt P"                 └──────────┘


Step 3: PROCESSING
                                                ┌──────────┐
                                                │          │
                                                │  Server  │
                                                │          │
                                                └─────┬────┘
                                                      │
                                                      │ Accesses
                                                      ▼
                                                ┌──────────┐
                                                │ Database │
                                                │   or     │
                                                │   API    │
                                                └──────────┘


Step 4: RESPONSE
┌──────────┐                                    ┌──────────┐
│          │  Returns data/result               │          │
│  Client  │◄────────────────────────────────── │  Server  │
│          │                                    │          │
└──────────┘                                    └──────────┘


Step 5: AI PROCESSING
┌──────────┐
│          │
│  Client  │  AI uses the data to help user
│          │  or execute further actions
└──────────┘
```

## The Three Core Primitives

```
┌─────────────────────────────────────────────────────────────────┐
│                     MCP CORE PRIMITIVES                         │
└─────────────────────────────────────────────────────────────────┘

┌──────────────────┐
│   RESOURCES      │  What: Read-only data sources
│                  │
│   📄 📊 📁       │  Examples:
│                  │  • File contents
│   "Read this"    │  • Database records
│                  │  • API responses
└──────────────────┘  • Document collections

                      Usage: Provide context to AI
                      Direction: AI reads ←


┌──────────────────┐
│   TOOLS          │  What: Executable actions
│                  │
│   🔨 ⚙️ 🛠️       │  Examples:
│                  │  • Send email
│   "Do this"      │  • Create calendar event
│                  │  • Update database
└──────────────────┘  • Call external API

                      Usage: AI performs actions
                      Direction: AI writes →


┌──────────────────┐
│   PROMPTS        │  What: Reusable templates
│                  │
│   📝 💬 🎯       │  Examples:
│                  │  • Code review template
│   "Use this     │  • Bug report format
│    template"    │  • Documentation generator
│                  │  • Analysis framework
└──────────────────┘
                      Usage: Consistent AI interactions
                      Direction: AI uses internally ↻
```

## MCP vs Traditional API

```
TRADITIONAL API INTEGRATION
════════════════════════════

 Your App A          Your App B          Your App C
     │                   │                   │
     │ Custom            │ Custom            │ Custom
     │ Integration       │ Integration       │ Integration
     │                   │                   │
     ▼                   ▼                   ▼
┌─────────┐         ┌─────────┐         ┌─────────┐
│ REST API│         │ REST API│         │ REST API│
└─────────┘         └─────────┘         └─────────┘

Problem: N × M integrations (N apps × M APIs)
Each app needs custom code for each API


MCP APPROACH
════════════

   AI App A           AI App B           AI App C
   (Claude)          (Other AI)         (Future AI)
       │                  │                  │
       │ MCP              │ MCP              │ MCP
       │ Protocol         │ Protocol         │ Protocol
       │                  │                  │
       └──────────────────┴──────────────────┘
                          │
                          ▼
                  ┌──────────────┐
                  │  MCP Server  │  ← You build this ONCE
                  └──────┬───────┘
                         │
            ┌────────────┼────────────┐
            ▼            ▼            ▼
       ┌────────┐   ┌────────┐   ┌────────┐
       │Database│   │  Files │   │  APIs  │
       └────────┘   └────────┘   └────────┘

Solution: Build once, use everywhere
One MCP server works with all MCP clients
```

## Real-World Example: Development Workflow

```
WITHOUT MCP
═══════════

Developer needs to:
1. Switch to GitHub → Check PR status
2. Switch to Terminal → Run tests locally
3. Switch to CI Dashboard → Check build status
4. Switch to Code Editor → Review code
5. Switch back to GitHub → Leave comments
6. Repeat for each PR...

Time: ~15-20 minutes per PR
Context switches: 5+ per PR
Manual coordination: High


WITH MCP
════════

Developer asks Claude:
"Review PR #123"

Behind the scenes:
┌─────────────┐
│   Claude    │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ MCP Server  │
└──────┬──────┘
       │
       ├──► GitHub MCP Server → Fetches PR details
       │
       ├──► Git MCP Server → Analyzes code changes
       │
       ├──► Test Runner MCP Server → Runs tests
       │
       └──► CI/CD MCP Server → Checks build status

Claude provides:
• Comprehensive review
• Test results
• Security analysis
• Suggestions for improvement
• All in one response

Time: ~2-3 minutes per PR
Context switches: 0
Manual coordination: None
```

## Security Model

```
┌────────────────────────────────────────────────────────────┐
│                    MCP SECURITY LAYERS                     │
└────────────────────────────────────────────────────────────┘

Layer 1: USER CONTROL
┌──────────────────────────────────────────────────────────┐
│  User decides which MCP servers to enable                │
│  User grants permissions to AI                           │
└──────────────────────────────────────────────────────────┘

Layer 2: MCP SERVER IMPLEMENTATION
┌──────────────────────────────────────────────────────────┐
│  Server developer defines:                               │
│  • What resources are exposed                            │
│  • Which tools are available                             │
│  • Input validation rules                                │
│  • Rate limiting                                         │
└──────────────────────────────────────────────────────────┘

Layer 3: TRANSPORT SECURITY
┌──────────────────────────────────────────────────────────┐
│  Secure communication channels                           │
│  Credential management                                   │
│  Audit logging                                           │
└──────────────────────────────────────────────────────────┘

Layer 4: SYSTEM PERMISSIONS
┌──────────────────────────────────────────────────────────┐
│  Operating system file permissions                       │
│  Database access controls                                │
│  API authentication                                      │
└──────────────────────────────────────────────────────────┘


EXAMPLE: File System MCP Server

User Request: "Read my documents"
                    │
                    ▼
        ┌───────────────────────┐
        │ Can AI access files?  │
        │ (User configured)     │
        └───────┬───────────────┘
                │ YES
                ▼
        ┌───────────────────────┐
        │ Which directories?    │
        │ (Server config)       │
        └───────┬───────────────┘
                │ Only ~/Documents
                ▼
        ┌───────────────────────┐
        │ File permissions OK?  │
        │ (OS level)            │
        └───────┬───────────────┘
                │ YES
                ▼
        ┌───────────────────────┐
        │ Read files            │
        │ Return to AI          │
        └───────────────────────┘
```

## Data Flow Example: Recipe Manager

```
USER REQUEST: "Find me a vegetarian pasta recipe"

┌─────────────────────────────────────────────────────────────────┐
│                         FLOW DIAGRAM                            │
└─────────────────────────────────────────────────────────────────┘

1. User Input
   ┌──────────┐
   │  User    │  "Find vegetarian pasta recipe"
   └────┬─────┘
        │
        ▼
2. AI Client Processing
   ┌──────────────┐
   │   Claude     │  Understands: Need to search recipes
   └────┬─────────┘  with filters: vegetarian, pasta
        │
        ▼
3. MCP Request
   ┌──────────────┐
   │ MCP Client   │  Calls: searchRecipes(
   └────┬─────────┘    query: "pasta",
        │              filters: {vegetarian: true}
        │            )
        ▼
4. Server Processing
   ┌──────────────┐
   │ Recipe MCP   │  Receives request
   │ Server       │  Validates parameters
   └────┬─────────┘  Executes search
        │
        ▼
5. Data Access
   ┌──────────────┐
   │   Recipe     │  SELECT * FROM recipes
   │  Database    │  WHERE type='pasta'
   └────┬─────────┘  AND vegetarian=true
        │
        ▼
6. Server Response
   ┌──────────────┐
   │ Recipe MCP   │  Returns: [
   │ Server       │    {name: "Veggie Pasta", ...},
   └────┬─────────┘    {name: "Pesto Pasta", ...}
        │            ]
        ▼
7. AI Processing
   ┌──────────────┐
   │   Claude     │  Formats results
   └────┬─────────┘  Adds recommendations
        │
        ▼
8. User Response
   ┌──────────────┐
   │    User      │  "I found 2 vegetarian pasta recipes:
   └──────────────┘   1. Veggie Pasta - Fresh vegetables...
                      2. Pesto Pasta - Classic basil pesto..."
```

## Ecosystem Growth

```
CURRENT STATE (2024-2025)
═════════════════════════

┌─────────────────────────────────────────────────────┐
│  Foundation Layer                                   │
│  • MCP Specification                                │
│  • TypeScript SDK                                   │
│  • Python SDK                                       │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│  Official Servers                                   │
│  • Filesystem                                       │
│  • GitHub                                           │
│  • SQLite                                           │
│  • Memory                                           │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│  AI Clients                                         │
│  • Claude Desktop                                   │
│  • Community projects                               │
└─────────────────────────────────────────────────────┘


NEAR FUTURE (1-2 years)
═══════════════════════

┌─────────────────────────────────────────────────────┐
│  Expanded SDKs                                      │
│  • Go, Rust, Java, C#                               │
│  • Additional language support                      │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│  Community Servers (Growing)                        │
│  • Business tools (Slack, Jira, etc.)               │
│  • Cloud services (AWS, Azure, GCP)                 │
│  • Databases (PostgreSQL, MongoDB, etc.)            │
│  • Custom integrations                              │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│  More AI Clients                                    │
│  • Additional AI assistants                         │
│  • Custom AI applications                           │
│  • Enterprise AI platforms                          │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│  Tooling & Infrastructure                           │
│  • Testing frameworks                               │
│  • Monitoring tools                                 │
│  • Security scanners                                │
│  • MCP marketplaces                                 │
└─────────────────────────────────────────────────────┘
```

## Your Learning Journey

```
WHERE YOU ARE NOW                    WHERE YOU'RE GOING
═════════════════                    ══════════════════

    ┌─────────┐                     ┌──────────────────┐
    │Lesson 01│ ◄─── You are here   │  Build real MCP  │
    │  Intro  │                     │     servers      │
    └────┬────┘                     │                  │
         │                          │  • File systems  │
         ▼                          │  • Databases     │
    ┌─────────┐                     │  • APIs          │
    │Lesson 02│                     │  • Custom tools  │
    │  Basics │                     └──────────────────┘
    └────┬────┘                              ▲
         │                                   │
         ▼                          ┌────────┴─────────┐
    ┌─────────┐                     │   Deploy and     │
    │Lesson 03│                     │   share your     │
    │First MCP│                     │   creations      │
    └────┬────┘                     └──────────────────┘
         │
         ▼
    ┌─────────┐
    │ ...more │
    │ lessons │
    └─────────┘
```

---

## Using These Diagrams

These visual representations are designed to help you:

1. **Understand architecture** - See how components connect
2. **Follow data flow** - Track requests and responses
3. **Compare approaches** - MCP vs traditional methods
4. **Visualize concepts** - Abstract ideas made concrete
5. **Remember key points** - Visual memory aids

Refer back to these diagrams as you progress through the course. They'll make more sense as you build actual MCP servers!

---

**Tip**: Try drawing your own diagrams as you learn. It's a great way to test your understanding!
