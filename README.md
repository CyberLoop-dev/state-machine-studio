# State Machine Studio

![Status](https://img.shields.io/badge/status-early%20prototype-8b9cf7?style=flat-square)
![Dependencies](https://img.shields.io/badge/dependencies-zero%20external-28a6a1?style=flat-square)
![Maintainer](https://img.shields.io/badge/maintained-by%20CyberLoop-151b2c?style=flat-square)

State Machine Studio is a compact workbench for sketching finite-state machines and trying event sequences against them. It makes state transitions explicit before they become application code.

## The problem

Stateful workflows are often described in prose, where missing or invalid transitions are easy to overlook. A small interactive model makes the rules easier to inspect.

## Features

- Define a comma-separated set of states.
- Add transitions with source, event, and destination.
- Send an event to the current state and see whether it is accepted.
- Inspect the transition list and current-state history.
- Runs locally in a single browser page.

## Design and architecture

The page stores states and transitions in JavaScript arrays. The simulator looks up a transition matching the current state and event, then updates the current state or reports that no rule exists.

### Project structure

~~~text
state-machine-studio/
|-- README.md
|-- index.html
~~~

The starter implementation is intentionally small. Extend it in focused steps and keep the documented behavior aligned with the code.

## Requirements and setup

Open index.html in a modern browser. No build tools or external services are required.

## Quick start

Start with idle,running,done. Add idle + start -> running and running + finish -> done. Select an event and press Send event.

## Example

When the current state is idle, sending start follows the matching transition to running. Sending finish from idle is rejected because no such transition is defined.

## Current scope

This repository is an initial, working starter rather than a claim of production readiness. Review the code and test it in your own environment before relying on it in a workflow. Any feature not listed above is not implied to exist.

## Roadmap

- [ ] Add a visual node-and-edge canvas.
- [ ] Export and import machine definitions as JSON.
- [ ] Add deterministic test-sequence playback.

## Contributing

Bug reports, small improvements, documentation fixes, and focused pull requests are welcome. Include reproducible steps for issues and explain the expected behavior. Please avoid committing secrets, private data, or large generated files.

## License

No license file has been selected yet. Until a license is added, do not assume that the code may be redistributed or used outside the permissions granted by GitHub's default terms.
