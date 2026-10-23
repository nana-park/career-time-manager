# Career Time Manager

**Get an automatic daily check-in for your job search.**

See what is due.

Know what to do first.

Carry unfinished work into tomorrow.

This is a **Codex skill for daily briefings and reminders**.

Your workspace or Codex automation controls when it runs.

## What you get

- Time available today.
- Your top 1–3 tasks.
- Upcoming deadlines.
- Work that can wait.
- One clear step for tomorrow.

## How the existing workflow starts

**Morning:** Open your career workspace and send your first message after 8 a.m.

The workspace adds a daily briefing automatically.

It checks whether you already received one that day.

**End of day:** Say that you are done for today.

Codex summarizes unfinished work for the next morning.

These reports appear in the Codex conversation.

## Example morning briefing

> **Time today:** 2 hours.
>
> **Due tomorrow:** Your application.
>
> **Do first:** Check missing answers — 20 minutes.
>
> **Next:** Edit the application — 60 minutes.
>
> **Finish:** Check submission requirements — 20 minutes.
>
> Keep 20 minutes free.

## Example evening check-in

```text
I'm done for today.
Help me wrap up.
```

> **Done:** Application edits.
>
> **Carry over:** Interview preparation.
>
> **Start tomorrow:** Choose 3 practice questions.

## Want a reminder at a set time?

Set up a recurring Codex automation that uses this skill.

Choose the time, timezone, and conversation for its reports.

Installing the skill alone does not create that automation.

The morning workflow above starts with your first message.

It is not a timed push notification.

## Good to know

Connect Calendar and Notion if you want briefings based on those sources.

You can also provide your schedule in the chat.

The skill does not change Calendar or Notion unless you ask.

Keep personal schedules and application records out of this public repository.

<details>
<summary>Setup and verified behavior</summary>

### Install

Put this repository's files in `.agents/skills/career-time-manager` inside your project.

Compare any existing installation before replacing it.

If you use Git:

```sh
git clone https://github.com/nana-park/career-time-manager.git .agents/skills/career-time-manager
```

Open the project in Codex and check that the skill is available.

### Add the daily workflow

The original workspace supplies the morning and evening triggers outside this repository.

Its morning rule runs after the first ordinary message after 08:00 in Asia/Seoul.

A private date record prevents duplicate reports.

The rule does not run for scheduled automation turns.

Its evening rule runs when the user clearly ends the workday.

A private carry-over record feeds the next morning's briefing.

To reproduce this behavior, add equivalent workspace instructions and private state storage.

Do not copy someone else's personal state or connection settings.

### Set up scheduled reminders

For reports without sending a message first, configure a separate Codex automation.

The automation must explicitly call this skill.

Example instruction:

```text
Use career-time-manager to prepare my daily briefing.
Read my authorized calendar busy times and task deadlines.
Review unfinished work from the previous day.
Report my available time, top 3 tasks, and nearest deadline.
Do not edit my calendar or task records.
```

Select the schedule and timezone in your automation settings.

Connect the required services and allow the automation to access the workspace.

Choose where the report should appear.

App or device notifications depend on the host's notification settings.

This repository does not include email, SMS, or mobile push delivery.

### What was verified

The source skill defines planning, morning reports, and end-of-day carry-over.

The workspace documents define the first-message and end-of-day triggers.

A separate active workspace automation runs twice daily.

Its current prompt does not explicitly call this skill.

That schedule is not evidence that this skill already sends timed reminders.

No notification delivery or live automation run was tested for this documentation update.

### Files and origin

`SKILL.md` contains the skill instructions.

The source had no `agents/` or `references/` folder.

Only this skill was copied from `nana-park/skills` at commit `875982c984d8fd7f40931826dc4a73ff67e1e5cb`.

Other skills, personal records, and the original Git history were not copied.

</details>
