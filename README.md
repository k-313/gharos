# GharOS — Your Household Admin, Handled on WhatsApp

[![Hackathon 2026](https://img.shields.io/badge/Hackathon-2026_Pitch-128C4A?style=for-the-badge)](https://github.com)
[![WhatsApp Cloud API](https://img.shields.io/badge/Interface-WhatsApp_Cloud_API-25D366?style=for-the-badge)](https://business.whatsapp.com/)
[![Protocol](https://img.shields.io/badge/Protocol-Model_Context_Protocol_(MCP)-171A19?style=for-the-badge)](https://modelcontextprotocol.io/)

An AI-powered household assistant that automatically detects utility bills, schedules smart reminders to your calendar, and organizes roommate or family shared expenses — completely inside WhatsApp with zero app installations.

---

## 🌟 Key Highlights

- **100% WhatsApp Native**: Zero app downloads, zero new passwords. Multi-tenant households interact directly in 1-on-1 and group chats.
- **Model Context Protocol (MCP)**: Decoupled, sandboxed architecture connecting LLM reasoning with Google Workspace (Gmail, Calendar) and household ledgers.
- **Human-in-the-Loop Consent**: The AI detects and proposes; zero autonomous financial movements or calendar writes without 1-tap confirmation.
- **Dual Presentation Views**: Includes an interactive 16:9 widescreen presentation deck (`Deck Mode`) and a continuous SaaS landing page (`Website Mode`).

---

## 🏗️ MCP Architecture

```text
[ WhatsApp Client ]
        │
        ▼ (Meta Cloud Webhook)
[ GharOS AI Agent Core ] (Gemini 2.5 + Guardrails + Structured JSON)
        │
        ▼ (Standardized MCP Protocol)
[ MCP Client Gateway ]
        │
        ├─► [ Gmail MCP Server ] ────► Read whitelisted utility bills (BESCOM, Airtel, Gas)
        ├─► [ Calendar MCP Server ] ─► Create & sync due date events (Google Calendar)
        └─► [ Ledger MCP Server ] ───► PostgreSQL shared household expense splits
```

---

## 🚀 Quickstart

### Run Locally

1. Clone or download this repository:
   ```bash
   git clone https://github.com/<your-username>/gharos-presentation.git
   cd gharos-presentation
   ```

2. Start a local preview server:
   ```bash
   python -m http.server 8085
   ```

3. Open in your browser:
   ```text
   http://localhost:8085
   ```
   *(or double-click `index.html` to open it directly)*

---

## ⌨️ Presentation Keyboard Shortcuts

| Shortcut | Action |
|:---|:---|
| `→` / `Space` / `↓` | Next Slide |
| `←` / `↑` | Previous Slide |
| `F` | Toggle Borderless Fullscreen (16:9) |
| `Home` / `End` | Jump to Slide 1 / Slide 10 |

---

## 🛡️ Security & Privacy Principles

1. **User Approval Required**: Explicit click-to-approve confirmation required for all reminders and ledger updates.
2. **Least Privilege**: Scoped read-only access strictly for utility invoice emails (`label:bills`).
3. **Immutable History**: Full audit trail accessible at any time via `/audit`.
4. **Data Deletion**: Immediate cryptographic erasure on "Forget My Data".

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.
