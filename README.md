# B2B Rust Microservice Opportunity Suite

Five domain-led Rust microservice APIs built on the same production standards:
local data quality, deterministic business logic, lean operations, and measurable buyer value.

## Repositories

| Rank | Repo | Business thesis | Local path |
| --- | --- | --- | --- |
| 1 | trade-compliance-api | Developer-first trade/import instrumentation: tariff classification, landed cost, restricted-party screening, shipment validation. | `/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/trade-compliance-api` |
| 2 | utility-bill-normalization-api | Standardize messy utility/meter/bill exports into clean normalized records for CRE, energy, and benchmarking workflows. | `/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/utility-bill-normalization-api` |
| 3 | recall-intelligence-api | Recall feed normalization and catalog matching for product risk detection and notification ordering. | `/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/recall-intelligence-api` |
| 4 | warranty-infrastructure-api | Product registration, entitlement, claims adjudication, supplier recovery, and reserve analytics. | `/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/warranty-infrastructure-api` |
| 5 | construction-change-order-api | Standardized RFIs, change events, change orders, approvals, and budget variance for construction PM systems. | `/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/construction-change-order-api` |

## Stack

- Rust workspace with Axum + Tokio + SQLx + Redis + NATS JetStream + MinIO
- Zig only where justified as an optional parser/import acceleration tool
- OpenAPI via utoipa
- CI via GitHub Actions
- Containerized via Docker + Docker Compose

## Current status

All repositories are scaffolded and documented. Verification is blocked by missing toolchain/auth in the current local environment.
Recovery steps are recorded in `STATUS.md`.

## Recommended first pilot

## Immediate verification plan

Verify the scaffold with machine-actionable commands. This suite surfaces the same issues found in the Node.js and Zig implementations: absent toolchain, stale lockfiles, and missing auth. Each repo has a single documented recovery path so execution can continue once the environment is ready.

Install Rust + Cargo + rustfmt + clippy:

source "$HOME/.cargo/env"

Validate under strict lint:

cargo fmt --check
cargo clippy --workspace --all-targets -- -D warnings

Run the test and build pipeline:

cargo test --workspace
cargo build --workspace

Bring up dependencies only if Docker is available:

docker compose config
docker compose up -d

Seed demo data:

cargo run -p cli -- seed

Start the API:

cargo run -p api

Run the smoke routine:

cargo run -p cli -- smoke

Enable GitHub repo creation when GitHub CLI is available. Without the GitHub CLI, create the repos manually, using this recovery command to add the origin and push each separate repository:

git remote add origin git@github.com:Hardonian/{repo-name}.git
git push -u origin main

## Recovery checklist

| Repo | Local path | Blocked cause | Recovery command(s) |
| --- | --- | --- | --- |
| trade-compliance-api | `/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/trade-compliance-api` | Missing Rust/Cargo/Docker and GitHub auth | Install Rust toolchain, enable GitHub CLI auth, then run verification commands |
| utility-bill-normalization-api | `/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/utility-bill-normalization-api` | Missing Rust/Cargo/Docker and GitHub auth | Install Rust toolchain, enable GitHub CLI auth, then run verification commands |
| recall-intelligence-api | `/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/recall-intelligence-api` | Missing Rust/Cargo/Docker and GitHub auth | Install Rust toolchain, enable GitHub CLI auth, then run verification commands |
| warranty-infrastructure-api | `/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/warranty-infrastructure-api` | Missing Rust/Cargo/Docker and GitHub auth | Install Rust toolchain, enable GitHub CLI auth, then run verification commands |
| construction-change-order-api | `/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/construction-change-order-api` | Missing Rust/Cargo/Docker and GitHub auth | Install Rust toolchain, enable GitHub CLI auth, then run verification commands |

---
Generated: 2026-06-05
