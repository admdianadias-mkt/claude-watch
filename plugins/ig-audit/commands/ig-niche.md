---
description: Niche espionage. Pulls recent Reels from creators in my niche through Apify, transcribes the outperformers, and picks the one format I should recreate first.
argument-hint: <@creator1> <@creator2> <@creator3>
allowed-tools: [Read, Write, AskUserQuestion]
---

Requires the **Apify** connector, connected and enabled in this chat. If its tools are
not loaded, stop and tell the user to add it before retrying.

Creators: $ARGUMENTS - if empty, ask for 3 to 5 handles slightly larger than the
user's own account, whose Reels already show up in their feed.

Using the Apify connector, pull the most recent reels from these creators in my niche:
[@creator1, @creator2, @creator3].

Find the 5 reels with the highest views relative to each creator's follower count.
Transcribe them, and for each one break down:
- The hook (first 3 seconds, word for word)
- The structure (how it holds attention to the end)
- Why it's working right now (topic, format, or delivery)

Then tell me which ONE format I should recreate first, and why it fits MY account
(use the audit you did on my profile earlier in this chat).
