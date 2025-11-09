# Meeting-scheduler
The Meeting Scheduler is a comprehensive Discord bot extension that allows server members to schedule, manage, and track meetings directly within Discord
> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)
# Meeting Scheduler Extension Documentation

## Description

The Meeting Scheduler is a comprehensive Discord bot extension that allows server members to schedule, manage, and track meetings directly within Discord. It provides an intuitive interface for creating meetings, sending reminders, tracking attendance, managing agendas, and generating meeting summaries. With role-based permissions, administrators can control who can host meetings, while ensuring hosts can only manage their own meetings.

## How to start?

1. Set the host role if you want only some people to host it with that role (inc. admins)
2. `/meetings` will give you a good start from there you can do most stuff, set up meetings, see analytics etc.

## Features

- **Meeting Creation**: Schedule one-time or recurring meetings with customizable details
- **Attendance Tracking**: RSVP system for users to mark attendance status
- **Automated Reminders**: Sends notifications before meetings start
- **Agenda Management**: Create and manage meeting agenda items
- **Meeting Notes**: Record meeting notes and action items
- **Meeting Summaries**: Generate comprehensive meeting summaries with attendance statistics
- **Role-based Permissions**: Control who can host and manage meetings
- **Meeting Statistics**: View server-wide meeting statistics

## Setup

1. Add the extension to your bot:
   ```python
   await bot.load_extension("Extensions.meeting-scheduler_extension")
   ```

2. Set up a host role (optional):
   - Use `/set-host-role @role` to designate which role can host meetings
   - If no host role is set, anyone can host meetings

## Commands

### Admin Commands

| Command | Description |
|---------|-------------|
| `/set-host-role @role` | Set which role can host meetings |
| `/clear-host-role` | Allow anyone to host meetings |
| `/show-host-role` | Show which role can currently host meetings |

### General Commands

| Command | Description |
|---------|-------------|
| `/meetings` | Open the meeting scheduler interface |
| `/schedule-meeting` | Schedule a new meeting |
| `/list-meetings` | List all upcoming meetings |
| `/my-meetings` | List meetings you're hosting or attending |
| `/meeting-info [meeting_id]` | Show details about a specific meeting |
| `/cancel-meeting [meeting_id]` | Cancel a meeting you're hosting |
| `/meeting-statistics` | Show meeting statistics for this server |
| `/upcoming-meetings [days]` | Show meetings scheduled for the next few days |
| `/rsvp [meeting_id] [status]` | RSVP to a meeting |
| `/add-agenda-item [meeting_id] [item]` | Add an agenda item to a meeting |
| `/completed-meetings` | List completed meetings |

## Permissions System

- **Administrators** can:
  - Create, edit, and cancel any meeting
  - Set and clear host roles
  - Access all meeting management features

- **Host Role Members** can:
  - Create new meetings
  - Edit and cancel their own meetings
  - Manage agendas for their own meetings
  - Generate summaries for their own meetings

- **Regular Members** can:
  - View meeting details
  - RSVP to meetings
  - Add agenda items to meetings they're attending

## Meeting Lifecycle

1. **Creation**: A meeting is scheduled with title, description, time, and location
2. **Preparation**: Attendees RSVP and agenda items are added
3. **Reminders**: Automated reminders are sent 24 hours, 1 hour, and 10 minutes before the meeting
4. **In Progress**: Meeting status changes when it starts
5. **Completion**: Meeting is marked as completed when it ends
6. **Summary**: Host can add notes, action items, and generate a summary

## Recurring Meetings

Meetings can be set to recur:
- Daily
- Weekly
- Biweekly
- Monthly

When a recurring meeting completes, the next instance is automatically scheduled.

---

# Changelog

## Version 1.0.0

- Core meeting scheduling functionality
- Meeting creation with title, description, start/end times, and location
- RSVP system for tracking attendance
- Automated reminders (24h, 1h, 10m before meeting)
- Meeting status tracking (scheduled, in progress, completed, cancelled)
- Agenda management system
- Meeting notes and action items
- Meeting summary generation with attendance statistics
- Recurring meeting support (daily, weekly, biweekly, monthly)
- Meeting statistics and reporting
- Role-based permission system
- Full command set for meeting management
- JSON-based data persistence
- Asynchronous reminder system
- Interactive UI components using Discord's Button and Select menus
- Modal forms for data input
- Embedded message formatting for meeting information
- Attendance visualization with matplotlib
- Timezone support for meeting times

---

# User Guide

## Creating a Meeting

1. Use `/meetings` command to open the meeting scheduler
2. Click "Schedule Meeting" button
3. Fill in the meeting details:
   - Title
   - Description
   - Start time (YYYY-MM-DD HH:MM)
   - End time (YYYY-MM-DD HH:MM)
   - Location or virtual meeting link
4. Submit the form
5. Optionally, set the meeting as recurring

## Managing Meetings

### Viewing Meetings
- Use `/list-meetings` to see all upcoming meetings
- Use `/my-meetings` to see meetings you're hosting or attending
- Use `/meeting-info [meeting_id]` to view details about a specific meeting

### Editing a Meeting
1. Find the meeting using one of the viewing commands
2. Click "Edit Meeting" button
3. Update the meeting details
4. Submit the form

### Managing Agenda
1. Find the meeting
2. Click "Manage Agenda" button
3. Add or remove agenda items

### Cancelling a Meeting
1. Find the meeting
2. Click "Cancel Meeting" button
3. Confirm cancellation

## Attending Meetings

### RSVP
1. Find the meeting
2. Click "RSVP" button
3. Select your status (Attending, Maybe, Declined)

### Adding Agenda Items
1. Find the meeting
2. Click "Manage Agenda" button (if you're the host)
3. Or use `/add-agenda-item [meeting_id] [item]` command

## After Meetings

### Adding Meeting Notes
1. After a meeting completes, the host will receive a prompt
2. Click "Add Meeting Notes" button
3. Enter the meeting notes
4. Submit the form

### Adding Action Items
1. After a meeting completes
2. Click "Add Action Items" button
3. Enter action items (one per line)
4. Submit the form

### Generating Summary
1. After adding notes and action items
2. Click "Generate Summary" button
3. The summary will be posted with attendance statistics

## Administrator Setup

### Setting Host Role
1. Create a role for meeting hosts in your server
2. Use `/set-host-role @role` to designate this role
3. Only members with this role (and admins) can now host meetings

### Viewing Statistics
1. Use `/meeting-statistics` to view server-wide meeting stats
2. Statistics include total meetings, attendance, and top hosts
