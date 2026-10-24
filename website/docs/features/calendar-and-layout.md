---
title: Calendar & Layout
sidebar_position: 1
---

The **Family Week Calendar** is the centerpiece card: a full-screen, tablet-friendly calendar with each person's events in their own color, the week's meals, weather for each day, and reminders.

![Week view: meals at the top of each day, colored events below, a pencil on events that can be edited](/img/screenshots/calendar-week.webp)

*All screenshots on this site use a made-up demo household (Mom, Dad, Emma, Leo and a shared Family calendar).*

## Views

- **Week view and Month view**, switchable from the card itself, with a
  default-view setting. Tapping a day in Month view jumps to that week.
- **The Week button can show three layouts** (Settings → General →
  **Week button shows**, saved per device):
  - **Week**: a column per day, with each day's meals at the top.
  - **Planner**: a row per day and a column per person, so you can read
    across one person's week. It fills the whole card, and over a holiday
    photo it gets a solid (or, on a glass theme, frosted) background so it
    stays readable.
  - **Agenda**: a plain list of the coming days' events and reminders, no
    columns, ideal for a narrow screen or a sidebar. It uses the same
    **Days shown** setting as Week, and can include meals too.
- **Layout ideas**: one tap fills in a starting layout for your screen:
  Week, Portrait (7 days on 2 rows), Agenda or Two-Week Ahead. See
  [Settings Modal → Layout ideas](/docs/settings-modal#layout-ideas-this-device-only).
- **Month + Day (split view)**: Month view can show the selected day's
  events in a panel beside the grid, with a **Go to this week** shortcut.
- **Optional hourly timeline** view, toggle is **device-specific** (saved to
  that browser/tablet only, via `localStorage`). Range is configurable start
  hour to end hour, with the end able to reach **Midnight**.
- **Word-wrapped event names** in both Week and Month view: full titles are shown rather than truncated.
- **Phones**: on a narrow screen the week stacks one day per row, and the
  person pills wrap onto two lines.

![Month view with the day panel open](/img/screenshots/calendar-month.webp)

![Planner layout: a row per day and a column per person](/img/screenshots/calendar-planner.webp)

![Agenda layout in the Liquid Glass Dark theme](/img/screenshots/calendar-agenda.webp)

## People and calendars

- **A column and color per person**: each person's calendar becomes their
  column, in their color. A person can have **more than one calendar**
  (say, a work Google calendar and a Local Calendar): their first
  calendar becomes their column and the rest are shown inside it, in the
  same color.
- **Colors come from Home Assistant**: a newly added calendar starts in
  the color Home Assistant (or Google, for a Google calendar) already uses
  for it. Linking a calendar to a person gives it that person's color,
  unless you've changed it since. Tap a calendar's color dot in Settings
  and pick **Reset to calendar color** to go back to its own color.
- **Shared calendars** (a Family calendar, a school calendar, a child
  without their own login) get a column of their own.
- **Picked by name, from Settings**: calendars are added under
  Settings → General → **Calendars**, choosing from a list of your Home
  Assistant calendars by name, with no YAML editing. The name fills in
  automatically and a new calendar gets a color nobody else is using. See
  [Settings Modal → Calendars](/docs/settings-modal#calendars).
- **First run**: a fresh install with no calendars shows a
  **+ Add your first calendar** button that opens Settings straight to the
  Calendars section.
- **Person pills**: the colored pills under the week heading show each
  person's event count. Tap pills to show just those people; tap again
  to turn them off.
- **Prevent duplicate events** (on by default): when the same event is on
  two calendars you show (e.g. an invite on both parents' calendars), it
  only appears once. Repeating events still show every occurrence.
- **Per-calendar badges**: any calendar can define a keyword to watch for in
  event titles, a short badge (e.g. "N") to display next to the date when it
  matches, and a separate keyword for events that should be hidden from the
  grid entirely (e.g. a background custody-schedule calendar).

<img src="/HA-Family-Hub/img/screenshots/calendar-phone.webp" alt="The calendar on a phone" width="320" />

## Adding and editing events

- **Add-event button**: a floating **+** button with two tabs, **Calendar
  Event** (calendar, title, all-day or timed, date, optional end date for
  multi-day events, repeat, location, notes, optional reminder lead time)
  and **Reminder** (a standalone to-do-backed reminder with its own
  date/time and an optional "roll over to next day if not completed"
  toggle), without leaving the card.
- **Starts on your calendar**: New Event picks the signed-in person's own
  calendar, and only offers calendars that can actually take new events
  (a read-only Holidays feed isn't in the list).

![The New Event form](/img/screenshots/add-event.webp)

- **Edit pencil**: events on a calendar that Home Assistant can edit (for
  example the built-in **Local Calendar**) show a small ✎ pencil. Tap it to
  open the event with its edit form already open: title, date, times and
  location. Tapping anywhere else on the event opens its details as usual.
  You need the **Edit/move calendar events** permission to see it.
- **Read-only calendars say so**: events from a calendar that can't be
  changed from Home Assistant (e.g. Google Calendar, a holidays feed) don't
  get a pencil, and their details popup explains that they're read-only
  and where to edit them instead.
- **Edit, countdown and delete on one line**: at the bottom of an event's
  details are **Edit event**, **Use as countdown** and **Delete event**
  (each only when it applies).
- **Duplicate an event**: open **Edit event** and tap **Duplicate**. A
  small **Duplicate to…** window asks for the copy's date and start/end
  time (just the date for an all-day event). It starts on the event's own
  date and time, has **Tomorrow** and **Next week** shortcuts, and moving
  the start time keeps the copy the same length. Nothing is added until
  you tap **Add copy**. The copy keeps the title (as the edit form has
  it), location and details, goes on the same calendar, and the original
  isn't touched. On calendars that can't be edited from Home Assistant
  but can take new events (like Google Calendar), the button is
  **Duplicate event** and its form already has the date and time, so it
  just has **Add copy**.

<img src="/HA-Family-Hub/img/screenshots/duplicate-picker.webp" alt="The Duplicate to… window with Tomorrow and Next week shortcuts, a date, and start and end times" width="380" />

- **Repeating events**: the New Event form has a **Repeat** section
  (daily, weekly on chosen days, monthly or yearly, every N, with an
  optional end date). It only appears for calendars that can store
  repeating events. A repeating event's details say **Repeats** and list
  the other dates in the series, and editing one asks whether to change
  **This event**, **This and following events** or **All events in the
  series**.

![An event opened from its pencil, with the edit form open](/img/screenshots/event-edit.webp)

- **Multi-person events**: any event's info popup gets an **"Also for"**
  row: check off any other household member and the event shows in their
  column too (Week/Month view), with a diagonal collage/stripe background
  blending everyone's colors instead of one solid color. The event still
  lives on exactly one real calendar; tagging is purely a display overlay,
  nothing is duplicated onto anyone else's actual calendar.
- **Event extras**: reminders (5 minutes to 1 day before), a checklist, and
  **Use as meal** (turn an event into that day's breakfast, lunch or dinner).

## The Right Now bar

Turn the top of the calendar into a live **Right Now** strip: the time and
weather, plus a tile for each person showing whether they're home, what
they're doing right now (with a progress bar until it ends), and what's
next. Sensor pills, like a phone's battery level, show up on the tile too.

![The Right Now bar across the top of the calendar](/img/screenshots/right-now-top.webp)

Turn it on from Settings → General → **Calendar top bar style** →
**Right Now** (saved per device, so the kitchen tablet can have it while a
phone doesn't). Then choose:

- **Placement**: **Top** shares one row with the calendar's navigation;
  **Left** or **Right** show it as a sidebar beside the whole calendar. On
  a phone it's always a strip across the top.
- **Size** (Top only): **Small** shows names and the current event,
  **Medium** adds Home/Away and sensor pills, **Large** (the default) adds
  the clock and weather.
- **Right Now shows**: turn the clock & date or the weather off.
- **Who's shown**: uncheck anyone (or anything, like a Holidays calendar)
  that shouldn't get a tile. They still show everywhere else.

The bar's heading (clock, date and weather), like the calendar's own
week label beside it, turns white when the background behind it is dark,
so it stays readable on dark themes.

The bar shows the same people as the calendar, in the same colors. Home/Away
comes from each person's presence entity and the extra pills from their
sensors, both set in their profile (Settings → Users → **Presence &
sensors**).

![The Right Now bar as a sidebar on the left](/img/screenshots/right-now-sidebar.webp)

The same view is also available as its own card, `family-right-now-card`,
for any other dashboard. See [Card Configuration](/docs/card-configuration#right-now-card).

## Printing

- **Print/export view**: prints (or "Save as PDF" via the browser's print dialog) whichever view, week or month, is currently on screen, carrying over the active theme's colors.
