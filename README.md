# semrel-test

A test repository for validating [semantic-release](https://semantic-release.gitbook.io/) functionality and GitHub Actions workflow configurations.

## Purpose

This repository serves as a testing ground for semantic release automation, including:

- **Automated versioning** based on conventional commit messages
- **Changelog generation** using commit history
- **GitHub release creation** with release notes
- **Workflow orchestration** with multiple job dependencies
- **Matrix strategy testing** for different checkout scenarios

## What's Tested

### Semantic Release Configuration
- Commit analysis using conventional commits
- Automatic version bumping (major, minor, patch)
- Changelog generation and maintenance
- Git tagging and GitHub release creation

### GitHub Actions Workflow
The repository includes a comprehensive release workflow (`/.github/workflows/release.yml`) that tests:

1. **Before Release Job**: Displays git log for debugging
2. **Release Job**: Executes semantic-release with proper permissions
3. **After Release Job**: Verifies post-release state
4. **Matrix Strategy Job**: Tests different checkout scenarios:
   - Latest commit checkout
   - Empty ref handling
   - No ref specified
   - Tag-based checkout

### Release Configuration
The semantic-release setup (`.releaserc.json`) includes:
- **@semantic-release/commit-analyzer**: Analyzes commits for release type
- **@semantic-release/release-notes-generator**: Creates release notes
- **@semantic-release/changelog**: Maintains CHANGELOG.md
- **@semantic-release/git**: Commits changelog updates
- **@semantic-release/github**: Creates GitHub releases

## Usage

This repository automatically creates releases when commits following conventional commit format are pushed to the `main` branch. The workflow validates that all semantic-release components work correctly together.

## Changelog

See [CHANGELOG.md](./CHANGELOG.md) for the automatically generated release history.