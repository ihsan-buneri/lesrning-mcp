# Learning MCP: A Beginner's Guide to Model Context Protocol

Welcome to the complete beginner's guide to MCP (Model Context Protocol)! This repository is designed to teach you MCP from the ground up, with no prior knowledge required.

## What is MCP?

Model Context Protocol (MCP) is an open protocol developed by Anthropic that enables AI assistants like Claude to securely connect to external data sources and tools. Think of it as a universal adapter that lets AI applications interact with your files, databases, APIs, and services in a standardized way.

## Prerequisites

- Basic understanding of JavaScript/TypeScript or Python
- Node.js installed (version 18 or higher) OR Python 3.10+
- A code editor (VS Code recommended)
- Basic familiarity with command line/terminal

## Course Structure

This course is organized into progressive lessons, each building on the previous one. Each lesson has its own folder with:
- Detailed tutorial
- Code examples
- Exercises
- Solutions

### Lesson Plan

#### **Lesson 01: Introduction to MCP**
- What is MCP and why does it matter?
- Understanding the MCP architecture
- Real-world use cases
- MCP vs traditional APIs
- Setting up your learning environment

#### **Lesson 02: MCP Fundamentals**
- Understanding the client-server model
- MCP communication protocol (JSON-RPC)
- The three core primitives:
  - Resources (data sources)
  - Tools (actions)
  - Prompts (templates)
- How MCP servers work

#### **Lesson 03: Setting Up Your First MCP Server**
- Choosing your language (TypeScript/Python)
- Installing the MCP SDK
- Creating a basic "Hello World" MCP server
- Understanding the server structure
- Testing your server locally

#### **Lesson 04: Working with Resources**
- What are MCP resources?
- Implementing resource providers
- URI schemes and resource identification
- Building a file system resource server
- Hands-on: Create a notes resource provider

#### **Lesson 05: Building MCP Tools**
- Understanding tools in MCP
- Tool schemas and parameters
- Implementing tool handlers
- Error handling and validation
- Hands-on: Build a calculator tool server

#### **Lesson 06: Creating MCP Prompts**
- What are prompt templates?
- Designing effective prompts
- Dynamic prompt generation
- Prompt arguments and variables
- Hands-on: Build a code review prompt library

#### **Lesson 07: Connecting MCP to Claude**
- Configuring Claude Desktop with MCP
- Testing your MCP server with Claude
- Debugging MCP connections
- Using Claude Dev Tools
- Best practices for MCP integration

#### **Lesson 08: Building a Real-World MCP Server**
- Project: Todo List Manager
- Combining resources, tools, and prompts
- Implementing CRUD operations
- Adding data persistence
- Error handling and logging

#### **Lesson 09: Advanced MCP Concepts**
- Server capabilities and negotiation
- Pagination and large datasets
- Streaming responses
- Authentication and security
- Rate limiting and performance

#### **Lesson 10: MCP Server Deployment**
- Packaging your MCP server
- Environment configuration
- Publishing to npm/PyPI
- Sharing your MCP server
- Documentation best practices

#### **Lesson 11: Working with External APIs**
- Integrating third-party APIs
- API key management
- Building a weather MCP server
- Building a GitHub MCP server
- Hands-on: Create your own API integration

#### **Lesson 12: Database Integration**
- Connecting to databases
- Building a SQLite MCP server
- Query safety and SQL injection prevention
- Schema introspection
- Hands-on: Create a database explorer

#### **Lesson 13: Testing MCP Servers**
- Unit testing MCP tools and resources
- Integration testing strategies
- Using the MCP Inspector
- Debugging common issues
- Test-driven development with MCP

#### **Lesson 14: MCP Security Best Practices**
- Understanding security implications
- Input validation and sanitization
- Secure credential management
- Sandboxing and permissions
- Privacy considerations

#### **Lesson 15: Building Complex MCP Applications**
- Final project: Multi-feature MCP server
- Combining multiple data sources
- Implementing complex workflows
- Performance optimization
- Production readiness checklist

## How to Use This Repository

1. **Start with Lesson 01** and work through each lesson sequentially
2. **Read the tutorial** in each lesson folder
3. **Try the examples** - run the code yourself
4. **Complete the exercises** before moving to the next lesson
5. **Check your solutions** against the provided answers
6. **Experiment** - modify the examples and see what happens!

## Getting Started

```bash
# Clone this repository
git clone https://github.com/yourusername/lesrning-mcp.git
cd lesrning-mcp

# Start with lesson 01
cd lesson-01-introduction
```

## Additional Resources

- [Official MCP Documentation](https://modelcontextprotocol.io/)
- [MCP TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk)
- [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk)
- [MCP Specification](https://spec.modelcontextprotocol.io/)
- [Claude Desktop](https://claude.ai/download)

## Contributing

Found a typo? Have a suggestion? Want to add more examples? Contributions are welcome! Please:
1. Fork this repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## Support

If you're stuck or have questions:
- Check the lesson's FAQ section
- Review the troubleshooting guide
- Open an issue on GitHub

## Learning Path

```
Beginner → Lesson 01-07 (Core concepts and basics)
Intermediate → Lesson 08-12 (Real-world applications)
Advanced → Lesson 13-15 (Testing, security, and production)
```

## License

MIT License - feel free to use this for learning and teaching!

## Acknowledgments

Built with the goal of making MCP accessible to everyone. Special thanks to Anthropic for creating MCP and the open-source community for their examples and contributions.

---

**Ready to start?** Head over to [Lesson 01: Introduction to MCP](./lesson-01-introduction) and begin your MCP journey!
