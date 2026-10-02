---
layout: default
title: Privacy Policy
---

# StickSquad — Privacy Policy

**Last updated: 3 October 2026**

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
to us — unless you choose to email us yourself, for example to report an AI
reply (section 3).

There is no analytics, no telemetry, no crash reporting that reaches us, and no
advertising of any kind. If the app crashes, the report stays on your computer;
"Copy diagnostics" in Settings → About shows you the full text, with personal
details removed, before you choose to send it to anyone.

## 2. What is stored on your computer

All of it lives in your own Windows user profile, under
`%APPDATA%\StickSquad` and `%LOCALAPPDATA%\StickSquad`:

| What | Where | Notes |
|---|---|---|
| Conversations and things the stickmen remember about you | `sticksquad.db` | You can view and delete individual memories in Settings → Memories |
| Your crew: names, personalities, jobs, outfits | `crew.json` | |
| Reminders, your to-do list, settings and sticker book | `sticksquad.db` | |
| Meal entries, if you use the health tracker | `sticksquad.db` | Calorie estimates are off unless you turn them on |
| Activity journal, if you switch it on | `sticksquad.db` | See section 4 |
| Recorded routines | `routines.json` | Which apps you opened and what you searched for |
| Account tokens, if you connect Google or Microsoft | `accounts.json` | Encrypted — see section 5 |
| Your Google Gemini API key, if you provide one | `brain-key.json` | Encrypted — see section 6 |
| An error log and crash reports | `logs\`, `Crashpad\` | Never sent anywhere — see section 1 |
| Mods you add | `mods\` | Plain files you put there yourself |
| Voice files and the AI engine, if you download them | `%LOCALAPPDATA%\StickSquad` | Only when you press download |

Two things are saved **outside** that folder, and only when you ask: a clip you
record goes to your **Videos\StickSquad** folder, and a research note you save
goes to **Documents\StickSquad\Research**. A postcard (a stickman you send to a
friend) is a small file saved wherever you choose; it holds that stickman's
name, personality, colour, outfit and any message you type — never your
conversations or memories.

Uninstalling StickSquad does **not** delete this folder, so that reinstalling
keeps your crew. To remove it, delete the folders above, or use the delete
controls inside the app before uninstalling.

## 3. The AI runs on your computer

StickSquad ships with a small language model and runs it locally. Your messages
are answered on your own machine and are not sent anywhere. The voices and the
speech recognition run locally too.

**The microphone** is on only while you are talking to a stickman, and the
screen shows it the whole time. Nothing is recorded in the background, and what
you say is turned into text on your computer and not kept as audio.

**The clipboard** is read only at the moment you press the "read aloud" key,
and is not read out at all if it looks like a password or key. It is never
watched, stored or sent anywhere.

**The screen** is recorded only when you start a clip yourself, for the few
seconds you choose, and a stickman says so while it happens. The clip is saved
on your computer and not uploaded.

**Reporting an AI reply.** The stickmen's replies are written by an AI and can
be wrong or inappropriate, so every reply in the chat has a "Report" link. A
report is an email that opens in your own email app, addressed to
sticksquad.app@gmail.com. It contains the reply, the reason you picked, any note
you add, the app's version and which AI wrote the reply — and what you said just
before it only if you tick that box. Nothing is sent unless you press Send
yourself. Reports are used only to look into the reply and make the AI's
answers better.

The one optional exception to "the AI runs locally" is described in section 6.
It is off unless you turn it on, and the app shows when it is in use.

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

## 5. Connecting Google or Microsoft (optional)

If you connect a Google or Microsoft account, StickSquad uses that company's
standard OAuth sign-in: your browser opens Google's or Microsoft's own page, and
the app never sees your password. The app then talks **directly** to Google's
APIs or to Microsoft Graph from your computer — never through a server of ours.

**Access tokens are encrypted** with Windows DPAPI (via Electron's
`safeStorage`) and stored in your user profile. They are never written in plain
text, never shown to the app's own windows, and never sent to us.

**What StickSquad does with Google user data — Limited Use.** StickSquad's use
and transfer to any other app of information received from Google APIs will
adhere to the
[Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy),
including the Limited Use requirements. Specifically:

- Your Gmail, Calendar, Drive and Tasks data is used **only** to carry out the
  task you asked a stickman to do, or a job you set up for it (for example, a
  heads-up before a meeting), on your computer.
- It is read by the **local** language model. It is not sent to us, and it is
  not sent to any third party. (The one exception is if **you** choose Google
  Gemini as the brain in section 6: the words a stickman works with then go to
  Google's Gemini service under your own API key.)
- It is **not** used for advertising, and it is **not** used to train any AI
  model.
- It is **not** sold or transferred to anyone.
- It is held only for as long as the task takes. It is not copied into the
  app's own database, except where you explicitly ask a stickman to remember
  something.
- Nobody reads it. We could not — it never reaches us.

By default StickSquad asks Google only for permission to send email (each one
only after you approve it; an email you would rather send yourself opens in
Gmail's own window instead, which needs no permission at all), to read and add
calendar events, to open files you pick, and to keep your
to-do list in step with Google Tasks (the sync itself is off until you switch it
on). Reading your email and searching your Drive requires a separate switch in
Accounts, which is off unless you turn it on.

From Microsoft it asks to read and write your Outlook mail and calendar, to send
mail, and for your basic profile (so the account can be shown by its address).
The same rules apply to that data as to Google's: used only for what you asked,
processed on your computer, never sent to us, sold, used for advertising or
used to train AI.

Anything a stickman wants to **send, create or change** shows you an approval
card first. Nothing is sent without you agreeing to that specific action.

You can disconnect an account at any time in Accounts, which deletes its stored
tokens. You can also revoke access at
[myaccount.google.com/permissions](https://myaccount.google.com/permissions)
for Google, or [account.live.com/consent/Manage](https://account.live.com/consent/Manage)
(personal) or [myapps.microsoft.com](https://myapps.microsoft.com) (work or
school) for Microsoft.

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

Besides sections 5, 6 and 7, StickSquad connects out only when you set one of
these up yourself:

- a calendar address you paste in, to read that calendar;
- the researcher job, which searches Wikipedia, OpenAlex and arXiv for the topic
  you ask about — nothing about you is in the search;
- the travel-deals job, which fetches public deal feeds;
- checking for updates, if you said yes to it: once a day the app asks whether a
  newer version exists, and the request carries nothing but the app's version.
  It never downloads or installs anything by itself. (Copies from a store are
  updated by that store instead, and do not check.)
- downloading an optional larger AI model, the voice files or the AI engine,
  when you press the download button (from GitHub or Hugging Face).

The app's **Privacy** screen lists which of these are on at any moment.

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
