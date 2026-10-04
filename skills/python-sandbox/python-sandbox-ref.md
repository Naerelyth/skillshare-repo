# Python Sandbox Reference & Troubleshooting Guide

Use this reference to perform advanced setup, package management, verification, or troubleshooting within the `agent-sandbox` environment.

## 1. Advanced Command Templates

### Running Python
- **Inline Code**:
  ```bash
  conda run -n agent-sandbox python -c "your code here"
  ```
- **Module Execution**:
  ```bash
  conda run -n agent-sandbox python -m <module_name>
  ```

### Package Management
- **Requirements File**:
  ```bash
  conda run -n agent-sandbox pip install -r requirements.txt
  ```
- **Using Conda**:
  ```bash
  conda install -n agent-sandbox <package_name>
  ```

## 2. Verification Commands
Verify that python is running from the sandbox:
```bash
conda run -n agent-sandbox python -c "import sys; print(sys.executable)"
```
*Expected output contains: `envs/agent-sandbox`.*

To list installed packages:
```bash
conda run -n agent-sandbox pip list
```

## 3. Environment Setup & Recovery
If the environment `agent-sandbox` is missing or corrupted, recreate it:
```bash
conda create -y -n agent-sandbox python=3.11
```
Then run the verification command above to ensure it is functional.
