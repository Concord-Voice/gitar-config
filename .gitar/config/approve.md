Approve only when ALL of these hold. When in doubt, do not approve.
1. The repository is not Release-Ops, Internal-Dev-Tooling, Agentic-Dev-Tooling, gitar-config, .github, .github-private or Concord-Voice.
2. The PR changes no agent instruction or review-config file: CLAUDE.md, AGENTS.md, agent.md, any SKILL.md, anything under .claude/, .agents/ or .gitar/, or any CODEOWNERS file.
3. The PR changes no CI, supply-chain or scanner file: .github/workflows/, .github/scripts/, .pre-commit-config.yaml, sonar-project.properties, .semgrep/, .gitleaks.toml, .secrets.baseline, eslint or golangci config, Dockerfiles, package.json, package-lock.json, go.mod, go.sum, Gemfile, Gemfile.lock, Podfile, Podfile.lock.
4. The PR changes no security-sensitive path: any path containing auth, mfa, rbac, session, password, token, crypto, e2ee, encryption, preload, ipc, signing or migrations, or anything under infrastructure/.
5. The PR has none of these labels: risk: hotfix, risk: security, risk: privacy, risk: breaking-change, risk: data-loss.
6. All Gitar findings are resolved, and no other reviewer has an unresolved or change-requesting comment.
