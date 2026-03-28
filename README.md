# Legalize

**Legislation as code.** Every law as a Markdown file. Every reform as a Git commit.

Legalize turns official legislation into version-controlled, machine-readable data. Browse, search, diff, and build on structured legal data from multiple countries.

**[legalize.dev](https://legalize.dev)** — Browse laws, see diffs, search across legislation.

## Countries

| Country | Repo | Laws | Source | Status |
|---------|------|------|--------|--------|
| 🇪🇸 Spain | [legalize-es](https://github.com/legalize-dev/legalize-es) | 8,642 | [BOE](https://www.boe.es/) | ✅ Live |
| 🇫🇷 France | [legalize-fr](https://github.com/legalize-dev/legalize-fr) | 80 codes | [Légifrance](https://www.legifrance.gouv.fr/) | 🚧 Beta |
| 🇩🇪 Germany | — | — | [BGBL](https://www.bgbl.de/) | 🔜 Help wanted |
| 🇵🇹 Portugal | — | — | [DRE](https://dre.pt/) | 🔜 Help wanted |
| 🇸🇪 Sweden | — | — | [Riksdagen](https://www.riksdagen.se/) | 🔜 Help wanted |
| 🇫🇮 Finland | — | — | [Finlex](https://www.finlex.fi/) | 🔜 Help wanted |
| 🇳🇱 Netherlands | — | — | [Overheid.nl](https://www.overheid.nl/) | 🔜 Help wanted |
| 🇧🇷 Brazil | — | — | [LeXML](https://www.lexml.gov.br/) | 🔜 Help wanted |
| 🇺🇸 USA | — | — | — | 🔜 Help wanted |

**Want to add your country?** See the [step-by-step guide](https://github.com/legalize-dev/legalize-pipeline/blob/main/docs/ADDING_A_COUNTRY.md).

## How it works

Each law is a Markdown file with YAML frontmatter. When a reform is published, the file is updated and committed with the official publication date.

Standard Git tools become legal research tools:

```bash
# Clone Spanish legislation
git clone https://github.com/legalize-dev/legalize-es.git

# What does Article 135 of the Constitution say today?
grep -A 10 "Artículo 135" spain/BOE-A-1978-31229.md

# When did it change?
git log --oneline -- spain/BOE-A-1978-31229.md

# Show the exact diff of the 2011 fiscal stability reform
git diff 6660bcf^..6660bcf -- spain/BOE-A-1978-31229.md
```

## Repos

| Repo | What |
|------|------|
| **[legalize](https://github.com/legalize-dev/legalize)** | This repo. Index, docs, overview. |
| **[legalize-pipeline](https://github.com/legalize-dev/legalize-pipeline)** | The engine. Fetches, parses, and commits legislation. |
| **[legalize-es](https://github.com/legalize-dev/legalize-es)** | Spanish laws as Markdown + git history. |
| **[legalize-fr](https://github.com/legalize-dev/legalize-fr)** | French codes as Markdown + git history. |

## Why

Legal texts are amended constantly, but tracking changes is hard. Official sources publish consolidated versions with no way to compare. Commercial providers charge hundreds per month for version history.

Legalize is open legal infrastructure:

- **For developers** — structured, versioned legal data with a REST API
- **For researchers and journalists** — explore the evolution of legislation with git
- **For citizens** — see how the laws that affect you have changed

## Contributing

The main contribution is adding a new country. Fork [legalize-pipeline](https://github.com/legalize-dev/legalize-pipeline), follow the [guide](https://github.com/legalize-dev/legalize-pipeline/blob/main/docs/ADDING_A_COUNTRY.md), and open a PR.

Found an error in a law text? Open an issue in the relevant country repo with the law name, article, and the official source showing the correct version.

## Support

Legalize is open source and free. If you want to help fund hosting and development:

- [Open Collective](https://opencollective.com/legalize)
- [Buy me a coffee](https://buymeacoffee.com/elopcast)

## License

Legislative content: public domain (sourced from official government publications).
Repository structure, metadata, and tooling: [MIT](LICENSE).

---

Created by [Enrique Lopez](https://enriquelopez.eu) · [legalize.dev](https://legalize.dev)
