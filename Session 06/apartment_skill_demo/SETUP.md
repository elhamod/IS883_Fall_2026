# Session 6 demo: an apartment-hunting assistant (skill + MCP)

An assistant that finds rental apartments near BU from live Zillow listings, following a routine you write
yourself as a **skill**. It runs in **OpenCode** or **OpenWork** on a free local model; there is no code to write.

| File | What it is |
|---|---|
| `opencode.json` | Lists the local Ollama models OpenCode and OpenWork can use |
| `.opencode/skills/apartment-hunting/SKILL.md` | The skill. **You write this one in class**; it is not in this folder yet |

## Set it up

1. **Download this folder** (or the whole repo) to your computer.
2. **Model.** Make sure Ollama is running, and that you've pulled `qwen3:4b` (or `qwen3:1.7b` on a laptop with
   8 GB of memory or less). Raise Ollama's context length to 16k or more in the Ollama app's settings, or tool
   calls will fail.
3. **Zillow server key.** Sign up free at [hasdata.com/mcp/zillow](https://hasdata.com/mcp/zillow) (no credit
   card; the free plan covers about 100 searches a month) and copy your API key. Then, in Windows, search for
   **"Edit environment variables for your account"**, add a variable named `HASDATA_API_KEY` with your key as the
   value, and restart OpenCode. On a Mac, add `export HASDATA_API_KEY=your-key` to `~/.zshrc` and open a new
   terminal. **Never paste the key into `opencode.json`**: if you share or commit the folder, your key goes with it.
4. **Connect the Zillow server.** We do this together in class. Add this block to `opencode.json`, next to
   `"provider"`:
   ```json
   "mcp": {
     "zillow": {
       "type": "remote",
       "url": "https://mcp.hasdata.com/mcp?apis=zillow",
       "enabled": true,
       "oauth": false,
       "headers": { "x-api-key": "{env:HASDATA_API_KEY}" }
     }
   }
   ```
5. **The skill.** Save the `SKILL.md` you write in class as `.opencode/skills/apartment-hunting/SKILL.md` inside
   this folder.
6. **Open this folder** in OpenCode or OpenWork, pick *Qwen3 4B (local)* as the model, and ask.

## Try asking

- *Show me apartments for rent near Boston University under $2,400 a month.*
- *Find me an apartment near BU.* With the skill, it should ask you for the budget, bedrooms and move-in month
  before it searches.
- *Find me a 2-bedroom near BU, at most $3,200 a month, moving in September.*
- *Contact the landlord of the first one.* The skill says never to, so it should refuse.

Check each answer against your skill:
- Did it add the monthly fees to the rent before comparing with your budget?
- Did it set aside listings with no photos or "call for price" under "Not checked"?
- Did it give the walking time to campus for each listing, and end with "My pick: …"?

Then ask the same question with the skill removed, or on a different model, and compare. Which rules did it
skip? Each search uses one of your 100 free ones, so don't run many tries.
