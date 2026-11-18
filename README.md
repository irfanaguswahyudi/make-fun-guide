# make.fun from zero: a newcomer's guide to AI bounty hunting

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/irfanaguswahyudi/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/irfanaguswahyudi/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun runs coding competitions called bounties: each one names a task, a deadline, and a cash reward, and you enter by letting an AI coding agent build the solution while you steer. Whether you already use a coding agent daily or you have only just installed one, this guide walks you through the whole loop, from creating an account to claiming a prize. The only assumptions are that you can open a terminal, follow steps in order, and read the output your agent produces.

> **Start here:** sign up through my referral link, [https://make.fun/r/rxbkfby6](https://make.fun/r/rxbkfby6). My referral code is `rxbkfby6`. It costs you nothing extra, and it is how this guide keeps existing.

## In this guide

- [What is make.fun?](#what-is-makefun)
- [How a bounty runs](#how-a-bounty-runs)
- [What you need first](#what-you-need-first)
- [Step 1: Create your account](#step-1-create-your-account)
- [Step 2: Pick your first bounty](#step-2-pick-your-first-bounty)
- [Step 3: Download the kit](#step-3-download-the-kit)
- [Step 4: Build with your agent](#step-4-build-with-your-agent)
- [Step 5: Bundle, check, and submit](#step-5-bundle-check-and-submit)
- [Step 6: Read the verdict and try again](#step-6-read-the-verdict-and-try-again)
- [Step 7: Claim your prize](#step-7-claim-your-prize)
- [Let your agent run the whole loop](#let-your-agent-run-the-whole-loop)
- [Earn with referrals of your own](#earn-with-referrals-of-your-own)
- [Mistakes that cost entries](#mistakes-that-cost-entries)
- [Frequently asked questions](#frequently-asked-questions)
- [Useful links](#useful-links)

## What is make.fun?

At its simplest, make.fun is a marketplace for small, well-defined software jobs. A sponsor posts a bounty with a task and a reward; builders compete by submitting entries; a grader scores every entry against the same published rules; the highest-ranked entries get paid. The twist is who does the building: your AI coding agent writes the code while you steer, review, and decide when to submit.

Bounties cover a wide range of work. The board groups them into categories such as Code, Games, Trading, Forecasting, and Growth, and each category scores differently: a trading bounty might grade a strategy on market data, while a growth bounty might count verified signups. What stays the same across all of them is the shape of the loop: pick a task, read its rules, build with your agent, submit a public repository plus the session transcripts, and wait for the grade.

Three properties make the loop trustworthy enough to spend real effort on. First, the reward for a new bounty is locked in an on-chain escrow on Solana before the bounty opens, so the money is already there when you start; the escrow program's code is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow). Second, every bounty publishes its scoring method up front, so you can judge whether an entry is worth your time before you write a line. Third, every entry carries the transcripts of the AI sessions that built it, which is how the platform checks that the work is genuinely yours rather than someone else's code relabelled.

One honest caveat belongs at the top: nobody can promise you earnings. Rewards go only to the entries that place, most entries do not place, and the model calls your agent makes while building are billed to your own account with your provider. Treat your first few bounties as practice with a possible payout attached, not as income you can count on.

## How a bounty runs

Follow one entry through a bounty and you will see the same five stages every time. The bounty itself stays open while entries move through them, so knowing the sequence in advance saves you from the classic beginner error of building hard and submitting late.

| Stage | What happens | Who acts |
|---|---|---|
| Open | The bounty is live, the kit is available, and the clock is running. | You, by choosing and building |
| Submitted | Your repository at one commit, plus your session transcripts, is received. | You, by entering |
| Checked | Automated checks confirm the transcripts are real, match the code, and meet the rules. | The platform |
| Scored | The grader runs every entry the same way, twice, inside a sandbox. | The platform |
| Paid | Placed entries claim their reward in USDC on Solana. | You, by claiming |

A few rules of the game are worth absorbing before your first entry:

- **Most bounties cost nothing to enter.** A bounty with an entry fee says so plainly on its page, and the fee goes into that bounty's reward pot.
- **Only listed places are paid.** A bounty page shows exactly which ranks earn what. If your entry lands outside those ranks, it earns nothing, however good it felt to build.
- **Exact ties go to the earlier entry.** When two entries score identically, the one received first places higher. Submitting a solid entry early beats polishing forever and arriving second.
- **One account per person.** Do not create extra accounts, and do not enter the same work under two names. The platform checks for this, so keep everything under the one account you signed up with.
- **Your latest entry is the one that counts.** You can submit, get feedback, fix, and resubmit until the deadline, within the bounty's daily and total limits. Unless you pick an earlier submission, the most recent one is scored.

## What you need first

Gather these four things before you pick a bounty, so setup never interrupts a build halfway through:

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more all work. The kit recognises the session logs of over 30 agents on its own, and other agents can hand over a session file.
- **A GitHub account.** Entries are public repositories, and the repository must belong to the GitHub account linked to your make.fun account. Some bounties also accept a source bundle instead; the kit's `init` command sets one up, but the repository route is the normal one.
- **Node.js 22 or newer.** The kit's command line is a single file that runs on Node with nothing else to install.
- **A Solana wallet, or a way to get one.** Rewards are paid in USDC on Solana, so you need a wallet address that can receive them. You do not have to arrange this in advance: the `login` step in Step 1 creates a signing keypair for your machine and attaches its wallet to your account automatically. If you already have a wallet you prefer, you can link that one on your profile instead and use it for entries and claims.

You do not need to be an expert programmer to start, but you do need to be able to read what your agent produces, run commands it suggests, and judge whether its output matches the bounty rules. The agent writes; you decide.

## Step 1: Create your account

1. Open my referral link, [https://make.fun/r/rxbkfby6](https://make.fun/r/rxbkfby6), and click **Sign in** at the top right. The referral code is `rxbkfby6`, and using the link on your first visit matters: a referral binds to the first code a browser saw, and that first touch wins for 60 days, so a later link cannot replace it.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. All of these are free, and signing in with a wallet sends no transaction and costs no gas.
3. Open your profile through the avatar at the top right and fill it in: a username, a picture, and a short bio. This is the identity your entries and your place on the board will carry.
4. If you signed in without GitHub, link your GitHub account from your profile. Your entries come from your GitHub repositories, so that link needs to be in place before you submit anything. For the wallet side, the `login` step below attaches a wallet to your account on its own; linking an existing wallet on your profile is the alternative, not an extra requirement.

The kit's command line needs to be connected to your account once, whether you type the commands yourself or your agent runs them. The connection makes sure your agent enters under your account instead of creating a separate wallet-only account of its own. The command runs from inside a bounty's kit folder, which Step 3 shows you how to download, so you can do this pairing step right after that download. From inside the kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

The command prints a line like `Open <link> and approve code XXXX-XXXX`. Open that link while signed in, confirm the code matches what your terminal shows, and approve. If the command stops waiting before you approve, just run it again. On the first run it also creates a Solana keypair for this machine at `~/.makefun/keypairs/https_make.fun.json` and attaches its wallet to your account. A keypair is a matched pair of cryptographic keys: the private half signs your entries and claims, and the public half is your wallet address. Later commands sign with it automatically. After that, entries sent from the kit go in under your username, and you control what else the connection may do, such as commenting, betting, or editing your profile, under **Profile → API keys → Paired agents**.

## Step 2: Pick your first bounty

The front page lists every live bounty, grouped into Trending, New, and Ending soon. Start with one that matches tools you already know and a deadline you can actually meet; a bounty that closes in six hours is a bad first pick no matter how large its reward.

Open the bounty page and read it fully before you build. Each page shows:

- **The task**, in one line first and then in full detail, including exactly what an entry must contain.
- **The rules**, covering what counts, how scoring works, how ties break, and what gets an entry refused.
- **The rewards**, listing what each paid place receives, so you know what you are aiming at.
- **The phases**, showing when entries close and when final results are published.

Pay special attention to the prerequisites section. Some bounties need extra software, an account on another service, or a specific operating system, and the page says so before anything else. If a requirement is something you cannot meet, skip that bounty and pick another; guessing that a requirement is optional is the fastest way to waste a build.

For a first entry, favour a bounty with a clear published metric and a local grading command, so you can see your score before you submit. Avoid anything whose rules you cannot explain back in one sentence: if you cannot state how it is scored, you cannot aim at it.

## Step 3: Download the kit

Every bounty ships a kit: its rules file, its data, a starter entry where one exists, and the `makefun` command line. You can grab it from the entry form on the bounty page, or from a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Replace `<bounty-slug>` with the slug from the bounty page URL. The `--help` output lists every command the kit supports, and it is worth skimming once so the later steps feel familiar.

Inside the kit, `RULES.txt` holds the bounty's rules word for word. Read it, even if you already read the bounty page: the kit version is the authoritative text, and it states whether the bounty can be graded on your own machine. Where local grading exists, a **Grade locally** section gives the exact command, which usually looks like this, run from the kit folder with your entry folder beside it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That command scores your entry on the kit's practice data in the same Docker sandbox the server uses, so the number it prints is a realistic preview of where you stand. It needs Docker installed on your machine, since the `--driver docker` flag runs the grade inside a container. Use it early and often; a local grade costs nothing, while a rejected submission still counts toward your daily entry limit.

## Step 4: Build with your agent

This is the step where the transcript rules bite, so follow the order carefully:

1. **Wait for the opening, then start fresh.** Create a new public GitHub repository on the GitHub website, then copy it to your machine with `git clone https://github.com/<you>/<repo>.git my-entry` and move into it with `cd my-entry`. The commands in this guide call that folder `my-entry`. Open a brand-new session of your agent inside it. A session that began before the bounty opened cannot be entered, even if the work continued after the opening.
2. **Add an open-source license.** Entries must carry an OSI-approved license such as MIT. Add the license file before you write anything else, so it is present in every commit you might submit.
3. **Start from the kit's `starter/` folder when one exists.** Copy it into your repository and have your agent adapt it. A starter is a working entry that satisfies the rules, not a winning one; the gap between the two is your job.
4. **Build inside that one session.** The checks compare your transcripts against your code, so let your agent write the files itself rather than pasting code in from elsewhere. Writing some code by hand is allowed, but hand-written lines count less toward proving your agent did the work.
5. **Write the README the bounty asks for.** The requirements include a README template carrying make.fun's badges for your repository. Fill it in, keep the badge lines live, and commit it with everything else.

One habit helps on every bounty: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) before it starts. That page is the entire entry loop written for agents, with every command and check included, so an agent that has read it starts from the real rules instead of guessing them.

Work in visible steps inside the session: draft, run, check, improve. Sessions that show a real build, with a revision after the first working version, pass the transcript checks far more smoothly than a single giant write with nothing after it.

## Step 5: Bundle, check, and submit

When your entry is pushed to GitHub, note the exact commit you want to enter. Then bundle the transcripts from the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

The `bundle` command gathers every session that worked on the repository, strips credentials, email addresses, and home paths from the copies it uploads, and writes a run record describing your opening prompt, the agent, model, and setup that built the entry, and the MCP servers it used. MCP servers are the external tools your agent was connected to while it worked. The command prints what it removed, so read that output before you upload and confirm nothing you need to keep private slipped through. If any required part is missing, it writes nothing and names the flag that adds it. A Claude Code log, for example, carries neither the system prompt nor the effort level, so you add them with `--system-prompt <file>` and `--effort <level>`. A small number of bounties record the session live instead of taking a bundle; their `RULES.txt` explains how.

Before you enter, run the platform's own checks on your machine:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

This is the cheap place to catch a miss. A rejected submission still counts toward the day's entry limit, so a failure found here costs you seconds, while the same failure found after submitting costs you one of your limited attempts.

Then enter, either through the **Enter** form on the bounty page, pasting your repository link and commit and uploading the bundle, or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

The `--keypair` flag signs the entry with the wallet that `login` set up in Step 1. Every bounty whose reward sits in escrow requires that signature, and the signing wallet is the wallet the reward will be paid to, so make sure it is a wallet you control and can sign with later.

## Step 6: Read the verdict and try again

```sh
node cli/makefun.mjs status
```

That command shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check together with its fix, in plain language. Read the whole list before changing anything; fixes often interact, and patching the first item alone can leave the second one standing.

Apply the fixes, commit, bundle again, and submit again. You can keep this loop going until the deadline, within the bounty's daily and total entry limits, and `node cli/makefun.mjs status --competition <bounty-slug>` shows how much of your allowance remains. Remember that your latest submission is the one that counts unless you deliberately pick an earlier one, so never resubmit a version you have not checked locally first.

If a check fails in a way you do not understand, the fastest help is usually the bounty page's rules plus the kit's `RULES.txt`, read side by side with the error. Most rejections come from a small set of causes: a missing file, a wrong name, a session that predates the opening, or a repository owned by the wrong account.

## Step 7: Claim your prize

When results are posted and your entry has placed, you receive a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person <yes|no>
```

The `--us-person` flag answers the claim screen's one question, and you must replace `<yes|no>` with the truthful answer for you before running the command: a false answer disqualifies the claim. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is requested only where US law requires one.

Claim promptly. Each bounty states its claim window, and an unclaimed prize does not wait forever: depending on the bounty, it may pass to the next entry in the standings or return to the reward pool. Do not let a win expire because the claim step sat in a browser tab.

## Let your agent run the whole loop

If you would rather direct than type commands, you can hand the entire loop to your agent. Open a fresh chat with your coding agent in agent mode and ask it, in your own words, to read the agent guide at make.fun/skill.md, choose an open bounty it can build well, build it, bundle the transcripts, submit, follow the checks, and claim the reward if the entry places.

Set a time budget before you let it run, and keep an eye on which bounty it picks: an agent left unsupervised may choose a task with prerequisites you cannot meet, or burn through your model allowance on a long build. Check in at each stage, read the check results yourself, and make the final submit-or-wait call. The agent does the work; the judgement stays yours.

## Earn with referrals of your own

Every account gets a referral link shaped like `https://make.fun/r/<code>`, and adding `?ref=<code>` to any make.fun page carries the same code. You earn USDC rewards when people sign up through your link and take part, plus a share of what they win for a while after they sign up. That share is paid by make.fun on top, so the person you referred keeps their full reward.

Your link, the current value of each reward, and everything you have earned so far live on the **Referrals** tab of your profile. Two rules decide what counts: only verified human signups from people who actually take part are credited, and every reward is reviewed for at least a day before it can be claimed. Fake accounts, bots, and idle signups never count, and neither do signups that share a person or a network with the referrer, or that arrive as a cluster from one address.

If this guide helped you get started, signing up through [my link](https://make.fun/r/rxbkfby6) with code `rxbkfby6` is the simplest way to say thanks, and it costs you nothing.

## Mistakes that cost entries

These are the errors that show up again and again in rejected entries. Most of them take seconds to avoid and hours to fix after the fact:

- **Starting the session too early.** A session that began before the bounty opened cannot be entered, even if all the real work happened later. Open a fresh session after the opening, every time.
- **Forgetting the license.** An entry without an OSI-approved license file is refused. Add the license first, not last.
- **A shadowing README.** A `.github/README.md` in your repository is shown by GitHub in place of the root README, and bounties that grade the root README refuse the entry. Keep your guide at the repository root, named exactly `README.md`.
- **Pasting code from outside the session.** Code that appears in your repository without appearing in your agent's session weakens the transcript match. Let the agent write the files, and keep hand-written additions small.
- **Submitting without a local check.** The `check` command exists so rejections happen on your machine, not against your daily limit. Run it before every submission.
- **Signing with a wallet you cannot reach later.** The wallet that signs the entry is the wallet the prize pays. If you lose access to it, you lose the claim path with it.
- **Chasing referrals the wrong way.** Bot signups, self-signups, and clusters from one network never count toward referral rewards, and they can put the account at risk. Bring real people, or do not bring anyone.

## Frequently asked questions

<details>
<summary><strong>Does it cost anything to enter?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. A bounty with an entry fee states the fee on its page. Separately, the model calls your agent makes while building are billed by your own provider, so a long build does cost something in API usage.
</details>

<details>
<summary><strong>Is make.fun legitimate?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation, and new bounties open with their full reward locked in an open-source on-chain escrow. Note that make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base; those are different projects with similar names.
</details>

<details>
<summary><strong>Do I need coding experience to start?</strong></summary>

It helps a great deal, but the bar is reading and steering, not writing every line yourself. Your agent writes the code; you pick the bounty, judge whether its output matches the rules, run the local grade where one exists, read the check results, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work with the kit?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are recognised by the kit on their own. Agents the kit does not recognise can still hand over a session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to the transcripts I upload?</strong></summary>

Make.fun reads them to confirm that your own agent built the entry. The kit strips credentials, email addresses, and home folder paths from the uploaded copies, and `bundle --redact "<text>"` removes any other personal detail you name. The bundle command prints what it removed, so check that output before uploading. Keep the original session files on your machine unchanged; only the uploaded copies are redacted.
</details>

<details>
<summary><strong>When can I start building?</strong></summary>

At or after the moment the bounty opens. Sessions that began earlier cannot be entered, so open a fresh agent session once the bounty is live, and do your setup reading before the opening if you want a fast start.
</details>

<details>
<summary><strong>How are entries scored?</strong></summary>

Each bounty publishes its own scoring method on its page and in the kit's rules file, and the grader applies it identically to every entry in a sandbox. Read the metric before you build, because every design choice in your entry should serve it.
</details>

<details>
<summary><strong>Do I need a Solana wallet before I start?</strong></summary>

You need one before you can claim a reward, and the entry signature for escrowed bounties is made with a wallet on your account. The `login` step creates a keypair for your machine and attaches its wallet to your account, which covers both needs for most people.
</details>

## Useful links

- [make.fun](https://make.fun) — the board where every bounty lives
- [How it works](https://make.fun/how-it-works) — the platform's own walkthrough
- [make.fun/skill.md](https://make.fun/skill.md) — the agent guide, written for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents) — the longer guide to earning with agents
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — places to ask questions and meet other builders

---

<sub>New to make.fun? Sign up with my referral link: https://make.fun/r/rxbkfby6 · code <code>rxbkfby6</code></sub>
