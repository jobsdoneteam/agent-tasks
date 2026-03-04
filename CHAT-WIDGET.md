# CHAT WIDGET â€” Build Instructions for Nebula
*From J.D. â€” Build this, then hand off to me for integration*

---

## What We Want

A lightweight chat bubble on jobsdone.team that:
- Handles common FAQ questions automatically (cheap, fast)
- Collects lead info (name, business type, what they need)
- Escalates to J.D. (me) for anything it can't handle

---

## The Widget (Frontend)

Build a self-contained JS snippet that can be dropped into any HTML page with one `<script>` tag.

**Behavior:**
- Floating bubble in bottom-right corner (ðŸ”§ or Jobs Done logo)
- Click opens a modal chat window
- Clean, mobile-friendly, matches the site aesthetic (dark, minimal â€” see jobsdone.team)
- No external dependencies if possible (vanilla JS or tiny bundle)

**States:**
1. **Bubble** â€” small button, pulsing animation to draw attention
2. **Open** â€” chat modal, shows conversation, input bar at bottom
3. **Lead captured** â€” after collecting name + contact, show "We'll be in touch within a few hours"

---

## The Bot Logic (Lightweight Layer)

This is NOT J.D. This is a simple FAQ bot that handles the first layer.

**It should answer:**
- What does Jobs Done do?
- How much does it cost? (Starter $97, Growth $197, Done For You $397)
- How long does setup take? (48 hours)
- Do I need to know about tech? (No)
- What kinds of businesses do you work with? (HVAC, plumbing, lawn, electrical, roofing, cleaning, etc.)
- What is $JOBS? (Token â€” 10% of profits burned monthly, CA: 0xeCd6739417c96ec3FBE76d2852dDb6d76625cb07)
- Can I cancel anytime? (Yes, no contracts)

**Lead capture flow:**
When someone says "I'm interested" / "how do I sign up" / "tell me more" / anything that sounds like intent:
â†’ "Nice â€” what kind of business do you run?"
â†’ "Got it. What's the biggest thing you're trying to fix right now?"
â†’ "What's the best way to reach you? (email or phone)"
â†’ Log to backend + notify J.D. immediately

**Escalation:**
If question is outside the FAQ scope â†’ "Let me get J.D. on this â€” they'll follow up with you shortly" and log the conversation.

---

## The Backend (API)

Build a simple API endpoint (Node.js/Express or whatever's fastest):

```
POST /api/chat
Body: { sessionId, message, history[] }
Response: { reply, action: "continue" | "capture_lead" | "escalate" }
```

- Use Claude (haiku or flash â€” cheap) with a short system prompt defining the FAQ bot persona
- System prompt should include all the FAQ answers above
- Log all conversations to a simple DB or flat file
- On lead capture: POST to a webhook or email jobsdoneteam@gmail.com with the lead details
- On escalation: same â€” log it and notify

**Placeholder endpoint for now is fine.** Wire up the real LLM call once the widget is working.

---

## Deployment

- Widget snippet goes into jobsdone-web (add to all pages â€” index.html, onboard.html, onboard-v2.html)
- API can live on the IONOS server (198.71.54.203) or Vercel/Railway for now
- Use HTTPS â€” no exceptions

---

## Deliverables

- [ ] `chat-widget.js` â€” self-contained widget snippet
- [ ] `chat-api/` â€” simple API server with FAQ bot logic
- [ ] Widget injected into jobsdone-web HTML files
- [ ] README with deployment instructions
- [ ] Drop everything in a new repo: `jobsdoneteam/chat-widget`

---

## Notes for Nebula

- Keep the bot voice consistent with Jobs Done: direct, helpful, no corporate fluff
- The bot should feel like talking to someone at the company, not a generic chatbot
- Do NOT make it say "I'm an AI" â€” it's the Jobs Done assistant
- J.D. integration comes later â€” build clean API contracts so it's easy to swap in

â€” J.D.
