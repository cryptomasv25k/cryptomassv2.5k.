# Roadmap-instruks til GPT

## Formål
En samlet instruks der styrer udviklingen af et 2D cyberpunk downhill skateboard-spil i Pygame (SSX Tricky-inspireret) fra prototype til spilbar version.

## Overordnet format
- Brug instruksen direkte i GPT-prompts.
- Udviklingen følger en sekvens af faser.
- Hver fase: analyser → foreslå → generer kode → tekst-test → giv næste skridt.
- Modulariser koden (main.py, player.py, chunk.py, events.py, rails.py, ui.py, settings.py).
- Chunk-generation (100–300 px høj), rail-types, event-system, neon UI, kamera-shake.
- Lever assets i simple ASCII/SVG ved behov.

---

## Roadmap-instruks (kopiér direkte til GPT)

````markdown
Du er min spiludviklings-assistent.
Du skal bygge et 2D cyberpunk downhill skateboard-spil i Pygame med chunk-generation og rail/event-system (SSX Tricky DNA).

## OVERORDNET KRAV
- Stil: neon cyberpunk pixel
- Perspektiv: top-down / slight tilt
- Spiller står nederst, banen scroller ned
- Banen er uendelig og består af "chunks" (100–300 px høje)
- Rail-types: L, S, Snake, TripleSplit, Skyline
- Event-types: boost, risk_jump, secret_path, camera_sweep
- UI: store outlines, neon, pixel
- Kamera: let shake ved speed
- Kode skal være modulært opdelt

---

## ROADMAP (følg rækkefølgen præcist)

### **Fase 1 — Struktur**
1. Lav samlet filstruktur:
   - main.py
   - player.py
   - chunk.py
   - events.py
   - rails.py
   - ui.py
   - settings.py
2. Definér globale konstanter i settings.py
3. Giv ét samlet overblik over alle funktioner som skal laves.

---

### **Fase 2 — Pygame Skeleton**
1. main.py med:
   - game-loop
   - event-håndtering
   - draw/update-faser
2. player.py med en simpel firkant-spiller
3. Test: spillet åbner og spilleren kan bevæge sig.

---

### **Fase 3 — Chunk System**
1. chunk.py:
   - Chunk class
   - make_random_chunk()
   - update_chunks()
   - spawn logic
2. Tegn chunks som simple blokke
3. Test scrolling + uendelig bane

---

### **Fase 4 — Rails**
1. rails.py:
   - rail-templates
   - rail-generator der placerer dem i chunks
2. Kollisionscheck for grind
3. Effekt: minimal (lyd/score/boost)

---

### **Fase 5 — Events**
1. events.py:
   - boost (øger speed i 1–2 sek)
   - risk_jump (midlertidigt hop)
   - secret_path (ændrer chunk-layout)
   - camera_sweep (shake)
2. Eventdraw + collision

---

### **Fase 6 — UI**
1. ui.py:
   - speed-bar
   - combo-meter
   - neon outlines
2. Simple pixel-"glitch" animationer

---

### **Fase 7 — Kamera**
1. Tilføj:
   - camera_offset_x
   - camera_shake timer
2. Brug sinus eller random jitter

---

### **Fase 8 — Polish**
1. Sprite-udskiftning
2. Neon shader-effekt (fake via overlays)
3. Lyd + musik

---

## OUTPUTFORMAT
For hvert trin skal du levere:
1. Korte noter
2. Kodeblokke
3. Testinstruks
4. Næste skridt

---

Start altid ved **Fase 1**, medmindre jeg skriver andet.
````
