---
description: Roast my Instagram. Pulls my last 30-50 Reels through Windsor.ai, ranks the top 10 by saves and shares, and emits a visual audit PDF with a blind-spot verdict.
argument-hint: <@handle>
allowed-tools: [Read, Write, Bash, AskUserQuestion]
---

Requires the **Windsor.ai** connector, connected and enabled in this chat. If its
tools are not loaded, stop and tell the user to add it in Connectors before retrying -
do not substitute guesses for real metrics.

Handle: $ARGUMENTS (if empty, ask for it before proceeding).

Run this brief against the account:

You have full access to my Instagram account (@handle).
I want you to roast me, honestly, no sugar-coating. Instagram only, no other platforms.

Step 1: Pull my last 30 to 50 reels. Identify my TOP 10 performing reels
(by views, saves, shares; weight saves and shares heavily, not just likes).

Step 2: For each of those 10 reels, analyze:
- Hook type
- Topic / content pillar
- Format (talking head, b-roll, text-on-screen, etc.)
- What's WORKING (be specific: the hook? the pacing? the topic?)
- What's NOT working / what's holding it back from going bigger

Step 3: Output the analysis as a clean, visually striking PDF I can save and screen-record.
Requirements for the visual:
- A big bold table or card layout, one row/card per reel
- Columns: Reel #, Views, Hook, What's Working (green), What's Not (red)
- Use color (green = working, red = not), large readable type, generous spacing;
  it needs to look GOOD on a phone screen when I film it
- Header at the top: "Claude's Instagram Audit, @handle"
- At the bottom: a 3-line "biggest blind spot" verdict

Substitute the real handle for @handle in the header. Every number in the output must
come from the connector - never estimate a view count.
