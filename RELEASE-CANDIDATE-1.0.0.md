# OfferLoop Assist 1.0.0 release-candidate record

Recorded: 2026-10-07

Status: **NO-GO for public sale**. The build is a technical release candidate, not a legally approved or signed market release.

## Build artifacts

| Artifact | Size (bytes) | SHA-256 |
| --- | ---: | --- |
| `release/OfferLoop-Assist-Setup-1.0.0-x64.exe` | 131,513,664 | `77f538893d0fc0fc01a2bf12550a9a8c83f00f7b6eb7c3de4616a86e450aa3f5` |
| `release/OfferLoop-Assist-Portable-1.0.0-x64.exe` | 131,299,160 | `f4e1fdfe7eb334b31ee22064ab2dd24d1d26182bcaff35c217a152f9dbaa5611` |

The canonical checksum file is `release/SHA256SUMS.txt`.

## Technical evidence

- TypeScript, Electron TypeScript, Vite, NSIS, and portable-package build stages completed successfully.
- Production dependency report contains 198 packages, zero unknown licences, and zero copyleft/manual-review classifications.
- `npm audit --omit=dev --audit-level=high` reported zero production vulnerabilities.
- Sharp and its bundled libvips runtime were removed. Electron `nativeImage` now performs the required legacy image conversion.
- The unpacked application and `app.asar` contain no Sharp or libvips package/runtime. Text matches such as `csharp`, `fsharp`, and `qsharp` are syntax-highlighting language names and are unrelated.
- The packaged `resources/legal` directory contains the licence, provenance, dependency report, governance, contributor, and DCO records listed by the legal-file manifest.

## Signature evidence

Windows Authenticode status on 2026-10-07:

| File | Status | Signer |
| --- | --- | --- |
| `release/win-unpacked/OfferLoop Assist.exe` | `NotSigned` | None |
| Setup executable | `NotSigned` | None |
| Portable executable | `NotSigned` | None |

Do not represent these files as signed or as having a verified publisher.

## Required approvals and evidence still missing

- Replace the provisional `OfferLoop contributors` copyright holder with the exact person or company after written confirmation.
- Collect contributor ownership/assignment or DCO evidence.
- Complete and sign the asset ownership register for the logo, Windows icon, screenshots, and OfferLoop name.
- Obtain a trademark/name clearance decision for `OfferLoop` from qualified counsel.
- Obtain written legal approval for the MIT + Apache-2.0 structure and store the approval reference in the release playbook.
- Obtain a Windows code-signing certificate in the final seller's legal name, sign all executables, and repeat signature and checksum verification.
- Complete the remaining commercial, privacy, payment, clean-machine, support, and launch gates in `SITE-BETA-RELEASE-PLAYBOOK.md`.

Only an authorized owner and qualified lawyer can approve the legal gates. This repository record does not substitute for legal advice or approval.
