# Directory Selection Guidelines

To keep the MNU Pages database organized, we follow the **"Source vs. System"** rule when deciding where to place a new `.mn` file.

## I. The "Source vs. System" Rule

### A. The `cli/` Folder (Universal / Third-Party Tools)
Think of this as the **"Developer’s Toolbox."** Use this directory if the tool is a standalone "Product" or "Protocol" that is designed to work identically across multiple operating systems.

*   **The Test:** If you run this command on Linux, macOS, or Windows (via WSL/PowerShell), are the core flags and outputs exactly the same?
*   **Examples:**
    *   **Protocols/Networking:** `ssh`, `scp`, `curl`, `wget`.
    *   **Version Control:** `git`.
    *   **Runtimes/Engines:** `node`, `python`, `docker`.
    *   **Multi-platform Apps:** `vim`, `ffmpeg`, `rclone`.

### B. OS-Specific Folders (`linux/`, `mac/`, `windows/`)
Think of these as the **"System's Backbone."** Use these directories if the command is native to the operating system or is used to manage the specific environment.

*   **The Test:** 
    1. Is it used to manage the OS itself (e.g., package managers, service controllers)?
    2. Is it a core utility (like `ls` or `grep`)? Note: While POSIX tools exist on many systems, their implementations (GNU vs. BSD) often have different flags, so they are **not** universal.
*   **Examples:**
    *   `linux/`: `apt`, `systemctl`, `ls`, `grep`, `ip`, `cd`, `pwd`, `sudo`.
    *   `mac/`: `brew`, `pbcopy`, `mdfind`, `diskutil`.
    *   `windows/`: `powershell`, `wsl`, `dir`, `chkdsk`.

---

## II. Quick Decision Flowchart

1.  **Is it a system-wide management tool?** (e.g., `apt`, `brew`, `systemctl`)
    *   **Yes** -> Specific OS Folder.
2.  **Is it a core shell/POSIX utility?** (e.g., `ls`, `cd`, `grep`)
    *   **Yes** -> `linux/` (as the primary reference for GNU/Linux behavior).
3.  **Is it a third-party application or a universal protocol?** (e.g., `git`, `ssh`, `docker`)
    *   **Yes** -> `cli/`.

## III. When in Doubt

If a command exists on multiple platforms but its flags or behavior vary significantly, prioritize the **Linux version** in the `linux/` folder. If a truly universal standard exists that spans all major platforms without deviation, move it to `cli/`.
