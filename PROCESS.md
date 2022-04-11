# Process for Preparing Mainnet Artifacts

## Preparing Genesis File

Once the Oasis Network reaches the agreed block height, release preparers should
follow the instructions in the [Upgrade Log] and [Handling Network Upgrades]
docs to dump the network's state to a genesis file and modify it as agreed by
the community.

## Signing Genesis File with PGP

Each signer should verify the new genesis file and then sign it by running:

```bash
gpg --armor --output genesis.json.<SIGNER-NAME>.asc --detach-sign genesis.json
```

replacing `<SIGNER-NAME>` with his name.

The release manager should collect all the signatures.

## Preparing a GitHub Release

Create a new release and attach the new genesis file (`genesis.json`) and the
corresponding PGP signatures (`genesis.json.<SIGNER-NAME>.asc`).

[Upgrade Log]: https://docs.oasis.dev/general/run-a-node/upgrade-log
[Handling Network Upgrades]:
  https://docs.oasis.dev/general/run-a-node/maintenance-guides/handling-network-upgrades
