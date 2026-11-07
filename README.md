# Dal releases

Downloads and the auto-update feed for **Dal**, a native Git client for macOS (macOS 14 or later).

## Install

**In Terminal (recommended)** — downloads the latest release into `/Applications` and opens it:

```bash
url=$(curl -fsSL https://api.github.com/repos/Bur0/dal-releases/releases/latest | grep -o 'https://[^"]*/Dal-[^"]*\.zip' | head -1) && curl -fsSL "$url" -o /tmp/Dal.zip && ditto -x -k /tmp/Dal.zip /Applications && rm /tmp/Dal.zip && open /Applications/Dal.app
```

**In the browser** — download `Dal-x.y.z.zip` from [the latest release](https://github.com/Bur0/dal-releases/releases/latest),
unzip it and drag **Dal.app** into **Applications**. Dal isn't notarized yet, so the first launch is blocked once:

- macOS 15 Sequoia and later: click **Done**, then **System Settings → Privacy & Security → Open Anyway**.
- macOS 14 Sonoma: right-click **Dal.app** → **Open** → **Open**.
- Or in Terminal: `xattr -dr com.apple.quarantine /Applications/Dal.app`

You also need Git (accept the Command Line Tools prompt on the first `git` command, or `brew install git`);
for pull requests, `brew install gh && gh auth login`.

### Türkçe

Terminal'e yukarıdaki komutu yapıştırman yeterli. Tarayıcıdan indirirsen zip'i aç, **Dal.app**'i
**Uygulamalar**'a sürükle; ilk açılışta **Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç**
(macOS 14'te sağ tık → **Aç**).

## Updates

Dal updates itself: it reads [`appcast.xml`](appcast.xml) from this repository every hour, downloads new
versions in the background and shows **Update ready · Restart Dal** in its tab bar. Updates are signed;
Dal refuses any that don't match its key.

This repository only holds release artifacts; it's updated by the release script.
