# Dal releases

Downloads and the auto-update feed for **Dal**, a native Git client for macOS.

- Get the latest build from [Releases](https://github.com/Bur0/dal-releases/releases), unzip it and move
  `Dal.app` to `/Applications`. Dal isn't notarized, so open it the first time with right-click → **Open**
  (or run `xattr -dr com.apple.quarantine /Applications/Dal.app`).
- After that, Dal updates itself: it reads [`appcast.xml`](appcast.xml) from this repository daily.

This repository only holds release artifacts; it's updated by the release script.
