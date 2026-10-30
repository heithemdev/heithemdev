# Install this GitHub profile

Target repository: `https://github.com/heithemdev/heithemdev`

## 1. Put the files in their exact paths

- `README.md` → the repository root.
- `.github/workflows/metrics.yml` → create this workflow file.

Do not upload `SETUP.md` unless you want the setup instructions in your public profile repository.

## 2. Enable the metrics GitHub Action

`lowlighter/metrics` needs a personal access token (PAT) to access user-level GitHub data. It should **never** be stored in the README or a committed file.

1. GitHub → Settings → Developer settings → Personal access tokens.
2. Create a personal access token with only the access needed to read your profile data. For public metrics, the upstream project's instructions say a classic token with **no additional scopes** is normally sufficient. If you need private repo information, review the upstream scopes documentation first; it is not enabled in this setup.
3. Open your `heithemdev/heithemdev` repository → Settings → Secrets and variables → Actions → New repository secret.
4. Name it exactly `METRICS_TOKEN` and paste the token.
5. Under repository Settings → Actions → General → Workflow permissions, allow GitHub Actions to write repository contents if necessary. The workflow also sets `permissions: contents: write`.
6. Commit the workflow, then open Actions → **GitHub profile metrics** → Run workflow.
7. After a successful run, the action commits `assets/github-metrics.svg` to your repository automatically. Only then will the README metrics image render.

**Security:** Never put your token in the source, a workflow literal, a README, or a screenshot. For stronger isolation, use a fine-grained token if it works for your selected metrics and configure the smallest permissions you can.

## 3. Keep your existing Pac-Man workflow

The README reuses your existing `output` branch URLs:

- `output/pacman-contribution-graph.svg`
- `output/pacman-contribution-graph-dark.svg`

If these exist and animate on your current profile, do not modify the Pac-Man workflow. If they do not exist, install or repair the generator from https://github.com/abozanona/pacman-contribution-graph and publish both assets to an `output` branch.

## 4. What was deliberately excluded

- No projects section; your portfolio handles detailed case studies.
- No profile photo or AI artwork; your GitHub avatar already shows you.
- No visitor counters, made-up statistics, trophy boards, or repetitive GitHub stats cards.
- No custom CSS; GitHub sanitizes profile README markup. The layout uses basic HTML and generated SVGs.

## Sources / maintenance

- GitHub profile README generator: https://github.com/rahuldkjain/github-profile-readme-generator
- Metrics engine and Action: https://github.com/lowlighter/metrics
- Metrics GitHub Action setup: https://github.com/lowlighter/metrics/blob/master/.github/readme/partials/documentation/setup/action.md
- Animated Pac-Man contributions: https://github.com/abozanona/pacman-contribution-graph
- Wave generator: https://github.com/kyechan99/capsule-render

The metrics badge is generated from **GitHub data**, not from your full professional project history. That distinction matters if your strongest work lives in private client repos.
