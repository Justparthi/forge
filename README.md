# Forge

**Write the computation once. Run it from any language.**

Forge separates *what* a computation does from *where* it runs.

You write the logic once in **FDS**, a small meta-language built for numbers, matrices and control flow, directly inside your host language. Forge takes it from there. The code around it stays yours, and the computation inside it moves with you.

Python is the first host. Java and Rust follow, and the FDS you write today doesn't change when they arrive.

---

## A taste

```fds

%%
@0 = 3;
@1 = 3;
@2 = @0 ? @1 : -@1;
%%

print("result:", %{@2})
```

Python sets things up, FDS does the math, and the answer comes back to Python. You only write it once.

Embedded inside ordinary Python, it looks like this:

```fds
%%
@0 = 3;
@1 = 3;
%%
print(%{@0}, %{@1})
```

---

## What FDS gives you

| Idea | Looks like |
|---|---|
| Cells | `@0`, `@1`, `@42` |
| Numbers | `7`, `3.14`, `.5`, `2e10` |
| Arithmetic | `+ - * /`, `++ --` |
| Choice | `cond ? a : b` |
| Matrices | `#[ 1 2 3 4 ]#`, with `\|` and `---` for blocks |
| Sections | `%% … %%` inside host code |
| Host to FDS | `{{x}}`, `$$...$$` |
| FDS to Host | `%{@n}`, `%%...%%` |

The complete language guide is in [`compiler/GRAMMAR.md`](compiler/GRAMMAR.md).

---

## Getting started

```bash
git clone https://github.com/dheerajshyampvsofficial/forge.git
cd forge
```

Sample FDS code in [`compiler/samples/one.fds`](compiler/samples/one.fds).

---

## Status

Forge is under active development. The language and compiler are close to complete, and the runtime is growing from scalars to tensors. Expect things to move, next milestone: `November 20, 2026`

# Contributing to Forge

Thank you for your interest in building Forge with us.

Forge grows like a house: one foundation, with new rooms added over time. Every room is connected to the house, and nothing is built off on its own. This keeps the project in one piece as it grows. There is one language, one compiler and one runtime, with no competing variants and no fragmentation.

---

## How contributions flow

Every piece of work starts from `main` and comes back to `main`.

```
main ──▶ feature ──▶ … ──▶ feature ──▶ main
```

- New ideas are built as **extensions of main**, not as separate versions of Forge.
- A host language, an operation or a tool is a new room in the same house.
- Work that can't find its way back to `main` is discussed early and reshaped so that it can.

This means users always have **one official Forge**, and every improvement reaches all of them.

---

## Step 1: Get in touch

Contributing starts with a short conversation. Email us at **info@aquesa-solutions.com** with:

- Your name and GitHub profile
- What interests you about Forge
- Any area you'd like to work on (for example, the language, a new host language, the runtime or the tooling)

We'll reply with the next onboarding dates.

---

## Step 2: Onboarding (2 weeks)

Every contributor goes through a guided **two-week onboarding**. Forge has a lot of thinking behind it, and we'd rather explain it properly than leave you to guess.

During onboarding we walk you through:

- **The codebase, line by line:** what each part does and why it is written that way
- **The algorithms** used across the compiler and runtime
- **The ideas behind the design** and where the project is heading
- **Your first contribution**, chosen together and started with guidance

If you come up with a new idea during onboarding, we'll start working on it with you right away.

---

## Step 3: Weekly sync

Contributors meet **every weekend** for a short progress sync. In each sync we:

- Review progress across all ongoing work
- Check that each piece of work is still heading back toward `main`
- Spot work that has drifted from the roadmap, and either realign it or close it
- Welcome new contributors and recognise the people making progress

Attendance is expected while you have active work in progress.

---

## Pull requests

- Open a pull request only for work that was agreed during onboarding or at a weekly sync.
- Keep each pull request focused on one change.
- Link the pull request to the discussion where the work was agreed.

Pull requests that weren't discussed first may be closed with a note inviting you to start at Step 1.

---

## Issues and questions

You don't need onboarding to open an issue, report a bug or ask a question. Anyone can do that, any time.

All contributions are reviewed by the maintainers, and everyone is expected to keep collaboration respectful.

---

## A note on freedom

Forge is free and open-source software under the [Mozilla Public License 2.0](LICENSE). You are always free to read, use, study and modify the code under that license.

The process above applies to contributing to **the official Forge project**. It exists so that everyone building Forge builds the same thing, together.

## License

[Mozilla Public License 2.0](LICENSE)