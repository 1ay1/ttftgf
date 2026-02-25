# Type Theory from the Ground Up

**A Programmer's Journey into the Foundations of Types — with C++ as Your Companion**

[![Build and Release PDF](https://github.com/1ay1/ttftgf/actions/workflows/release.yml/badge.svg)](https://github.com/1ay1/ttftgf/actions/workflows/release.yml)

> *"The purpose of abstraction is not to be vague, but to create a new semantic level in which one can be absolutely precise."*
> — Edsger W. Dijkstra

---

## Download the Book

**[⬇ Download latest PDF](https://github.com/1ay1/ttftgf/releases/latest)**

The PDF is built automatically from source on every tagged release. No LaTeX installation required.

---

## What Is This Book?

This book exists because of a gap.

On one side sit the **practitioners**: C++ programmers who use templates every day, who write `std::vector<int>` without a second thought, who have perhaps wrestled with SFINAE or fumbled through a concept declaration. They know that types matter, but they have never been told *why* types work the way they do.

On the other side sit the **theorists**: type-theory textbooks that begin with judgment forms and inference rules, that assume familiarity with proof theory, and that rarely mention a real programming language until the appendix (if ever).

This book is a bridge. It starts from C++ — the language whose templates are among the most powerful (and most confusing) type-level mechanisms in any mainstream language — and walks you, step by step, through the mathematical ideas that make those mechanisms tick.

By the end you will understand:

- Why `std::variant` is a **sum type** and `std::pair` is a **product type**
- Why function types are **contravariant** in their argument
- How **Hindley–Milner inference** works and why it terminates
- What the **Curry–Howard correspondence** really says about the programs you write
- Why Rust's borrow checker is secretly **linear type theory**
- What dependent types, session types, and refinement types look like — and where they are heading

---

## Who Is This Book For?

You are a working programmer — primarily in C++, but the ideas transfer to any statically typed language. You should be comfortable reading C++ code including basic templates and lambdas. You do **not** need a mathematics background beyond curiosity and the willingness to follow a careful argument.

This book is for you if you have ever:

- Stared at a template error message and wished you understood what the compiler was actually complaining about
- Wondered what "type erasure" really means, or why `std::function` is slower than a raw template
- Heard the phrase "types are propositions" and wanted to know what that means concretely
- Wanted to design types that make illegal states *impossible* rather than just detectable
- Been curious about Haskell, Rust, or Idris and wanted a conceptual bridge from C++

---

## Contents

The sixteen chapters form a deliberate arc across four parts.

### Part I — Foundations (Chapters 1–4)

What is a type? How do we build new types from old ones? What is the lambda calculus and why does it underlie everything?

| # | Chapter | Key Ideas |
|---|---------|-----------|
| 1 | **What Are Types, Really?** | Set-theoretic, behavioural, and syntactic views of types; static vs dynamic typing; soundness and completeness |
| 2 | **The Type Zoo** | Primitive types, unit, bottom, booleans, enumerations, product types, sum types, function types, arrays |
| 3 | **Type Constructors** | Types as functions on types; introduction and elimination rules; kinds; C++ templates as type constructors |
| 4 | **Functions and the Lambda Calculus** | Untyped λ-calculus; α/β/η reduction; Church encodings; Simply Typed Lambda Calculus; strong normalisation |

### Part II — The Core Theory (Chapters 5–9)

The major pillars of modern type theory, each grounded in concrete C++ code.

| # | Chapter | Key Ideas |
|---|---------|-----------|
| 5 | **Parametric Polymorphism** | System F; the `∀` quantifier; parametricity; "theorems for free"; monomorphisation vs type erasure; existential types |
| 6 | **Type Inference** | Constraint generation; Robinson unification; Algorithm W (Hindley–Milner); let-polymorphism; C++ `auto` and `decltype` |
| 7 | **Subtyping, Variance, and Inheritance** | Liskov substitution; nominal vs structural subtyping; covariance, contravariance, invariance; the expression problem |
| 8 | **Type Algebra** | Cardinality; types as numbers; algebraic identities; ADTs; the derivative of a type; zipper data structures |
| 9 | **Recursive and Inductive Types** | Fixed points of type constructors; `μ` and `ν` notation; inductive vs coinductive types; W-types; CRTP |

### Part III — Advanced Type Systems (Chapters 10–13)

Where C++'s template system reveals its deep connection to type theory.

| # | Chapter | Key Ideas |
|---|---------|-----------|
| 10 | **Dependent Types** | Π-types and Σ-types; the lambda cube; `Vec(A, n)`; Martin-Löf Type Theory; Agda/Idris; C++ non-type template parameters |
| 11 | **Higher-Kinded Types** | Kinds; functors; applicatives; monads; template template parameters; type-level programming; category theory |
| 12 | **Concepts, Constraints, and Bounded Polymorphism** | Bounded quantification; Haskell type classes; qualified types; C++20 concepts; Rust traits; subsumption |
| 13 | **SFINAE, Type Traits, and Compile-Time Dispatch** | `std::enable_if`; type trait library; tag dispatch; `decltype`/`declval`; detection idiom; `if constexpr` |

### Part IV — The Big Picture (Chapters 14–16)

Stepping back to see the full landscape.

| # | Chapter | Key Ideas |
|---|---------|-----------|
| 14 | **The Curry–Howard Correspondence** | Types as propositions; programs as proofs; modus ponens as function application; proof assistants; identity types; HoTT |
| 15 | **Advanced Topics and the Frontier** | Linear and affine types; session types; effect systems; refinement types; gradual typing; row polymorphism; QTT |
| 16 | **Putting It All Together** | Grand tour of the theory; type-safe state machine; dimension-checked matrix library; typed expression evaluator; where to go next |

---

## Structure of Each Chapter

Every chapter follows the same rhythm:

1. **Motivating question** — a concrete problem you have seen in real code
2. **Theoretical answer** — the type-theoretic concept, developed carefully
3. **C++ manifestation** — how the idea appears in C++ features and idioms
4. **Worked examples** — complete, compiling code with explanation
5. **Exercises** — from straightforward to open-ended research questions

Highlighted boxes appear throughout:

- **Key Insight** — the single most important idea on the page
- **C++ Connection** — the direct mapping from theory to C++ feature
- **Warning** — a common misconception or pitfall
- **Chapter Takeaways** — a bulleted summary at the end of every chapter

---

## Notation

Mathematical notation is introduced gradually and always accompanied by an intuitive explanation.

| Notation | Meaning |
|----------|---------|
| `A → B` | Function type (A to B) |
| `A × B` | Product type (pair of A and B) |
| `A + B` | Sum type (either A or B) |
| `∀α. T` | Universally quantified (polymorphic) type |
| `Γ ⊢ e : T` | Typing judgment ("in context Γ, expression e has type T") |
| `⟦T⟧` | The set of values inhabiting type T |

Code examples are in **C++20** unless labelled otherwise. Haskell and Idris snippets are clearly marked. All C++ code targets GCC 13+ or Clang 17+.

---

## Building Locally

You need a full TeX Live installation (TeX Live 2023+ recommended).

```bash
cd book
pdflatex -interaction=nonstopmode main.tex
bibtex main
makeindex main
pdflatex -interaction=nonstopmode main.tex
pdflatex -interaction=nonstopmode main.tex
# Output: book/main.pdf
```

Three `pdflatex` passes are needed: the first pass collects cross-references, `bibtex` resolves citations, `makeindex` builds the index, and the final two passes incorporate everything.

### With latexmk (simpler)

```bash
cd book
latexmk -pdf -interaction=nonstopmode main.tex
```

---

## Automated Releases

Every push of a `v*` tag triggers the GitHub Actions workflow, which:

1. Spins up Ubuntu with `texlive-full`
2. Runs the full build pipeline (pdflatex → bibtex → makeindex → pdflatex × 2)
3. Publishes a GitHub Release with `main.pdf` attached

To cut a new release:

```bash
git tag -a v1.1.0 -m "Description of changes"
git push origin v1.1.0
```

---

## Further Reading

The book includes a full bibliography. Key references for going deeper:

- **Pierce** — *Types and Programming Languages* (TAPL) — the standard graduate text
- **Pierce** — *Advanced Topics in Types and Programming Languages* (ATAPL)
- **Martin-Löf** — *Intuitionistic Type Theory* (1984)
- **Wadler** — *Propositions as Types* (CACM 2015)
- **The HoTT Book** — *Homotopy Type Theory* (free at homotopytypetheory.org)
- **Pierce et al.** — *Software Foundations* (free at softwarefoundations.cis.upenn.edu)
- **Milewski** — *Category Theory for Programmers* (free online)

---

## Acknowledgments

The ideas in this book belong to generations of researchers: Alonzo Church, Haskell Curry, William Howard, Per Martin-Löf, Robin Milner, John Reynolds, Benjamin Pierce, Philip Wadler, and many others.

*Generated with [Claude](https://claude.ai) (Anthropic). February 2026.*
