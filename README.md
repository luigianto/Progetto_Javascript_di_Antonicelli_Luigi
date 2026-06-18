# Contatore Dinamico JavaScript

Un'applicazione web che simula il comportamento di un counter (contatore), sviluppata interamente in JavaScript puro con manipolazione dinamica del DOM.

## Descrizione

L'applicazione permette all'utente di aumentare, diminuire o azzerare il valore di un contatore tramite tre pulsanti interattivi. L'interfaccia viene costruita completamente via JavaScript, senza alcun HTML statico dedicato ai componenti UI.

## Funzionalità

- Visualizzazione del valore iniziale del counter impostato a **0**
- Pulsante **+** per incrementare il valore
- Pulsante **−** per decrementare il valore
- Pulsante **Reset** per riportare il counter a 0
- **Feedback visivo**: il colore del numero cambia dinamicamente in base al valore
  - Verde (`#27ae60`) → valore positivo
  - Rosso (`#c0392b`) → valore negativo
  - Scuro (`#2c3e50`) → valore zero

## Struttura del progetto

```
Progetto contatore/
├── index.html
├── css/
│   └── style.css
└── js/
    └── contatore.js
```

## Tecnologie utilizzate

- **HTML5** — struttura minimale con un singolo `div#root`
- **CSS3** — stili per layout, pulsanti e tipografia
- **JavaScript puro (Vanilla JS)** — nessun framework o libreria esterna

## Come eseguire il progetto

1. Clona o scarica la repository
2. Apri il file `index.html` in un browser
3. Interagisci con i pulsanti **+**, **−** e **Reset**

Non sono richieste installazioni o dipendenze.

## Dettagli tecnici

### Creazione dinamica del DOM

Tutti gli elementi dell'interfaccia (titolo, display numerico, pulsanti) vengono creati e inseriti nel DOM tramite JavaScript:

```js
const title = document.createElement("h1");
const countDisplay = document.createElement("h1");
const buttonplus = document.createElement("button");
const buttonminus = document.createElement("button");
const reset = document.createElement("button");

contenitore.append(title, countDisplay, buttonminus, reset, buttonplus);
```

### Gestione degli eventi

Ogni pulsante ha un proprio event listener che aggiorna il valore e chiama `updateDisplay()`:

```js
buttonplus.addEventListener("click", () => {
  count++;
  updateDisplay();
});

buttonminus.addEventListener("click", () => {
  count--;
  updateDisplay();
});

reset.addEventListener("click", () => {
  count = 0;
  updateDisplay();
});
```

### Feedback visivo dinamico

La funzione `updateDisplay()` aggiorna sia il testo che il colore del display in base al valore corrente:

```js
function updateDisplay() {
  countDisplay.textContent = count;
  if (count > 0) countDisplay.style.color = "#27ae60";
  else if (count < 0) countDisplay.style.color = "#c0392b";
  else countDisplay.style.color = "#2c3e50";
}
```

## Autore

Luigi Antonicelli
Progetto realizzato nell'ambito del corso di Web Development su **Start2Impact**.
