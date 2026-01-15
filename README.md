# copilot-toolkit
A curated collection of GitHub Copilot instructions, prompts, agents, and experimental workflows. A sandbox for exploring and refining Copilot capabilities while documenting ideas, patterns, and prototypes in a living knowledge base.


## Setup

Guide on setting instructions/rules and prompts/workflows in different IDEs.

### Visual Studio Code

#### Globals
Custom instructions, prompts, and skills stored globally are available across all workspaces.

**Instructions:**
- Windows: `%APPDATA%\Code\User\`
- macOS/Linux: `~/.config/Code/User/`

**Prompts:**
- Windows: `%APPDATA%\Code\User\`
- macOS/Linux: `~/.config/Code/User/`

**Skills:**
- Windows: `%USERPROFILE%\.copilot\skills\`
- macOS/Linux: `~/.copilot/skills/`
- Alternative: `~/.claude/skills/` (Copilot coding agent and GitHub Copilot CLI)

#### Workspace
Custom instructions, prompts, and skills scoped to a specific project or workspace.

**Instructions:**
- `.github/instructions/` or `.claude/instructions/`

**Prompts:**
- `.github/prompts/` or `.claude/prompts/`

**Skills:**
- `.github/skills/` or `.claude/skills/`

---

### IntelliJ

#### Globals
Custom instructions, prompts, and skills stored globally are available across all projects.

**Instructions:**
- Windows: `%USERPROFILE%\.IntelliJIdea<version>\config`
- macOS/Linux: `~/.config/JetBrains/IntelliJIdea<version>` or `~/.IntelliJIdea<version>/config`

**Prompts:**
- Windows: `%USERPROFILE%\.IntelliJIdea<version>\config`
- macOS/Linux: `~/.config/JetBrains/IntelliJIdea<version>` or `~/.IntelliJIdea<version>/config`

**Skills:**
- Windows: `%USERPROFILE%\.intellij\skills\`
- macOS/Linux: `~/.intellij/skills/`

#### Workspace
Custom instructions, prompts, and skills scoped to a specific project.

**Instructions:**
- `.idea/instructions/` or `.claude/instructions/`

**Prompts:**
- `.idea/prompts/` or `.claude/prompts/`

**Skills:**
- `.idea/skills/` or `.claude/skills/`

---

### Antigravity

#### Globals
Custom rules, workflows, and skills available globally across all workspaces.

**Instructions (Rules):**
- `~/.gemini/GEMINI.md`

**Prompts (Workflows):**
- `~/.gemini/antigravity/global_workflows/`

**Skills:**
- `~/.gemini/antigravity/skills/{skill_folder}/`

#### Workspace
Custom rules, workflows, and skills scoped to a specific workspace.

**Instructions (Rules):**
- `{workspace_root}/.agent/rules/`

**Prompts (Workflows):**
- `{workspace_root}/.agent/workflows/`

**Skills:**
- `{workspace_root}/.agent/skills/{skill_folder}/`

#### Breaking down Rule Files: `@ Mentions`

You can reference other files using `@filename` in a Rules file.

- If filename is a relative path, it will be interpreted relative to the location of the Rules file.
- If filename is an absolute path, it will be resolved as a true absolute path, otherwise it will be resolved relative to the repository.
  - For example, `@/path/to/file.md` will first attempt to be resolved to `/path/to/file.md`, and if that file does not exist, it will be resolved to `workspace/path/to/file.md`.
