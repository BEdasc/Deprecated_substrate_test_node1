# Logion NFT

This pallet implements the management of Logion NFTs.

## Requirements

- A Substrate 3.x node (below usage works with [Substrate Node Template v3.0](https://github.com/substrate-developer-hub/substrate-node-template/releases/tag/v3.0.0))

## Usage

### In your node runtime Cargo.toml

Add the following to `dependencies` section:

    pallet-logion-nft = { git = 'ssh://git@github.com/logion-network/pallet-logion-nft.git', default-features = false }

Also, in the `features` section, add the following string to the `std` feature: `'pallet-logion-nft/std'`

### In your node runtime lib.rs

Add this snippet before building your runtime:

```
use pallet_logion_nft;

impl pallet_logion_nft::Config for Runtime {
	type Event = Event;
}
```

Finally, add this variant to your Runtime enum:

	LogionNft: pallet_logion_nft::{Module, Call, Storage, Event<T>},
