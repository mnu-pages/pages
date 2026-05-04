# Contributing to the pages repository

Welcome to the official pages repository of the mnu-pages organization. We are thrilled to have you contribute!

To ensure every page remains clean, parses at lightning speed in our C-based renderer, and is equally helpful for a beginner as it is for an expert, we enforce a strict formatting layout called the **mnu standard**.

This guide breaks down every minor detail. Please follow it carefully to ensure your Pull Request is merged without friction.


## 1. Global Formatting & Syntax Rules

Our renderer is designed to be extremely lightweight. Because of this, the parser only understands a specific set of syntax rules.

**Valid Formatting Tokens:**
 * **text** : Double asterisks trigger **bold** styling.
 * __text__ : Double underscores trigger **underline** styling.

**Critical Formatting Rules:**
 * **Renderer Automations:** The renderer automatically styles .TITLE (centers and underlines) and .DIV (bolds). **Do not** add manual formatting tokens to these tags.
 * **No Nesting or Combining:** You must never combine formatting tokens inside standard text.
   * **Bad:** **__text__** (Will break the parser)
   * **Good:** **bold text** and __underlined text__
 * **Encoding:** All files must be UTF-8.
 * **File Extension:** Every file must end in .mn (e.g., tar.mn).


## 2. General Writing Style

 * **Keep it active and factual:** Use the present indicative tense. Think of it like a technical dictionary.
 * **Skip the fluff:** We want to get straight to the point. Eliminate filler words like "simply," "just," or "actually."

**Example 1 (Voice and Tense):**
 * **Bad:** Create a directory. (Imperative)
 * **Good:** Creates a directory. (Present Indicative)

**Example 2 (Filler Words):**
 * **Bad:** Simply lists the actual files easily.
 * **Good:** Lists the files in the current directory.


## 3. The Structure of a .mn File

Every file is built using specific Divisions (.DIV). They must appear in the exact order listed below.

### 3.1. The Title

 * Start your file with .TITLE "command"
 * The command name must be fully lowercase, wrapped in double quotes, and match the actual CLI tool exactly.
 * *Note:* The renderer automatically places this at the top middle of the screen and applies an underline. Do not format this string manually.

**Example:**
 * **Bad:** **.TITLE "ls"**
 * **Good:** .TITLE "ls"

### 3.2. The Description Division

 * Start with .DIV "DESCRIPTION" (The renderer automatically applies bold to the division header).
 * Explain what the tool does in a formal way. Keep it brief (maximum 5 wrapped lines) and do not use blank lines inside the division.
 * **Formatting Rules:** * Use the underline highlighter (__text__) strictly for variables, flags, or command names.
   * Use the bold highlighter (**text**) strictly when a detail is important, critical, or constitutes a warning.

**Example (Demonstrating __ and **):**
 * **Bad:** It manages **containers** and is very DANGEROUS.
 * **Good:** Manages lightweight **containers**. Using the **-f** flag skips all prompts. Use with **extreme caution**.

### 3.3. The TLDR Division (The Core Architecture)

 * Start with .DIV "TLDR"
 * Add enough commands to cover 80-90% of the most common use cases.
 * **Spacing:** Leave exactly one blank line between each command entry.
 * **The 3-Line Rule:** Every command entry must be exactly 3 lines long.

**Line 1 (The Action):** The entire command must be wrapped in **bold**. You must decouple flags.
 * **Bad:** tar -xvf archive.tar
 * **Good:** **tar -x -v -f archive.tar**

**Line 2 (The Intent):** Write a complete sentence explaining the command. You must use __keyword__ (double underscores) to wrap words that directly map to the action, flags, or variables from Line 1. No other formatting is allowed.
 * **Bad:** Extracts a file.
 * **Good:** **Extracts** a specific **file**.

**Line 3 (The Legend):** Start with >  and define your variables and flags, separated by a |. You must **always** underline the argument or flag itself using double underscores. If your command has no variables, leave a blank > .
 * **Bad:** > -x extract flag | file the target archive
 * **Good:** > **-x** extract flag | **file** the target archive

### 3.4. The Summary Division

 * Start with .DIV "SUMMARY"
 * Provide a helpful tip, a best practice, or a good habit. Maximum 5 wrapped lines, no blank lines inside.
 * **Formatting Rules:** Same as the Description Division.
   * Use __text__ to highlight variables, flags, or commands.
   * Use **text** to highlight important tips, critical concepts, or warnings.

**Example (Demonstrating __ and **):**
 * **Good:** Always run **git status** before committing. Deleting files with **rm** is permanent on most systems; proceed with **caution** to avoid losing **critical production data**.

### 3.5. The See Also Division

 * Start with .DIV "SEE ALSO"
 * Link up to 3 related pages. Every link must be formatted as **cli:command**. Skip this division if there are no related tools.

**Example:**
 * **Bad:** cli:ls cli:pwd
 * **Good:** **cli:ls** **cli:pwd**

### 3.6. External Links (The Spacer)

 * Leave exactly one blank line after your SEE ALSO division (or Summary, if skipped).
 * Documentation URL must use double underscores.
 * License must use the standard plain text short-name (e.g., MIT, GPL-3.0). If the tool uses a custom license, write Custom License and include the URL to the license if possible.

**Example:**
 * **Good Documentation:** documentation: __https://example.com__
 * **Good License:** license: MIT
 * **Good Custom License:** license: Custom License (**https://example.com/license**)

### 3.7. The Author Division

 * Start with .DIV "AUTHOR" at the very bottom of the file.
 * Plain text only. No formatting.
 * **When to use your GitHub Username:** Use this if you want public attribution for your contribution and have an active GitHub account (e.g., written by nstarkdev).
 * **When to use mnu contributor:** Use this fallback if you prefer to remain anonymous, do not have a GitHub account, or are submitting code on behalf of a larger anonymous group.

**Example:**
 * **GitHub User:** written by nstarkdev
 * **Anonymous Fallback:** written by mnu contributor


## 4. Local Testing

Before submitting a Pull Request, you should verify how your page renders. You can test your .mn files locally using the official mnu client.

Run the following command in your terminal:

```bash
mnu run file.mn
# or
mnu run path/to/file.mn
```

Ensure there are no parsing errors and that the visual output perfectly matches the layout expectations.


## 5. Reference Examples

For complete, real-world examples of files written entirely in the mnu standard, please redirect to the examples/ folder in this repository. We highly recommend copying a file from examples/ to use as a baseline template for your new command.


## 6. How to Contribute

Ready to submit a page? Follow these industry-standard steps:

 1. **Fork the Repository:** Click the 'Fork' button at the top right of this repository to create your own copy.
 2. **Clone your Fork:** Clone the repo to your local machine using git clone.
 3. **Create a Branch:** Create a new branch for your command. Use a descriptive name: git checkout -b add-command-name.
 4. **Write the Page:** Create command-name.mn in the correct directory, test it locally with mnu run, and follow all rules in this guide.
 5. **Commit your Changes:** Commit with a clear, concise message: git commit -m "feat: add mnu page for command-name".
 6. **Push and PR:** Push to your fork and open a Pull Request against our main repository.


## 7. AI-Generated Code Policy

AI-generated content is welcome and respectfully accepted in this project. If you use Large Language Models to help draft your .mn pages, we only ask two things:

 1. Ensure the output strictly adheres to the **mnu standard** detailed above.
 2. Provide a thorough human review of the generated content to verify technical accuracy and grammar before submitting your Pull Request.
