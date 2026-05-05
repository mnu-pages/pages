# Writing Style Guidelines for .mn Files

This document provides guidelines for the linguistic style and content of `.mn` pages. Consistent writing is essential for delivering clear, concise, and helpful documentation, ultimately enhancing the user's understanding and experience.

## I. General Writing Principles

-   **Active and Factual Tone:** Use the present indicative tense. Treat the content as a technical dictionary, stating facts directly.
    -   **Bad:** `Create a directory.` (Imperative)
    -   **Good:** `Creates a directory.` (Present Indicative)
-   **Conciseness and Clarity:** Eliminate filler words (e.g., "simply," "just," "actually") and avoid hyperbolic or subjective language. Get straight to the point with factual descriptions.
    -   **Bad:** `Simply lists the actual files easily.`
    -   **Bad:** `This amazing tool dramatically boosts your productivity.`
    -   **Good:** `Lists the files in the current directory.`
    -   **Good:** `This tool displays file information.`

## II. Division-Specific Writing Guidelines

### A. The Description Division

-   **Purpose:** Explain what the tool does in a formal way.
-   **Length:** Keep it brief, with a maximum of 5 wrapped lines.
-   **Structure:** Do not use blank lines within the division.

### B. The Alias Division

-   **Purpose:** List all common command aliases for the tool.

### C. The TLDR Division

-   **Purpose:** Provide core command examples that cover 80-90% of common use cases.
-   **Line 2 (The Intent):** Write a complete sentence explaining the command's purpose.
-   **Line 3 (The Legend):** Provide brief definitions for variables, flags, or subcommands. Avoid redundancy—if the Intent line already explains an element, do not repeat it here.

### D. The Summary Division

-   **Purpose:** Provide a helpful tip, best practice, or good habit related to the tool.
-   **Length:** Maximum 5 wrapped lines.
-   **Structure:** Do not use blank lines within the division.
