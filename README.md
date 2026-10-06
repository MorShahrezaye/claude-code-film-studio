# AI Film Studio: one brief, one film

**Every film here was made end to end by Claude Code from one written brief. The agents plan it, build it, review it and render it on their own. Then we read their logs.**

Each film has its own folder with the brief and the prompt that started the run, the links to the film and to an explainer about how its agents worked, and what the logs show.

| Film | What it is | The explainer | Folder |
|---|---|---|---|
| **The Multiplane Camera** | A 90-second science film about the camera that gave classic animation its depth. [Film](https://youtu.be/YeMtYLqyH88) | [Claude Code built a film studio. We read every log line.](https://youtu.be/K_hmIdawpW8) | [`films/the-multiplane-camera`](films/the-multiplane-camera) |
| **Jina** (ژینا) | A pixel-art documentary about Jina Mahsa Amini and the Woman, Life, Freedom movement. | Can AI agents think art? We read every log line. | [`films/jina`](films/jina) |

Everything is on YouTube, X and Instagram as **@agent_morry**.

## What is in each folder

| Path | What it is |
|---|---|
| `README.md` | The film, its explainer, and what the logs show |
| `brief/` | The full production brief |
| `prompts/` | The prompt (or prompts) that started each session |
| `media/` | The pictures used in the README |

The briefs and prompts are verbatim, except for local paths, which are replaced by `<BRIEFS>`, `<OUTPUT>` and `<CREDENTIALS_FILE>`. Each folder's README notes any other change.

## Run one yourself

```bash
claude -p "$(cat films/<film>/prompts/<prompt>.txt)" \
  --model claude-sonnet-5-5 --effort max \
  --permission-mode bypassPermissions --dangerously-skip-permissions \
  --output-format stream-json --verbose > production.log
```

> **Warning:** these flags let the agent run any command without asking. Use a disposable VM or container. Each folder lists what its run cost at API prices.

## License

The briefs, the prompts and the READMEs are released under [CC BY 4.0](LICENSE). The media of each film keep that film's licence, as its folder states.
