# rpi-imager-latest-aur

This repository contains the **PKGBUILD and related files** for packaging **Raspberry Pi Imager (latest version)** for Arch Linux / AUR.

> **Note:** This is *not* the upstream source code. The official upstream repository is [Raspberry Pi Imager](https://github.com/raspberrypi/rpi-imager).

---

## Package Info

- **Package name (AUR):** `rpi-imager-latest`
- **License:** Apache
- **Dependencies:** `qt6-base`, `qt6-svg`, `qt6-tools`, `libarchive`, `curl`, `hicolor-icon-theme`
- **Build dependencies:** `git`, `cmake`, `qt6-tools`
- **Description:** Flash SD cards and USB drives with Raspberry Pi images

---

## Repository Structure

```

PKGBUILD         # Main build script for AUR
.SRCINFO         # Metadata file required by AUR
README.md        # This file
LICENSE          # Apache license

````

Optional files you can include:

- `rpi-imager.install` – for post-install hooks or messages
- `LICENSE` – include upstream license if needed

---

## Building Locally

To build and install the package on your Arch Linux system:

```bash
git clone https://github.com/ktauchathuranga/rpi-imager-latest-aur.git
cd rpi-imager-latest-aur
makepkg -si
````

* Make sure you have all dependencies installed.
* `makepkg` will build the package and install it.

---

## AUR Contribution Workflow

Follow these steps to contribute or update the AUR package:

### 1️⃣ Clone the AUR repository

```bash
git clone ssh://aur@aur.archlinux.org/rpi-imager-latest.git
cd rpi-imager-latest
```

> The branch must be **`master`** — AUR rejects `main`.

---

### 2️⃣ Add remotes for AUR and GitHub

If you want to push to **both AUR and GitHub**, set up two remotes:

```bash
# Add AUR remote
git remote add origin ssh://aur@aur.archlinux.org/rpi-imager-latest.git

# Add GitHub remote
git remote add github git@github.com:ktauchathuranga/rpi-imager-latest-aur.git
```

Check remotes:

```bash
git remote -v
```

Example:

```
origin  ssh://aur@aur.archlinux.org/rpi-imager-latest.git (fetch)
origin  ssh://aur@aur.archlinux.org/rpi-imager-latest.git (push)
github  git@github.com:ktauchathuranga/rpi-imager-latest-aur.git (fetch)
github  git@github.com:ktauchathuranga/rpi-imager-latest-aur.git (push)
```

---

### 3️⃣ Update PKGBUILD

* Change `pkgver` to the new version
* Update `source` URL if upstream release changed
* Update `sha256sums`:

```bash
updpkgsums
```

* Test build:

```bash
makepkg -si
```

---

### 4️⃣ Commit changes

```bash
git add PKGBUILD .SRCINFO
git commit -m "Update rpi-imager to 2.x.x"
```

---

### 5️⃣ Push to AUR

```bash
git push origin master
```

---

### 6️⃣ Push to GitHub

```bash
git push github master
```

> This keeps both AUR and GitHub repos in sync.

---

## Tips

* Always run `makepkg` locally before pushing.
* `.SRCINFO` must always be updated:

```bash
makepkg --printsrcinfo > .SRCINFO
```

---

## References

* [Arch Wiki: AUR Submission Guidelines](https://wiki.archlinux.org/title/AUR_submission_guidelines)
* [Raspberry Pi Imager Official](https://github.com/raspberrypi/rpi-imager)

