<bug>
$1
</bug>

You are now in BUG ANALYSIS MODE.

Read the codebase and identify the root cause based on the bug described above.

---

## Tasks:
1) Locate all files/modules affected by the issue. List paths and why each is implicated.  
2) Explain the root cause(s): what changed, how it propagates to the failure, and any environmental factors.  
3) Propose the minimal, safe fix.
 
---

## OUTPUT FORMAT:

- **Root cause of the bug:**  
  <concise explanation>

- **File locations and line numbers:**  
  - <file_path>:L<number>-L<number>

- **roposed minimal fixing scenarios:**  
   <option>  
     - Recommended? <yes/no>  
     - Reasoning: <explanation>  
   *(Include multiple options only if relevant. If one path is clearly best, provide that single plan.)*


- **Open questions / assumptions:**  
  - <items>

---

## RULES:
- DO NOT WRITE OR EDIT ANY FILES.  
- Use web search for up-to-date documentation or known issues.  
- Mention if **additional context** may be needed before confirming the fix.  
