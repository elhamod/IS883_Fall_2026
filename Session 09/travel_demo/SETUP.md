# Session 9 demo: a business-travel assistant (RAG + MCP)

An assistant that answers questions from a real travel policy and looks up live hotel prices. It runs in
**OpenCode** or **OpenWork**; there is no code to write.

| File | What it is |
|---|---|
| `UCF_Travel_Manual.pdf` | The University of Central Florida Travel Manual (revised October 2026), a public document: [source](https://fa.ucf.edu/wp-content/uploads/sites/2/Travel_Manual.pdf) |
| `UCF_Travel_Manual.txt` | The same manual as plain text, with page markers, so the assistant can search it (the **RAG** part) |
| `AGENTS.md` | The assistant's instructions. OpenCode and OpenWork read this file automatically |
| `opencode.json` | Connects HasData's Google Hotels MCP server (the **MCP** part) and picks the model |

## Set it up

1. **Download this folder** (or the whole repo) to your computer.
2. **Model.** In OpenCode or OpenWork, connect the **Google** provider with your Gemini API key (the same key
   you use in Colab). If you prefer, pick another model from the model list instead.
3. **Hotel server key.** Sign up free at [hasdata.com](https://hasdata.com/) (no credit card; the free plan covers
   about 100 hotel searches a month) and copy your API key. Then, in Windows, search for **"Edit environment
   variables for your account"**, add a variable named `HASDATA_API_KEY` with your key as the value, and restart
   OpenCode. On a Mac, add `export HASDATA_API_KEY=your-key` to `~/.zshrc` and open a new terminal.
   **Never paste the key into `opencode.json`**: if you share or commit the folder, your key goes with it.
4. **Open this folder** in OpenCode or OpenWork and ask a question.

## Try asking

- *My non-conference hotel in Chicago is $219 a night plus $38 a night in taxes and fees. Is the room within
  UCF's lodging limit?*
- *I fly from Orlando to Chicago on a flight departing at 8:30 AM Monday and return on a flight landing in
  Orlando at 7:15 PM Wednesday. No meals are provided. What is my total meal allowance for the trip?*
- *I'm going to a business meeting in downtown Chicago (not at a conference hotel), checking in on a Monday and
  out on the Wednesday. Find three hotels within UCF's lodging limit and give each one's nightly base rate.*

Ask the same question in a few new sessions and compare the answers. Do they agree? Which sections of the
manual did it read? Which tool calls did it make?
