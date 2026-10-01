# Peer Point Toronto Agent Hackathon

Build and deploy one of five Cloudflare Agent challenges. Each card starts as a working, limited application. Choose a card, deploy it to your temporary lab account, then give the generated Git repository URL to Peer Point OS or clone it into your own IDE.

## Start

1. Choose one card below.
2. Select its **Deploy to Cloudflare** button.
3. Authorize GitHub and select only your temporary lab account.
4. Wait for the starter deployment to finish.
5. Copy the generated Git repository URL.
6. Invoke the card's Peer Point OS skill with that URL, or clone it locally.
7. Build, verify, merge the proposed pull request, and let Workers Builds redeploy automatically.

| Card          | Build                                         | Main primitives                                 | Repository                                                               | Deploy                                                                                                              | Status                           |
| ------------- | --------------------------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
| Threat Hunter | Investigate a seeded authentication attack    | Agents, Workers AI, AI Gateway, Durable Objects | `https://github.com/vnikhilbuddhavarapu/peer-point-card-1-threat-hunter` | `https://deploy.workers.cloudflare.com/?url=https://github.com/vnikhilbuddhavarapu/peer-point-card-1-threat-hunter` | Ready                            |
| Code Review   | Repair a failing repository in isolation      | Agents, Sandbox, Containers                     | `https://github.com/vnikhilbuddhavarapu/peer-point-card-2-code-review`   | `https://deploy.workers.cloudflare.com/?url=https://github.com/vnikhilbuddhavarapu/peer-point-card-2-code-review`   | Ready with preview fallback      |
| Inbox Agent   | Clarify an email and gate sending on approval | Agents, durable Actions, Email                  | `https://github.com/vnikhilbuddhavarapu/peer-point-card-3-inbox-agent`   | `https://deploy.workers.cloudflare.com/?url=https://github.com/vnikhilbuddhavarapu/peer-point-card-3-inbox-agent`   | Ready with simulator fallback    |
| Cross-System  | Join CRM, ERP, Jira, and config evidence      | Agents, MCP Portal, Access                      | `https://github.com/vnikhilbuddhavarapu/peer-point-card-4-cross-system`  | `https://deploy.workers.cloudflare.com/?url=https://github.com/vnikhilbuddhavarapu/peer-point-card-4-cross-system`  | Ready with direct MCP fallback   |
| Watcher       | Detect one material page change without noise | Browser Run, R2, scheduled tasks                | `https://github.com/vnikhilbuddhavarapu/peer-point-card-5-watcher`       | `https://deploy.workers.cloudflare.com/?url=https://github.com/vnikhilbuddhavarapu/peer-point-card-5-watcher`       | Ready with manual-check fallback |

## Peer Point OS starter prompts

After deployment, replace the example with the GitHub repository that Deploy to Cloudflare created for you.

### Threat Hunter

```text
/threat-hunter https://github.com/<your-user>/<deploy-created-repository>
```

### Code Review Agent

```text
/code-review-agent https://github.com/<your-user>/<deploy-created-repository>
```

### Inbox Agent

```text
/inbox-agent https://github.com/<your-user>/<deploy-created-repository>
```

### Cross-System Agent

```text
/cross-system-agent https://github.com/<your-user>/<deploy-created-repository>
```

### Watcher Agent

```text
/watcher-agent https://github.com/<your-user>/<deploy-created-repository>
```

Peer Point OS prefers Container MCP verification. If Container MCP becomes unavailable, it continues through a GitHub branch and pull request, then uses GitHub Actions and Workers Builds as the verification and deployment gates.

## Own IDE

```bash
npm ci
npm run verify
npm run dev
```

After implementing your card:

```bash
npm run verify
npm run deploy
```

## Rules

- Deploy only to the assigned temporary lab account.
- Never commit tokens, capabilities, or private keys.
- Do not hardcode the expected answer.
- Preserve each card's validation, bounds, and approval controls.
- A different implementation is welcome if the required behavior and Cloudflare primitives remain demonstrable.
