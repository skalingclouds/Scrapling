# Scrapling Development Patterns

> Auto-generated skill from repository analysis

## Overview

Scrapling is a Python web scraping library that focuses on stealth capabilities and anti-detection mechanisms. The codebase emphasizes multilingual documentation support, browser automation with stealth features, and AI integration through MCP (Model Context Protocol) server functionality. Development follows conventional commit patterns with a strong emphasis on documentation maintenance and version release coordination.

## Coding Conventions

### File Naming
- Use `snake_case` for all Python files and directories
- Test files follow `*.test.*` pattern
- Documentation files use language suffixes: `README_AR.md`, `README_CN.md`, etc.

### Import Style
```python
# Mix of absolute and relative imports
from scrapling.engines._browsers._stealth import StealthConfig
from .toolbelt.navigation import NavigationHandler
import scrapling.core.ai as ai_core
```

### Commit Style
- Use conventional commit prefixes: `docs:`, `fix:`, `feat:`, `test:`, `ops:`, `build:`, `style:`
- Keep commit messages around 45 characters
- Example: `feat: add cloudflare bypass mechanism`

## Workflows

### Multilingual Documentation Update
**Trigger:** When documentation content needs to be synchronized across all language variants
**Command:** `/update-docs`

1. Update the main `README.md` with new content or changes
2. Synchronize changes across all language-specific documentation:
   - `docs/README_AR.md` (Arabic)
   - `docs/README_CN.md` (Chinese)
   - `docs/README_DE.md` (German)
   - `docs/README_ES.md` (Spanish)
   - `docs/README_JP.md` (Japanese)
   - `docs/README_RU.md` (Russian)
3. Update `docs/index.md` to reflect any structural changes
4. Commit with: `docs: update multilingual documentation`

### Version Release Preparation
**Trigger:** When releasing a new version of the package
**Command:** `/prepare-release`

1. Update version number in `pyproject.toml`:
   ```toml
   [tool.poetry]
   version = "x.y.z"
   ```
2. Update version in `scrapling/__init__.py`:
   ```python
   __version__ = "x.y.z"
   ```
3. Update `setup.cfg` with new version metadata
4. Update documentation to reflect version changes
5. Commit with: `build: bump version to x.y.z`

### Stealth Browser Enhancement
**Trigger:** When enhancing anti-detection features for web scraping
**Command:** `/enhance-stealth`

1. Modify stealth configuration in `scrapling/engines/_browsers/_stealth.py`:
   ```python
   class StealthConfig:
       def update_fingerprint_protection(self):
           # Add new stealth mechanisms
   ```
2. Update JavaScript bypass scripts in `scrapling/engines/toolbelt/bypasses/`:
   - Add new bypass techniques
   - Update existing detection evasion methods
3. Enhance navigation logic in `scrapling/engines/toolbelt/navigation.py`
4. Test stealth capabilities against common detection systems
5. Commit with: `feat: improve browser stealth capabilities`

### GitHub Actions Maintenance
**Trigger:** When updating GitHub Actions workflows for compatibility or improvements
**Command:** `/update-workflows`

1. Review and update workflow files:
   - `.github/workflows/code-quality.yml`
   - `.github/workflows/docker-build.yml`
   - `.github/workflows/release-and-publish.yml`
   - `.github/workflows/tests.yml`
2. Upgrade action versions to latest stable releases
3. Test workflow compatibility with current dependencies
4. Update environment variables and secrets as needed
5. Commit with: `ops: update github actions workflows`

### MCP Server Development
**Trigger:** When working on AI integration features or MCP server improvements
**Command:** `/update-mcp`

1. Update AI core functionality in `scrapling/core/ai.py`:
   ```python
   class AIHandler:
       def process_scraping_context(self):
           # Enhanced AI integration logic
   ```
2. Modify MCP server configuration in `server.json`:
   ```json
   {
     "mcpServers": {
       "scrapling": {
         "command": "python",
         "args": ["-m", "scrapling.mcp"]
       }
     }
   }
   ```
3. Update MCP documentation in `docs/ai/mcp-server.md`
4. Test AI integration endpoints
5. Commit with: `feat: enhance mcp server functionality`

## Testing Patterns

- Test files use the pattern `*.test.*`
- Testing framework is project-specific (not detected as standard framework)
- Tests should cover stealth functionality and bypass mechanisms
- Include integration tests for browser automation features

```python
# Example test structure
def test_stealth_functionality():
    # Test anti-detection mechanisms
    pass

def test_bypass_cloudflare():
    # Test specific bypass capabilities
    pass
```

## Commands

| Command | Purpose |
|---------|---------|
| `/update-docs` | Synchronize documentation across all supported languages |
| `/prepare-release` | Update version numbers and prepare for package release |
| `/enhance-stealth` | Improve browser stealth and anti-detection capabilities |
| `/update-workflows` | Maintain and upgrade GitHub Actions CI/CD workflows |
| `/update-mcp` | Develop MCP server functionality and AI integration features |