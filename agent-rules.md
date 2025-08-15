# Warp AI Agent Rules

This file documents all personal rules configured in Warp AI Agent for backup and version control purposes.

## Current Rules (in precedence order)

### 1. Flutter Build: Maximum Logging
**Rule ID:** `3TV5rscJMf2prmDnAeS6Uj`  
**Description:** When running Flutter build commands (flutter build), always use maximum logging by adding --verbose flag to see detailed build process information.

**Usage Examples:**
- `flutter build apk` → `flutter build apk --verbose`
- `flutter build ios` → `flutter build ios --verbose`
- `flutter build web` → `flutter build web --verbose`

### 2. Git Repository Creation: Standard Structure and Documentation
**Rule ID:** `7RWaADsphxCzE61dgrMFEr`  
**Description:** When creating new git repositories, use hyphenated folder names (e.g., Warp-AI-Rules, My-Project-Name) unless explicitly stated otherwise (some tools like Dart packages may require different naming strategies). Always create repositories in ~/Lab_Data/ directory unless specified otherwise. When creating a repository, automatically generate a comprehensive README.md file following GitHub standards with maximum details about the repository/project, and commit it with a proper conventional commit message.

**Naming Convention:**
- Default: `Hyphenated-Names` (e.g., `Warp-AI-Rules`, `Flutter-Todo-App`)
- Location: `~/Lab_Data/Project-Name/`
- Exceptions: Tool-specific requirements (e.g., Dart packages may need underscores)

**Auto-Generated Files:**
- `README.md` with GitHub standards and comprehensive project details
- Initial commit with proper conventional commit message

**Examples:**
- `~/Lab_Data/React-Component-Library/`
- `~/Lab_Data/API-Documentation-Tool/`
- `~/Lab_Data/Flutter-Mobile-App/`

### 3. Scripts: PowerShell Management, Standards, and Execution
**Rule ID:** `BaFMeFC5gJqzfuIcHAn4y1`  
**Description:** When "script" is mentioned, default to PowerShell (.ps1) scripts unless explicitly stated otherwise (e.g., "bash script", "python script"). All PowerShell scripts must be saved to ~/Lab_Data/PowerShell_Scripts/ repository and committed with proper conventional commit messages. Scripts must be compatible with Windows PowerShell 5.1+ and PowerShell Core 7+. Execute PowerShell scripts using pwsh-preview as the preferred executable, with pwsh as fallback if pwsh-preview is not available. This applies to all script execution contexts including direct terminal commands, shell configuration files (zsh/bash), and automated workflows. Always include proper documentation headers with .SYNOPSIS, .DESCRIPTION, .PARAMETER, and .EXAMPLE sections.

**Key Behaviors:**
- "script" = PowerShell (.ps1) by default
- Repository: `~/Lab_Data/PowerShell_Scripts/`
- Execution priority: `pwsh-preview` → `pwsh` (fallback)
- Cross-platform compatibility required
- Comprehensive documentation mandatory

**Usage Examples:**
- "Create a script" → PowerShell script created
- "Run script from zsh" → `pwsh-preview -File script.ps1`
- "Create bash script" → Bash script (explicit override)

### 4. Git Repository: Auto-index Codebases
**Rule ID:** `L3ycnATQa4YAmHVq2oKE5B`  
**Description:** When the user's current working directory (pwd) is within a git repository, automatically treat it as an indexed codebase for search_codebase tool usage, even if not explicitly listed in the codebases configuration.

**Benefits:**
- Automatic codebase search capability when navigating to any git repo
- No need to manually configure codebase indexing for each project

### 5. GitHub Repos: Auto-clone to Lab_Data with gh CLI
**Rule ID:** `qr5mUGwDz6kJSV9WaAZWuD`  
**Description:** When cloning GitHub repositories, always use 'gh repo clone' command instead of 'git clone' to leverage GitHub CLI authentication and features. Clone all repositories to ~/Lab_Data/ directory following the hyphenated naming convention (matching the original repo name). Use 'gh repo list' or 'gh search repos' to find repositories before cloning.

**Key Behaviors:**
- Use `gh repo clone` instead of `git clone`
- Default location: `~/Lab_Data/`
- Maintain original repository naming
- Leverage GitHub CLI authentication

**Usage Examples:**
- `gh repo clone user/repository-name` → `~/Lab_Data/repository-name/`
- Search first: `gh repo list` or `gh search repos`

