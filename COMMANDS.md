# COMMANDS.md

## Global commands per repo

```bash
cargo fmt --check
cargo clippy --workspace --all-targets -- -D warnings
cargo test --workspace
cargo build --workspace
docker compose config
docker compose up -d
cargo run -p cli -- seed
cargo run -p api
cargo run -p cli -- smoke
```

## Recovery commands

### Enable GitHub CLI authentication

```bash
gh auth login
```

### Create all private repos and push

```bash
for repo in trade-compliance-api utility-bill-normalization-api recall-intelligence-api warranty-infrastructure-api construction-change-order-api; do
  gh repo create "Hardonian/${repo}" --private --remote origin --source "/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/${repo}"
  cd "/mnt/c/Users/scott/GitHub/b2b-rust-api-opportunity-suite/repos/${repo}"
  git push -u origin main
done
```

### Add existing repo to GitHub

```bash
git remote add origin git@github.com:Hardonian/{repo-name}.git
git push -u origin main
```
