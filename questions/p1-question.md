# Sahara Tyre — WhatsApp Promotional Campaign Platform — Interview Questions

**Stack**: Node.js, Express, React Native, Expo, TypeScript, Google Sheets API, WhatsApp Web API, GitHub Actions, Render

---

## Backend Tech Lead Lens

### Technical
1. You used Google Sheets API as your primary contact store. Walk me through the read/write pattern — how did you handle concurrent batch processing without hitting API rate limits? What's the Sheets API's write quota and how did you design around it?
2. Your WhatsApp Web session persistence strategy — how did you manage reconnection on crash? What data did you persist and how did you detect a stale session vs a valid one?
3. You mention "rate-limit-safe randomized delays" for batch processing. What was the delay algorithm? Did you implement jitter, exponential backoff, or a token bucket? Why?
4. How did you handle campaign errors mid-execution? If message 37 of 500 failed, did you retry, skip, or abort? What was your partial-failure strategy?

### System Design
5. Design this system for 100x scale — 1M contacts, 50 concurrent campaigns, sub-hour delivery. Where does Google Sheets break? What would you replace it with and why?
6. The system uses WhatsApp Web (a consumer API) rather than WhatsApp Business API. What are the practical limits of WhatsApp Web for campaign delivery? At what user threshold would you be forced to migrate to Business API?

### Behavioral
7. You chose Google Sheets over a traditional database for this project. Walk me through your decision process. What was the trade-off and what would you do differently in production?

---

## Full Stack Engineer Lens

### Technical
8. Walk me through the full data flow: from the React Native app sending a campaign request, to the Node.js backend processing, to WhatsApp delivery, and back to the UI with status updates. Where are the breakpoints?

### Frontend
9. Your React Native app has tab-based navigation with vehicle category filtering. How did you structure the navigation tree? Did you use React Navigation? How did you pass campaign state between screens?

### Behavioral
10. This project has a mobile app + backend. If you had to rebuild only one side (frontend or backend), which would you cut and why?

---

## Product Manager Lens

### Product
11. Who is the user of this campaign platform? A marketing manager, a sales agent, or the tire shop owner? How would the UI and campaign workflow differ for each persona?
12. What's the single metric you'd track to determine if this platform is successful? Delivery rate? Campaign completion time? User engagement? Revenue from campaigns?

---

## HR / Talent Acquisition Lens

### Behavioral
13. This is a WhatsApp campaign tool — how did you handle the risk of your IP or phone number being banned by WhatsApp for automated messaging? What's your understanding of WhatsApp's ToS around bulk messaging?
