# 🤖 Google ADK Learning Resources

> A comprehensive collection of resources to master Google's Agent Development Kit (ADK) - from basics to production deployment.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Made with ❤️](https://img.shields.io/badge/Made%20with-❤️-red.svg)](https://github.com/yourusername/google-adk-resources)

---

## 📚 What's Inside?

This repository contains everything you need to build sophisticated AI agents using Google's Agent Development Kit:

- 📖 **[Interactive Learning Guide](google_adk_learning_guide.html)** - Visual, story-driven HTML guide & Comprehensive Presentation Deck(aiagentswithgooglesagentdevelopmentkit.pptx)
- 🎥 **Video Primer** - ADK walkthrough (see below)
- 💻 **Code Examples** - Real-world implementations
- 🛠️ **Best Practices** - Security, deployment, and optimization tips

---

## 🎥 Video Primer

Watch the complete walkthrough on YouTube:
https://www.youtube.com/watch?v=_K-WxIFcz1c 

> 🔔 **Subscribe** to stay updated with new content and tutorials!

---

## 📖 Interactive Learning Guide & Comprehensive Deck

Open the **[Google ADK Learning Guide](google_adk_learning_guide.html)** in your browser for a comprehensive, visual learning experience.


**What you'll learn:**
- ✅ Core concepts of AI agents and ADK
- ✅ Setting up your first agent
- ✅ Creating and integrating tools
- ✅ Building multi-agent systems
- ✅ Memory and state management
- ✅ Deployment to production
- ✅ Security best practices

**Features:**
- 🎨 Beautiful, interactive design
- 📊 Visual diagrams and flows
- 💡 Real-world examples and use cases
- 🔧 Copy-paste code snippets
- 🎯 Actionable learning path

Open the  **[Google ADK Comprehensive Deck](aiagentswithgooglesagentdevelopmentkit.pptx)**
---

## 🚀 Quick Start

### Prerequisites
- Python 3.9+
- Google Cloud account (optional, for production)
- API key from [Google AI Studio](https://aistudio.google.com/apikey)

### Installation

```bash
# Install Google ADK
pip install google-adk

# Create your first project
adk create --type=code my_first_agent
cd my_first_agent

# Configure your API key
echo "GOOGLE_GENAI_USE_VERTEXAI=0" > .env
echo "GOOGLE_API_KEY=your-api-key-here" >> .env

# Run the agent
adk web
```

---

## 💻 Code Examples

### All the examples notebooks(ipynb) are Kaggle compatible and can be executed in Kaggle. Download & modify the code accordingly to execute in local environments(Replace Kaggle environments & properties)

### 1. Basic Agent

```python
from google.adk.agents import LlmAgent

# Create a simple assistant
assistant = LlmAgent(
    name="my_assistant",
    model="gemini-2.0-flash",
    instruction="You are a helpful assistant."
)
```

### 2. Agent with Custom Tools

```python
from google.adk.tools import tool

@tool
def get_current_time() -> str:
    """Returns the current time."""
    import datetime
    return datetime.datetime.now().strftime("%H:%M:%S")

# Create agent with tool
assistant = LlmAgent(
    name="time_assistant",
    model="gemini-2.0-flash",
    tools=[get_current_time],
    instruction="You can tell users the current time."
)
```

### 3. Multi-Agent System

```python
from google.adk.tools import AgentTool

# Create specialist agents
flight_agent = LlmAgent(
    name="flight_expert",
    model="gemini-2.0-flash",
    description="Expert in flight bookings"
)

hotel_agent = LlmAgent(
    name="hotel_expert",
    model="gemini-2.0-flash",
    description="Expert in hotel bookings"
)

# Create coordinator that uses specialists
coordinator = LlmAgent(
    name="travel_coordinator",
    model="gemini-2.0-flash",
    tools=[
        AgentTool(agent=flight_agent),
        AgentTool(agent=hotel_agent)
    ],
    instruction="Help users plan trips by delegating to specialists."
)
```

### 4. Agent with Memory

```python
from google.adk.tools import ToolContext

@tool
def save_preference(key: str, value: str, tool_context: ToolContext) -> str:
    """Save user preference."""
    tool_context.state[key] = value
    return f"Saved {key}: {value}"

assistant = LlmAgent(
    name="personalized_assistant",
    model="gemini-2.0-flash",
    tools=[save_preference],
    instruction="Remember user preferences across conversations."
)
```


## 🎯 Learning Path

### Week 1: Foundations
- [ ] Set up environment and create first agent
- [ ] Understand core concepts (agents, tools, sessions)
- [ ] Build simple conversational agent

### Week 2: Tools & Integration
- [ ] Create custom function tools
- [ ] Integrate built-in tools (Google Search, Code Execution)
- [ ] Implement OpenAPI tools

### Week 3: Advanced Patterns
- [ ] Build multi-agent systems
- [ ] Implement memory and state management
- [ ] Use workflow agents (Sequential, Parallel, Loop)

### Week 4: Production Ready
- [ ] Add error handling and validation
- [ ] Implement security best practices
- [ ] Deploy to Vertex AI Agent Engine

---

## 🔗 Official Resources

- 📚 [Official ADK Documentation](https://google.github.io/adk-docs/)
- 💻 [GitHub - ADK Python](https://github.com/google/adk-python)
- ☁️ [Google Cloud - Vertex AI ADK](https://cloud.google.com/vertex-ai/generative-ai/docs/agent-development-kit/overview)
- 🎓 [Google Cloud Blog - Multi-Agent Systems](https://cloud.google.com/blog/products/ai-machine-learning/build-multi-agentic-systems-using-google-adk)

---

## 🤝 Contributing

Contributions are welcome! Whether it's:
- 🐛 Bug fixes
- 📝 Documentation improvements
- 💡 New examples
- 🎨 UI/UX enhancements

Please feel free to open an issue or submit a pull request.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Dheeraj Chitlangi**

- GitHub: [DheerajChitlangi](https://github.com/DheerajChitlangi)
- LinkedIn: [DheerajChitlangi](https://linkedin.com/in/dheerajchitlangi)

---

## ⭐ Show Your Support

If you find this resource helpful, please consider:
- ⭐ Starring this repository
- 🔄 Sharing it with others
- 💬 Providing feedback

---

## 🙏 Acknowledgments

- Google Cloud team for creating the amazing ADK framework
- The open-source community for inspiration and support
- Everyone contributing to making AI agents accessible

---

## 📮 Contact & Feedback

Have questions or suggestions? Feel free to:
- 📧 Open an issue on GitHub
- 💬 Start a discussion
- 🐦 Reach out on social media

---

<div align="center">

### 🚀 Happy Building with Google ADK!

**Made with ❤️ for the AI developer community**

© 2025 Dheeraj Chitlangi. All rights reserved.

</div>
