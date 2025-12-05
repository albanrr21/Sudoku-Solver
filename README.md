# Sudoku Solver — Project README

**Project Overview**

- **What**: A web-based Sudoku solver and visualizer built with Next.js and React. It accepts user-input puzzles, shows candidate elimination and solving steps, and computes solutions programmatically.
- **Who**: Developed by Alban (GitHub: `albanrr21`) in collaboration with Leutrim Istrefi.
- **Where to look**: Key source files include `lib/solver.ts`, `lib/utils.ts`, the UI under `app/` and `components/`, and `package.json` for scripts and dependencies.

**How to Run (Development)**

- **Install dependencies**: Run the package manager of your choice.

```cmd
pnpm install
pnpm run dev
```

- **npm alternative**:

```cmd
npm install
npm run dev
```

- **Build for production**:

```cmd
pnpm run build
pnpm start
```

**Project Structure (high level)**

- **`lib/solver.ts`**: Core solver implementation — domains, constraint checking, backtracking, heuristics, and propagation routines.
- **`lib/utils.ts`**: Helpers for board conversions, validation, and candidate handling.
- **`app/` and `components/`**: UI, board renderer, controls, and visualization components (step-by-step mode shows propagation/backtracking).
- **`src/`**: Tests and bootstrapping used in the repo (some legacy CRA/React test artifacts exist here).

**Mathematical Foundations**

- **Constraint Satisfaction Problem (CSP)**: Sudoku is modeled as a CSP where cells are variables, domains are digits 1–9, and constraints enforce uniqueness across rows, columns, and 3x3 blocks. The solver manipulates domains and assignments to satisfy all constraints.
- **Backtracking Search (Depth-First Search)**: The solver explores possible assignments with a recursive DFS/backtracking framework — illustrating search trees and recursion.
- **Constraint Propagation & Logical Deduction**: Deterministic reductions (candidate elimination, naked singles, etc.) are used before or during search to prune domains — demonstrating logical inference in CSPs.
- **Graph Theory Analogy**: Represent the grid as a graph where adjacent (constrained) cells are connected; solving is similar to a graph coloring problem with 9 colors under Sudoku-specific structure.
- **Combinatorics & Complexity**: The project comments on the combinatorial explosion of complete assignments and how constraints drastically reduce feasible states; it includes simple empirical observations on runtime for different puzzles.

**Demonstration & Teaching Uses**

- **Step-by-step visualization**: The UI can show candidate removal and backtracking steps so you can observe the algorithm’s behavior — ideal for teaching CSPs and search strategies.
- **Benchmarking**: The codebase collects basic step counts and timings to compare heuristics and puzzle difficulty.

**Testing & Validation**

- **Automated tests**: There are example tests under `src/` (e.g., `App.test.js`). Run tests with your test runner setup (the project currently uses the Next.js + React testing toolchain).
- **Solver correctness**: Solutions produced by the solver are validated against Sudoku constraints before being accepted.

**Notes on Dependencies & Tooling**

- **Framework**: Next.js + React. See `package.json` for versions and scripts.
- **Package manager**: `pnpm` is recommended for fast installs, but `npm` works too.

**Acknowledgements & Collaborators**

- **Primary authors**: Alban (`albanrr21`) and Leutrim Istrefi (collaborator).
- **Primary authors**: Alban (`albanrr21`) and Leutrim Istrefi (collaborator) — https://github.com/trimiiss (GitHub: `trimiiss`).
- **Purpose**: Academic project and demonstration of algorithmic and mathematical concepts.

**Contact & Demo**

- **Demo offer**: I can prepare a short (10–15 minute) demo or a written walkthrough of the CSP formulation and solver pseudocode on request.
- **Contact**: Replace this README’s contact line with your preferred email or GitHub handle.

**License**

- No license file is included by default — this repository is an academic submission. Add a license if you wish to open-source the project.
