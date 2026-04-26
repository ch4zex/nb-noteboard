# NB NoteBoard - Productivity & Life-Management Dashboard

<a href="https://ch4ze.net/">

The **NB NoteBoard** is a highly encrypted (Zero-Knowledge / E2EE), highly customizable, and feature-rich productivity dashboard. It combines note management, task planning (To-Dos), a calendar, a Pomodoro timer, and Quick-Links in a seamless, keyboard-controllable interface.

---

## 📑 Agenda (Table of Contents)

1. [Security & Authentication](#1-security--authentication)
2. [User Interface & Layout](#2-user-interface--layout)
3. [Keyboard Shortcuts](#3-keyboard-shortcuts)
4. [Editor Commands (The Magic Line)](#4-editor-commands-the-magic-line)
5. [Notes, To-Dos & Calendar](#5-notes-to-dos--calendar)
6. [Productivity Tools (Timer & Links)](#6-productivity-tools-timer--links)
7. [Mobile Push Notifications](#7-mobile-push-notifications)
8. [Theming & Personalization](#8-theming--personalization)
9. [Admin Dashboard](#9-admin-dashboard)

---

## 1. Security & Authentication

The dashboard uses true **Zero-Knowledge End-to-End Encryption (E2EE)** directly in your browser.

* **Registration:** When creating your account, a cryptographic key (MEK) is generated locally. Only you know your password, which encrypts and decrypts this key. The server does not store any readable data of your notes or configurations.
* **Recovery Key:** After registration, a long **Recovery Key** is displayed. **Save it securely!** If you forget your password, this is the only way to recover your data. (Login using your `Username` and `REC-...` as the password).
* **Change Password:** Type `:passwd NEW_PASSWORD` into the search/command bar at the top and press `Enter`.
* **Stay logged in:** The NoteBoard uses a single cookie to keep you logged in. This session automatically expires after 12 hours or upon logging out.

---

## 2. User Interface & Layout

The dashboard is structured into two main views: **Standard View** and **Fullscreen Mode**.

### Standard View
The default view is a compact, fixed-size grid that provides a quick overview of all important information. It is designed for quick access and at-a-glance updates.
*   **Top:** The global search and command bar.
*   **Left Column:** Contains the Clock and Pomodoro Timer widgets.
*   **Right Column:** Houses the Quick Access Links and Upcoming Events.
*   **Bottom:** The main Note Editor, which can be expanded for more space (`Space + Q`).

### Fullscreen Mode (`Space + F`)
This mode is designed for deep, focused work. It expands the dashboard to fill your entire screen, creating a distraction-free environment.
*   **Collapsible Sidebars:** The left and right widgets become sidebars.
*   **Additional Widgets:** In this mode, the **Scratchpad** (left) and **Task Manager** (right) become available.
*   **Layout Control:** You can minimize all sidebar widgets at once with `Space + M` to create a clean "rail" view. Widgets can also be collapsed individually by clicking their header or the `[ - ]` button.

---

## 3. Keyboard Shortcuts

NB NoteBoard is designed to keep your hands on the keyboard. Press and hold the `Spacebar` in combination with the following keys:

### Navigation & Layout
* `Space + F` ➔ Toggles **Fullscreen Mode** (Productivity Mode).
* `Space + Q` ➔ Expands / shrinks the central note editor.
* `Space + M` ➔ Minimizes / Maximizes all sidebar widgets simultaneously.
* `Space + S` ➔ Focuses directly on the global **Search bar**.

### Note Management
* `Space + W` ➔ Instantly creates a **new tab** in the current category.
* `Space + Left / Right Arrow` ➔ Cycles through your tabs or categories.
* `Space + [1-9]` ➔ Jumps directly to the tab or category at that specific position (1 to 9).
* `Space + ESC` ➔ Switches back from a note tab to the category overview.
* `Tab` ➔ Intelligently switches focus between the Dashboard and the Text Editor.

### Pomodoro Timer
* `Space + E` ➔ Starts, Pauses, or Resumes the timer.
* `Space + R` ➔ Resets the timer to the default focus duration.

---

## 4. Editor Commands (The Magic Line)

Almost everything in the text editor is controlled via "Commands". Type the command (including the colon) into the editor and press `Enter`.
**💡 Pro-Tip:** Many of these functions (like renaming, timestamps, colors, and mode switching) can also be triggered simply by clicking the corresponding **buttons in the toolbar** on the right side of the NoteBox. You can choose whether you prefer typing commands or using the UI buttons!

### Management
* `:title Your Title` ➔ Renames the current tab to "Your Title".
* `:cat Your Title` ➔ Renames the current category.
* `:ts` ➔ Inserts a timestamp at the current cursor position (e.g., `15.08.2024, 14:30:00`).
* `:onetodo` ➔ Pins a single "One-Todo" task permanently above your text.
* `:help` ➔ Opens this documentation directly inside the dashboard.

### Colors & Styling
* `:tabred`, `:tabgreen`, `:tabblue`, `:tabmauve`, `:tabpeach` ➔ Changes the accent color of the current tab.
* `:catred`, `:catgreen`, etc. ➔ Changes the accent color of the current category.

### Mode Switching (Transforms an empty tab)
* `:todo` ➔ Transforms the tab into an interactive To-Do list.
* `:cal` ➔ Transforms the tab into a global calendar view.
* `:themeedit` ➔ Opens the editor for creating custom themes.

### System Control (type in Search/Command Widget)
* `:themes` ➔ Opens the Theme Selector (Alternative: Button top right).
* `:passwd NewPassword` ➔ Securely changes your login password.
* `:logout` ➔ Locks the dashboard and logs you out.


---

## 5. Notes, To-Dos & Calendar

### Text Notes & HTML
By default, every tab is a simple text field. By entering specific commands, you can transform this text field into various other tools.

### To-Do Lists (Command: `:todo`)
To-Do lists are interactive.
* **Drag & Drop:** Click and hold the icon to the left of the checkbox to smoothly drag tasks up or down.
* **Enter:** Press Enter while typing to quickly add a new task below.
* **Bell Icon:** Set a time for a reminder (ntfy connection).
* **One-Todo:** Using `:onetodo`, you can pin a single checkbox to the top of a standard text note.

### The Global Calendar (Command: `:cal`)
As soon as you convert a tab via `:cal`, you'll see a monthly overview.
* Click on a day to add tasks (these work just like To-Do lists).
* Days with pending tasks are marked with colored dots.
* **Birthdays / Annual Events:** Use the 🎂 icon next to a task. This will automatically copy the event to the same day every year.

---

## 6. Productivity Tools (Timer & Links)

### Pomodoro Timer
Supports the Pomodoro Technique (Focus times and breaks).
* Click the small minute numbers at the bottom of the widget to adjust default times for focus and breaks (e.g., 30 and 5).
* **Focus Core (Gamification):** For every `X` seconds (Default: 900s / 15 Min) of concentrated work, a blue "Core" bar charges up in the right panel. This playfully tracks your daily progress. (Use the small `>` icon in the widget to expand the panel).

### Upcoming Events
This widget displays all tasks and birthdays from your calendar, starting today and into the future, sorted chronologically. Clicking an event jumps directly to the corresponding day in the calendar.

### Quick Access Links
Hover over the "Quick Access" widget and click the `+` symbol that appears.
You can now enter a display name (left) and the corresponding URL (right) for each row. Clicking the red `x` again saves the links, which will then be available as a clickable list.

---

## 7. Mobile Push Notifications

You can connect the dashboard with the **ntfy** app (available for iOS/Android) to receive Pomodoro timer alerts and task reminders as push notifications on your smartphone.
The ntfy server runs locally alongside the NoteBoard. They communicate internally, and ntfy connects directly to your app without relying on third-party services.

1. Open the help menu in the dashboard (`:help`).
2. Scroll all the way down. There you will find a unique, randomly generated **Topic Code** (e.g., `ntfy_1a2b3c4d...`).
3. Download the `ntfy` app on your device.
4. Subscribe to a new topic on the server `https://push.ch4ze.net` and enter your code (e.g., `ntfy_1a2b3c4d...`).

**Privacy Mode:** For privacy reasons, the cleartext of the task is *not* sent to the push server by default (it just says "Reminder due"). 
If you want to read the exact task in the notification, enable the "Show Task Content" toggle below your code in the Help menu.

---

## 8. Theming & Personalization

Open the Theme Selector (`:themes` or via the button in the top right). Here you can switch between pre-made **Catppuccin** color palettes (Mocha, Macchiato, Frappe, etc.).

### Creating Custom Themes (`:themeedit`)
1. Create a fresh note tab.
2. Type `:themeedit` and press Enter (or use the Theme Editor button on the right).
3. Here you can override all HEX colors of the system, adjust the gap size, and define custom CSS background patterns.
4. Click "Save Theme 1 / 2 / 3" to save and apply the theme.
5. Your custom themes will appear at the very top of the `:themes` window.

Your last used theme is also saved in your browser's `localStorage` to provide a themed login screen even when your session has expired.

---
