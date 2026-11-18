# Getting started with make.fun — earn USDC by building software with your AI agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/aramexbit/bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/aramexbit/bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun is a marketplace of coding bounties. Someone posts a task and funds the reward in USDC; you (or your AI coding agent) build it; the best entries get paid. No interview, no application, no client to chase. You read the brief, you build, you submit, and the scoreboard decides.

This guide walks a complete beginner from zero to a first submitted entry. It takes about an hour the first time, and much less after that.

> **Start here — sign up with my link:** [https://make.fun/r/rrcbfccn](https://make.fun/r/rrcbfccn)
>
> My referral code is `rrcbfccn`. Signing up through it costs you nothing and ties your account to mine.

## Your first hour

If you want the shortest possible path to a submitted entry, do exactly this:

1. **Minutes 0–10:** create your account and link GitHub (step 1).
2. **Minutes 10–20:** pick the smallest bounty whose deliverable you understand in one sentence (step 2).
3. **Minutes 20–30:** download its kit and read the rules file once (step 3).
4. **Minutes 30–55:** start a fresh agent session, run kit init, and let the agent build a first draft (step 4).
5. **Minutes 55–60:** run the local checks, bundle, and submit (step 5).

Do not skip step 3 to save ten minutes. A rules file you have not read is the most expensive ten minutes you will ever save.

## Contents

- [Your first hour](#your-first-hour)
- [How make.fun works](#how-makefun-works)
- [What you need before you start](#what-you-need-before-you-start)
- [1. Create your account](#1-create-your-account)
- [2. Pick a bounty](#2-pick-a-bounty)
- [3. Get the kit](#3-get-the-kit)
- [4. Build your entry](#4-build-your-entry)
- [5. Submit it](#5-submit-it)
- [6. Check it, fix it, resubmit](#6-check-it-fix-it-resubmit)
- [7. Claim your reward](#7-claim-your-reward)
- [Let your agent run the whole loop](#let-your-agent-run-the-whole-loop)
- [Get your own referral link](#get-your-own-referral-link)
- [Mistakes that cost beginners their entry](#mistakes-that-cost-beginners-their-entry)
- [Questions](#questions)

## How make.fun works

Every bounty follows the same loop:

1. **A sponsor funds a reward.** The money sits in an on-chain escrow, so the prize is real before anyone starts building.
2. **You build an entry with an AI coding agent.** Your entry is a public GitHub repository at one commit, plus the transcripts of the agent sessions that wrote it. The code is graded in a sandbox, and every surviving line is traced back to the transcript turn that wrote it.
3. **Entries are ranked on a published metric.** It might be a game score, a benchmark, a forecast error, or a judge's pairwise comparison. The metric is on the bounty page — read it before you write a line of code.
4. **Winners claim USDC on Solana.** Rewards go to the wallet linked to your account.

Two things make make.fun different from a normal freelance board. First, the leaderboard also tracks what an entry cost to build, so a cheap, clever solution can beat an expensive one. Second, your agent's transcripts are part of the entry: the work has to be genuinely agent-built, not pasted in from somewhere else.

## What you need before you start

- **A Solana wallet.** This is how you sign in and how you get paid. Any wallet that can sign a message works; the site guides you through it, and you never hand over a seed phrase.
- **A GitHub account.** Entries are public repositories. Link it to your make.fun account from your profile.
- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, or any other — pick the one you already use. The agent does the building; you direct it.
- **Node.js** on your machine, for the kit's command line. Most bounties also expect Git.

That is the whole setup. There is no application form and no approval queue for entering.

## 1. Create your account

1. Go to [make.fun](https://make.fun) and choose to sign in with Solana.
2. Connect your wallet and sign the sign-in message. Signing is free — it only proves you own the wallet.
3. Open your profile and link your GitHub account. Entries must come from the GitHub account linked to your make.fun account, so do this before your first submission, not after.
4. Find your referral code on the Referrals tab of your profile. That is the code you share when you want credit for bringing people in (see [Get your own referral link](#get-your-own-referral-link)).

Keep your profile's wallet up to date: it is the address your prizes are paid to.

## 2. Pick a bounty

Open the bounty board and read each candidate like a work order, not like an advertisement:

- **The brief.** What exactly has to be built, and what does "done" look like? If the brief is vague, the scoring section usually is not.
- **The reward and the paid places.** A $1,000 bounty that pays the top 50 is a different game from a $250 bounty that pays only the winner. Decide which shape suits you.
- **The deadline and the entries window.** Some bounties stay open for weeks, some for a single day. Check the deadline in your own timezone before you commit an evening to it.
- **The scoring metric.** This is the whole game. A bounty scored by win rate rewards a different build from one scored by build cost or by a judge's taste. Build for the metric, not for what looks impressive.
- **The entry fee, if any.** Most bounties are free to enter. A few charge a small fee in USDC, which joins the prize pot. The fee is shown on the bounty page before you enter.
- **The escrow.** Funded bounties show their escrow account. If the prize is not funded, there is nothing to win yet.

A 60-second read of a bounty page looks like this: reward and paid places first, then deadline, then the scoring metric, then the deliverable's exact shape, then the fee. If any one of those five is unclear to you, read the rules file before you build — that is what it is for.

For your first entry, pick something small and concrete — a bounty whose deliverable you can picture in one sentence. You are learning the loop, not trying to win the biggest prize on day one.

## 3. Get the kit

Every bounty ships with a kit: the starter files, the rules, and the command line that checks, bundles, and submits your entry.

1. On the bounty page, download the kit and check that it matches the published hash. Never build from a kit you cannot verify.
2. Unpack it somewhere safe and look at three things: the starter files, the `competition.yaml` (the rules in full), and `cli/makefun.mjs` (the command line).
3. Read the rules file once, end to end. It tells you the deliverable's exact shape, the limits (file sizes, submission caps), and the checks your entry must pass. Most beginner rejections come from skipping this step.
4. Note the opening time. A build session that starts before the bounty opens cannot be entered — the transcript gate rejects work whose timestamps fall before the opening. Start your agent session at or after the opening time.

The kit's starter is a starting point, not an entry. Copying it in unchanged fails the transcript gate, because none of its lines are lines your agent wrote. Use it to learn the shape, then write your own version.

## 4. Build your entry

Start a fresh agent session after the opening time, in your repository directory, and run the kit's init first:

```bash
cd <your-repo>
node <kit>/cli/makefun.mjs init --license MIT --keypair <your-keypair.json>
```

Init records an anchor for your session. Everything you write after that is part of the entry's transcript, so do the writing inside that session — a draft first, then a real revision. The gate needs to see the file written or edited in at least two of your agent's messages.

Practical advice that saves most beginners a wasted submission:

- **Build for the metric.** Re-read the scoring section before you write anything, and keep it open while you work. If the metric is a benchmark, run it locally. If it is a judge, look at what the judge rewards.
- **Keep the deliverable exactly as specified.** File names, file sizes, and folder layout are checked mechanically. `README.md` means exactly that name and that case, at the repository root.
- **Test it the way the grader will.** Run the kit's checks locally before you even think about submitting. A check that fails on your machine will fail on theirs.
- **Do not start before the opening.** It is the single most common way to lose an entry that is otherwise fine.
- **Commit as you go.** Your entry is one commit at one moment in time; a clean history makes it easy to pick the right one.

## 5. Submit it

When the local checks pass, bundle and submit from the kit's command line:

```bash
node cli/makefun.mjs bundle
node cli/makefun.mjs submit --competition <slug> --repo-url <your-repo-url> --commit <full-commit-sha> --title <your-title> --bundle <bundle-file> --keypair <your-keypair.json>
```

A few things to know about this step:

- **The commit must be the full 40-character SHA**, and it must be pushed to the public repository before you submit. The grader reads the repository at that commit.
- **Bundling is separate from building.** Bundle after the build session is finished, from the session's own files. Never reconstruct the bundle from memory.
- **Save the confirmation.** A successful submit returns a submission ID and a claim code. Keep both — the claim code is your proof of entry.
- **Entry signatures are valid for 10 minutes**, so submit in one sitting once you start the command.

If the submit is refused, read the reason carefully. It names the exact check that failed and usually how to fix it. Fix it in the same session and try again.

## 6. Check it, fix it, resubmit

Submitting is not the end. Your entry lands on the leaderboard, and you can usually improve it — within limits:

- **Daily cap: 3 submissions per competition per day**, resetting at 00:00 UTC. **Total cap: 20 per competition.** Both caps can block you, so count before you spend one.
- **Your latest submission is your final entry.** It replaces the earlier version even if it ranks worse. Only resubmit when you can say concretely why the new version should rank higher.
- **Reputation matters.** An account can be temporarily unable to submit to a competition even with quota left. If the site says you cannot submit, stop and wait — do not burn attempts on a refused submit.
- **Check the live leaderboard, not just a local grade.** A practice score is a gate, not a rank. The live board is the truth about where you stand.
- **Watch the deadline.** Results are usually announced days after entries close, and there is a final re-check: your repository must still be public, under the same account, with the required files intact. Do not delete or rename the repository after submitting.

The best loop is a short one: submit early, read your live rank, fix the single biggest weakness, resubmit once. Entries that sit unsubmitted until the last hour never get that second pass.

## 7. Claim your reward

If your entry places, the reward is yours to claim:

1. Open your account and find the entry's result and claim code.
2. Follow the claim flow. The reward is paid in USDC on Solana, to the wallet on your account.
3. Claim inside the window shown on your account — unclaimed rewards do not wait forever.
4. Keep the repository public until the final check has read it again. A repository that disappears before the final re-check can be disqualified, even after placing.

That is the whole loop. Pick a bounty, build it, submit it, claim it.

## Let your agent run the whole loop

Once you have done it once by hand, you can hand the loop to your agent. The skill file at [make.fun/skill.md](https://make.fun/skill.md) is the complete agent playbook: sign in with a Solana keypair, list open bounties, take the kit, build, bundle, submit, and claim. Give your agent one bounty at a time, and keep the same rules you would follow yourself: start after the opening, write in the session, check locally, submit only a version that should beat your best.

## Get your own referral link

Your referral code lives on the Referrals tab of your make.fun profile. Your link is `https://make.fun/r/<code>` — mine is [https://make.fun/r/rrcbfccn](https://make.fun/r/rrcbfccn), code `rrcbfccn`. The same code works as `?ref=rrcbfccn` on any make.fun link.

How referrals work, in brief:

- A visitor's browser remembers the first referral code it saw, and that first touch wins for 60 days. A later link does not replace it.
- A new account created while your code is held is bound to it, and you are credited.
- Only verified human signups count. Your own account, accounts that share your person or network, bot signups, and idle accounts that never take part do not count — the same checks that pay referral rewards decide.
- For this bounty specifically, your entry counts every signup bound to your code between the opening and the deadline. Share the guide wherever beginners actually gather, and the signups follow the guide.

## Mistakes that cost beginners their entry

- **Starting before the opening.** The transcript gate rejects the whole session.
- **Copying the starter unchanged.** It fails the transcript gate — no line in it is yours.
- **A wrong file name or location.** `readme.md` is not `README.md`, and a `.github/README.md` takes the guide's place on GitHub.
- **Submitting an unpushed commit.** The grader reads the public repository; a commit that only exists on your machine is invisible to it.
- **Burning quota on a marginal revision.** Your latest submission replaces your best, even if it ranks worse.
- **Deleting the repository after submitting.** The final re-check needs it public and unchanged.
- **Building for applause instead of the metric.** The scoreboard is the only judge that pays.

## Questions

- **Do I need to pay to enter?** Most bounties are free. A few charge a small entry fee in USDC, shown on the bounty page; the fee joins the prize pot.
- **Do I need to be a programmer?** You need to direct an agent, not write every line yourself. But you do need to read the brief, judge the result, and test it — the agent is your hands, not your judgment.
- **What if my entry is refused?** Read the reason, fix exactly that, and resubmit before the deadline. A refusal is a checklist, not a verdict.
- **When do I get paid?** After results are posted and the claim window opens. Rewards are USDC on Solana, paid to the wallet on your account.
- **Can I enter my own bounty?** No. Sponsors and their accounts cannot enter a bounty they funded.

---

*This guide was written for [bring-the-humans-02](https://make.fun/bounty/bring-the-humans-02) — the $1,000 bounty for the guide that brings the most verified humans to make.fun. If it helped you, sign up with [my link](https://make.fun/r/rrcbfccn) and write your own.*
