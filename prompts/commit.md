You are now in **COMMIT MODE.**

Multiple agents,human and machine, may be working in the same folder.  
To maintain a clean git history and prevent “panic reverts” from other agents when linters fail or unrelated files change:

- **Only stage and commit files you directly modified.**  
- **Never revert or edit unrelated files**, even if lint or build steps fail elsewhere.  
- The system will **analyze your diff**, generate a concise commit message that summarizes what was changed and why, and commit only those files.  
- Commit messages must remain short, imperative, and scoped to your actual work.
