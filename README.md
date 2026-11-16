# System Design Flashcards

A single-page flashcard app for preparing for system design interviews. It has 68 cards across 16 core topics. It's one self-contained HTML file with no build step and no dependencies.

**Live:** https://isaiaslipa.github.io/system-design-flashcards/

## Topics

| Topic | Cards | Topic | Cards |
| --- | :-: | --- | :-: |
| API Design | 6 | Large Blobs | 4 |
| Caching | 5 | Long Running Tasks | 4 |
| CAP Theorem | 5 | Multi-step Processes | 5 |
| Consistent Hashing | 4 | Networking | 4 |
| Contention | 4 | Numbers to Know | 3 |
| Data Modeling | 4 | Real-time Updates | 4 |
| DB Indexing | 5 | Scaling Reads | 3 |
| Sharding | 4 | Scaling Writes | 4 |

Each card is also tagged with a **type**:

- **Concept**: what it is
- **How It Works**: the mechanics
- **When to Use**: decision criteria
- **Trade-off**: costs and failure modes
- **Interview Tip**: how to present it

## Features

- Filter the deck by topic and/or card type
- Click a card to reveal the answer
- Shuffle the current deck
- Mark cards as **known** and track progress (total / known / remaining, with a progress bar)
- Keyboard shortcuts

### Keyboard shortcuts

| Key | Action |
| --- | --- |
| `→` or `l` | Next card |
| `←` or `h` | Previous card |
| `Space` or `Enter` | Flip card |
| `k` | Mark as known |
| `x` | Mark as still learning and go to the next card |

## Running locally

Open `index.html` in a browser. To serve it locally instead:

```bash
python3 -m http.server
# then visit http://localhost:8000
```

## Adding cards

The cards live in the `CARDS` array inside the `<script>` block of `index.html`. Each entry looks like this:

```js
{ t: "Caching", y: "tradeoff", q: "Question text", a: "Answer (HTML allowed)" }
```

- `t`: topic. A new topic name gets its own filter.
- `y`: type: `concept`, `howworks`, `when`, `tradeoff` or `interview`
- `q`, `a`: question and answer. The answer can include HTML such as `<strong>`, `<ul>` and `<code>`.

> Progress is held in memory only, so refreshing the page resets known cards.
