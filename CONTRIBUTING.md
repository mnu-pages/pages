Contributing to MNU Pages

«Our job is not to make things complex, but to make them simple and understandable.»

Hey — if you're here, you're helping make CLI tools easier to understand.
That matters more than you think.

The goal is simple:
Someone with zero knowledge should read a page once and go,
“Oh… I get it now.”

---

The idea behind everything here

We’re not trying to be:

- encyclopedic
- overly technical
- or “funny docs”

We’re trying to be:

- clear
- calm
- and actually helpful

If a page is easy to follow and makes sense quickly, it’s doing its job.

---

Write like you're teaching someone (not documenting)

Don’t write like:

«“commit records changes”»

Write like:

«“commit records the changes you’ve prepared.”»

You’re guiding someone, not labeling things.

---

Always assume the reader knows nothing

Explain everything simply:

- what the tool is
- what each part does

If it feels “too basic”, it’s probably right.

---

What the reader should get

The reader does NOT need to master the tool.

They should:

- understand what it does
- know how to use the main commands
- feel confident trying it

If they can use it after reading → success.

---

Keep it simple, but not empty

“Short and to the point” means:

- no filler
- no repetition
- no useless lines

But still:

- clear explanation
- enough context to understand

---

What “enjoyable” means

Not jokes or hype.

It means:

- smooth to read
- easy to follow
- no confusion

---

Where your page should go

- "cli/" → general CLI tools (git, tar, grep, docker)
- "linux/" → Linux-specific commands
- "windows/" → Windows-specific tools
- "mac/" → macOS-specific tools

If it works everywhere → use "cli/".

---

How to write a page

We use git as a reference example here to show structure.
Your actual page should follow the same pattern.

---

1. Start with DESCRIPTION

Explain:

- what it is
- what it does
- optional: creator or mental model

Example idea:

«“Git is a version control system used to track changes in code.”
“You can think of it like a timeline for your project.”»

---

2. Choose the right commands

Include only fundamental commands:

- 3 to 5 total
- beginner-focused
- part of real workflow

Do NOT:

- add advanced commands
- skip basics

---

3. Show real EXAMPLES

Keep them raw:

git commit -m "save work"

No formatting. No fake placeholders.

---

4. Explain clearly (like a human)

Start with what it does:

«git commit saves the staged changes.»

Then explain parts:

«Here, git is the tool you're using.
commit is the action that records changes.
-m lets you add a message.»

Then give insight:

«This creates a checkpoint you can return to later.»

---

5. Always include best practices

Commands should not just be explained — they should be used correctly.

Add small practical guidance:

- when to run it
- why it matters
- what to do before/after

Example:

- “Run this before committing to check your changes.”
- “Use this after making changes.”

Avoid:

- random tips
- unrelated advice

---

6. End with SUMMARY

Keep it short:

- restate idea
- give one useful habit

Example:

«Git tracks changes and manages project history.
Always check your work with git status before committing.»

---

Formatting (minimal)

- "**bold**" → commands, important actions
- "__underline__" → flags, arguments, key terms

Rules:

- don’t mix formatting
- don’t overuse it
- don’t format everything
- never format examples

---

Spacing

- keep it tight
- no extra blank lines
- no clutter

---

Before submitting

Ask:

- Can a beginner understand this?
- Can they use the command now?
- Did I include best practices?
- Does it read smoothly?

---

How to submit your work

We use Pull Requests (PRs) to add new pages.
If you've never done this before, here is the simple path:

1. **Fork** this project to your own account.
2. **Create a branch** for your new page (e.g., `git checkout -b add-grep-page`).
3. **Write your page** in the correct folder using the rules above.
4. **Commit your work** using our specific format: `<title>(scope): <description>`.

**Allowed Titles:**
- `add`: for new pages.
- `fix`: for correcting errors.
- `refine`: for improving tone or clarity.
- `meta`: for changes to project files or guidelines.

**Allowed Scopes:**
- Use the folder name: `cli`, `linux`, `windows`, `mac`.
- Use `core` for project-wide files (like README or this file).

*Example:* `add(cli): add grep page`

5. **Push your changes** and open a **Pull Request**.

We will review your page, maybe suggest some tweaks to the tone, and then merge it in.

---

Final note

You don’t need to teach everything.
You need to make the basics clear enough to use — and use correctly.

That’s it.
