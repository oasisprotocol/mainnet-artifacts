# Mainnet Artifacts

Artifacts for and leading up to the Oasis Mainnet.

## PGP Keys of Current Maintainers

- [Jernej Kos]:

    ```text
    pub   rsa8192/0xD2C5CA66EBF32285 2013-09-11 [C]
        Key fingerprint = D411 CB23 1098 FE0C FD51  F5E2 D2C5 CA66 EBF3 2285
    uid                              Jernej Kos <jernej@kos.mx>
    sub   rsa4096/0x592E8C59DC05FDED 2014-10-30 [A]
    sub   rsa4096/0x14E26E7833B95334 2013-09-11 [S]
    sub   rsa4096/0x22484A1D1CC37261 2013-09-11 [E]
    ```

- [Peter Us]:

    ```text
    pub   rsa4096/0x8BCCEE2C3A33191C 2020-12-27 [SC]
        Key fingerprint = 69F9 5042 868C 3CB0 DCA5 5855 8BCC EE2C 3A33 191C
    uid                              Peter <peter@u-s.si>
    sub   rsa4096/0xA870DCACB5F33080 2020-12-27 [S]
    sub   rsa4096/0xFF26975916ECBFA5 2020-12-27 [A]
    sub   rsa4096/0x62BF065D0C921DAD 2020-12-27 [E]
    ```

- [Tadej Janež]:

    ```text
    pub   rsa4096/0x3C4CCAFC8E6DEC53 2018-02-18 [C]
        Key fingerprint = 6DCA A76B D25A 2E11 7CBC  BE07 3C4C CAFC 8E6D EC53
    uid                              Tadej Janež <tadej.j@nez.si>
    sub   rsa4096/0x37B064855C101C1B 2018-02-18 [S]
    sub   rsa4096/0xB8FEAF8A15C65517 2018-02-18 [E]
    sub   rsa4096/0x1971268908E4B1B7 2018-02-18 [A]
    ```

[Jernej Kos]: https://keys.openpgp.org/search?q=jernej@kos.mx

[Peter Us]: https://keys.openpgp.org/search?q=peter@u-s.si

[Tadej Janež]: https://keys.openpgp.org/search?q=tadej.j@nez.si

## Verifying Genesis File Signatures

Obtain PGP keys of the current maintainers and import them into your keyring.

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
gpg:                 aka "Jernej Kos <kostko@irnas.eu>" [unknown]
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
gpg: Good signature from "Tadej Janež <tadej.j@nez.si>" [ultimate]
Primary key fingerprint: 6DCA A76B D25A 2E11 7CBC  BE07 3C4C CAFC 8E6D EC53
     Subkey fingerprint: DBE7 D641 D40E 1A0C 5D43  FCD8 37B0 6485 5C10 1C1B
```

then you've successfully verified the genesis file signatures.
