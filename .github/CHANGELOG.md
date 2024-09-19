# Changelog

## v1.0

Initial release for the Composite Action to setup workspace for Open Source JavaScript/TypeScript projects.

## v1.1

### What's New

Pnpm installation and setup is prepended before Node.js setup and utilizes Open Source `pnpm/action-setup` workflow.

### Improvements

The workflow can now distinguish between Classic Yarn and Yarn Berry (v2+) and execute `install` command with appropriate arguments. _(Reference: #2)_
