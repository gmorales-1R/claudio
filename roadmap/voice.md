# Voice Interaction

## Vision

Natural, life-like voice dialogue with Claudio — not dictation or one-shot commands
but real back-and-forth conversation with full workbench context.

## The Problem with Current Voice AI

- No persistent context across turns
- STT breaks on technical vocabulary
- Feels like talking to a hotline, not a collaborator
- Loses the thread on multi-step technical discussions

## What "Life-like" Means Here

- Understands workbench context without re-briefing every session
- Handles interruptions and corrections naturally
- Can execute — not just talk. "Add a high priority task for Monday" actually does it
- Low latency — no perceptible delay between speech and response
- Aware of who is speaking in a multi-user team setting

## Approaches to Explore

### 1. Claude + WebRTC + Whisper
- Browser captures audio, streams to Whisper for STT
- Text hits Claude API with full workbench context injected
- Response streamed back as TTS (e.g. ElevenLabs or browser native)
- Closest to a real dialogue loop

### 2. Claude Voice Mode (native)
- Already exists, low setup cost
- Context injection still unsolved
- Good for brainstorm, bad for execution

### 3. Twilio / Daily.co + Claude
- Phone or browser call routed through Claude
- More infrastructure but team-friendly (no app needed)

## Key Challenges

- Context injection at session start (the brief approach is a workaround, not a solution)
- STT accuracy on technical terms (agent names, file paths, commands)
- Execution bridge — voice intent → Bridge → git push → Vercel
- Multi-user voice (who is speaking, what are their permissions)

## Dependencies

- Stable Bridge agent
- Supabase or persistent DB (stateless voice + stateless files = chaos)
- Auth layer for multi-user

## Status

Deferred — PoC phase. Revisit after persistent DB is in place.
