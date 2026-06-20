# Handoff Note

## Scope

- Modifica richiesta: Aggiungere un empty state quando la lista ticket è vuota. Messaggio chiaro con testo "Non ci sono ticket aperti. Quando verra' creato un nuovo ticket, lo vedrai qui."
- Fuori scope: TicketList.jsx, TicketCard.jsx, api.js, styles.css, server, routing, layout globale, filtri, creazione ticket, refactor.

## Prompt Strategy

- Zero-shot o few-shot: Zero-shot.
- Esempi usati, se presenti: Nessuno.
- Evidenze sintetiche richieste: Pattern di stati già esistente in App.jsx, classe CSS `.state-message` già presente.

## Changes

- File principali: `src/App.jsx`
- Sintesi: Aggiunta condizione `tickets.length === 0` nello stato `ready`, prima del render di `<TicketList>`. La lista viene renderizzata solo con `tickets.length > 0`. Riutilizzata classe `.state-message` esistente.

## Validation

- Controlli eseguiti: Diff verificato — solo `src/App.jsx` modificato, +3 righe, −1 riga, nessun file fuori scope.
- Controlli non eseguiti: Verifica visiva con `pnpm dev` su `?empty=true` e URL normale. Build (`pnpm run build`) non eseguita.

## Review Notes

- Punti da controllare in review: Il diff tocca solo la condizione di render in `App.jsx`. Verificare che lo stato vuoto (`?empty=true`) mostri il messaggio e lo stato normale mostri la lista.
- Rischi o dubbi residui: Nessuno. Modifica minima, reversibile, classe CSS riutilizzata.
