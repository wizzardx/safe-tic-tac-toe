# 🧠 Safe Tic-Tac-Toe

**Safe Tic-Tac-Toe** is a multi-language MVP combining **Lean4**, **Koka**, and **Rust** to demonstrate a fully verified, auditable implementation of the classic game Tic-Tac-Toe.

Built as an experiment in reproducible, type-safe, and effect-traceable computation, this project ensures:
- Game logic is **proven correct** in Lean4
- IO and randomness are **tracked as effects** in Koka
- Output is **rendered and saved** via Rust

---

## 📦 Project Structure

```bash
safe-tic-tac-toe/
├── lean/                  # Game rules, validation, and proofs
│   ├── TicTacToe.lean
│   ├── GameProof.lean
│   └── Test.lean
├── koka/                  # Traceable execution logic
│   └── tictactoe_trace.kk
├── rust/                  # CLI frontend and board rendering
│   └── main.rs
├── docker-compose.yml     # Dev environment for all languages
├── Makefile               # Easy build/test automation
└── output/                # Generated outputs (board, trace, etc.)
````

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/safe-tic-tac-toe.git
cd safe-tic-tac-toe
```

### 2. Run it with Docker

```bash
docker compose up --build
```

### 3. Or run individual components:

#### 🧠 Lean4 tests

```bash
cd lean
lake build && lake test
```

#### 🔁 Koka simulation

```bash
cd koka
koka tictactoe_trace.kk
```

#### 🖥️ Rust rendering

```bash
cd rust
cargo run
```

---

## 🧪 What It Does

* Uses a random seed to simulate a full game
* Validates game legality in Lean4
* Records all move traces, inputs, and outcomes in JSON
* Renders a pretty board and trace summary via Rust

---

## 📂 Example Output

**`output/board.txt`**

```
 X | O | X
-----------
 O | X | O
-----------
 X | . | .
```

**`output/trace.json`**

```json
{
  "seed": 23818423,
  "moves": [
    {"player": "X", "pos": [0, 0]},
    {"player": "O", "pos": [1, 1]},
    ...
  ],
  "valid": true,
  "winner": "X"
}
```

---

## 🧬 Tech Stack

| Component | Language                             | Purpose |
| --------- | ------------------------------------ | ------- |
| ✅ Lean4   | Game logic + correctness proofs      |         |
| ✅ Koka    | Effect-traced simulation (IO, RNG)   |         |
| ✅ Rust    | Rendering, trace display, CLI        |         |
| ✅ Docker  | Cross-language environment           |         |
| ✅ LLMs    | Assistive generation, not core logic |         |

---

## 💡 Why This Exists

> To explore what happens when formal verification, traceable execution, and elegant CLI design meet—even for something as simple as Tic-Tac-Toe.

---

## 📜 License

MIT

---

## 🤝 Contributing

If you'd like to expand the project (e.g. support minimax AI, or use Lean to verify a winner-determination algorithm), PRs are welcome!
