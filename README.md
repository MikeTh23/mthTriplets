# Triplets

Gioco da tavolo strategico per 2 giocatori, implementato come web app standalone in un singolo file HTML — nessuna dipendenza, nessun server necessario.

🎮 **[Gioca online](https://tuo-username.github.io/triplets/)**

---

## Il gioco

*Triplets* è un gioco da tavolo astratto di strategia che ho scoperto su una rivista molti anni fa. L'obiettivo è attraversare la scacchiera dall'angolo di partenza all'angolo opposto, ma con un vincolo originale: **le mosse disponibili sono determinate dalla casella su cui si trova l'avversario**, non dalla propria.

### Campo di gioco

- Scacchiera **8×8**
- **4 caselle centrali** intransitabili
- **4 angoli** come punti di partenza e arrivo
  - Giocatore 1 (cerchio azzurro): `(7,0)` → `(0,7)`
  - Giocatore 2 (quadrato arancione): `(7,7)` → `(0,0)`
- **56 caselle normali**, ognuna con 3 frecce direzionali

### I tasselli

Ogni casella porta 3 delle 8 possibili direzioni (N, NE, E, SE, S, SW, W, NW), rappresentate come frecce. Le combinazioni possibili sono esattamente C(8,3) = **56** — una per ogni casella disponibile. Esistono 14 schemi unici, ciascuno nelle sue 4 rotazioni di 90°: 14 × 4 = 56.

All'inizio di ogni partita i 56 tasselli vengono distribuiti casualmente sulla scacchiera.

### Regole di movimento

1. **Prima mossa**: il Giocatore 1 si muove liberamente verso una delle caselle adiacenti al proprio angolo di partenza.
2. **Mosse successive**: ogni giocatore può spostarsi **solo nelle direzioni indicate dalla casella su cui si trova l'avversario** in quel momento.
3. **Nessuna mossa disponibile**: il turno viene saltato.
4. **Entrambi bloccati**: il giocatore di turno effettua una mossa libera.
5. **Due pedine sulla stessa casella**: permesso.
6. **Vince** chi raggiunge per primo il proprio angolo di arrivo.

### Pedine trasparenti

Come nell'edizione originale in legno, le pedine sono **trasparenti** (cerchio per P1, quadrato per P2) in modo da lasciare visibili le frecce del tassello occupato — informazione strategicamente importante.

---

## Modalità di gioco

| Modalità | Descrizione |
|---|---|
| vs Intelligenza Artificiale | Giocatore umano contro la CPU |
| vs Giocatore Umano | Due giocatori sullo stesso schermo |
| IA vs IA (Demo) | Partita automatica tra due AI |

### Livelli di difficoltà dell'IA

- **Facile** — mosse casuali tra quelle disponibili
- **Medio** — greedy: sceglie sempre la mossa che minimizza la distanza al proprio obiettivo
- **Difficile** — minimax con alpha-beta pruning, profondità 6

---

## Come giocare

### Online
Apri direttamente il link GitHub Pages (vedi sopra).

### In locale
Scarica `index.html` e aprilo in qualsiasi browser moderno. Non richiede installazioni, server o connessione internet.

---

## Dettagli tecnici

- **HTML + CSS + JavaScript** vanilla, zero dipendenze
- Rendering tramite **SVG inline** generato dinamicamente
- IA implementata con **minimax + alpha-beta pruning**
- Completamente **responsive**: funziona su desktop, tablet e smartphone

---

## Storia

Il gioco originale era pubblicato su una rivista di giochi da tavolo. Ne avevo realizzato una versione in C++ negli anni '90 per giocare contro il computer. Questa è la riedizione moderna, sviluppata con l'assistenza di [Claude Code](https://claude.ai/claude-code).
