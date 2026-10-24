---
title: Changelog
sidebar_position: 8
---

This page mirrors the actual tagged releases on [GitHub](https://github.com/JVarhol/HA-Family-Hub/releases), newest first, in the words of their original release notes. Not every version bump got its own tagged release, so there are gaps between some of these — this is the real release history, not a log of every intermediate build. Releases older than v1.103.0 are in the [changelog archive](/docs/changelog-archive).

## Latest builds (not yet tagged)

These builds are newer than the last tagged GitHub release below. They're summarized here so the docs match what you'll see once they're released.

- **v1.168.84**: downloading a Family Hub backup (Configure → Restore a backup → Export) now really saves the file to your device, and the backup screens say snapshots are taken every 12 hours.
- **v1.168.83**: new installs start on the **Slate** theme (existing households keep theirs), and screens set to the Agenda layout can save their device settings again.
- **v1.168.82**: if you use UniFi, the Wi-Fi QR code option suggests UniFi's own QR code instead, and offers to turn those codes on in Home Assistant when they're off.
- **v1.168.81**: Pop-ups and menus on the Liquid Glass themes are less see-through, so they're easier to read.
- **v1.168.80**: Duplicating an event while editing it now asks for the copy's date and time first, with Tomorrow / Next week shortcuts.
- **v1.168.79**: Liquid Glass themes now look like glass everywhere - Chores, Rewards, To-Do, Timers, Goals, Pantry, Recipe Box, Right Now and Today all show the theme's background through frosted surfaces; the planner stays frosted and the Settings Save bar is solid.
- **v1.168.78**: More menu buttons can show your **UniFi** Wi-Fi network's own QR code, live from Home Assistant, so it stays right when the password changes.
- **v1.168.77**: two new themes that match Home Assistant - **HA Light** and **HA Dark** - plus calendar fixes: the Agenda layout idea picks Agenda, a new view shows as soon as Settings closes, and the Planner fills the card and stays readable over holiday photos.
- **v1.168.76**: five new languages - Dutch, French, Italian, Portuguese (Brazil) and Polish - and German/Spanish complete again; text that used to be stuck in English on the cards, the Theme Builder page and the setup screens now translates too.
- **v1.168.75**: calendars take their own color from Home Assistant (Google's color for a Google calendar) when added, and tapping a calendar's color offers **Reset to calendar color**.
- **v1.168.74**: timers and alarms overhaul - every timer rings (starting on the screen that started it) and keeps ringing until someone taps Stop on any screen, phone or speaker; speakers are linked to people or house timers so only the right ones ring; alarms survive restarts and go off on the exact second; a new Timer log; and timer start/cancel events plus start/cancel/stop actions for automations.
- **v1.168.73**: an event's Edit, Use as countdown and Delete buttons share one line, and you can **duplicate** an event from its edit form (or with Duplicate event on calendars like Google that can't be edited here).
- **v1.168.72**: the Right Now card shows the title you give it, its Away and battery pills are easy to see again, tiles line up in even columns, the weather shows the current temperature, and an empty card offers a Go to Calendar button.
- **v1.168.71**: lock a More menu pop-up so only the people you pick can open it (straight away on their own login, with their PIN on a shared or kiosk screen); ready-made starting points for new buttons (Babysitter / house info, Emergency contacts, Address book, Guest Wi-Fi); and a security fix: kiosk PINs are stored privately with stronger hashing and lock for 5 minutes after 5 wrong tries.
- **v1.168.70**: More menu buttons: icons save correctly (whole emoji, and Home Assistant `mdi:` icons), and the QR code now asks what it should show (Wi-Fi, link, contact card, phone, text message, email or plain text) and builds the code for you.
- **v1.168.69**: the Right Now bar's clock, date and weather now use the same color as the calendar's date-range label, so they turn white over a dark background photo too.
- **v1.168.68**: an editable **More menu**: show, hide and reorder its items, and add your own buttons that open a pop-up with a heading, text, a QR code made from any link, up to 2 photos and a link button (Settings → General → More menu).
- **v1.168.67**: fixes GitHub issue #10: cards now show German/Spanish (or any Home Assistant language) right away instead of only after opening Settings, and weekday names, hour labels and event times follow each user's Home Assistant language and 12/24-hour setting.
- **v1.168.66**: a **Just me** option on the Chores and Rewards cards (whoever is signed in, or PIN-logged-in on a kiosk). The My Chores card is deprecated: saved dashboards switch to Chores set to Just me + Chore Bin automatically. The Right Now heading and the calendar's week label turn white on dark backgrounds.
- **v1.168.65**: Waiting to Recur on the Chores card is now a name pill like everyone else's (and can be hidden in the card editor). A small ✎ pencil on events from calendars Home Assistant can edit (like Local Calendar) opens the event straight into its edit form.
- **v1.168.64**: fixed the calendar grid collapsing to a thin strip with the Right Now bar at the top at Medium or Large size.
- **v1.168.63**: a **People on this card** option for the Chores and Rewards cards (YAML: `people`), so a card can show just some of the household.
- **v1.168.62**: colored name pills across the top of the Chores and Rewards cards, just like the calendar's: tap people to show only them.
- **v1.168.61**: the Right Now bar sizes itself to its content, has cleaner tiles, and shows Home/Away and sensor pills again; the Today and Right Now cards read your live settings.
- **v1.168.60**: simpler calendar setup: calendars are picked by name in Settings → Calendars (the one place to link them to people), a "+ Add your first calendar" button, New Event starts on your own calendar and skips read-only ones, read-only events say so, a sticky Save button, and setup-wizard calendars now become columns.
- **v1.168.59**: repeating events show every occurrence again with "Prevent duplicate events" on; members set up only from the Users tab get their extra calendars merged; the Right Now bar shows exactly the calendar's people; faster Right Now tiles; safer recipe imports from links.

## Changelog

### 1.135.4 (pre-release)

Pre-release to attempt to fix an open issue. Some changes, all in progress. Release notes in next update.

### 1.132.65

This update goes over and unifies a lot of the UI with the calendar card; most cards were touched in this update. Some more tweaks to function, and a few much-needed added features, like clicking a day and then adding a calendar event, which now defaults to it.

**Reminders**
- Roll over to next day now allows you to select what days are applicable.

**Chores**
- Chores can now be marked as important.
- Chores can now be assigned to multiple people; you mark them done separately for each person.
- Added a common Routine library to make routine creation faster and easier.
- Confetti pop when a chore is completed.
- Routines can now be completed by a sensor changing.

**Calendar**
- Cleaned up Month UI to make sure all-day events show at the top.
- Incorporated greyed-out passed events in Month view.
- Selecting a day in Week or Month view, then clicking Add calendar event or Add reminder, now defaults to the selected day.
- Calendar events can now be deleted (some calendar integrations, like Google Calendar, don't support this and will throw an error).
- Reminders and calendar events can now have lists attached: choose a preexisting list, or create one that only exists on that calendar event or reminder.

**Family Today**
- Added a new compact view, and the option to add a reminder or calendar event from the daily Today card.

**Meals**
- Now suggests meals from your saved past dishes based on what you're typing; will recommend up to 3.

**Todo Lists**

**Other**
- Started working on multi-language support.
- New setting for where to return on screen saver wake.

**Themes**
- Cleaned up the Settings menu considerably; non-admins now have a very restricted Settings modal. Users can be marked as child accounts for further-restricted Settings.

**New cards**
- None. 😀

### 1.132.10

Fix issues with HACS.

### 1.132.9

This update, a lot of time went into fixing small issues, making the UI a little cleaner, and a ton of usability work.

**Meal Planning**
- Improved the ingredient matching some more (this will be a constant battle, but it's getting better with each update).
- Adding multiple grocery meals to a meal card results in multiple tabs at the top of the recipe viewer, so you can easily and quickly switch between the recipes.
- Fixed a bug causing the "Don't inventory" ingredients button to remove the item from the ingredients on the recipe card.

**Rewards**
- Stars now have a manager modal, so you can easily add a reason for adding or removing stars.

**Calendar**
- Better support for smaller screens; Settings for calendar now have a 3/5/7-day view option, as well as a small-screen mode that hides a lot of the top-bar UI for smaller screens.

**Todo Lists**
- Added wishlist support. Users have a to-do list assigned to them as a wish list in their settings, which can have photos and links added to it. Any user can claim items on a wish list, but the list's owner doesn't see it: great for not having multiple people buy or get the same thing. Wish list items can also be converted to rewards by assigning chore values.
- Who can see wish list claims is a permission setting, great for kiosk displays.
- To-do lists are no longer the same config across every instance of the card.
- Better layout options.

**Other**
- Multicard login: the to-do list card got a login button, and login is now persistent across every card and dashboard, so there's no more logging into Chores and Rewards separately.
- Multicard FAB: when using more than one card on a dashboard, the floating "+" buttons used to stack on top of each other; now you can choose whether the FAB sits in the bottom corner of the dashboard or of the card.
- Cleaned up the user settings; moved permissions to the bottom of each user's settings page instead of into their own tab. Better list management for users.
- Lots of little tiny things I can't think of……

**Themes**
- Every card can now have its own theme set in its settings, for building better dashboards.

**New cards**
- Menu Box (beta): a new card similar to the menu box on the calendar, letting you browse menu items and recipes. Gets a lot more attention next update.
- Timers (beta): shows every active timer; chores and rewards can now have timers, shown here. Next update will add more robust notifications and alarming for these going off.

### 1.109.6

**Meal Planning**
- Meals now have leftover ability, or multiday meals. Select days where the leftovers can be used.
- Move meal to another week: edit a meal, and under more options there's now a place to move a meal to another week.
- New option for no meal cards in Settings, for users who don't want the meal planner.
- Meal cards now allow additional recipes; add recipes for sides, desserts, and more.
- Meal cards now show a description.
- Fixed a bug preventing meals from being un-favorited.
- New permission for Edit Menu; users without it are only allowed to add suggestions.

**Chores**
- Chores can now be completed "X" times. Example: "Complete 3 loads of laundry."
- Users now have a permission to not require their chores to need approval to mark complete.
- Chores now move into a completed accordion once finished.
- Chores expiring soon now show first.
- New setting to toggle showing date due, or date and time due.
- Chores and Routines now have a login button at the top right.

**Routines**
- Routine events can now earn stars; choose to require approval or not on creation.

**Goals**
- The Goals card is now My Goals. Shows just the goals of the current user.
- Added a way to mark a goal completely, to hide it.

**Rewards**
- Users can now gift stars to another user: click the gift box and type how many to transfer.

**Calendar**
- Calendar now allows you to add people to an event on the calendar.
- New views: Portrait (a new week view for vertical monitors), Month + Day.
- New setting to grey out events passed on the calendar.

**Themes**
- Added "Liquid Glass" themes.

**New Cards**
- My Pantry and To-Do cards introduced.
