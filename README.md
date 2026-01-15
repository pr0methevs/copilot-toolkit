# copilot-toolkit
A curated collection of GitHub Copilot instructions, prompts, agents, and experimental workflows. A sandbox for exploring and refining Copilot capabilities while documenting ideas, patterns, and prototypes in a living knowledge base.


## Setup

Guide on settng instructions/rules and prompts/workflows in different IDEs


### Visual Studio Code

Global Instructions and Prompts: These are typically stored in user configuration directories, not within the workspace.

Windows: `%APPDATA%\Code\User`\` 
- (e.g., `C:\Users\YourName\AppData\Roaming\Code\User\`).​

Linux: `~/.config/Code/User/` 
- (e.g., `/home/yourname/.config/Code/User/`).​

Workspace Instructions and Prompts: These are stored in the workspace directory, usually under `.github/instructions` or similar, and are not global.​


### Intellij 

Global Instructions and Prompts: IntelliJ stores global (user-specific) configuration files in the user's home directory.

Windows: `%USERPROFILE%\.IntelliJIdea<version>\config`
- (e.g., `C:\Users\YourName\.IntelliJIdea2025.2\config)`.​

Linux: `~/.config/JetBrains/IntelliJIdea<version>` or `~/.IntelliJIdea<version>/config`
- (e.g., `/home/yourname/.config/JetBrains/IntelliJIdea2025.2/config`).​

Workspace (Project) Instructions and Prompts: These are stored in the `.idea` folder within the project directory and are not global.​



### Antigravity:

Both Rules and Workflows can be applied globally or per workspace and saved to the following locations:

- Global rule: `~/.gemini/GEMINI.md`
- Global workflow: `~/.gemini/antigravity/global_workflows/global-workflow.md`
- Workspace rules: `your-workspace/.agent/rules/`
- Workspace workflows: `your-workspace/.agent/workflows/`

#### Breaking down Rule Files: `@ Mentions`

You can reference other files using @filename in a Rules file. 

- If filename is a relative path, it will be interpreted relative to the location of the Rules file. 
- If filename is an absolute path, it will be resolved as a true absolute path, otherwise it will be resolved relative to the repository. 
  - For example, @/path/to/file.md will first attempt to be resolved to /path/to/file.md, and if that file does not exist, it will be resolved to workspace/path/to/file.md.