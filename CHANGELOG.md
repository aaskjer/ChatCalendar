# Changelog

## v1.0.0-Pre-Release.1 - 2026-10-26

### Added
- A Settings window: run the trigger 'Test' of the new action '[CC] - .Settings'. Its pages are
  Chat (greetings on/off, `!nextholidays`, `!nextbirthdays`), Announcements (webhooks, covered with an eye to
  show them, and a Test button; time, look, a colour picker), Calendar (country, region, time zone, chat language, year, download),
  Holidays (greetings of the official holidays, your own holidays), Birthdays, Messages (your own texts
  with a chat preview, bot or broadcaster, /me), Log, Help and About. It saves `configs.json` next to `holidays.json`, which every action reads; a damaged
  file is kept as `configs.json.broken` and the window falls back to the last save. The header shows when a
  newer release is out on GitHub (aaskjer/ChatCalendar).
- YouTube and Kick: chatters there are greeted on holidays, and both commands answer in the chat they came
  from (split for YouTube's 200 characters). Untick a trigger or a command source to leave a platform out.
- New action 'Announce Holidays': posts today's holidays to Discord, Stoat and GameVox webhooks once a day at
  the time set in the Settings window. A timer inside the script checks every minute, so no Streamer.bot timer
  is needed and the action history gets one entry a day. A failed webhook is tried again after 15 minutes, at
  most three times a day, without posting twice to the ones that worked.
- Own holidays without a year: a date like `12-24` (or `24.12.`) comes back every year, in the greeting,
  Upcoming Holidays and the announcements. 29 February is the 28th in other years.
- Birthdays in `birthdays.json`, next to `holidays.json`. Viewers save theirs with the new command
  `!birthday 24.12.` / `!geburtstag` (day and month only; `!birthday` shows it, `!birthday remove` deletes it);
  the streamer adds others on the Birthdays page, with a year for `{age}` and an own greeting. Chatters are
  greeted on their birthday once that day, the announcements list the day's birthdays, and Upcoming Holidays
  can list the next ones.
- Moderators and the broadcaster save, show and remove other viewers' birthdays with `!birthday @name 24.12.`
  (`@name`, `@name remove`). On Twitch the name is looked up, so the entry keeps the user id; others ask in vain.
- Messages from the bot or the broadcaster account, and on Twitch as a /me message.
- Regions: official holidays that only count in other regions (e.g. Epiphany outside DE-BW, DE-BY, DE-ST) are
  left out of the greeting, Upcoming Holidays and the announcements. A code no holiday uses is named in the
  log, together with the ones that exist. Own holidays always count.
- Greetings on holidays and on birthdays can be switched off separately; the command still answers.
- `!nextbirthdays` (`!birthdays`, `!geburtstage`): the next birthdays alone, 5 by default, at most 25.
- A log of what was said and posted: `Logs\ChatCalendar-YYYY-MM-DD.txt`, kept 30 days, shown on the Log page.

### Fixed
- Holidays download again: date.nager.at dropped its CSV export, '[CC] - Calendar Setup' now uses its JSON API.
- `{holidayName}` was empty, and two holidays on the same day were announced as one.
- The command answered nothing on days without a holiday.
- Upcoming Holidays failed for country codes without a translation (AT, CH, GB, PL ...); they get German or
  English text with their own date format now.
- `IndependenceDayMessage` and other per-holiday arguments are found whatever their capitalisation.
- No more `Hello @,` when there is no user name, and no error in the log for every viewer without pronouns.

### Changed
- No more Set Argument sub-actions: every setting is made in the Settings window. An argument of the same name
  in an action still wins over `configs.json`. Updating from an older version: the country, region and time
  zone in `holidays.json` are taken over; webhooks and your own texts are entered once in the window.
- All holidays live in `holidays.json`. `holidays.csv` is no longer read; its own holidays are taken over once.
- Renamed from Twitch Calendar to Chat Calendar: the action group and commands (`ChatCalendar - ...`), the log
  prefix `[Chat Calendar - ...]`, the README (`Chat-Calendar-README.txt`) and the export `ChatCalendar.sb`.
- Everything lives in the folder `Chat Calendar` in the Streamer.bot folder. Holidays of older versions
  (`C:\streamer.bot\Twitch Calendar`, or `Twitch Calendar` in the Streamer.bot folder) are copied over on the
  first run.
- '.. Setup Action ..' is now '[CC] - Calendar Setup' and has no trigger: nothing has to be run there. The Settings
  window runs it when it opens without holidays (or without this year's), and when another country, region,
  time zone or year is saved.
- '[CC] - Calendar Setup' keeps your own greetings and own holidays, also into the next year, and keeps the previous
  file as `holidays.json.bak`. 'Save and download now' in the Settings window downloads every year again.
- When a new year begins (or from November on, for the next one), the other actions run '[CC] - Calendar Setup'
  themselves; saving another country, region, time zone or year in the Settings window runs it too.
- Every chatter is greeted once per holiday, also when the stream runs past midnight (trigger: Twitch Chat
  Message instead of First Words).
- A time zone (e.g. `Europe/Berlin`) sets when a day begins; without it, the PC's clock does.
- The command's answer on days without a holiday and `{pronounType}` follow the country, or the chat language
  set in the Settings window. Bavarian is the chat language 'Boarisch'; the country BY (Belarus) gets Russian.
- Upcoming Holidays shows at most 25 holidays and pauses a second between chat messages.
