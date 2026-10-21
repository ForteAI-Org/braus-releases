# braus-releases

The update feed of [Braus](https://braus.ai), the macOS app of
[ForteAI-Org/mecum-private](https://github.com/ForteAI-Org/mecum-private).

This repository is a container, not a place to read: it holds nothing but what
Sparkle, the app's updater, polls and downloads.

- `docs/appcast.xml`, served by GitHub Pages at
  <https://forteai-org.github.io/braus-releases/appcast.xml>, is `SUFeedURL` in
  every build of Braus. It names the newest release, its build number and the
  EdDSA signature of its archive.
- The archives (`Braus-<version>.zip`) are the assets of this repository's
  releases, tagged `v<version>`. They are too large to travel through git.

Both are written by the app repository's **Release** workflow
(`.github/workflows/release.yml`) or by `BrausApp/App/Scripts/publish_release.sh`
on a maintainer's Mac. Nothing here is edited by hand.

Do not rename this repository: its Pages URL is compiled into every installed
copy, and GitHub does not redirect Pages. Do not sign the appcast with any key
but Braus's: the public half is `SUPublicEDKey` in the app's Info.plist, and an
appcast signed otherwise is one every installed build refuses.
