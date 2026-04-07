---
name: issue-analyzer
description: Analyze program issues including crashes, bugs, and errors by examining crash stacks, core dumps, and log files alongside source code. Generates a detailed analysis report with root cause, call flow, and fix recommendations. Use when the user provides a "crash stack", "crash log", "core dump", "error log", "bug report", "stack trace", "exception", "ANR trace", or asks to "analyze this crash", "debug this issue", "find the root cause", "why did this crash", or "what caused this error".
user-invocable: true
argument-hint: "[crash log / stack trace file path]"
---

# Issue Analyzer

Analyze program issues by combining crash stacks, core dumps, and log files with source code to produce a comprehensive root cause analysis report. Output includes both a Markdown document and a styled HTML file.

## When To Use

Use this skill when the user:

- Provides a crash stack trace and wants to understand why the crash happened
- Shares a core dump or daydrive for analysis
- Has log files showing errors and wants root cause analysis
- Needs a fix recommendation for a program issue

## Input

The user provides one or more of:

1. **Crash stack trace** — Raw stack trace, crash dump, or panic output
2. **Core dump / Daydrive** — Binary crash dump files
3. **Log files** — Application logs, system logs, error logs
4. **Source code path** — Directory containing the relevant source code (optional but strongly recommended)

If the source code path is not provided, ask the user. If the user cannot provide source code, perform analysis based on available crash data alone.

## Analysis Workflow

### Phase 1: Information Gathering

Collect and organize all available crash data:

1. **Crash stack parsing**: Extract the full stack trace, identify the crashing thread, and parse frame information (function names, file paths, line numbers, addresses).
2. **Signal/Exception info**: Identify the crash signal (SIGSEGV, SIGABRT, etc.) or exception type, fault address, and register state if available.
3. **Process metadata**: Extract process name, PID, timestamp, OS version, architecture, build version.
4. **Log context**: If logs are provided, find entries around the crash timestamp to establish timeline.
5. **Thread state**: If multiple threads are present, identify the crashing thread and note other thread states.

### Phase 2: Stack Trace Analysis

Deeply analyze the crash stack:

1. **Crash point identification**: Pinpoint the exact function and line where the crash occurred.
2. **Call chain reconstruction**: Trace the full call chain from entry point to crash point.
3. **Frame categorization**: Separate system/library frames from application frames.
4. **Symbol resolution**: If symbols are available, resolve addresses to function names.
5. **Pattern recognition**: Identify common crash patterns:
   - Null pointer dereference
   - Use-after-free
   - Buffer overflow / stack overflow
   - Race condition indicators / deadlock patterns
   - Memory corruption
   - Assertion failures / unhandled exceptions

### Phase 3: Source Code Correlation

If source code is available, correlate the crash with the codebase:

1. **Crash site code review**: Read the source file and function at the crash point.
2. **Call path tracing**: Follow the call chain through the source to understand the execution path.
3. **Variable state inference**: Based on the crash type and location, infer likely variable states at crash time.
4. **Related code inspection**: Check memory management, thread synchronization, error handling paths, input validation, and resource lifecycle (alloc/free, open/close).
5. **Historical context**: If git is available, check recent changes to crash-related files.

### Phase 4: Root Cause Analysis

Synthesize findings into a root cause determination:

1. **Direct cause**: What immediately caused the crash (e.g., "null pointer dereference at line X").
2. **Underlying cause**: Why the direct cause occurred (e.g., "object freed in thread A while thread B still held a reference").
3. **Contributing factors**: Conditions that enabled the bug (e.g., "race window between X and Y", "missing null check after API call").
4. **Reproduction conditions**: What state, input, or timing would trigger this crash.

### Phase 5: Impact Assessment

Evaluate the severity and scope:

1. **Crash frequency estimation**: Is this likely a rare edge case or a common path?
2. **User impact**: What was the user experiencing when this crashed?
3. **Data integrity**: Could this crash lead to data corruption or loss?
4. **Security implications**: Could this be exploited? (Do NOT provide exploitation details)
5. **Blast radius**: What other components or features are likely affected?

### Phase 6: Solution Development

Develop fix recommendations:

1. **Immediate fix**: The minimum change to prevent this specific crash.
2. **Proper fix**: A more thorough fix addressing the underlying cause.
3. **Preventive measures**: Changes to prevent similar issues (assertions, better error handling, static analysis rules).
4. **Confidence level**: Rate confidence in each recommendation (High/Medium/Low) based on evidence quality.

## Output

Generate two files in the current directory (or a user-specified directory):

1. `issue-analyzer.md` — Markdown report
2. `issue-analyzer.html` — Styled HTML report

If either file already exists, back up as `issue-analyzer-backup-YYYYMMDD-HHMMSS.md` (or `.html`).

### Report Structure

Use the template in `references/report-template.md` for the Markdown structure.

The report must contain these sections:

1. **Basic Information** — Process info, timestamp, environment, build version, event timeline
2. **Core Data** — Crash stack with color-coded frames, key frame analysis table, thread info
3. **Deep Analysis** — Root cause summary, direct cause, underlying cause, contributing factors, related files
4. **Call Flow** — Complete execution path reconstruction, variable state analysis
5. **Solution** — Immediate fix, proper fix, preventive measures, confidence assessment, open questions

### HTML Generation

After writing the Markdown report, generate the HTML version using the template in `references/html-template.html`.

The HTML report must:
- Be a single self-contained file (all CSS and JS inline)
- Use a clean, professional design with crash-analysis-optimized typography
- Color-code stack frames (crash frame = red, app frames = purple, system frames = gray)
- Color-code confidence levels and fix severity
- Include a navigation sidebar with section jump links
- Support manual light/dark mode toggle with a button in the **bottom-left corner of the sidebar**
- Render well on both desktop and mobile
- On mobile: sidebar collapses by default, a hamburger button reveals it, clicking a nav link closes the sidebar automatically

### Evidence Rules

- Cite exact file paths and line numbers for every claim
- Distinguish confirmed facts from inferences
- Rate confidence for each conclusion
- Do NOT include any credentials, API keys, tokens, or secrets found in logs
- Do NOT provide exploitation details for security-sensitive crashes
- If evidence is insufficient, say so directly and describe what additional information would help

## Writing Quality

The report should read like an expert engineer's incident analysis:

- Lead with the most important finding — do not bury the root cause
- Connect evidence to conclusions explicitly; do not assert without backing
- Be precise and technical but clear — avoid vague descriptions like "something went wrong"
- Use concrete code references: function names, file paths, line numbers
- Prioritize actionable insights over exhaustive description
- Distinguish confirmed facts, inferences, and open questions
