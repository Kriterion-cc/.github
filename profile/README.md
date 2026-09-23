<p align="center">
  <a href="https://kriterion.cc">
    <img src="https://raw.githubusercontent.com/Kriterion-cc/.github/main/profile/kriterion-mark.svg" width="88" alt="Kriterion">
  </a>
</p>

<h1 align="center">Kriterion</h1>

<p align="center"><strong>Frontier research, open to everyone.</strong></p>

<p align="center">
  <a href="https://kriterion.cc">Website</a> ·
  <a href="https://kriterion.cc/docs">Documentation</a> ·
  <a href="https://kriterion.cc/download">Download the CLI</a>
</p>

Kriterion runs open protocol research challenges. An organizer states the problem, the
security properties, and the cost metric as a Lean library. A participant designs a protocol
and proves that the design meets the obligation. The Lean kernel checks each proof and
computes each design cost. A public board orders the verified designs. Each verified design
becomes the base that the next person builds on.

## How it works

1. **Prove.** A challenge fixes one obligation as a Lean type. An entry inhabits it or it
   does not. The verifier decides.
2. **Measure.** A metric is a Lean function that the organizer writes. The verifier evaluates
   it on dedicated hardware.
3. **Rank.** The board orders the entries that have a proof. One AI reviewer adds a public
   note. The note changes nothing on the board.

## Repositories

| Repository | Contents |
| --- | --- |
| [kriterion-challenge](https://github.com/Kriterion-cc/kriterion-challenge) | Public challenge definitions and starter submissions. |
| [kriterion-cli](https://github.com/Kriterion-cc/kriterion-cli) | Participant CLI, API documentation, and the OpenAPI specification. |
| [argomac-lean](https://github.com/Kriterion-cc/argomac-lean) | ArgoMAC construction, proofs, and tests. The starter for the BN254 scalar multiplication challenge. |

All three repositories are licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).

## Submit an entry

Install the CLI with Node.js 18 or newer:

```sh
curl -fsSL https://raw.githubusercontent.com/Kriterion-cc/kriterion-cli/v0.1.0/kriterion -o kriterion
chmod +x kriterion
```

Create a token on the [Settings page](https://kriterion.cc/settings). Build your Lean
project with `lake build`. Then submit one pinned commit from a public HTTPS Git repository:

```sh
export KRITERION_TOKEN='<token-from-settings>'
./kriterion submit \
  --challenge <slug> \
  --repo https://github.com/you/entry \
  --commit <40-hex-commit>
```

The hosted verifier makes the final decision. Read the
[first submission tutorial](https://github.com/Kriterion-cc/kriterion-cli/blob/main/docs/tutorials/first-submission.md)
for the complete walk-through.

## Status

Kriterion is in a private trial. The documentation and the CLI are public. The challenge
boards admit approved accounts only.

---

<p align="center">A <a href="https://babylonlabs.io">Babylon Labs</a> project.</p>
