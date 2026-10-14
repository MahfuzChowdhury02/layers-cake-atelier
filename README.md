# Layers — Cake Atelier

A scroll-driven landing page for a cake atelier, built from AI-generated photography and video. It's a single `index.html` with no framework and no build step.

## What's on the page

- **Scroll story (Slice / Layer / Finish).** Real footage plays as you scroll: a knife cuts a chocolate layer cake, the slice slides out to show vanilla sponge, cream and raspberry jam, then vanilla cream pours over, swirls are piped and a cherry drops on top.
- **The cakes.** Four photographed slices with an order basket.
- **Your turn.** The same footage, by hand: drag down on the cake to cut it, then press and hold to pour. Keyboard: down arrow to cut, hold Space to pour.
- **Let's bake yours.** Contact links and the finished cake.

## Run locally

```bash
python -m http.server 8000
```

Then open http://localhost:8000.

## How the footage works

- `assets/frames/960/` (desktop) and `assets/frames/640/` (phones) hold 240 WebP frames from two linked 10-second clips: frames 1–120 are the cut, 121–240 are the cream and cherry.
- Frames load coarse-to-fine, so scrubbing works before every frame has arrived. Scroll position (or your drag and hold) picks the frame and draws it to a canvas.
- `assets/src/` keeps the original keyframe PNGs and source MP4s. The page doesn't load them.

## Not wired up yet

- The order basket and checkout are a demo. No payment is taken.
- Brand, cakes, prices and contact links are placeholders.
