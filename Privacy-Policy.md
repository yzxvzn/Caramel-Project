# Privacy Policy — Caramel Project

**Last Updated:** November 5, 2026

This Privacy Policy explains what data is collected, stored, and processed by Discord bots and applications operated under **Caramel Project** (collectively referred to as "the Bot" or "the Service"), in accordance with the [Discord Developer Policy](https://support-dev.discord.com/hc/en-us/articles/8563934450327-Discord-Developer-Policy).

---

## 1. Data We Collect and Store

The Bot only collects and stores the minimum Discord data necessary to provide its moderation, security, and utility features. Depending on which features a server enables, the Bot may store:

| Feature | Data Stored | Storage File |
| :--- | :--- | :--- |
| **Warnings (`/warn`)** | Guild ID, target User ID, moderator tag, warning reason, and timestamp | `warns.json` |
| **Giveaways (`/giveaway`)** | Guild ID, Channel ID, Message ID, Host User ID, prize text, end time, participant User IDs, and excluded User/Role IDs | `giveaways.json` |
| **Autoresponders (`/autoresponder`)** | Guild ID, configured trigger phrases, response text, and restricted Channel IDs | `autoresponders.json` |
| **Sticky Messages (`/sticky`)** | Guild ID, Channel IDs, last posted Message IDs, and sticky message content | `sticky.json` |
| **Honeypot (`/honeypot`)** | Guild ID, monitored Channel ID, panel Message ID, and moderation action logs (triggering Message ID, User ID, timestamp, and action status) | `honeypot.json`, `honeypot-actions.json` |
| **Verification (`/verify`)** | Guild ID, verification Channel ID, and panel Message ID | `verify.json` |
| **Script Panel (`/script`)** | Guild ID, Channel ID, and active panel Message ID | `script-panels.json` |
| **Temporary Whitelist (`/whitelist`)** | Guild ID, User ID, granted Role ID, duration, and expiration timestamp | `whitelist.json` |
| **AFK Status (`/afk`)** | Guild ID, User ID, custom AFK message, timestamp, and original nickname | `afk.json` |
| **Channel Lock (`/lock`)** | Guild ID, Channel ID, and previous `@everyone` permission overwrite bitfields | `lockStates.json` |
| **24/7 Voice Stay (`/alive`)** | Guild ID and target Voice Channel ID | `voiceStay.json` |

---

## 2. Gateway Intents & Transient Data Processing

To operate properly, the Bot uses the following Discord Gateway Intents:
1. **Message Content Intent (`GatewayIntentBits.MessageContent`):**
   - Used in real time solely to detect prefix commands (default `.`), match configured `/autoresponder` triggers, process `/afk` mentions, and enforce `/honeypot` channel protection.
   - **The Bot does NOT log, archive, or store general chat messages or conversation histories.**
2. **Guild Members Intent (`GatewayIntentBits.GuildMembers`):**
   - Used to resolve member profiles for `/whois`, `/avatar`, moderation commands, role hierarchy validation, and temporary `/whitelist` role management.
3. **Guild Voice States Intent (`GatewayIntentBits.GuildVoiceStates`):**
   - Used to maintain and restore 24/7 voice channel connections configured via `/alive`.

---

## 3. How We Use Information

Data collected by the Bot is used exclusively for:
- Executing commands requested by server administrators, moderators, and members.
- Persisting server configurations (such as active giveaways, sticky messages, autoresponders, voice sessions, and role expirations) across bot restarts.
- Displaying server-specific moderation statistics (such as honeypot ban counts and member warning records).

---

## 4. Data Sharing and Third Parties

- **No Selling or Sharing:** Caramel Project **never** sells, rents, trades, or shares any user or server data with third parties.
- Data is accessed only by the Bot's automated systems and authorized **Caramel Project** developers for maintenance and debugging purposes.

---

## 5. Data Retention and Deletion

Most stored data can be cleared directly by server administrators at any time using built-in commands:
- **Warnings:** `/warn reset`
- **Autoresponders:** `/autoresponder delete` or `/autoresponder clear`
- **Sticky Messages:** `/sticky delete` or `/sticky clear`
- **Honeypot Configuration:** `/honeypot reset`
- **Whitelist Records:** `/whitelist reset`
- **Voice Session:** `/leave`
- **AFK Status:** Automatically removed when the user sends a message or runs `/afk` again.

Server owners may also request complete removal of all stored guild data by removing the Bot from their server or contacting the **Caramel Project** developer team.

---

## 6. Changes to This Privacy Policy

Caramel Project may update this Privacy Policy from time to time to reflect new features or regulatory requirements. Updates will be reflected by the "Last Updated" date at the top of this document.
