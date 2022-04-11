# Mainnet Artifacts

Artifacts for and leading up to the Oasis Mainnet.

## PGP Keys of Current Maintainers

- [Jernej Kos] ([keys.openpgp.org][opengpg-jernej],
  [keyserver.ubuntu.com][ubuntu-jernej]):

  ```text
  pub   rsa8192 2013-09-11 [C] [expires: 2027-03-02]
        D411CB231098FE0CFD51F5E2D2C5CA66EBF32285
  uid           [ unknown] Jernej Kos <jernej@kos.mx>
  sub   rsa4096 2013-09-11 [S] [expires: 2027-03-02]
  sub   rsa4096 2013-09-11 [E] [expires: 2027-03-02]
  ```

- [Peter Us] ([keys.openpgp.org][opengpg-peter],
  [keyserver.ubuntu.com][ubuntu-peter]):

  ```text
  pub   rsa4096 2020-12-27 [SC] [expires: 2022-12-27]
        69F95042868C3CB0DCA558558BCCEE2C3A33191C
  uid           [ unknown] Peter <peter@u-s.si>
  sub   rsa4096 2020-12-27 [S] [expires: 2022-12-27]
  sub   rsa4096 2020-12-27 [A] [expires: 2022-12-27]
  sub   rsa4096 2020-12-27 [E] [expires: 2022-12-27]

  ```

- [Tadej Janež] ([keys.openpgp.org][opengpg-tadej],
  [keyserver.ubuntu.com][ubuntu-tadej]):

  ```text
  pub   rsa4096 2018-02-18 [C] [expires: 2022-05-18]
        6DCAA76BD25A2E117CBCBE073C4CCAFC8E6DEC53
  uid           [ unknown] Tadej Janež <tadej.j@nez.si>
  sub   rsa4096 2018-02-18 [E] [expires: 2022-05-18]
  sub   rsa4096 2018-02-18 [S] [expires: 2022-05-18]
  sub   rsa4096 2018-02-18 [A] [expires: 2022-05-18]
  ```

[Jernej Kos]: https://github.com/kostko
[opengpg-jernej]: https://keys.openpgp.org/search?q=jernej@kos.mx
[ubuntu-jernej]:
  https://keyserver.ubuntu.com/pks/lookup?search=0xD411CB231098FE0CFD51F5E2D2C5CA66EBF32285&fingerprint=on&op=index

[Peter Us]: https://github.com/ptrus
[opengpg-peter]: https://keys.openpgp.org/search?q=peter@u-s.si
[ubuntu-peter]:
  https://keyserver.ubuntu.com/pks/lookup?search=0x69F95042868C3CB0DCA558558BCCEE2C3A33191C&fingerprint=on&op=index

[Tadej Janež]: https://github.com/tjanez
[opengpg-tadej]: https://keys.openpgp.org/search?q=tadej.j@nez.si
[ubuntu-tadej]:
  https://keyserver.ubuntu.com/pks/lookup?search=0x6DCAA76BD25A2E117CBCBE073C4CCAFC8E6DEC53&fingerprint=on&op=index

## Obtaining PGP keys of Current Maintainers

One way to obtain PGP keys of the current maintainers and import them into your
keyring is via the [GnuPG] command line tool:

```bash
gpg --keyserver hkps://keys.openpgp.org:443 --recv-key \
  D411CB231098FE0CFD51F5E2D2C5CA66EBF32285 \
  69F95042868C3CB0DCA558558BCCEE2C3A33191C \
  6DCAA76BD25A2E117CBCBE073C4CCAFC8E6DEC53
```

If fetching was successful, the output should be similar to:

```text
gpg: key 3C4CCAFC8E6DEC53: public key "Tadej Janež <tadej.j@nez.si>" imported
gpg: key 8BCCEE2C3A33191C: public key "Peter <peter@u-s.si>" imported
gpg: key D2C5CA66EBF32285: public key "Jernej Kos <jernej@kos.mx>" imported
gpg: Total number processed: 3
gpg:               imported: 3
```

You can also list the keys at any later point by running:

```bash
gpg --keyid-format=none --list-keys \
  D411CB231098FE0CFD51F5E2D2C5CA66EBF32285 \
  69F95042868C3CB0DCA558558BCCEE2C3A33191C \
  6DCAA76BD25A2E117CBCBE073C4CCAFC8E6DEC53
```

You should get output similar to to the one
[above](#pgp-keys-of-current-maintainers).

[GnuPG]: https://www.gnupg.org/software/index.html

## Verifying Genesis File Signatures

To verify the genesis file signatures, download a release's `genesis.json` and
the corresponding `genesis.json.<SIGNER>.asc` files and run:

```bash
for f in genesis.json.*.asc; do gpg --verify $f genesis.json; done
```

If the output is similar to:

```text
gpg: Signature made Mon 11 Apr 2022 10:55:04 AM CEST
gpg:                using RSA key E91ED01D68E7470A25B7439B14E26E7833B95334
gpg: Good signature from "Jernej Kos <jernej@kos.mx>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: D411 CB23 1098 FE0C FD51  F5E2 D2C5 CA66 EBF3 2285
     Subkey fingerprint: E91E D01D 68E7 470A 25B7  439B 14E2 6E78 33B9 5334
gpg: Signature made Mon 11 Apr 2022 11:32:33 AM CEST
gpg:                using RSA key D6EAA0C3AD3F59934656B734A870DCACB5F33080
gpg: Good signature from "Peter <peter@u-s.si>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 69F9 5042 868C 3CB0 DCA5  5855 8BCC EE2C 3A33 191C
     Subkey fingerprint: D6EA A0C3 AD3F 5993 4656  B734 A870 DCAC B5F3 3080
gpg: Signature made Mon 11 Apr 2022 11:02:03 AM CEST
gpg:                using RSA key DBE7D641D40E1A0C5D43FCD837B064855C101C1B
gpg: Good signature from "Tadej Janež <tadej.j@nez.si>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 6DCA A76B D25A 2E11 7CBC  BE07 3C4C CAFC 8E6D EC53
     Subkey fingerprint: DBE7 D641 D40E 1A0C 5D43  FCD8 37B0 6485 5C10 1C1B
```

then you've successfully verified the genesis file signatures.
