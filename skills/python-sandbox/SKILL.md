---
name: python-sandbox
description: MUST use when the agent plans to execute python code/scripts, run python tests/modules, or install/manage python packages. Ensures everything runs inside the 'agent-sandbox' conda environment.
---
# Python Sandbox Enforcement

## Core Rules
1. **Never use host Python/Pip**: Never run bare `python`, `python3`, `pip`, or `pip3` on the host base environment.
2. **Stateless Prefix Rule**: Always prefix all python/pip commands with `conda run -n agent-sandbox`. Do not rely on `conda activate`.
   - *Example*: `conda run -n agent-sandbox python script.py`
   - *Example*: `conda run -n agent-sandbox pip install <package>`
3. **Detail Reference**: If you need to perform environment setup, verification, advanced package management, or troubleshooting, read [python-sandbox-ref.md](python-sandbox-ref.md).