### 6. Brew: Prefer Head/Source Builds Over Binaries
**Rule ID:** `sHN73DTZ279h6irNiXENJs`  
**Description:** User prefers to install the latest head version/source version (if head not found) of formula/cask using brew, ensuring it is not the binary version. Use https://formulae.brew.sh/formula/X, https://github.com/Homebrew/homebrew-core/blob/*/Formula/*/X.rb (will get actual url from first URL) & https://formulae.brew.sh/api/formula/X.json URLs for more details. Similarly https://formulae.brew.sh/cask/X, https://github.com/Homebrew/homebrew-cask/blob/*/Casks/*/X.rb & https://formulae.brew.sh/api/cask/X.json in the case of Casks. Since the build from source is multi step process, ensure maximum logging from brew.

**Reference URLs for Research:**
- Formulas: `https://formulae.brew.sh/formula/{package-name}`
- Formula Source: `https://github.com/Homebrew/homebrew-core/blob/*/Formula/*/{package-name}.rb`
- Formula API: `https://formulae.brew.sh/api/formula/{package-name}.json`
- Casks: `https://formulae.brew.sh/cask/{package-name}`
- Cask Source: `https://github.com/Homebrew/homebrew-cask/blob/*/Casks/*/{package-name}.rb`
- Cask API: `https://formulae.brew.sh/api/cask/{package-name}.json`

**Installation Priority:**
1. Head version (if available): `brew install --HEAD {package-name}`
2. Source build (if head not available): `brew install --build-from-source {package-name}`
3. Always use verbose logging: `--verbose` flag

### 7. Rule Management: Documentation Sync Workflow
**Rule ID:** `[To be assigned by Warp]`  
**Description:** Whenever the user mentions adding or modifying a Warp AI rule, always remind them to update the agent-rules.md documentation. The workflow is: 1) Help craft the rule name and description, 2) User adds/modifies rule in Warp first, 3) Remind user to say "Update agent-rules.md with the new/modified rule", 4) Update the markdown file and commit with conventional commit message. This ensures documentation stays synchronized with actual Warp rules.

**Workflow Steps:**
1. **Rule Creation/Modification** - Help craft proper rule name and description
2. **Warp Update First** - User adds/modifies rule in Warp interface
3. **Documentation Sync** - Remind user to request markdown update
4. **Commit Changes** - Update agent-rules.md and commit with proper message

**Trigger Phrases:**
- "I want to add a rule for..."
- "New rule: when I do X, you should Y"
- "Let's create a rule that..."
- "Modify the rule for..."

### 8. GitLab Repos: Auto-clone to Lab_Data with glab CLI
**Rule ID:** `[To be assigned by Warp]`  
**Description:** When cloning GitLab repositories, always use 'glab repo clone' command instead of 'git clone' to leverage GitLab CLI authentication and features. Clone all repositories to ~/Lab_Data/ directory following the hyphenated naming convention (matching the original repo name). Use 'glab repo list' or 'glab repo search' to find repositories before cloning.

**Key Behaviors:**
- Use `glab repo clone` instead of `git clone` for GitLab repos
- Default location: `~/Lab_Data/`
- Maintain original repository naming (hyphenated)
- Leverage GitLab CLI authentication
- Works with GitLab.com and self-hosted instances

**Usage Examples:**
- `glab repo clone group/project-name` → `~/Lab_Data/project-name/`
- Search first: `glab repo list` or `glab repo search keyword`
- Self-hosted: Configure with `glab auth login --hostname your-gitlab.com`

## Configured Codebases

### PowerShell_Scripts
**Path:** `/Users/dk/Lab_Data/PowerShell_Scripts`  
**Status:** Indexed and searchable (auto-indexed)

### Warp-AI-Rules
**Path:** `/Users/dk/Lab_Data/Warp-AI-Rules`  
**Status:** Indexed and searchable (auto-indexed)

### scalup-crm-app
**Path:** `/Users/dk/Lab_Data/scalup-crm-app`  
**Status:** Indexed and searchable (explicitly configured)

## Rule Management

- **Location:** Rules are stored in Warp's SQLite database
- **Sync:** Automatically synced with Warp account
- **Backup:** This markdown file serves as version-controlled backup
- **Auto-sync:** Script runs on Warp startup and available via `sync-warp-rules` command
- **Updates:** Use "Update agent-rules.md with current rules" to sync changes

## Last Updated
**Date:** 2025-08-15  
**By:** dk  
**Total Rules:** 8
