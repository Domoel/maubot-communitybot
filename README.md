# Advanced Community Bot

<p align="center">
  <a href="https://ztfr.eu/matrix">Zeitfresser Matrix Community</a>
</p>

Advanced Community Bot is a powerful Maubot plugin designed to help you manage Matrix communities that are structured around Spaces. It combines moderation tools, automation, and community-driven workflows into a single, opinionated solution that focuses on simplicity, reliability, and clean integration with modern Matrix clients.

The plugin is particularly well suited for communities that want strong control over membership, clear moderation flows, and a balance between automation and human oversight.

It was originally created as Community Bot by <a href="https://github.com/williamkray/maubot-communitybot">William Kray</a>. This fork uses his bases and adds additional features and refinments to the bot.

---

## 🛠 What this bot is for

Advanced Community Bot is not meant to replace large-scale moderation frameworks like Draupnir or Mjolnir. Instead, it focuses on providing a cohesive set of tools for managing structured communities with minimal overhead.

It is a strong fit if you:

- already run Maubot or prefer lightweight, Python-based tooling  
- manage a space-centric community with multiple rooms  
- want simple but effective moderation and automation features  
- prefer an opinionated setup over highly complex configuration  

Communities that benefit most from this plugin typically follow a structure where a central Space controls access to multiple rooms, often with a mix of private and public entry points.

---

## 🚀 Core Features

### Community initialization

The bot can bootstrap an entire community structure from scratch using a single command. It creates a Space, sets up initial rooms, assigns permissions, and prepares a working moderation environment.

This allows you to go from zero to a fully structured community in minutes, following best practices for access control and moderation.

---

### Greetings and join notifications

The bot can greet users when they join rooms and optionally notify moderators or administrators about new arrivals.

Messages support templating and make use of native Matrix pills for users and rooms, resulting in clean, readable, and interactive notifications.

---

### Activity tracking and pruning

User activity is tracked across rooms, allowing you to generate reports on inactive members and take action where needed.

You can:
- identify inactive users  
- exclude specific accounts from pruning  
- remove inactive members from your community  

This is especially useful for keeping invite-only communities clean and manageable over time.

---

### User management

Advanced Community Bot provides a full set of tools for managing users across your entire space:

- kick users from all rooms  
- ban and unban users globally  
- optionally redact recent messages when banning  
- prevent unauthorized invitations via power level control  

All actions are applied consistently across your space and its child rooms.

---

### Crowd moderation

The bot includes a lightweight, community-driven moderation system.

Users can report problematic messages by reacting with configured emojis. Reports are aggregated and forwarded to a moderation room, including direct links to the affected content.

If enabled, the bot can automatically redact messages once a majority of users in a room have reported them. This allows communities to react quickly to spam or abuse, even when moderators are not immediately available.

---

### Moderation workflows

Moderation messages, reports, and redactions are designed to be easy to read and interact with.

All relevant entities—users, rooms, and events—are linked using native Matrix URIs, allowing moderators to jump directly to the relevant context inside their client.

This significantly improves the speed and usability of moderation workflows.

---

### Room management

The bot simplifies working with rooms inside a space:

- create rooms with consistent settings and permissions  
- enforce join restrictions based on space membership  
- automatically invite configured users  
- manage encryption settings during creation  

Room creation follows a predictable pattern, ensuring consistency across your community.

---

### Room archival and replacement

Rooms can be archived or replaced when necessary.

Archiving removes a room from active use while preserving its history. Replacement allows you to create a fresh room while retaining names and aliases, which is useful when permissions become inconsistent or settings need to be reset.

---

### Public banlist support

The bot can consume external banlists in read-only mode. When users join, they are checked against these lists and automatically banned if necessary.

This allows you to integrate with broader moderation ecosystems without managing policies yourself.

---

### Message redaction and filtering

Basic content moderation features are included:

- automatic redaction of messages based on keywords  
- optional blocking/redaction of file uploads  
- configurable scope (global or per room)  

These tools are intentionally simple and best used in combination with a well-structured community setup.

---

### User verification

Optional verification flows can be enabled for specific rooms.

New users are required to complete a simple challenge via direct message before being allowed to participate. This can help reduce spam in publicly accessible entry rooms.

---

## 🧠 Design Philosophy

Advanced Community Bot follows a few key principles:

- **Keep things simple** – avoid unnecessary configuration complexity  
- **Leverage Matrix-native features** – rely on client capabilities where possible  
- **Be opinionated** – provide sensible defaults instead of endless options  
- **Stay maintainable** – prioritize clean structure and predictable behavior  

The codebase has been continuously refactored to support these goals, with a strong focus on reducing duplication, improving structure, and making future changes easier.

---

## ✨ Modern Matrix-Native Experience

One of the core goals of this project is to align closely with how modern Matrix clients behave.

User and room references throughout the bot are rendered using native `matrix:` URIs instead of legacy `matrix.to` links. This means that interactions happen directly inside the client, without external redirects, resulting in a faster and more seamless experience.

At the same time, the visual representation has been intentionally simplified. Instead of exposing raw Matrix identifiers, the bot displays clean, human-readable names such as display names and room names. In supporting clients, these elements appear as clickable pills, combining clarity with interactivity.

## ⚙️ Configuration

Configuration is handled via `base-config.yaml`.

Templates support placeholders such as `{user}`, `{room}`, `{user_id}`, and `{room_link}`. The `{user}` and `{room}` placeholders render as clickable elements using native Matrix URIs, while link-specific placeholders retain their original behavior.

The configuration surface is intentionally kept minimal. Advanced customization can still be achieved by adjusting internal constants if needed.

---

## 📦 Installation

Install the plugin like any other Maubot plugin:

- package it using `mbc build` or use the pre ompiled .mbp file in the release section.
- upload it via the Maubot web interface  

Make sure the bot has sufficient permissions in your rooms (especially for kicking, banning, and redacting messages), otherwise some features will not function correctly.

---

## 🧭 Final Notes

Advanced Community Bot aims to strike a balance between usability and control. It provides the tools needed to manage a structured Matrix community effectively, without overwhelming administrators with complexity.

If your use case requires highly advanced policy management or federation-wide moderation, you may want to look at tools like Draupnir. For most community-centric setups, however, this bot offers a practical and efficient solution.
