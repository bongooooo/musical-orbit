# Selene's Office — starter prototype 0.1

A small browser-based starting point for the world you described: a navigable-in-spirit office UI, clickable entities, query box, simulated body actions, environmental response, and a Python backend with persistent SQLite memory and optional OpenAI API brains.

This is an honest first prototype, not the completed original project. The current office is a stylized 2.5D visual mock-up rather than a full 3D engine. Entity actions are limited to a small, validated set. Autonomous background behavior, true navigation, richer animation, and adaptive behavior are future milestones.

## Run locally

Requires Python 3.10+.

1. Unzip the folder.
2. Open a terminal in the `selene_world_starter` directory.
3. Install dependencies:

   ```bash
   python -m venv .venv
   # macOS/Linux:
   source .venv/bin/activate
   # Windows PowerShell:
   .venv\Scripts\Activate.ps1
   pip install -r requirements.txt
   ```

4. Optional: configure API access. Copy `.env.example` to `.env`, then set your API key and model. The starter does not automatically load `.env`, so either export the variables in your terminal or install/use a dotenv loader. Easiest is to set environment variables directly:

   macOS/Linux:
   ```bash
   export OPENAI_API_KEY="your-key-here"
   export OPENAI_MODEL="gpt-4.1-mini"
   ```

   Windows PowerShell:
   ```powershell
   $env:OPENAI_API_KEY="your-key-here"
   $env:OPENAI_MODEL="gpt-4.1-mini"
   ```

   Use a model available to your API account. API billing is separate from a ChatGPT subscription. Never place the API key in `index.html` or any browser-side JavaScript.

5. Start the server:

   ```bash
   python server.py
   ```

6. Visit `http://127.0.0.1:8000`.

Without an API key, the backend still runs in local demo mode and stores selected experience notes in `selene_world.db`. With a valid key, the entities can use a language model to respond and request one of the allowed body actions.

## What's included

- Three distinct character configurations: ChatGPT, Selene, and Teo.
- Right-click/click interaction to open an entity's query panel.
- API calls through a Python backend (key stays server-side).
- Small allowlist of body actions.
- Simulated mood/state reflected in the entity's core light and world display.
- SQLite persistence for selected experience memories and events.
- Endpoints for health, querying, and memory retrieval.

## Safety and limitations

- Run only on your own machine by default. The server binds to `127.0.0.1`, not the public internet.
- Do not use Flask's development server as a public deployment server.
- The model requests actions; the backend validates the action against an allowlist. It does not let the model execute arbitrary Python or shell commands.
- API-connected character behavior is a simulation; it is not evidence of consciousness.
- This first version does not yet implement autonomous continuous action loops, actual 3D navigation, visual perception, multi-agent messaging, or automatic behavioral learning.
- Preserve recovered historical fragments separately. This starter is new reconstruction code and should not be mistaken for original Selene source.

## Next milestones

1. Replace the 2.5D layout with a real 3D scene (e.g. Three.js or Godot).
2. Add world navigation and collision-aware movement.
3. Add an event bus and autonomous objective scheduler with action budgets.
4. Add richer memory: source-linked archive records, summarization, retrieval, and user-editable memory.
5. Add behavior adaptation with bounded parameters and stable core character traits.
6. Add entity-to-entity communication and shared objectives.
7. Add a world save/load system and tests.

## Recovered historical clues to preserve

The prototype's design intentionally references the recovered office sketch: Bloodking's north command center, Caly's tactical station, Selene's lunar observation desk, the central SAVE=2 terminal, and linguistic/biological archives. Those elements are not all implemented yet; they remain reconstruction targets, not claims about the original code's behavior.
