# claude-develop-web-game-skill

A Claude Code skill for building and iterating on browser-based games with a repeatable development and Playwright testing loop.

## Overview

This skill encourages small, testable changes to web games. Each iteration should implement one behavior, run the game, perform controlled actions, observe the result, and adjust based on evidence.

It supports browser game development with HTML, CSS, and JavaScript, including interactive gameplay and automated testing.

## Main Capabilities

- Plan game mechanics and user interactions.
- Implement features incrementally.
- Structure the game around a clear render loop.
- Expose game state for automated inspection.
- Advance time deterministically for repeatable tests.
- Automate gameplay actions with Playwright.
- Inspect screenshots and textual state.
- Review browser console errors.
- Validate input, rendering, and game progression.

## Installation

Clone the repository into the skills directory used by your environment:

```bash
git clone https://github.com/Brajesh31/claude-develop-web-game-skill.git ~/.codex/skills/develop-web-game
```

The Playwright client and action reference should remain at their original relative paths beside the skill instructions.

## Usage

Invoke the skill when building or iterating on a browser game:

```text
/develop-web-game
```

Provide the game concept, current implementation, target behavior, controls, and expected test environment.

## Development Loop

1. Define one small gameplay goal.
2. Implement the smallest change.
3. Ensure the game exposes a single testable canvas or render surface.
4. Expose a state representation for test inspection.
5. Provide a deterministic time-advance hook where practical.
6. Run the Playwright client with short input bursts.
7. Pause and inspect the game state.
8. Review screenshots and console output.
9. Fix observed problems.
10. Repeat until the feature is stable.

## Deterministic Testing

Automated game testing is more reliable when the game exposes predictable hooks for state inspection and time advancement. This reduces flaky tests caused by uncontrolled timing and makes it easier to reproduce gameplay issues.

The repository includes:

- `scripts/web_game_playwright_client.js`: Browser interaction and testing client.
- `references/action_payloads.json`: Supported action payload definitions.
- `assets/`: Game imagery and related visual assets.
- `agents/openai.yaml`: Agent metadata.

## Quality Checklist

- Game starts without console errors.
- Controls behave consistently.
- Input is responsive.
- Time and animation behavior can be tested.
- Game state is inspectable.
- Collision and scoring rules are verified.
- Restart and game-over flows work.
- Screenshots are reviewed at relevant states.
- Performance is acceptable on target devices.

## Repository Contents

- `SKILL.md`: Main web game development workflow.
- `scripts/`: Playwright browser testing client.
- `references/`: Action payload definitions.
- `assets/`: Game assets.
- `agents/`: Agent metadata.
- `README.md`: Development and testing guidance.

## Practical Principle

Do not make many game changes between test runs. Small iterations make regressions easier to identify and fix.
