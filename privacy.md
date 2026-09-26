---
layout: default
title: Privacy Policy
---

# StickSquad — Privacy Policy

**Last updated: 23 September 2026**

StickSquad is a desktop companion for Windows, published by **Jeff Perez**.
This policy explains what it stores, where it stores it, and who else can see
it.

The short version: **StickSquad keeps your data on your own computer.** It has
no servers, no accounts and no analytics. By default it makes no network
connections at all.

---

## 1. We have no servers, so we receive nothing

There is no StickSquad account, no sign-up and no cloud. We do not operate a
server that your copy of the app talks to. We cannot see your conversations,
your files, your email or how you use the app, because none of it is ever sent
to us.

There is no analytics, no telemetry, no crash reporting that reaches us, and no
advertising of any kind.

## 2. What is stored on your computer

All of it lives in your own Windows user profile, under
`%APPDATA%\StickSquad` and `%LOCALAPPDATA%\StickSquad`:

| What | Where | Notes |
|---|---|---|
| Conversations and things the stickmen remember about you | `sticksquad.db` | You can view and delete individual memories in Settings → Memories |
| Your crew: names, personalities, jobs, outfits | `crew.json` | |
| Reminders | `sticksquad.db` | |
| Meal entries, if you use the health tracker | `sticksquad.db` | |
| Activity journal, if you switch it on | `sticksquad.db` | See section 4 |
| Recorded routines | `routines.json` | Which apps you opened and what you searched for |
| Account tokens, if you connect Google | `accounts.json` | Encrypted — see section 5 |
| Your Google Gemini API key, if you provide one | `brain-key.json` | Encrypted — see section 6 |

Uninstalling StickSquad does **not** delete this folder, so that reinstalling
keeps your crew. To remove it, delete the folders above, or use the delete
controls inside the app before uninstalling.

## 3. The AI runs on your computer

StickSquad ships with a small language model and runs it locally. Your messages
are answered on your own machine and are not sent anywhere.

Two optional exceptions are described in sections 6 and 7. Both are off unless
you turn them on, and the app shows which one is in use at all times.

## 4. The activity journal (off by default)

If you give a stickman the **Activity journal** job, it can record which
application is in front and that window's title, every few seconds, so it can
tell you what you did today.

- It is **off until you press "Start recording"**. Choosing the job is not
  enough.
- It records the application name and window title only. It does **not** record
  your keystrokes, your mouse, your screen, your clipboard, page contents, or
  anything you type.
- Private and incognito windows, and password managers, are reduced to the
  application name with no title.
- It stops on its own when you have been away from the computer for five
  minutes, and it never runs while it is paused.
- It is kept for 30 days and then deleted automatically.
- While it is recording, the stickman says so, the tray menu shows it, and the
  crew screen shows a red dot. It is never silent.
- You can pause it, delete today's entries, delete a single entry, or delete
  everything, at any time, in the Activity log.

This journal never leaves your computer.

## 5. Connecting Google (optional)

If you connect a Google account, StickSquad uses Google's standard OAuth
sign-in: your browser opens Google's own page, and the app never sees your
password.

**Access tokens are encrypted** with Windows DPAPI (via Electron's
`safeStorage`) and stored in your user profile. They are never written in plain
text, never shown to the app's own windows, and never sent to us.

**What StickSquad does with Google user data — Limited Use.** StickSquad's use
of information received from Google APIs follows Google's
[Limited Use requirements](https://developers.google.com/terms/api-services-user-data-policy).
Specifically:

- Your Gmail, Calendar and Drive data is used **only** to carry out the task
  you asked a stickman to do, on your computer, at the time you asked.
- It is read by the **local** language model. It is not sent to us, and it is
  not sent to any third party.
- It is **not** used for advertising, and it is **not** used to train any AI
  model.
- It is **not** sold or transferred to anyone.
- It is held only for as long as the task takes. It is not copied into the
  app's own database, except where you explicitly ask a stickman to remember
  something.
- Nobody reads it. We could not — it never reaches us.

By default StickSquad asks only for permission to write and send email, to read
and add calendar events, and to open files you pick. Reading your email and
searching your Drive requires a separate switch in Accounts, which is off
unless you turn it on.

Anything a stickman wants to **send, create or change** shows you an approval
card first. Nothing is sent without you agreeing to that specific action.

You can disconnect an account at any time in Accounts, which deletes its stored
tokens. You can also revoke access at
[myaccount.google.com/permissions](https://myaccount.google.com/permissions).

## 6. Google Gemini as the brain (optional, off by default)

You may choose, in Settings → Brain, to have Gemini answer instead of the local
model. If you do:

- You supply your own Google Gemini API key. It is encrypted with Windows DPAPI
  and stored on your computer. It is never sent to us.
- Your messages to the stickmen are then sent to **Google**, and are handled
  under Google's terms and privacy policy, not this one. Google's free tier may
  use conversations to improve their models.
- The app's header says **"Google Gemini · your words leave this machine"** the
  whole time this is on, so it is never ambiguous.

This is off unless you choose it, and it can be switched back at any time.

## 7. Streamer mode (optional, off by default)

If you turn on Streamer mode and enter a Twitch channel name, StickSquad
connects to Twitch's public chat for that channel to read it, the same way any
viewer's browser does. No Twitch account, login or token is used.

Messages are filtered and shown above your stickmen. Nothing about you is sent
to Twitch beyond the connection itself, and nothing is sent to us.

## 8. Other network connections

Besides sections 6 and 7, StickSquad connects out only when you set one of
these up yourself:

- a calendar address you paste in, to read that calendar;
- the travel-deals job, which fetches public deal feeds;
- downloading an optional larger AI model or the optional voice files, when you
  press the download button.

With none of these configured, StickSquad makes **no network connections at
all**. This is verified by an automated test that fails the build if anything
contacts the network in the default configuration.

## 9. Children

StickSquad is family-friendly and is not directed at children under 13. We do
not knowingly collect information from anyone, of any age, because we do not
collect information at all.

## 10. Your control over your data

Because everything is on your computer, you do not need to ask us for it:

- **See it** — Settings → Memories lists everything a stickman remembers; the
  Activity log shows every recorded entry.
- **Delete it** — individual memories, a single activity entry, a whole day, or
  everything. Disconnecting an account deletes its tokens.
- **Take it** — the files listed in section 2 are yours; copy the folder.
- **Erase it completely** — delete `%APPDATA%\StickSquad` and
  `%LOCALAPPDATA%\StickSquad` after uninstalling.

## 11. Changes to this policy

If this policy changes, the date at the top changes with it, and the new version
appears at this address.

## 12. Contact

Questions about this policy: **sticksquad.app@gmail.com**

Published by Jeff Perez.
