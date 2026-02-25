# Type Theory from the Ground Up

**A Programmer's Journey into the Foundations of Types — with C++ as Your Companion**

[![Build and Release PDF](https://github.com/1ay1/ttftgf/actions/workflows/release.yml/badge.svg)](https://github.com/1ay1/ttftgf/actions/workflows/release.yml)

---

## Download

Grab the latest compiled PDF from the [Releases page](https://github.com/1ay1/ttftgf/releases/latest).

---

## About

This book bridges the gap between working C++ programmers and the mathematical foundations that make type systems tick. It starts from concepts you already use — templates, `std::variant`, lambdas — and walks step by step through the theory that underlies them.

By the end you will understand why `std::variant` is a sum type, why function types are contravariant in their argument, how Hindley–Milner inference works, and what the Curry–Howard correspondence really says about the programs you write.

## Contents

| # | Chapter |
|---|---------|
| 1 | What Are Types, Really? |
| 2 | The Type Zoo — A Catalog of Types |
| 3 | Type Constructors — Building New Types from Old |
| 4 | Functions and the Lambda Calculus |
| 5 | Parametric Polymorphism — One Function, Many Types |
| 6 | Type Inference — How the Compiler Reads Your Mind |
| 7 | Subtyping, Variance, and Inheritance |
| 8 | Type Algebra — The Mathematics of Types |
| 9 | Recursive and Inductive Types |
| 10 | Dependent Types — When Types Depend on Values |
| 11 | Higher-Kinded Types and Type-Level Programming |
| 12 | Concepts, Constraints, and Bounded Polymorphism |
| 13 | SFINAE, Type Traits, and Compile-Time Dispatch |
| 14 | The Curry–Howard Correspondence — Types as Proofs |
| 15 | Advanced Topics and the Frontier |
| 16 | Putting It All Together |

## Building Locally

You need a full TeX Live installation (or equivalent).

```bash
cd book
pdflatex -interaction=nonstopmode main.tex
bibtex main
makeindex main
pdflatex -interaction=nonstopmode main.tex
pdflatex -interaction=nonstopmode main.tex
# Output: main.pdf
```

## Releases

A new PDF is built and published automatically whenever a version tag is pushed:

```bash
git tag -a v1.x.0 -m "release message"
git push origin v1.x.0
```

The workflow installs `texlive-full`, runs the full build pipeline, and attaches `main.pdf` to the GitHub Release.

---

*Generated with [Claude](https://claude.ai). Ideas belong to Church, Curry, Howard, Martin-Löf, Milner, Reynolds, Pierce, Wadler, and many others.*
