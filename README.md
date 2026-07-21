# flox-gh-research

An eight-page analysis of a prototype that ports GitHub CLI's `gh extension`
model to the `flox` CLI — covering the design document, the shipped
architecture, the author-facing manifest contract, three reference
extensions, a file-by-file change inventory, and an impact-and-risk
assessment.

The pages are self-contained HTML. Open `index.html` in a browser; no build
step, no server, no dependencies beyond a Google Fonts link.

## Pages

| Page | What's in it |
|---|---|
| `index.html` | Overview, status board, and reading paths |
| `research.html` | Walkthrough of the design document — PRD, the five `gh` primitives preserved, the one deliberate divergence, and the milestone plan |
| `architecture.html` | The subsystem as built: crate split, the two-phase `bpaf` parse, dispatch flow, activation modes, on-disk layout, install and upgrade per kind |
| `changes.html` | Every file touched, with new-and-isolated separated from edits to pre-existing code, and verbatim diff hunks for the wiring |
| `manifest.html` | `flox-extension.toml` field reference, `state.toml`, and a designed-versus-shipped drift table |
| `plugins.html` | The three reference extensions side by side — script, binary, and local |
| `examples.html` | Public repository links and install commands |
| `risks.html` | Impact, accepted risks, the post-GA hardening sweep, documentation drift, and open questions |

## Subjects

The analysis covers a prototype branch (`smorin/github-extension-prototype`)
in a clone of [flox/flox](https://github.com/flox/flox), plus three reference
extensions:

- [smorin/flox-hello-script](https://github.com/smorin/flox-hello-script) — script kind
- [smorin/flox-hello-binary](https://github.com/smorin/flox-hello-binary) — binary kind
- [smorin/flox-hello-local](https://github.com/smorin/flox-hello-local) — local authoring kind

## Scope and accuracy

Figures in `changes.html` are measured against merge-base `0badcdf59` and
reflect the **committed** state of the branch as of **2026-07-21**. The
branch had uncommitted work in its working tree at that time; where that
affects a number, the page says so.

The prototype branch has never been pushed upstream. Nothing described here
shipped in a released version of flox.

Where the design document and the shipped code disagree, the pages describe
both and flag the divergence rather than picking one — the design document
explicitly asks to be overridden by the code.

## License

The analysis text is CC BY 4.0. Quoted source excerpts remain under their
original licenses (flox is Apache-2.0).
