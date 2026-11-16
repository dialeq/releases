# DIALeQ releases

**DIALeQ** is a fast, local-first API testing tool from [Jana Software Lab](https://dialeq.janasoftwarelab.in).
_Connect. Test. Deliver._

This repository holds the files that go with each DIALeQ release but can't ship inside the app's store package: the source code of the open-source components we're required to offer, and the third-party notices for that version. It doesn't contain DIALeQ's own source code.

## Getting DIALeQ

| What                    | Where                                                                                                                         |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Desktop app (Windows)   | [Microsoft Store](https://apps.microsoft.com/detail/9NN1DCS6VN06). The Store installs and updates it.                         |
| Command line (desktop)  | Installed with the app as the `dialeq` command (alias `dq`).                                                                  |
| CI runner               | [`@dialeq/ci`](https://www.npmjs.com/package/@dialeq/ci) on npm, command `dialeq_ci`.                                          |
| macOS                   | Not yet available. When it is, it will be published here.                                                                     |

The app isn't distributed as a download from this repository; install it from the Microsoft Store.

## What each release contains

Each DIALeQ version has a release here tagged `v<version>` (for example `v0.12.1`), with:

- **`THIRD_PARTY_NOTICES.txt`**: the licences and notices of the open-source software that version of DIALeQ includes. The same file is inside the installed app.
- **`git-source-<git release>.tar`**: the complete source code of the Git build bundled with DIALeQ, named after that Git build's release (not DIALeQ's version). Git is licensed under the GNU General Public License v2.0, and this archive is the corresponding source we provide under it.

The notices inside the app name the release they belong to. The website's [licences page](https://dialeq.janasoftwarelab.in/legal/licences/) links here as well.

## Licences and legal

- DIALeQ itself is proprietary software, licensed under its End User Licence Agreement, which is shown when you install the app and published on the [website](https://dialeq.janasoftwarelab.in).
- Third-party components are licensed under their own terms, as listed in each release's `THIRD_PARTY_NOTICES.txt`.
- Privacy: [dialeq.janasoftwarelab.in/legal/privacy](https://dialeq.janasoftwarelab.in/legal/privacy/).

## Support

Questions, problems or source-code requests: **support@janasoftwarelab.in**.

Please report problems with DIALeQ by email rather than in this repository's issues.

## For maintainers

Publish a release with each Microsoft Store submission, from the standalone clone the Store package was built from:

1. Collect the Git source with `pnpm collect:git-source` (it lands in `dist-git-source/`).
2. Take `THIRD_PARTY_NOTICES.txt` from the package's `release/win-unpacked/resources/`.
3. Create the release:

   ```bash
   gh release create v<version> --repo dialeq/releases --title "DIALeQ <version>" \
     dist-git-source/git-source-<git release>.tar \
     release/win-unpacked/resources/THIRD_PARTY_NOTICES.txt
   ```

Never delete or replace a published release's files: the notices in that version of the app point at them.

---

Copyright © 2026 Jana Software Lab.
