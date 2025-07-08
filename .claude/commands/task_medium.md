Use sequential-thinking mcp and all its tools that you will need about the problem and how to solve it. You must ultrathink for the solution and use reasoning.

You must consider edge cases and follow best coding practices for everything. Never do bandaid fixes.

## Configuration

STEP 1: 
CREATE a folder inside claude-code-storage folder with the name claude-instance-{id}, in place of id choose an incremental number depending on how many folders you find there.

STEP 2: 
You must create a subagent with a task to investigate all codebase files and find the files related to the problem and always create a "REPORT.md" inside /claude-code-storage/claude-instance-{id} which you will then read to learn the list of files needed for you to check in order to understand and solve the problem. YOU MUST NEVER read the subagents results directly from the subagent, you have to wait until the subagent has finished executing its task and only then search for the "REPORT.md" file on project root. After you finish reading the "REPORT.md" file, enter plan mode.

STEP 3: 
When the user accepts your plan, write it in a "PLAN.md" file inside /claude-code-storage/claude-instance-{id} folder you created.

Problem: $ARGUMENTS
