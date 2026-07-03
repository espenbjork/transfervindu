# Overgangsvindu – studio-grafikk

Sky Sports-inspirert "Transfer Deadline Day"-bakgrunn for toastmaster-sketch
i Jonas & Eirin sitt bryllup (11. juli 2026).

Live: https://espenbjork.github.io/transfervindu/

Flyt: ventebilde med ventemusikk → Enter (eller START-knappen) →
sendestart-vignett med egen musikk → studio med lav musikkseng under innslaget.
Esc hopper over vignetten (kjekt på øving). All lyd genereres i nettleseren
(Web Audio), ingen lydfiler.

Ventebilde: klikk hvor som helst for å skru på ventemusikken,
F = fullskjerm, M = lyd av/på.

Hurtigtaster i studio:
Mellomrom = start/pause · R = nullstill · ↑/↓ = ±1 min ·
B = breaking · C = spillerkort · D = DONE DEAL ·
T = gjestefeed · M = lyd · F = fullskjerm

## Live gjestefeed ("SISTE FRA SALEN")

Bruker samme backend som bryllupsbackdrop-en: gjestene sender hilsener via
send.html (QR-koden på backdropen), Apps Script lagrer i Google Sheets, og
denne skjermen poller etter nye meldinger hvert 3. sekund. Innkommende
meldinger vises som X/Twitter-kort i en feed til høyre, maks 3 om gangen.

- Kun meldinger som kommer inn ETTER at sendingen er i gang vises
  (historikk og middagshilsener hopper vi over).
- FEED_URL øverst i index.html skal være identisk med SCRIPT_URL i
  bryllupsbackdrop/config.js. NB: redeploy av Apps Script med "New
  deployment" gir ny URL som må oppdateres begge steder.
- Test uten backend: åpne siden med ?demo=1 (falske meldinger etter
  at sendingen er startet).
