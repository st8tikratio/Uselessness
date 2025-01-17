##### This is a personal file and does not reflect all meeting content
##### NOTE: Any CIP data listed below is NOT COMPELTE. Please see CIP itself, link provided

# Meeting Minutes
- 15 Jan 2025
- Links Provided
    - Collective [Discord server](https://discord.gg/sKdmXtsWYe)
    - DRep distribution by [Tempo.Vote](https://tempo.vote/dreps) 
    - DRep mapping & metadata discussion on [Cardano Forum](https://forum.cardano.org/t/human-interoperability-metadata-standards-and-ecosystem-maps-do-we-need-a-set-of-metadata-standards-and-definitions-for-defining-ecosystem-roles-relationships-and-sectors/135155) 
    - Boyds Real OODA Loop (It's Not What It Seems) - [PDF](https://github.com/st8tikratio/Uselessness/blob/main/blockchain/cardano/drep-collective-unofficial/docs/boyds-real-ooda-loop.pdf) 
    - Example of website template style - [I Side With](https://www.isidewith.com)

---
# Other Topics

## Wallet Architecture
- Open Wallet/credo-ts - [Architecture Update](https://github.com/openwallet-foundation/credo-ts/discussions/722)

## Cardano Metadata Standards (needs updating)

### [All CIPs](https://github.com/cardano-foundation/CIPs/tree/master)

### [CIP-10](https://github.com/cardano-foundation/CIPs/edit/master/CIP-0010/README.md) - Reserved Metadatum Values

#### Terminology
`Transaction metadata refers to an optional CBOR object in every transaction since the start of the Shelley era. It is defined as the follow CDDL data structure`

```
transaction_metadatum =
    { * transaction_metadatum => transaction_metadatum }
  / [ * transaction_metadatum ]
  / int
  / bytes .size (0..64)
  / text .size (0..64)

transaction_metadatum_label = uint

transaction_metadata =
  { * transaction_metadatum_label => transaction_metadatum }
```

#### Reserved `transaction_metadatum_label` values

`transaction_metadatum_label` | description
----------------------------  | -----------------------
0 - 15                        | reserved\*
65536 - 131071                | reserved - private use



### [CIP-25](https://github.com/cardano-foundation/CIPs/tree/master/CIP-0025) - Media Token Metadata Standard - `CBOR tag 721`
```
      {
      "721": {
        "<policy_id>": {
          "<asset_name>": {
            "name": <string>,
    
            "image": <uri | array>,
            "mediaType": image/<mime_sub_type>,
    
            "description": <string | array>,
    
            "files": [{
              "name": <string>,
              "mediaType": <mime_type>,
              "src": <uri | array>,
              <other_properties>
            }],
    
            <other properties>
          }
        },
        "version": <version_id>
      }
    }
```

### [CIP-27](https://github.com/cardano-foundation/CIPs/tree/72d499ffa0d6116c41b46276946bb5dc03f53165/CIP-0027) - Community Royalties

### [CIP-68](https://github.com/cardano-foundation/CIPs/tree/master/CIP-0068) - Datum Metadata Standard - ***Allow [* bounded_bytes] for images***

#### Considerations
```
The basic idea is to have two assets issued, where one references the other. We call these two a `reference NFT` and
an `user token`, where the `user token` can be an NFT, FT or any other asset class that is transferable and represents
any value. So, the `user token` is the actual asset that lives in a user's wallet.

To find the metadata for the `user token` you need to look for the output, where the `reference NFT` is locked in. How
this is done concretely will become clear below. Moreover, this output contains a datum, which holds the metadata. The
advantage of this approach is that the issuer of the assets can decide how the transaction output with
the `reference NFT` is locked and further handled. If the issuer wants complete immutable metadata, the `reference NFT`
can be locked at the address of an unspendable script. Similarly, if the issuer wants the NFTs/FTs to evolve or wants a
mechanism to update the metadata, the `reference NFT` can be locked at the address of a script with arbitrary logic that
the issuer decides.

Lastly and most importantly, with this construction, the metadata can be used by a Plutus V2 script with the use of
reference inputs [CIP-0031](https://github.com/cardano-foundation/CIPs/tree/master/CIP-0031). This will drive further
innovation in the token space.
```
#### 4 new label types
| asset_name_label | class | description                                                                                                                                     |
|------------------|-------|-------------------------------------------------------                                                                                          |
| 100              | NFT   | Reference NFT locked at a script containing the datum                                                                                           |
| 222              | NFT   | NFT held by the user's wallet making use of CIP-0025 inner structure                                                                            |
| 333              | FT    | FT hold by the user's wallet making use of Cardano foundation off-chain registry inner structure                                                |
| 444              | RFT   | RFT hold by the user's wallet making use of the union of CIP-0025 inner structure AND the Cardano foundation off-chain registry inner structure |


### [CIP-60](https://github.com/cardano-foundation/CIPs/tree/master/CIP-0060) - Music Token Metadata
- Extension of CIP-25 & CIP-68
