# PAX — Director of First Impressions

PAX — Latin for peace — is the live welcome at Mission Informatics' front door.

Mission Informatics is a new kind of IT service and digital creative agency in Toronto — for established actors and public figures, entrepreneurs, and small business owners. Web design, systems, video, photography, branding, and technology coaching, built as one connected system.

A small business's website is its front door, and for most, nobody is home. PAX is home. He appears as a video-conference-like presence — eyes and the line between them, the line changing colour with the moment — greets the visitor with captions always on, speaks in a real recorded human voice, and takes typed questions through the Ask box. Visitors who would rather speak than type can open the live conversation — Talk to PAX, below.

PAX answers strictly from a locked knowledge pack of public information about the business — 21 scripted answers covering what Mission Informatics does, how an engagement starts, its privacy stance, AI, apps, rescue, managed care, backups, and more.

> "Only what the work needs. A client never has to tidy their computer or fear embarrassment before we arrive."

Anything outside the pack, PAX says so plainly and walks the visitor to the EXPLORE MY DREAM questionnaire — seven questions in the visitor's own words. Nothing typed is sent while they answer; when the visitor chooses Finish, the answers are emailed to the business through a small private middleman in the founder's own Google account — no third-party form service touches them. He never invents an answer, never names a price, a platform, or a phone number.

## The demo journey (seven beats)

1. **Arrival** — the visitor clicks PAX; the greeting sound plays once; the welcome.
2. **What Mission Informatics does**
3. **How an engagement starts** — questionnaire, discovery, information gathering, a written proposal with one flat price, contract, onboarding, closing at delivery. Nothing moves forward without the client's sign-off.
4. **The privacy answer**
5. **The fallback** — anything outside the pack routes to a person.
6. **The questionnaire walk-in** — "Tell us your dream — not just the problem."
7. **The close**

The wider 21-answer pack sits behind those seven beats, ready for the visitor's own questions.

Colour carries emotion: calm cyan at rest, warm amber while listening, with distinct colours per answer and rainbow reserved for a celebration moment only.

## Talk to PAX — the live conversation

A visitor can also simply talk with PAX. Beside the scripted journey sits a live conversation: the visitor taps "Talk to PAX," and PAX welcomes them, softly asks their name first, and only then introduces himself — greeting them by name. From there the conversation is open: questions and follow-ups in the visitor's own words, answered in a live voice, with captions as he speaks.

The live conversation is powered by Gemini, grounded in the business's own published web copy — the same public material the scripted pack was built from. PAX is creative in expression and safe in substance: he invents no prices, timelines, promises, clients, or contact details. Anything outside the copy routes the visitor to the questionnaire, or to the team at care@missioninformatics.ca, with a reply within one business day.

The page itself holds no API key and no secret. A small private middleman in the founder's own Google account holds the key and hands the page a short-lived, single-session token whose session settings — model, voice, and grounding — are locked on the server side before the conversation begins. If a live session cannot start, the page says so plainly and the scripted journey carries on exactly as before.

## Running the demo

Open `index.html` in any browser — no server, no dependencies. The submitted build is a single self-contained file: PAX's recorded voice lines and the display font are embedded, so the scripted journey runs exactly as published, anywhere; the live conversation and the questionnaire send connect through the middleman when a visitor chooses them. The same build is live at https://muse.ai/s/pax-demo-xyt6n9xshsnxei/NgtCQA7pz5GUwx2fQwDLerkJfsv7aInJuOj5kf8hhmY

Click PAX to begin. PAX's lines play as recorded audio in a real human voice; the browser's own speech is only a fallback if a recording cannot play.

## Modes

- **The scripted journey** — the seven beats and the wider 21-answer pack run entirely from this one file: no API key, no cost, no network call. Questions return their scripted answers word for word; anything else returns the fallback. The `API_KEY` field in the code is intentionally empty — no key is used or shipped in this demo.
- **Talk to PAX** — an optional live conversation beside the scripted journey, powered by Gemini through the private middleman described above. The scripted journey remains the skeleton; the live layer never replaces it.

## One setting to know

`REPLY_PROMISE` — a single constant in the CONFIG block at the top of `index.html` — carries the fallback's promise of when a person replies, spoken and displayed in Beats 5 and 15. It is set in one place only, and currently reads "within one business day."

## Built by

A founder who is not a developer, working with an AI teammate: the founder brought PAX's character, judgment, and the demo; the teammate brought the knowledge pack, conversation design, and visitor-eye QA.

_Built for the Meta Global AI Developer Hackathon — Indie track, "Build for Your World" theme._
