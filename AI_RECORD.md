# AI Record

Log of AI-assisted design and implementation for this project.

## How to use

Add an entry whenever AI tools help with architecture, code, docs, or debugging in a meaningful way.

## Entries

### 2026-09-17 — Repository scaffold

- **Tool:** Cursor agent
- **Request:** Create project structure (`contracts/`, `test/`, `scripts/`, `docs/`, `architecture/`, `decisions/`, `frontend/`) plus `TEAM_CHARTER.md`, `PROPOSAL.md`, `.gitignore`, `.env.example`, `AI_RECORD.md`, and `README.md`
- **Outcome:** Empty directories with `.gitkeep` where needed; starter markdown stubs; `.gitignore` ignoring `node_modules/`, `.env`, `artifacts/`, `cache/`; `.env.example` with `DIDLAB_RPC` and `DEPLOYER_KEY`

### 2026-09-17 — Hardhat init and SimpleStorage compile

- **Tool:** Cursor agent
- **Request:** Activity 9 — initialize Hardhat (JavaScript), configure `hardhat` + `didlab` networks with dotenv, add `contracts/SimpleStorage.sol`, compile
- **Outcome:** Hardhat 2.x project with `@nomicfoundation/hardhat-toolbox` and `dotenv`; sample `Lock` removed; `SimpleStorage` compiles to `artifacts/`; ABI + bytecode available in `SimpleStorage.json`

### 2026-09-17 — Activity 10 ProjectAnchor (Bhavana)

- **Author:** Bhavana
- **Tool:** Cursor agent
- **Request:** Activity 10 — write `contracts/ProjectAnchor.sol`: store a `bytes32` commitment and last-updated time; only deployer can update; reject all-zero commitment; emit an event on update; expose a read that returns both values
- **Outcome:** `ProjectAnchor` compiles with Hardhat; `anchor` is `onlyOwner`, reverts `EmptyCommitment` on `bytes32(0)`, emits `CommitmentAnchored`; `current()` returns `(commitment, updatedAt)` 