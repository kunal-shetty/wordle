# Wordle Clone – HTML, CSS & JavaScript

This is a Wordle-style web game I built using plain HTML, CSS, and JavaScript. The game selects a new target word on each page refresh and uses a local JSON file to store the full word list. Building this helped me understand game logic, state management in the browser, and how to work with static data files.

---

## Features

* Classic Wordle gameplay mechanics (6 attempts to guess a 5-letter word)
* A new target word on every page refresh (randomly selected from `words.json`)
* All valid/target words stored in a local `words.json` file
* Immediate visual feedback for each guess (correct, present, absent)
* Keyboard input (physical keyboard and on-screen keyboard support)
* Simple, responsive UI that works on desktop and mobile
* Basic validation and error handling for invalid words

---

## How It Works

* On load, the app fetches `words.json` and randomly selects a target word.
* The player types guesses using the keyboard or the on-screen keys.
* After each guess, the game compares letters to the target word and marks tiles as:

  * Correct (right letter, right place)
  * Present (right letter, wrong place)
  * Absent (letter not in the word)
* The player has six attempts to find the target word. The game ends on success or after six incorrect guesses.
* Refreshing the page selects a new random target word.

---

## Project Files

```
/wordle-clone
│── index.html
│── style.css
│── script.js
│── words.json       # list of valid/target words
```

---

## words.json

* Store all valid words and possible target words in `words.json` as a JSON array of lowercase strings, e.g.

```json
["apple","brain","crate","dwarf","eager", ...]
```

* Keep the list curated to valid 5-letter words (or change the game logic if using different lengths).

---

## What I Learned

### Reading Static Data

I learned how to load a JSON file from the frontend (`fetch`) and use it as a data source for gameplay. Handling static files taught me about CORS and why serving files over HTTP matters during development.

### Game State Management

Implementing the guess grid and attempt logic taught me how to represent game state in JavaScript, update the DOM based on state changes, and manage turn-based interactions.

### Letter Matching Logic

I learned how to implement the Wordle-specific matching rules (handling duplicate letters, marking correct/present/absent accurately) and how to test those edge cases.

### Keyboard & UX

Supporting both physical keyboard input and an on-screen keyboard improved my understanding of event handling and accessibility considerations.

### Validation & UX Flow

I practiced validating guesses against the word list and giving clear feedback to the user (invalid word, success, failure), and built a clean flow for restarting or continuing play.

### Debugging & Testing

The project helped me debug timing/animation issues, manage asynchronous fetch calls, and structure code for readability and maintainability.

---

## Possible Enhancements

* Persist game progress and stats in `localStorage` (wins, streaks, total games)
* Add daily mode where the same word is shared by all players (requires server-side scheduling)
* Add animations and accessibility improvements (ARIA labels)
* Add difficulty modes (longer words, more/fewer attempts)
* Add a shareable results card (copyable text similar to Wordle)

---

## Tech Used

* HTML
* CSS
* JavaScript (ES6+)
* Static `words.json` file


* Add a `requirements` or `deploy` section for hosting (Netlify, Vercel, GitHub Pages)
* Convert `words.json` into a server endpoint for daily/deterministic words
* Expand the word-matching logic to handle variable word lengths

Tell me which enhancement you want next and I’ll update the README.
