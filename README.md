# Autonomous Secure Multi-Agent Software Development Pipeline

An optimized, local multi-agent system designed to act as an autonomous software engineering pipeline. The framework leverages a local Large Language Model (LLM) via Ollama to automatically audit code for cybersecurity vulnerabilities, generate structured assessments, and execute self-healing patch operations before code evaluation.

## 🏗️ System Architecture

Instead of relying on a single monolith prompt, this project implements a decentralized **Multi-Agent Architecture (MAS)** where specialized sub-agents collaborate asynchronously through structured data barriers:

1. **The Ingestion Sandbox:** Simulates or creates the unverified raw source code (potentially written by lower-tier modules or untrusted systems).
2. **The Cyber Security Proxy Agent:** Executes a behavioral and static safety scan using local LLM inference. It enforces structured schemas (`JSON`) to classify code safety signatures as `SAFE` or `UNSAFE`.
3. **The Engineering Self-Healing Agent:** Triggered only if a vulnerability signature is detected. It ingests the JSON threat error context, isolates the target vector, and executes a secure code refactoring patch.
4. **The Runtime Isolation Unit:** Executes the final sanitized script in a clean native terminal subprocess to guarantee functional equivalence.

## ⚙️ Core Engineering Highlights
* **Hardware Optimization (Edge/Local Deployments):** Specifically engineered to run with ultra-low latency on constraint-heavy host hardware (e.g., 8GB RAM local environments) by leveraging a quantized **Llama 3.2 (3B)** model topology.
* **Structured Guardrails:** Bypasses standard generative text prose by forcing raw JSON programmatic validation, enabling seamless agent-to-agent interface protocols.
* **Vulnerability Target Vector:** Out-of-the-box demo targets Shell Command Injections (such as arbitrary shell loops in `os.system`) and refactors them dynamically using safe native abstractions.

## 🚀 Getting Started

### Prerequisites
* Python 3.10+
* [Ollama](https://ollama.com/) installed and running locally
* Llama 3.2 model pulled down:
  ```bash
  ollama run llama3.2
