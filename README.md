# rescue-resolve
Detects spoken promises during calls and sends follow-up actions via Slack.

---

## 🔁 Atomic Loop

1. Bot joins Zoom/Meet (or processes .wav)
2. Whisper ASR → transcript
3. GPT-4o/Regex → detect promises ({actor, verb, object, deadline, impact_score})
4. Trigger Slack DM with 3 options: ✅ Do it · ⏰ Remind · 🛑 Not a promise
5. Agent drafts email or reopens ticket
6. 4h later: "Did we save you?" ✔️/❌

---

## 🔨 Tech Stack

- ASR: Whisper API (large-v3)
- NLP: GPT-4o + Regex fallback
- Bot: Slack Bolt (Node.js)
- DB: Supabase Postgres
- Agent: Gmail API + Linear REST
- Hosting: Vercel
- Analytics: Supabase Dash + SQL
- Storage: S3 for intent labels

---

## 🧪 Success Criteria (v0.1)

- ≥ 5 ✅ Do it actions executed across 3 teams
- ≥ 3 unsolicited "you saved me" quotes
- False-positive rate < 10%
- Daily Slack DM per active seat
