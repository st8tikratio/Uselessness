##### This is a personal file and does not reflect all meeting content

# Meeting Minutes

## 15 Jan 2025
- Collective Discord [server](https://discord.gg/sKdmXtsWYe)

---

## Metadata Standards

### [CIP-10](https://github.com/cardano-foundation/CIPs/edit/master/CIP-0010/README.md) - Reserved Metadatum Values

These are the reserved `transaction_metadatum_label` values

`transaction_metadatum_label` | description
----------------------------  | -----------------------
0 - 15                        | reserved\*
65536 - 131071                | reserved - private use

### [CIP-25](https://github.com/cardano-foundation/CIPs/tree/master/CIP-0025) - Media Token Metadata Standard `label 721`
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

### [CIP-68](https://github.com/cardano-foundation/CIPs/tree/master/CIP-0068) - Datum Metadata Standard
#### This CIP needs summarization
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
