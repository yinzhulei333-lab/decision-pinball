# PROCESS.md

## Starting idea

I wanted to make "pinball", but every pinball game on the market is about scoring points. I asked: what if the ball's job isn't to score, but to *decide*? People around me constantly struggle with tiny decisions ("what to eat", "buy or not"), and asking a friend always gets "whatever you want". So the concept became a **decision machine**: you feed it your dilemma, fire a ball, and the machine answers with physics. The key design choice was making the journey visible — a hidden random number would feel meaningless, but watching the ball bounce, nearly land in one pipe and then tip into another creates suspense and makes the answer feel earned.

## Design / code changes made during development

1. **Slots match user input.** Early versions had a fixed number of slots. I changed the answer pipes to be generated from the user's options (2–6), split around the cannon (left/right), so the board itself responds to input.
2. **Launcher moved to the bottom with aiming.** The first version dropped the ball from the top. I rebuilt it as a **bottom cannon** the user aims (slider or arrow keys) and fires (button or Space). This adds a second deliberate input (aiming), makes each round feel like the player's own shot, and gives the ball a much longer, more watchable flight.
3. **Anti-stuck nudge.** During testing the ball sometimes came to rest balanced on a peg. I added a stuck-detector: if the ball's speed stays near zero for ~55 frames, it gets a small random kick, plus a second failsafe for balls loitering near the cannon.
4. **Mario-style restyle.** I replaced the generic neon look with a playful game aesthetic (sky-blue sky, drifting clouds, brick ceiling/ground, spinning coins, green warp pipes, chunky press-down buttons) so the machine feels friendly and toy-like rather than like a developer tool.
5. **"A pinch of fate".** A tiny random horizontal impulse on every coin bounce keeps trajectories from ever looking identical on rerolls.

## User trial

*(Fill this in yourself after the trial — one paragraph is enough.)*

- **Who tried it:** a classmate / friend (not identified).
- **What I observed:** e.g. — they first clicked FIRE without adding any options and were surprised by the toast; they tried pressing fire repeatedly while the ball was in the air; they didn't notice the aim slider at first.
- **One improvement I made because of the trial:** e.g. — after seeing them ignore the slider, I added arrow-key aiming and the dotted aiming guide so the cannon's direction is obvious before firing. *(Replace with your real observation and the real change you made — or explain why you kept the design as it was.)*

## AI tools used

I used an AI coding assistant (WorkBuddy) to help build this project:

- **What I used it for:** generating the first version of the canvas physics simulation and page layout; brainstorming the "decision machine" concept; drafting README.md and this PROCESS.md.
- **One suggestion I kept:** the AI suggested the anti-stuck "nudge" for balls resting on pegs — a real failure mode I hadn't noticed, and it made the physics robust.
- **One suggestion I changed/rejected:** *(example)* the AI first proposed determining the winning pipe before launch and steering the ball toward it; I rejected this because the answer should come from the visible physics, not a hidden script — the whole point is watching the outcome happen.

*(Adjust these to match what actually happened for you. Keep this section honest.)*

## Credits

- All code written for this assignment with AI assistance as described above.
- No borrowed code, datasets, or media. The visual style is *inspired by* classic Mario games but uses no copyrighted assets — everything is drawn with Canvas/CSS and synthesized with WebAudio. Course examples were consulted for general HTML/Canvas patterns but no code was copied.
