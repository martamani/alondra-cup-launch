# Alondra Cup — Spain Launch: Case Study Draft

This project builds on [Pottery AI Content Pipeline](https://github.com/martamani/pottery-ai-content-pipeline), which covers the base AI content workflow. This repo applies and extends that workflow for a single product launch (the Alondra Cup) into the Spanish market, including multilingual content, campaign assets, and a documented editorial process.

Project diagram here https://canva.link/x5pxa6pnxdpsx8c

## Part 1 — Thesis, Problem, Solution

**Thesis**
An AI assistant (Claude) can support a small content team's core functions — drafting, translation, editorial review, workflow design — but it doesn't always work well. A human needs to check everything, and it makes you wonder is it worth automating some tasks when it takes you longer to correct them.

**Hypothesis**
Claude can simulate the output of an international content team (brand positioning, multilingual copy, campaign assets) faster than doing it manually, if a human stays in the loop for factual verification, tone correction, and structural decisions — but Claude-driven iteration inside third-party tools (like Notion) does not scale well.

**The problem**
Marta's Pottery Studio is launching a single product (the Alondra Cup) into the Spanish market with full supporting content: positioning, blog, social, email nurture, paid ads, sales enablement — with a fictional content team.

**The solution + workflow**
Simulate the team's output using Claude for drafting and translation, with Notion as the system of record. Content moves through a Draft → Review → Approved workflow before it's considered final.

High-level workflow:
1. Define product positioning and brand story (Alondra Cup, moon jar tradition, mingei philosophy)
2. Draft core content in Claude (blog, social, email, ads, sales playbook)
3. Translate and localize (EN ⇄ ES)
4. Human review against facts, tone, and glossary — corrections fed back to Claude
5. Approved content logged in Notion as the editorial system of record

## Part 2 — Tools & Key Findings

| Step | Tool | Role |
|---|---|---|
| Drafting & translation | Claude | Generated blog, social, email, ad, and sales copy in EN/ES |
| Editorial system of record | Notion | Editorial calendar, translations DB, glossary DB |
| Fact-checking | Claude + web search | Used to verify corrections once flagged by Marta — did not catch errors proactively |
| Content generation platform | AirOps | Evaluated, not used — see findings below |
| Publishing (planned) | Make.com → Bluesky | Native Bluesky module scheduled posts directly, no Buffer needed |

**Key findings**
1. Claude produced fluent, on-brand drafts quickly, but introduced factual errors (wrong museum, wrong century, wrong technique) that required manual fact-checking to catch — Claude did not self-correct any of them.
2. Editorial iteration directly inside Notion (via MCP) was slow and error-prone at scale — duplicated content across pages, and edits made in one place didn't propagate to others. Pasting Claude's drafts into Notion by hand was more reliable.
3. Make.com's native Bluesky integration made Buffer redundant — Make.com's own scheduling covers the queueing function Buffer would have handled.
4. The original AirOps-centric plan didn't survive contact with real pricing. Solo tier costs $200/month, not free, making a live generate-and-compare test impractical within this project's scope.
