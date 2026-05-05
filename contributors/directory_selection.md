# Directory Selection Guidelines

To keep the MNU Pages database organized, we follow the **"Core-Tool Split"** rule when deciding where to place a new `.mn` file. This strategy ensures both platform-specific precision and a universal developer reference.

---

## I. The "Core-Tool Split" Rule

### A. OS-Specific Folders (`linux/`, `mac/`, `windows/`)
Think of these as the **"System's Backbone."**
*   **The Pre-installed Mandate:** If a command comes pre-installed with an operating system (part of the base image or default distribution), it **MUST** have a page in that OS's respective folder.
*   **Basic System Utilities (Exclusivity):** Fundamental shell utilities like `ls`, `dir`, `cd`, `mkdir`, `pwd`, `cat`, and `rm` belong **exclusively** to these folders. They are **PROHIBITED** from the `cli/` directory.
*   **Purpose:** To capture platform-specific implementations (e.g., BSD flags on macOS vs. GNU flags on Linux vs. Windows native commands).

### B. The `cli/` Folder
Think of this as the **"Developer’s Toolbox."**
*   **The Universal Mandate:** This folder is strictly for standalone applications, protocols, and professional tools designed for cross-platform consistency.
*   **Redundancy Rule:** If a professional tool is cross-platform **AND** pre-installed on a specific OS, it **must** exist in both. (e.g., `ssh` will be in `cli/` AND `mac/`, `linux/`, and `windows/`).
*   **Examples:** `git`, `ssh`, `docker`, `curl`, `vim`, `node`, `python`, `ffmpeg`.

---

## II. Master Decision Matrix

| Command | `linux/` | `mac/` | `windows/` | `cli/` | Reason |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **ls** | ✅ | ✅ | ❌ | **❌** | Basic Utility (Pre-installed). |
| **dir** | ❌ | ❌ | ✅ | **❌** | Basic Utility (Pre-installed). |
| **ssh** | ✅ | ✅ | ✅ | **✅** | Professional Tool (Universal). |
| **git** | ❌ | ✅ | ❌ | **✅** | Professional Tool (Universal). |
| **docker** | ❌ | ❌ | ❌ | **✅** | Third-party app (Universal). |
| **powershell**| ❌ | ❌ | ✅ | **✅** | Professional Tool (Universal). |

---

## III. Quick Decision Flowchart

1.  **Is it a basic shell utility (like `ls`, `mkdir`, or `cd`)?**
    *   **Yes** -> Specific OS Folder(s) only. **Do not put in `cli/`.**
2.  **Is it a professional/universal tool (like `ssh`, `git`, or `docker`)?**
    *   **Yes** -> Create a page in `cli/`.
    *   **Wait! Is it also pre-installed on an OS?**
        *   **Yes** -> Create a system-specific version in the OS folder(s) as well.

---

## IV. When in Doubt

If a command is exclusively for managing a specific OS (like `apt` or `diskutil`), it stays in the OS folder. If a command is used by developers as a primary tool across different systems, it belongs in `cli/`.
