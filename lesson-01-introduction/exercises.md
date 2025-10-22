# Lesson 01: Exercises

Test your understanding of MCP fundamentals with these exercises. Try to answer all questions before checking the solutions!

## Part 1: Conceptual Understanding

### Exercise 1.1: Define MCP
In your own words, explain what MCP is and what problem it solves. (3-4 sentences)

---

### Exercise 1.2: Architecture Components
Name and briefly describe the three main components in the MCP architecture.

1. ________________: _________________________________________________
2. ________________: _________________________________________________
3. ________________: _________________________________________________

---

### Exercise 1.3: Core Primitives
Match each MCP primitive with its correct description:

| Primitive | Description |
|-----------|-------------|
| A. Resources | 1. Reusable templates for AI interactions |
| B. Tools | 2. Read-only data sources that provide context |
| C. Prompts | 3. Executable actions or functions |

**Your Answers:**
- A matches with: ____
- B matches with: ____
- C matches with: ____

---

### Exercise 1.4: MCP vs APIs
List three key differences between MCP and traditional REST APIs.

1. _________________________________________________________________
2. _________________________________________________________________
3. _________________________________________________________________

---

## Part 2: Use Case Analysis

### Exercise 2.1: Identify the Primitive
For each scenario, identify which MCP primitive(s) would be most appropriate:

**Scenario A**: An AI needs to read the contents of your company's employee handbook.
- Primitive(s): ________________

**Scenario B**: An AI needs to send a Slack message to your team channel.
- Primitive(s): ________________

**Scenario C**: An AI needs to use a pre-written template for creating bug reports.
- Primitive(s): ________________

**Scenario D**: An AI needs to both read your calendar and create new events.
- Primitive(s): ________________

---

### Exercise 2.2: Design an MCP Server
You're tasked with building an MCP server for a recipe management system. Users should be able to:
- Search and view recipes
- Add new recipes
- Generate shopping lists
- Get cooking tips from templates

**Questions:**
1. What resources would your MCP server expose?
2. What tools would your MCP server provide?
3. What prompts would be useful?
4. Draw or describe the architecture of this system.

---

### Exercise 2.3: Real-World Application
Think of a problem in your daily work or life that could be solved with MCP. Describe:

1. **The Problem**: What challenge are you trying to solve?
2. **The Data/Tools**: What systems or data sources would be involved?
3. **MCP Solution**: How would you use MCP to solve it?
4. **Benefits**: What advantages would this have over a traditional approach?

---

## Part 3: Technical Preparation

### Exercise 3.1: Environment Verification
Run the following commands and record the output:

```bash
# Check Node.js version
node --version

# OR check Python version
python3 --version

# Check if git is installed
git --version
```

**Your Output:**
```
Node/Python version: ________________
Git version: ________________
```

Are you ready for the next lessons? ☐ Yes ☐ No

---

### Exercise 3.2: Choose Your Path
Which language will you use for this course?

☐ TypeScript
☐ Python
☐ Both

**Why did you choose this language?**

_________________________________________________________________

---

### Exercise 3.3: Setup Practice
Create a new directory called `mcp-learning` in your preferred location and initialize it:

**For TypeScript users:**
```bash
mkdir mcp-learning
cd mcp-learning
npm init -y
```

**For Python users:**
```bash
mkdir mcp-learning
cd mcp-learning
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

Did this complete successfully? ☐ Yes ☐ No

If no, what error did you encounter?

_________________________________________________________________

---

## Part 4: Critical Thinking

### Exercise 4.1: Security Considerations
MCP gives AI assistants access to your data and tools. List three potential security concerns and how MCP might address them.

1. **Concern**: _____________________________________________________
   **How MCP addresses it**: ________________________________________

2. **Concern**: _____________________________________________________
   **How MCP addresses it**: ________________________________________

3. **Concern**: _____________________________________________________
   **How MCP addresses it**: ________________________________________

---

### Exercise 4.2: When NOT to Use MCP
Can you think of scenarios where MCP might NOT be the best choice? List two examples and explain why.

1. _________________________________________________________________
   _________________________________________________________________

2. _________________________________________________________________
   _________________________________________________________________

---

### Exercise 4.3: Future Implications
How do you think MCP might change the way we interact with AI in the next 2-5 years? (Open-ended, 1 paragraph)

_________________________________________________________________
_________________________________________________________________
_________________________________________________________________
_________________________________________________________________

---

## Part 5: Research Exercise

### Exercise 5.1: Explore the Ecosystem
Visit the [MCP GitHub organization](https://github.com/modelcontextprotocol) and find:

1. **An example MCP server** - Name: ________________
   - What does it do? ______________________________________________

2. **The TypeScript SDK repository** - URL: ________________

3. **The Python SDK repository** - URL: ________________

---

### Exercise 5.2: Community Discovery
Find one real-world MCP server built by the community (search GitHub, npm, or PyPI).

**Server Name**: ___________________________________________________

**What it does**: __________________________________________________

**Why it's interesting to you**: ____________________________________

---

## Bonus Challenge

### Challenge: Explain MCP to a Friend
Write a 2-3 paragraph explanation of MCP as if you're explaining it to a non-technical friend. Use analogies and simple language.

_________________________________________________________________
_________________________________________________________________
_________________________________________________________________
_________________________________________________________________
_________________________________________________________________
_________________________________________________________________

---

## Self-Assessment

Before moving to Lesson 02, rate your understanding of these concepts (1=not confident, 5=very confident):

| Concept | Rating (1-5) |
|---------|--------------|
| What MCP is and its purpose | ____ |
| MCP architecture components | ____ |
| The three core primitives | ____ |
| Difference between MCP and APIs | ____ |
| Real-world use cases for MCP | ____ |
| Your development environment | ____ |

**If any rating is below 3, review that section in the lesson before continuing!**

---

## Submission Checklist

Before checking solutions, ensure you've:
- ☐ Attempted all exercises honestly
- ☐ Written your own answers without looking ahead
- ☐ Verified your development environment is set up
- ☐ Thought critically about the concepts
- ☐ Identified areas where you need more clarity

Ready to check your answers? Proceed to [solutions.md](./solutions.md)

**Remember**: The goal is learning, not perfection. If you got something wrong, that's a learning opportunity!
