# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Docker environment setup for running Claude Code with various development tools. The project creates a containerized development environment based on Arch Linux with comprehensive tooling for multiple programming languages and development workflows.

## Architecture

The repository contains:
- **Dockerfile**: Main container definition with Arch Linux base, development tools (Python, Node.js, Go, Rust), and Claude Code installation
- **README.md**: Basic usage instructions for running the Docker container

The container is designed to:
- Provide a consistent development environment across different host systems
- Include multiple language runtimes and package managers
- Run Claude Code with custom API endpoint configuration
- Mount the host workspace directory for file persistence

## Common Commands

### Building and Running
```bash
# Build the Docker image
docker build -t any-router-claude .

# Run the container with workspace mounted
docker run -it --rm -v $(pwd):/workspace kilerd/any-router-claude

# Run container with custom environment variables
docker run -it --rm -v $(pwd):/workspace -e ANTHROPIC_AUTH_TOKEN=your_token kilerd/any-router-claude
```

### Development Tools Available in Container
- **Languages**: Python, Node.js (with npm/pnpm/yarn), Go, Rust
- **Utilities**: git, gh (GitHub CLI), ripgrep, fd, ast-grep, jq
- **Editors**: vim, neovim

## Configuration

The container sets:
- `ANTHROPIC_BASE_URL` to `https://anyrouter.top` (custom API endpoint)
- `ANTHROPIC_AUTH_TOKEN` placeholder (requires actual token)
- Working directory as `/workspace`
- Runs with `--dangerously-skip-permissions` flag

## Key Features

- Multi-language development support
- Pre-installed Claude Code CLI
- Custom API router configuration
- Non-root user setup for security
- Comprehensive development toolchain