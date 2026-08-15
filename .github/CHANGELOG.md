<!-- markdownlint-configure-file { "MD024": false } -->

# Changelog

## v1.4

Upgrade Node Setup, Pnpm Setup and Cache Action.

## v1.3

### What's New

Upgrade Node Setup workflow to version 5.

## v1.2

### What's Breaking

Pnpm will no longer install dependencies during installation step. This was in effect since **v1.1**.

## v1.1

### What's New

Pnpm installation and setup is prepended before Node.js setup and utilizes Open Source `pnpm/action-setup` workflow.

### Improvements

The workflow can now distinguish between Classic Yarn and Yarn Berry (v2+) and execute `install` command with appropriate arguments. _(Reference: #2)_

### Fixes

Add all required input fields for `pnpm/action-setup` workflow. Despite declaring fields _optional_, it still requires them during action execution.

## v1.0

Initial release for the Composite Action to setup workspace for Open Source JavaScript/TypeScript projects.
