# boxxcat-community

> This repository is **archived**.

This project was originally released as **BetterBoxx**, a Node.js chatbot designed to integrate with KakaoTalk messaging clients. It has since been renamed to **boxxcat-community** and is no longer under active development.

We are keeping this repository available for **historical reference and self-hosting enthusiasts**, but it will **not receive further updates**.

---

# The Future of This Project

While this repository remains open-source, development has moved to a **new platform** with significantly improved architecture, performance, and features.

You can use the **new generation of this chatbot** at:

**https://www.boxx.cat**

The new platform includes:

- A modernized architecture
- Continuous updates and improvements
- Extended **proprietary plugins**
- A hosted chatbot platform that removes the need for manual setup

Users and organizations who want a **fully managed chatbot service** can sign up directly on the platform.

---

# What This Repository Is

This repository contains the **self-hostable version of the original BetterBoxx chatbot**.

Features include:

- Node.js based chatbot server
- KakaoTalk integration using [`@remote-kakao/core`](https://github.com/remote-kakao/core)
- Basic OpenAI integration
- A plugin system located in `/plugins` for extending functionality
- Client/server structure for running the chatbot from Android devices

This repository hosts both **server and client code**.

The documentation below describes configuring the **server component**.

Pasting `reference/client.js` into  
[Messenger Bot R](https://play.google.com/store/apps/details?id=com.xfl.msgbot&hl=ko&gl=US)  
should make the client work out of the box.

---

# Getting Started

Clone the repository:

```bash
git clone https://github.com/BoxxCatLabs/boxxcat-community.git
```

Navigate to the directory and install dependencies:

```bash
cd boxxcat-community
npm install
```

Node.js **18 or higher** is required.

---

# Configuration

Before running the chatbot, configure environment variables.

Rename `.env.example` to `.env` and set your OpenAI API key.

```
OPENAI_API="Bearer YOUR_OPENAI_API_KEY"
PORT="3000" # optional
```

Room authentication can be enabled using:

```
USE_AUTH=true
AUTH_ROOM="ROOM_ID_1,ROOM_ID_2,ROOM_ID_3"
```

For additional security, it is recommended to rename room identifiers with random strings when configuring the client.

---

# Usage

Start the chatbot:

```bash
npm start
```

To keep the process running:

```bash
forever start index.js
```

The server will listen on the port defined in `.env` (default: `3000`).

---

# Functionality

Commands are triggered by specific prefixes.

Features include:

- `Ping!` → replies with `Pong!`
- Messages prefixed with `>>` are forwarded to the OpenAI API and return AI-generated responses.

---

# Plugin System

Plugins can extend the chatbot with additional functionality.

**Bundled plugin:**
- `openai-gpt` – Forwards messages prefixed with `>>` to OpenAI's `gpt-4o-mini` model and replies with the AI response.

You can write your own plugins.

---

# Using Android as a Server

KKS wrote a guide for running this system on Android using Termux.

Guide:
[https://iris-kilometer-f84.notion.site/readme-43ed9bb956ae44e4824105087c83a1f5](https://iris-kilometer-f84.notion.site/readme-43ed9bb956ae44e4824105087c83a1f5)

Archived copy:
[https://web.archive.org/web/20240319035753/https://iris-kilometer-f84.notion.site/readme-43ed9bb956ae44e4824105087c83a1f5](https://web.archive.org/web/20240319035753/https://iris-kilometer-f84.notion.site/readme-43ed9bb956ae44e4824105087c83a1f5)

---

# Developing Plugins

To build your own plugin:

1. Create a new folder inside `plugins`
2. Add a JavaScript file with the plugin name
3. Implement plugin metadata and handlers such as:

- `name`
- `version`
- `onLoad`
- `onMessage`

The `openai-gpt` plugin included in this repository can be used as a reference implementation.

---

# Credits

This project uses code from
[https://github.com/remote-kakao](https://github.com/remote-kakao)

Special thanks to the developers who contributed to the ecosystem around KakaoTalk automation.

---

# License

This repository is licensed under the **MIT License**.

You are free to use, modify, and distribute the code.

---

# Final Note

This project represents an **early generation of the BetterBoxx chatbot ecosystem**.

For the **actively maintained version**, improved infrastructure, and hosted services, visit:

**[https://www.boxx.cat](https://www.boxx.cat)**
