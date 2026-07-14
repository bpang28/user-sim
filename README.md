# Cohort Sim

A single-file web app that simulates how a defined audience will interact with a product. Describe the product and the audience, and it generates a cohort of distinct synthetic personas, walks each one through the product's core interaction flow via the Claude API, and synthesizes common friction points, outlier issues, and ranked design changes.

## How it works

1. **Persona generation.** One API call produces the cohort as structured JSON, with secondary traits (patience, prior experience, condition severity, context of use) varied so the cohort reflects realistic within-group diversity.
2. **One walkthrough call per persona.** Each persona gets a dedicated call so friction points stay tied to that persona's specific traits (e.g. "small tap targets + arthritis") instead of generic UX platitudes.
3. **Synthesis.** A final call aggregates the walkthroughs into common friction points with cohort fractions, persona-specific outlier issues, and a ranked list of design or accessibility changes.

## Running it

- **Inside claude.ai:** open the file as an artifact and leave the API key field blank. Calls are authenticated automatically.
- **Anywhere else** (local file, GitHub Pages, your own hosting): paste an Anthropic API key into the key field in the UI. The key stays in the page and is sent only to api.anthropic.com. Get a key at console.anthropic.com. Usage bills your Console account at standard API rates.

Never commit an API key to this repository or hardcode one into the HTML.

## Caveat

Results are simulated estimates based on modeled reasoning, not observed behavioral data. Use them to generate hypotheses for real user testing with the actual population, not as a substitute for it.

## Stack

Plain HTML, CSS, and JavaScript in one file. No build step, no dependencies beyond marked.js (loaded from a CDN) for rendering Markdown results.
