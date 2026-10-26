<p align="center">
  <img src="Assets/logo/ChatCalendar.png" alt="Chat Calendar" width="220" height="220">
</p>

<p align="center">
  <b>Holidays, birthdays and your own special days in your chat — on Twitch, YouTube and Kick.</b><br>
  Public holidays of 100+ countries from date.nager.at, posted once a day to Discord, Stoat and GameVox if you like.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/chat-Twitch%20%7C%20YouTube%20%7C%20Kick-9146FF" alt="Chat platforms">
  <img src="https://img.shields.io/badge/webhooks-Discord%20%7C%20Stoat%20%7C%20GameVox-5865F2" alt="Webhooks">
  <img src="https://img.shields.io/badge/tool-streamer.bot-0b73ff" alt="Streamer.bot">
  <img src="https://img.shields.io/github/license/aaskjer/ChatCalendar" alt="License">
  <img src="https://img.shields.io/github/v/release/aaskjer/ChatCalendar?include_prereleases" alt="Release">
</p>

<p align="center">
  <a href="Setup-Guide.md"><b>Setup Guide</b></a> &nbsp;·&nbsp;
  <a href="Import-String.md"><b>Import String</b></a> &nbsp;·&nbsp;
  <a href="CHANGELOG.md"><b>Changelog</b></a> &nbsp;·&nbsp;
  <a href="https://github.com/aaskjer/ChatCalendar/releases"><b>Download</b></a>
</p>

---

## In chat

```
mirabel_tv: hi chat!
YourBot: Happy 'Christmas Day', mirabel_tv!

kjell_plays: !birthday 22.7.
YourBot: Saved, kjell_plays: your birthday is on July 22.

ostwind: !nextholidays
YourBot: Upcoming Official Holidays: 'Veterans Day' on 11/11/2026, 'Thanksgiving Day' on 11/26/2026, ...
```

Every chatter is greeted once per holiday — also when the stream runs past midnight — and once on
their birthday. In German, French, Spanish and a dozen more languages, following your country.

<p align="center"><img src="Assets/screenshots/calendar.png" alt="The Settings window" width="620"></p>

---

## What it does

- **Greets your chat on holidays.** The public holidays of your country, downloaded from
  [date.nager.at](https://date.nager.at) — and only those of your region, if you pick one (Bavaria,
  Vienna, Zürich …). New years download themselves.
- **Your own days.** Channel birthday, charity stream, anything: once on a date, or every year.
- **Birthdays.** Viewers save their own with `!birthday 24.12.` (day and month only), moderators and you
  for others with `!birthday @name 24.12.`; you add more on the Birthdays page, with a year for `{age}`.
- **Twitch, YouTube and Kick.** Greetings and answers go back to the chat they came from, from your bot
  account or the broadcaster's, on Twitch as a `/me` message if you like.
- **Discord, Stoat and GameVox.** Today's holidays and birthdays as one post a day, at the time you
  set, through a webhook. No Streamer.bot timer needed.
- **One settings window for all of it.** Country, region, time zone, every greeting with a chat preview,
  own holidays, birthdays, webhooks with a test button and a colour picker, and the log of what was said.
  It downloads the holidays itself: there is nothing to run by hand.

---

## Commands

They ship switched off: enable them under `Commands` in Streamer.bot.

| Command | What it does |
|---|---|
| `!holiday` · `!feiertag` · `!ferien` … | Today's holidays, or that there is none today. On one's birthday, the birthday greeting. |
| `!nextholidays` · `!feiertage` … | The next holidays; your own ones and the next birthdays too, if you switch them on. |
| `!nextbirthdays` · `!birthdays` · `!geburtstage` | The next birthdays alone, as many as you set (5 by default). |
| `!birthday 24.12.` · `!geburtstag` · `!bday` | Saves your birthday. `!birthday` alone shows it, `!birthday remove` deletes it. |
| `!birthday @name 24.12.` | Moderators and the broadcaster: the same for someone else (`@name`, `@name remove`). |

---

## Requirements

- [Streamer.bot](https://streamer.bot) 1.0 or newer on Windows (exported from 1.0.7).
- Internet for the holidays (date.nager.at) and, on Twitch, pronouns (pronouns.alejo.io).

Import, setup and every page of the window are in the [Setup Guide](Setup-Guide.md).

---

## Credits & links

[aaskjer on Twitch](https://twitch.tv/aaskjer) · [Streamer.bot](https://streamer.bot) ·
[nate1280](https://www.patreon.com/c/nate1280/home) · [Nager.Date](https://date.nager.at) ·
[Alejo's pronouns](https://pronouns.alejo.io) ·
[Streamer.bot extensions thread](https://extensions.streamer.bot/t/twitch-calendar/2282)

Formerly *Twitch Calendar*. None of the services above is affiliated with or endorses Chat Calendar.
