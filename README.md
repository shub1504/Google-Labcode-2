# 🚀 MCP Toolbox + BigQuery Agent (Codelab 2)

## 📌 Overview

This project demonstrates how to integrate **MCP Toolbox for Databases** with a **BigQuery public dataset** and build an intelligent agent that can answer user queries.

The dataset used in this project is:

> **Google Cloud Release Notes** (from BigQuery Public Datasets)

---

## 🧠 What This Project Does

* Connects **BigQuery dataset** to MCP Toolbox
* Exposes the dataset as an **MCP Interface**
* Builds an **AI Agent (using ADK)**
* Enables querying release notes using natural language

---

## ⚙️ Workflow

This project follows a step-by-step approach:

1. Identify a relevant dataset from BigQuery public datasets
2. Configure MCP Toolbox for database access
3. Connect MCP Toolbox to BigQuery
4. Build an Agent using ADK
5. Query the dataset using the agent

---

## 🎯 Features

* 🔗 BigQuery integration
* 🤖 AI-powered query agent
* 🧩 MCP-compatible interface
* ⚡ Local testing environment
* 📊 Real-time query handling

---

## 📚 What You’ll Learn

* How to explore and use **BigQuery public datasets**
* How to configure **MCP Toolbox for Databases**
* How to expose datasets to MCP clients (IDEs, tools, etc.)
* How to build an **Agent using ADK**
* How to test MCP-based systems locally

---

## 🛠️ Tech Stack

* Python
* MCP Toolbox for Databases
* Agent Development Kit (ADK)
* BigQuery
* Local development environment

---

## 📦 Project Structure

```
mcp-toolbox/
│
├── my-agent/
│   ├── tools.yaml
│   ├── agent.py
│
├── assets/              # (optional - for screenshots)
├── README.md
```

---

## 🚀 Setup Instructions

### 1️⃣ Clone the Repository

```bash
git clone <https://github.com/shub1504/Google-Labcode-2>
cd mcp-toolbox
```

---

### 2️⃣ Setup Environment

```bash
python -m venv .venv
source .venv/bin/activate   # Linux / Mac
```
### Install the binary version of the MCP Toolbox for Databases via the script given below.
```
  export VERSION=0.23.0 curl -O 
  https://storage.googleapis.com/genai-toolbox/v$VERSION/linux/amd64/toolbox 
  chmod +x toolbox

```

The command given below is for Linux but if you are on Mac or Windows, ensure that you are downloading the correct binary. Check out the releases page for your Operation System and Architecture and download the correct binary.

[Release page for your Operating System and Architecture](https://github.com/googleapis/genai-toolbox/releases)

---

### 3️⃣ Create and run MCP Toolbox
Now, we need to define our BigQuery dataset and tools in the tools.yaml file that is needed by the MCP Toolbox for Database.

Use nano tools.yaml and Create a file named tools.yaml in the same folder i.e. mcp-toolbox
whose content is in:

[Configuration Code](https://github.com/shub1504/Google-Labcode-2/blob/main/mcp-toolbox/tools.yaml)

and run the MCP Toolbox via the following command
```bash
./toolbox --tools_file "tools.yaml"
```

---

### 4️⃣ Run with UI (optional)

```bash
./toolbox --tools_file "tools.yaml" --ui
```

---

## 🧪 Testing

* Open local server (usually `localhost`)
* Send queries like:

  * “Latest Google Cloud updates”
  * “New features released this month”
* Agent will respond using BigQuery data

---
### Install the Agent Development Kit (ADK)

Create a folder named my-agents followed by a virtual environment and then activate your venv with 
```bash
source .venv/bin/activate
```
Install the ADK and the MCP Toolbox for Databases packages
 
```bash
pip install google-adk toolbox-core
```
You can now invoke adk successfully 

We will now create a scaffolding for Google Cloud Release Notes Agent Application via the adk create command 

```bash
adk create gcp_releasenotes_agent_app
```
Choose gemini-2.5-flask and Vertex AI as your root agent and backend models 

Enter your Google Cloud Project ID and Google Cloud region as follows:

Enter Google Cloud project ID [YOUR_GOOGLE_PROJECT_ID]: 

Enter Google Cloud region [us-central1]: 

### Modify agent.py 
Modify agent. py with 

[Code](https://github.com/shub1504/Google-Labcode-2/blob/main/mcp-toolbox/agent.py)

We can now test the Agent that will fetch real data from our BigQuery dataset that has been configured with the MCP Toolbox for Databases.

In one terminal of Cloud Shell, launch the MCP Toolbox for Databases.

```bash
./toolbox --tools_file "tools.yaml"
```

Once the MCP server has started successfully, in another terminal, launch the Agent via the adk run

```bash
adk run gcp_releasenotes_agent_app/
```
---

## ✅ Final Outcome

✔ MCP Toolbox successfully configured
✔ BigQuery dataset exposed to MCP clients
✔ Agent built and tested
✔ Natural language queries working

---

## 🎉 Conclusion

You have successfully:

* Integrated **BigQuery with MCP Toolbox**
* Built a **functional AI Agent**
* Enabled **data-driven querying via MCP**

---

## 🔮 Future Improvements

* Add more datasets
* Improve agent reasoning
* Deploy on cloud
* Add authentication (OAuth)

---

## 🤝 Acknowledgment

This project is based on a hands-on codelab for learning MCP + BigQuery integration.

---
