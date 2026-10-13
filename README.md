# Scooby Gets a Bath — Chapter Reader

Public site: https://mr-pinpin.github.io/chapter-scooby-bath/
Authoring repository: https://github.com/mr-pinpin/mr-pinpin-source
Public release bucket: https://huggingface.co/buckets/miguelemosreverte/mr-pinpin-archive

Deployment-only repository: mr-pinpin/chapter-scooby-bath. Source, asset
authoring, and build history remain in the authoring repository. No site binaries
or source history belong in this repo.

Canonical local checkouts are siblings mr-pinpin-official and mr-pinpin-source
under /Users/miguel_lemos/anastasia-pinpin-repos/. Former local names are symlink
aliases; use canonical paths with the publishing tools. Old GitHub repository
URLs redirect to the mr-pinpin organization, but old Pages URLs do not automatically
redirect. Local directory names stay unchanged: mr-pinpin-official checks out
mr-pinpin/mr-pinpin.github.io.
A legacy source site may redeploy at /mr-pinpin-source/; it is not canonical.
The public HF bucket name, historical evidence, and release manifests stay unchanged.

| Location | Role |
| --- | --- |
| mr-pinpin-source | Authoring, recipes, tests, provenance, preserved history |
| mr-pinpin/chapter-scooby-bath | Scoped chapter deployment and immutable release records |
| mr-pinpin-archive on HF | Verified original media, experiments, release archives |

release.json selects a SHA-256-addressed releases/<sha>.json. The manifest records
the source commit, exact archive identity, and every site file's bytes and SHA-256.
CI downloads anonymously from the public Hugging Face bucket and verifies all of
them before deploying. No HF secret is needed. Set Pages source to GitHub Actions.

Run locally: python3 scripts/materialize.py --repo . --out NEW_OUTPUT_DIRECTORY
The Python materializer uses only the standard library and never replaces an
existing output. URLs and paths inside the built site are preserved unchanged.

| Path | Purpose |
| --- | --- |
| release.json | Current release selector |
| releases/<sha>.json | Immutable per-file manifest and source commit |
| scripts/ | Anonymous download and verification, stdlib only |
| .github/workflows/pages.yml | Verify, then deploy to the official site |

To publish or roll back, use tools/publishing/publish.py in the authoring repo:
stage --package PACKAGE --pages-repo THIS_REPO adds an immutable release record;
select --pages-repo THIS_REPO --release SHA --expected-current OLD_SHA explicitly
updates the selector. Review, commit, and push normally. Never force-push. Keep
older release records and HF objects so rollback remains available. First-time
template generation includes the initial selected manifest.

HF buckets are mutable storage, not provider WORM. Hash keys, refusal to overwrite
conflicting content, verified upload readback, and anonymous deployment checks
enforce immutability at the application level. Never replace/delete release
objects. External mutation causes verification failure, not silent deployment.
The script does not create repositories, configure Pages, commit, push, cut over
traffic, or redirect old Pages URLs. Operators manage those actions separately.

## Permissions

MIT covers only project-owned software under LICENSE and LICENSE-MIT.
Deployed stories, media, prompts, and other creative content are excluded even
when embedded in code. CONTENT-LICENSE.md gives limited personal/noncommercial
family permissions only for rights the project controls. THIRD-PARTY-NOTICES.md
preserves upstream terms; prior grants and legal exceptions remain unaffected.
No copyright is invented in public-domain or unprotectable AI-generated material.
These repo notices do not modify any existing immutable release archive.
