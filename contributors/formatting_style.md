# Formatting Style Guidelines for .mn Files

This document outlines the specific formatting and structural rules for creating `.mn` pages. Adhering to these guidelines is crucial for maintaining consistency, clarity, and a uniform presentation across all documentation, which greatly enhances the user experience.

## I. Global Formatting and Syntax Rules

These rules apply universally to all `.mn` files.

### A. Valid Formatting Tokens

-   `**text**`: Double asterisks trigger **bold** styling (used for emphasis, critical details, or command names in TLDR Line 1).
-   `__text__`: Double underscores trigger __underline__ styling (used for variables, flags, or command names in Description, Summary, and TLDR Line 3).

### B. Critical Formatting Constraints

-   **Renderer Automations:** The renderer automatically styles `.TITLE` (centers and underlines) and `.DIV` (bolds). **Do not** add manual formatting tokens to these tags.
-   **No Nesting or Combining:** You must never combine formatting tokens inside standard text (e.g., `**__text__**` is invalid).
-   **One Tool, One File:** Each CLI tool must have exactly one corresponding `.mn` file named after the base command (e.g., `git.mn`). Separate files for subcommands (e.g., `git-commit.mn`, `git-branch.mn`) are strictly prohibited. Document all essential subcommands within the main tool's file.
-   **Character Encoding:** All files must be UTF-8.
-   **File Extension:** Every file must end in `.mn` (e.g., `tar.mn`).

## II. Structure of an .mn File (Sections and Order)

Every `.mn` file must follow this exact order of sections, built using specific Divisions (`.DIV`).

### A. The Title (`.TITLE "command"`)

-   Start your file with `.TITLE "command"`.
-   The command name must be fully lowercase, wrapped in double quotes, and match the actual CLI tool exactly.
-   *Note:* The renderer automatically places this at the top middle of the screen and applies an underline. Do not format this string manually.

    **Example:**
     * **Bad:** `**`.TITLE "ls"` `**`
     * **Good:** `.TITLE "ls"`

### B. The Description Division (`.DIV "DESCRIPTION"`)

-   Start with `.DIV "DESCRIPTION"`.
-   **Formatting Rules:**
    -   Use `__text__` strictly for variables, flags, or command names.
    -   Use `**text**` strictly when a detail is important, critical, or constitutes a warning.

    **Example (Demonstrating __ and **):**
     * **Bad:** It manages **containers** and is very DANGEROUS.
     * **Good:** Manages lightweight **containers**. Using the **-f** flag skips all prompts. Use with **extreme caution**.

### C. The Alias Division (`.DIV "ALIAS"`)

-   Start with `.DIV "ALIAS"`.
-   List all command aliases.
-   **Formatting Rules:**
    -   All aliases must be included.
    -   Only **bold** formatting (`**text**`) is allowed.
    -   Aliases are separated by spaces.

    **Example:**
     * **Good:** `**nvim** **vi**`

### D. The TLDR Division (`.DIV "TLDR"`)

-   Start with `.DIV "TLDR"`.
-   Add enough commands to cover 80-90% of the most common use cases.
-   **Spacing:** Leave exactly one blank line between each command entry.
-   **The 3-Line Rule:** Every command entry must be exactly 3 lines long.
    -   **Line 1 (The Action):** The entire command must be wrapped in `**bold**`. You must decouple flags.
        * **Bad:** `tar -xvf archive.tar`
        * **Good:** `**tar -x -v -f archive.tar**`
    -   **Line 2 (The Intent):** Write a complete sentence explaining the command. No formatting is allowed on this line.
        * **Bad:** `__Extracts__ a specific __file__`.
        * **Good:** `Extracts a specific file.`
    -   **Line 3 (The Legend):** Start with `> ` and define your variables, flags, or subcommands, separated by a `|`.
        *   **Avoid Redundancy:** If Line 2 (The Intent) already clearly explains a variable, flag, or subcommand, do not repeat it in the Legend. Leave the Legend as a blank `> ` if every element is already self-evident from the Intent.
        *   **Formatting:** You must **always** underline the argument, flag, or subcommand itself using double underscores (`__text__`).
        *   **Subcommands:** You can define subcommands for clarity (e.g., `__commit__ the commit subcommand`).

        **Example (Standard Legend):**
        *   **Bad:** `> -x extract flag | file the target archive`
        *   **Good:** `> __-x__ extract flag | __file__ the target archive`

        **Example (Blank Legend for Clarity):**
        *   **Good Line 1:** `**ls**`
        *   **Good Line 2:** `Lists directory contents in the current path.`
        *   **Good Line 3:** `> ` (Blank because `ls` is self-evident from the intent)

        **Example (Subcommand in Legend):**
        *   **Good Line 1:** `**git commit -m "message"**`
        *   **Good Line 2:** `Records changes to the repository with a descriptive message.`
        *   **Good Line 3:** `> __commit__ subcommand | __-m__ message flag | __"message"__ description` (Note: If `commit` was already clear enough in Line 2, it could be omitted here).

### E. The Summary Division (`.DIV "SUMMARY"`)

-   Start with `.DIV "SUMMARY"`.
-   **Formatting Rules:** Same as the Description Division (refer to Section II.B).

    **Example (Demonstrating __ and **):**
     * **Good:** Always run `**git status**` before committing. Deleting files with `**rm**` is permanent on most systems; proceed with `**caution**` to avoid losing `**critical production data**`.

### F. The See Also Division (`.DIV "SEE ALSO"`)

-   Start with `.DIV "SEE ALSO"`.
-   Link up to 3 related pages. Every link must be formatted as `**cli:command**`. Skip this division if there are no related tools.

    **Example:**
     * **Bad:** `cli:ls cli:pwd`
     * **Good:** `**cli:ls** **cli:pwd**`

### G. Metadata (External Links and License)

-   Leave exactly one blank line after your SEE ALSO division (or Summary, if SEE ALSO is skipped).
-   **Documentation URL:** Must use double underscores (e.g., `documentation: __https://example.com__`).
-   **License:** Must use the standard plain text short-name (e.g., `license: MIT`, `license: GPL-3.0`). If the tool uses a custom license, write `Custom License` and include the URL if possible (e.g., `license: Custom License (__https://example.com/license__)`).

### H. The Author Division (`.DIV "AUTHOR"`)

-   Start with `.DIV "AUTHOR"` at the very bottom of the file.
-   Plain text only. No formatting.
-   **Attribution:**
    -   Use your GitHub Username (e.g., `written by nstarkdev`) for public attribution.
    -   Use your real name (e.g., `written by John Doe`) as a fallback if you want attribution but do not have a GitHub account.
    -   Use `mnu contributor` if you prefer to remain anonymous.

## III. Flexibility and Custom Divisions

While we have defined a standard set of Divisions, contributors are not strictly limited to them. You are welcome to include extra `.DIV` sections if you feel they add value to the page.

However, please keep the following in mind:
*   **Consistency is Key:** Any custom division must adhere to the [Writing Style Guidelines](writing_style.md) and maintain a clean, organized structure.
*   **Avoid Radical Changes:** Do not use a structure that diverges so significantly from the standard that it creates a jarring experience for the reader. The goal is a cohesive feel across all MNU Pages.
