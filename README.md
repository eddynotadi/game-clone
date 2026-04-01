# NEO-RUN — Cyberpunk Endless Runner

A single-file 2D endless runner built with PixiJS v7 as a playable ad creative.

**Live:** https://eddynotadi.github.io/game-clone

## Approach

**Why Cyberpunk**
Just watched Ready Player One recently and got a bit obsessed with the aesthetic. The reference game had a clean light theme so I thought why not flip it completely and go dark, neon, cyberpunk. Wanted to make something that felt different and a bit funky rather than just copying the vibe.

**Engine**
Went with PixiJS v7, lightweight, great sprite sheet support, solid delta-time ticker. Wrote all game logic from scratch, no frameworks on top.

**Assets**
Generated everything using NanoBanana Pro on Google AI Studio. Prompted for a hooded cyberpunk runner, street props, enemies, coins and background, iterated until it all felt visually consistent. For the billboard I wanted a neon ramen shop sign, used Craiyon's background remover to clean up the edges. The sprite sheet from NanoBanana had uneven frame sizes so I wrote a small Python script to normalize it into a proper grid before embedding.

**Single File Packaging**
PixiJS is inlined minified, every asset is base64 encoded as a JS variable and loaded through a custom async pipeline with a loading bar. Final size 2.61 MB, well under 5MB. No build tools, no npm, literally just one file.

**What I added on top**
Progressive speed ramp so it gets harder the longer you survive. Screen shake on hit and player blinks red after taking damage.

**Note:** The CTA button currently restarts the game — deep link to the advertiser's app/store page is a placeholder pending final asset delivery.

**Audio headache**
Regular HTML Audio kept getting blocked by browser autoplay policy. Switched to Web Audio API, decode the MP3 into an audio buffer inside the first tap event and loop it from there. Annoying to figure out but works cleanly.

**Tools used**
PixiJS v7, NanoBanana Pro (assets), Craiyon (bg removal), Python + PIL (sprite normalization), Claude AI (dev assistance, permitted by the assignment)
