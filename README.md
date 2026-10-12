# Tiny-AiRY
# AiRY Core

A tiny, offline browser runner for a compact subset of the AiRY language. The project includes a readable HTML build and a compressed `data:` URL designed to stay below a **3,072-byte URL budget**.


## Use the runner

- Edit the AiRY program in **AiRY source**.
- Enter one input value per line in **Input for read**. Each `read` consumes one line.
- Press **Run** to execute the program.
- Press **Example** to restore the sample program and clear input/output.
- Press **Clear** to clear the output.

The canvas draws the AiRY Core heading; the editor, input area, and output are ordinary HTML controls.

## Example

```airy
set s 0, loop i 0 5 { s = perform s + i * i }, show "sum: " + s, show s / 2.0, if s > 100 { show "big" } elseif s > 20 { show "mid" } else { show "small" }
```

Expected output:

```text
sum: 30
15
mid
```

## Supported syntax

This compact runner handles the common forms used by the example and syntax reminder:

- Statements: `set`, variable assignment (`x = ...`), `read`, `show`, `if` / `elseif` / `else`, `loop`, `infloop`, `break`, and `return`.
- Values: integer and decimal literals, `true`, `false`, quoted strings, and variables.
- Operators: arithmetic `+ - * / %`, bitwise `& | ^ ~`, comparisons `== != < > <= >=`, and logical `&& || !`.
- Parenthesized expressions and brace-delimited blocks.

## Size and implementation notes

This is a size-focused browser port, not a guarantee of perfect equivalence with the Rust implementation of AiRY. Edge cases involving type coercion, parsing, numeric behavior, or malformed programs may differ. Test programs that depend on Rust-specific behavior against the original Rust runner.(sorry but not enough time to make it better)

## Thanks for checking out!!
