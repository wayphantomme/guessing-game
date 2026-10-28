# Guessing Game

A number guessing game built in Rust, based on Chapter 2 of [The Rust Book](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html). This project covers the core fundamentals of Rust through a hands-on, interactive program.

---

## Getting Started

**Prerequisites:** Make sure you have [Rust and Cargo installed](https://www.rust-lang.org/tools/install).

```bash
git clone https://github.com/wayphantomme/guessing-game.git
cd guessing-game
cargo run
```

---

## How to Play

1. The program generates a random secret number between 1 and 100.
2. Type your guess and press Enter.
3. The program tells you if your guess is **Too small!**, **Too big!**, or **You win!**
4. Keep guessing until you get it right.
5. Non-numeric input is ignored and the game continues.

---

## Development Steps

This project was built incrementally, one concept at a time. Each step below corresponds to a commit in the repository.

### Step 1: Read user input
Introduced `std::io` to read a line from stdin and print it back to the user.

**Concepts:** `use`, `String::new()`, `io::stdin().read_line()`, `expect()`

### Step 2: Generate secret number
Added the `rand` crate to generate a random number between 1 and 100.

**Concepts:** external crates, `Cargo.toml` dependencies, `rand::rng().random_range()`

### Step 3: Compare guess to secret number
Parsed the user's input as a `u32` and compared it to the secret number using `match`.

**Concepts:** `std::cmp::Ordering`, `match`, type annotation, `.parse()`, `.trim()`

### Step 4: Add loop for multiple guesses
Wrapped the input and comparison logic in a `loop` so the player can keep guessing.

**Concepts:** `loop`

### Step 5: Quit after correct guess
Added a `break` statement inside the `Ordering::Equal` arm so the program exits when the player wins.

**Concepts:** `break`

### Step 6: Ignore invalid input
Replaced `.expect()` with a `match` on the `Result` from `.parse()` so non-numeric input is skipped instead of crashing the program.

**Concepts:** `Result`, `Ok`, `Err`, `continue`

### Step 7: Finish guessing game
Removed the debug line that printed the secret number, completing the game.

---

## Concepts Learned

- Importing modules and external crates with `use`
- Mutable vs immutable variables (`let` vs `let mut`)
- User input with `std::io`
- Random number generation with the `rand` crate
- Type conversion and string parsing
- Pattern matching with `match`
- `loop`, `break`, and `continue`
- Error handling with `Result`, `Ok`, and `Err`

---

## References

- [The Rust Book, Chapter 2: Programming a Guessing Game](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html)
- [Rust By Example](https://doc.rust-lang.org/stable/rust-by-example/)
- [Rustlings](https://rustlings.rust-lang.org/)
