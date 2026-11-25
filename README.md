# Frameworked Marketplace

The marketplace for Frameworked plugins, for Claude Code and Codex.

## Install

### Claude Code

```
/plugin marketplace add github:FrameworkedApp/marketplace
/plugin install launchpad@frameworked        # free, public
/plugin install growth-toolkit@frameworked   # paid, private (see the access section below)
/plugin install studio-toolkit@frameworked   # paid, private (see the access section below)
```

Restart Claude Code after install.

### Codex

```bash
codex plugin marketplace add FrameworkedApp/marketplace
codex plugin add launchpad@frameworked
```

Start a new Codex session, then run `$launchpad:lp help`. LaunchPad is the plugin available on Codex today; Growth Toolkit and Studio Toolkit are Claude Code only. Details, the verified command list, and the differences from Claude Code are in [LaunchPad: How It Works, Codex](https://github.com/FrameworkedApp/launchpad/blob/main/docs/guides/HOW_IT_WORKS.md#codex).

To update on Codex, run `codex plugin marketplace upgrade frameworked`, then `codex plugin add launchpad@frameworked` again.

### Moving from `builtform`

This marketplace was named `builtform` until the LaunchPad 2.4.0 release. The repository is the same; only the name after `@` changed.

- **Claude Code:** an existing `launchpad@builtform` install keeps working and keeps receiving updates. To move to the new name:

  ```
  /plugin marketplace remove builtform
  /plugin marketplace add FrameworkedApp/marketplace
  /plugin install launchpad@frameworked
  ```

  Removing the marketplace also uninstalls its plugins, so reinstall each one you use (for example `growth-toolkit@frameworked`). Projects that pin plugins in `.claude/settings.json` rename the `extraKnownMarketplaces` key and the `enabledPlugins` entries from `builtform` to `frameworked`.

- **Codex:** an existing `launchpad@builtform` install keeps working but no longer receives updates (`codex plugin marketplace upgrade builtform` reports a name mismatch). To move to the new name:

  ```bash
  codex plugin remove launchpad@builtform
  codex plugin marketplace remove builtform
  codex plugin marketplace add FrameworkedApp/marketplace
  codex plugin add launchpad@frameworked
  ```

  Remove the plugin before the marketplace: removing a Codex marketplace does not uninstall its plugins.

## Plugins

### LaunchPad

Autonomous AI coding harness for spec-driven software delivery. Greenfield and brownfield. Free, open source. Full docs and source at [github.com/FrameworkedApp/launchpad](https://github.com/FrameworkedApp/launchpad).

The listing follows the `stable` branch of the LaunchPad repository. That branch moves forward to each release only after the release checks pass, so both hosts always install the latest verified release.

### Growth Toolkit (paid)

Strategic growth workflows for your company, wired in as Claude Code agents and skills. One slash command per workflow produces a structured artifact you can immediately act on, edit, or hand to your team. No methodology lookups, no framework reading, no manual translation: the toolkit operationalizes the work.

**What it covers, every stage of growing a company:**

- **Customer discovery**: interview guides that surface real problems without leading the conversation
- **Positioning**: what makes you different, who you're for, what category you compete in
- **Sales pitch**: first-call storyboard that opens with the buyer's world, not your product
- **Offer construction**: the offer you sell, its components, naming, scarcity, and guarantees
- **Lead generation**: strategy for getting in front of buyers across warm outreach, content, cold outreach, and paid ads
- **Pricing & monetization**: the money model: attraction offers, upsells, downsells, continuity
- **Web copy**: page-by-page copy for landing, pricing, about, feature, and product pages
- **Content**: editorial calendars, content briefs, distillation strategy
- **Funnel design**: top/mid/bottom funnel mapping, leakage diagnostics, customer journey
- **Acquisition**: channel testing, SEO, paid ads, attribution architecture
- **Retention**: keeping the customers you win
- **Launch**: sequencing the moment you go live

Everything is already wired as agents and skills. You don't read about the methodology: you run the command, the artifact gets written to your repo, and you move on.

**Access:** This is a paid plugin. The source lives in the private `FrameworkedApp/growth-toolkit` repository.

To request access, open an issue using the [Request Growth Toolkit access](https://github.com/FrameworkedApp/marketplace/issues/new?template=request-access.yml) template. Once approved, your GitHub account is granted read access to the private repo, and the install command above succeeds. Until then, the install fails on the GitHub auth check, and no plugin files leave the private repo.

### Studio Toolkit (paid)

The Frameworked toolbox of asset-making tools, wired in as Claude Code commands backed by skills and agents. The Growth, Content, Marketing and Scale toolkits decide; Studio Toolkit makes the assets those decisions need, and every tool also runs on its own. Outputs follow your brand.

**Released:**

- **Image** (`/studio-image`): generate and edit images with the Nano Banana engine (Google Gemini image models). Cheap drafts, one high-quality final, chat refinement and Google Search grounding. Conversational by default; `--auto` drafts from a brief and checks the results; `--review` checks an existing image against its brief.

**Next:** charts and infographics, then logo and identity, design system and product demo. Video, audio and deck follow as needs arise.

**Requirements:** Python 3 with the packages and API keys each tool needs. Run `/studio-setup-check` after install; it lists anything missing. The Image tool needs a `GEMINI_API_KEY` in your environment.

**Access:** This is a paid plugin. The source lives in the private `FrameworkedApp/studio-toolkit` repository. To request access, open an issue in [FrameworkedApp/marketplace](https://github.com/FrameworkedApp/marketplace/issues) naming Studio Toolkit and your GitHub username. Until access is granted, the install fails on the GitHub auth check.

## Questions and support

Open an issue in [FrameworkedApp/marketplace](https://github.com/FrameworkedApp/marketplace/issues). We answer there.

## What this repo is

This repo holds the marketplace listing only; no plugin code lives here. Each plugin's source, issues, and documentation live in its own repo:

- LaunchPad → [github.com/FrameworkedApp/launchpad](https://github.com/FrameworkedApp/launchpad) (public)
- Growth Toolkit → `FrameworkedApp/growth-toolkit` (private, access on request)
- Studio Toolkit → `FrameworkedApp/studio-toolkit` (private, access on request)

## License

MIT, see [LICENSE](LICENSE).
