# dglinux-repo

Pacman repository with the DGLinux apps (DG Files, Govindamp, DG Burner, DG Games Center and others).
The DGLinux App Center shows them in their own section, **DGLinux apps**, separate from Arch and Flathub.

Repozitorijum paketa za pacman sa DGLinux programima. Centar aplikacija ih prikazuje u posebnom odeljku
**DGLinux programi**, odvojeno od Arch i Flathub programa.

## Use / Upotreba

These packages are made for DGLinux and install only on DGLinux (they require the `dglinux-release`
package, which comes with DGLinux and is not in this repository).

Paketi su napravljeni za DGLinux i instaliraju se samo na DGLinux-u (traže paket `dglinux-release`, koji dolazi
sa DGLinux-om i nije u ovom repozitorijumu).

Packages and the database are signed with the key **DGLinux Repository**
(`893D 661B 6743 20C8 F6BF  8612 CDE0 56F4 1D89 6846`, file `dglinux.gpg`):

```sh
curl -sL https://govindayu.github.io/dglinux-repo/dglinux.gpg | sudo pacman-key --add -
sudo pacman-key --lsign-key 893D661B674320C8F6BF8612CDE056F41D896846
```

Add to `/etc/pacman.conf`:

```ini
[dglinux]
Server = https://govindayu.github.io/dglinux-repo/$arch
```

Then `sudo pacman -Sy` and install apps from the App Center (or `sudo pacman -S <package>`).

## Layout / Sadržaj

- `x86_64/dglinux.db`, `x86_64/dglinux.files` — package database (`repo-add`)
- `x86_64/*.pkg.tar.zst` — packages
- `x86_64/catalog.json` — names, descriptions and icons for the App Center
