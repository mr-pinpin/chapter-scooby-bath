# Official publishing rules

This is mr-pinpin/chapter-scooby-bath, a deployment-only repo.
The local checkout remains mr-pinpin-official. Author in mr-pinpin-source:
https://github.com/mr-pinpin/mr-pinpin-source
Canonical readers: https://mr-pinpin.github.io/
Store: https://huggingface.co/buckets/miguelemosreverte/mr-pinpin-archive
Do not add authoring history or site binaries.
Never edit/delete releases/<sha>.json or rewrite published HF objects. New
releases add new records; rollback only changes release.json to an existing SHA.
Use the authoring repo's tools/publishing CLI, normal commits, and normal pushes.
Do not bypass archive/file verification or raise the 950,000,000-byte size cap.
HF public downloads require no credentials. Do not add secrets to this repo.
No deployment or old-site cutover without the operator's authorization.
Use canonical local paths, not former-name symlink aliases. GitHub repo redirects
do not imply Pages URL redirects. The source legacy site is not canonical.
Keep historical evidence and immutable release manifests unchanged after renames.
Read LICENSE, CONTENT-LICENSE.md, and THIRD-PARTY-NOTICES.md before reuse.
MIT covers owned software only, not creative content embedded in JS/JSON/HTML
or deployed media. Preserve upstream terms, prior grants, and legal exceptions;
do not invent rights in unprotectable AI or public-domain material.
Publish new notices through a new source build; never mutate an old archive.
