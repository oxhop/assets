# How to creata spl token on Solana?

## Create a keypair for the mint authority

```mkdir new-token```

```cd new-token```

```solana-keygen grind --starts-with bos:1```

```solana config set --keypair bosy1VC2BH2gh5fdXA3oKn53EuATLwapLWC4VR2sGHJ.json```

```solana config set --url devnet```

## Get some Devnet SOL for the mint authority

```solana address```

https://faucet.solana.com/

## Make a Mint Address

```solana-keygen grind --starts-with mnt:1```

## Creating the token mint account

```spl-token create-token --program-id TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb --enable-metadata mntLu5qEnjVYVdbcV6Q6eNjNuJyTXGSGYc1jdWfdMDp.json```

## Create and upload image and offchain metadata

https://raw.githubusercontent.com/oxhop/assets/refs/heads/main/spl-token/LOGO_OXHOP.png

https://raw.githubusercontent.com/oxhop/assets/refs/heads/main/spl-token/metadata.json

## Add the metadata to the token

```spl-token initialize-metadata mntLu5qEnjVYVdbcV6Q6eNjNuJyTXGSGYc1jdWfdMDp 'OxHop Token' 'OHT' https://raw.githubusercontent.com/oxhop/assets/refs/heads/main/spl-token/metadata.json```

https://explorer.solana.com/address/mntLu5qEnjVYVdbcV6Q6eNjNuJyTXGSGYc1jdWfdMDp?cluster=devnet

## Mint tokens

```spl-token create-account mntLu5qEnjVYVdbcV6Q6eNjNuJyTXGSGYc1jdWfdMDp```

```spl-token mint mntLu5qEnjVYVdbcV6Q6eNjNuJyTXGSGYc1jdWfdMDp 100```

https://explorer.solana.com/address/mntLu5qEnjVYVdbcV6Q6eNjNuJyTXGSGYc1jdWfdMDp?cluster=devnet

### Transfer tokens

```spl-token transfer mntTymSqMU4e1NEDdxJ9XoPN4MitCgQ7xxGW6AuRAWQ 10 (recipient wallet address) --fund-recipient```