# Contributing to MNU Pages

Welcome! We are thrilled that you want to contribute to the MNU Pages repository. Our goal is to make terminal documentation less intimidating and more accessible for everyone.

To maintain a high-quality experience, all contributions must adhere to the **mnu standard**.

---

## 1. The MNU Standard

The **mnu standard** is a combination of three core pillars. Before you start, please familiarize yourself with each:

*   [**Formatting Style**](contributors/formatting_style.md): The structural and syntactical rules for `.mn` files.
*   [**Writing Style**](contributors/writing_style.md): The tone, tense, and linguistic guidelines.
*   [**Commit Style**](contributors/commit_style.md): The structured format for your git commit messages.

---

## 2. Choosing the Right Directory

We follow the **"Source vs. System"** rule to keep the database organized. For a detailed breakdown, see the [**Directory Selection Guide**](contributors/directory_selection.md).

*   `cli/`: Universal tools, protocols, and third-party apps (e.g., `git`, `ssh`, `docker`).
*   `linux/`: Linux-specific tools and core POSIX utilities (e.g., `apt`, `ls`, `sudo`).
*   `mac/`: Utilities specific to macOS (e.g., `brew`, `pbcopy`).
*   `windows/`: Tools specific to the Windows environment (e.g., `powershell`, `wsl`).
*   `examples/`: **Do not add new pages here.** This folder is strictly for reference templates.

---

## 3. Local Testing

Before submitting your page, you must verify that it renders correctly. We recommend using the **C Client** for testing, as it is more battle-tested for edge cases, though the **Node.js** client is also a solid option.

### Using the C Client (Recommended)
You can find the C client repository here: [https://github.com/mnu-pages/mnu-client](https://github.com/mnu-pages/mnu-client). Follow the instructions in that repository to build and run it against your `.mn` file.

### Using the Node.js Client
1.  **Install the client:** `npm i -g mnu-pages`
2.  **Run your page:** `mnu run path/to/your-file.mn`

### What to check for:
*   **Visual Alignment:** Does the title appear centered and underlined?
*   **Highlighting:** Are variables correctly underlined (`__`) and commands correctly bolded (`**`)?
*   **TLDR Logic:** Is each entry exactly 3 lines? Is there exactly one blank line between entries?
*   **Errors:** Ensure the `mnu` client doesn't report any parsing failures.

---

## 4. How to Contribute

Follow these steps to submit your contribution:

1.  **Fork the Repository:** Click the 'Fork' button on GitHub to create your copy.
2.  **Clone your Fork:** `git clone https://github.com/your-username/pages.git`
3.  **Create a Branch:** `git checkout -b add-command-name`
4.  **Write the Page:** Create your `.mn` file following the [Formatting](contributors/formatting_style.md) and [Writing](contributors/writing_style.md) style guides. Use the [examples/](examples/) folder as a baseline.
5.  **Test Locally:** Run `mnu run` to verify your work.
6.  **Commit Changes:** Use the structured format defined in the [Commit Style Guide](contributors/commit_style.md).
7.  **Push and PR:** Push to your fork and open a Pull Request against our `main` branch.

---

## 5. The PR Review Process

Once you open a Pull Request:
*   **Automated Checks:** Our CI may run basic syntax checks.
*   **Human Review:** A maintainer will review your page for technical accuracy and adherence to the mnu standard.
*   **Feedback:** We might request minor changes. Don't worry—we're here to help you get your PR merged!
*   **Merge:** Once approved, your page will be available to all MNU users!

---

## 6. AI-Generated Code Policy

We welcome AI-assisted contributions, provided that:
1.  The output strictly follows the **mnu standard**.
2.  You have personally reviewed the content for technical accuracy, grammar, and helpfulness.

---

Thank you for helping us make the terminal a better place!
