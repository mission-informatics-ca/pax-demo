# Design and testing notes — PAX demo

How this demo was designed, built, and verified. Everything here is public-safe by design: PAX was built only from information Mission Informatics already publishes.

## How it was built

PAX was built by a founder who is not a developer, directing an AI teammate. The code was produced with Muse Code, Meta's coding agent powered by Muse Spark, with the founder making every character, wording, and boundary decision. The conversation design, the knowledge pack, and the visitor-eye quality checks came from the same partnership.

## Architecture

- **One self-contained file.** `index.html` carries everything — markup, logic, the recorded voice lines, and a subset display font — so the demo runs identically anywhere, with no server and no dependencies.
- **A locked knowledge pack is the scripted brain.** PAX answers 21 scripted questions from a fixed pack of public information about the business. Free-text questions are routed through an ordered set of topic checks; anything that matches nothing returns one honest fallback that routes the visitor to a person. PAX cannot improvise, because improvisation is where a concierge starts inventing prices, policies, and promises.
- **Boundary discipline is a feature.** Hours, location, prices, timelines, client names, and the company phone number are deliberately absent from the pack. Asked for any of them, PAX says so plainly and offers the questionnaire instead. For an IT business whose clients must trust it with their systems, a greeter that keeps a confidence is the product working as intended.
- **Nothing is sent until the visitor chooses.** The questionnaire walk-in states this on screen; typed answers are held only in the page while the visitor answers, and are emailed to the business only when they press Finish.
- **No key in the page.** The page itself holds no API key and no secret — the CONFIG block's `API_KEY` field is intentionally empty. A small private middleman — a Google Apps Script in the founder's own Google account — holds the Gemini key. It mints short-lived, single-session tokens whose session setup is locked server-side: the model, the voice, and the grounding, read at runtime from the business's own published web copy. The same middleman relays finished questionnaire answers to the business inbox. The scripted journey runs entirely from the local pack, exactly as before.

## Voice and accessibility

- PAX speaks in a real recorded human voice; the browser's built-in speech is only a fallback if a recording cannot play.
- Captions are always on.
- A Speak button uses the browser's speech recognition where available (turn-by-turn, so replies play as single uninterrupted takes). On iPhone Safari, which offers web pages no recognition hook, the demo shows a keyboard-microphone hint instead of pretending the button works.
- Colour carries emotion: calm cyan at rest, warm amber while listening, distinct colours per answer, slow breathing at rest and a pulse while speaking. Rainbow is reserved for one celebration moment.

## Testing

- **Routing batteries.** The free-text router was tested with scripted case batteries: 20 cases after the first expansion, then 37 cases for the final 21-answer build. All pass, including the boundary cases that matter most — "can you fix my car," "what are your hours," and "where are you located" all return the fallback rather than an invented answer.
- **Static QA pass.** Every scripted line was checked word-for-word against the approved script; the company phone number was verified absent from the file; the API key field was verified empty; the scripted pack was verified to run with no network call.
- **Live-layer testing.** The live conversation was tested on a real phone by the founder. The first version answered too slowly, so the grounding was slimmed down — from the full web copy to a lean essentials version — and the page's audio playback was reworked with a jitter buffer; response speed was then verified on the phone. The middleman's token mint and its questionnaire email delivery were each verified end to end.
- **The font lesson.** An early shareable build embedded a complete font file, and the sharing platform's review blocked it without naming a cause. Bisection isolated the font file as the trigger; the fix was to subset the font to only the glyphs the page displays (the words "MISSION INFORMATICS") — a 2.5 KB file in place of 61 KB, with no visible change. The submitted build embeds only the subset.

## What judging sees, honestly

Two layers, one discipline. A scripted concierge with a locked pack — word-for-word answers, routing that knows its edges, a fallback that tells the truth — and, beside it, a live Gemini conversation grounded in the same public material, held to the same boundaries. In both layers PAX invents nothing, and what he cannot answer he routes to a person. The discipline is the product; the live layer is that discipline, speaking freely.
