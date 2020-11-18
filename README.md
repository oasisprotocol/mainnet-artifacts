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
    pub   rsa4096/0x75D14FC60FDD148F 2019-01-11 [SC]
        Key fingerprint = 7A6A 1F3B 1121 EC79 8BF3  5BA9 75D1 4FC6 0FDD 148F
    uid                              Peter Us <ptrusr@gmail.com>
    sub   rsa4096/0x685CB020C82742AA 2019-01-11 [A]
    sub   rsa4096/0x3402D101339CF3ED 2019-01-11 [E]
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

[Peter Us]: https://keys.openpgp.org/search?q=ptrusr@gmail.com

[Tadej Janež]: https://keys.openpgp.org/search?q=tadej.j@nez.si

## Verifying Genesis File Signatures

Obtain PGP keys of the current maintainers and import them into your keyring.

To verify the genesis file signatures, download a release's `genesis.json` and
the corresponding `genesis.json.asc` file and run:

```bash
gpg --verify genesis.json.asc
```

If the output is similar to:

```text
gpg: assuming signed data in 'genesis.json'
gpg: Signature made Wed 18 Nov 2020 01:24:31 PM CET
gpg:                using RSA key E91ED01D68E7470A25B7439B14E26E7833B95334
gpg: Good signature from "Jernej Kos <jernej@kos.mx>"
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: D411 CB23 1098 FE0C FD51  F5E2 D2C5 CA66 EBF3 2285
     Subkey fingerprint: E91E D01D 68E7 470A 25B7  439B 14E2 6E78 33B9 5334
gpg: Signature made Wed 18 Nov 2020 01:13:39 PM CET
gpg:                using RSA key 7A6A1F3B1121EC798BF35BA975D14FC60FDD148F
gpg: Good signature from "Peter Us <ptrusr@gmail.com>"
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 7A6A 1F3B 1121 EC79 8BF3  5BA9 75D1 4FC6 0FDD 148F
gpg: Signature made Wed 18 Nov 2020 12:00:49 PM CET
gpg:                using RSA key DBE7D641D40E1A0C5D43FCD837B064855C101C1B
gpg: Good signature from "Tadej Janež <tadej.j@nez.si>"
Primary key fingerprint: 6DCA A76B D25A 2E11 7CBC  BE07 3C4C CAFC 8E6D EC53
     Subkey fingerprint: DBE7 D641 D40E 1A0C 5D43  FCD8 37B0 6485 5C10 1C1B
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
```

then you've successfully verified the genesis file signatures.
