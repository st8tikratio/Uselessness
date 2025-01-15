##### This is a personal file and does not reflect all meeting content

# Meeting Minutes

### 15 Jan 2025
- Collective Discord [server](https://discord.gg/sKdmXtsWYe)
#### Topics of interest:

#### NFT Related Metadata
- CIP-10 - Reserved Metadatum Values

These are the reserved `transaction_metadatum_label` values

`transaction_metadatum_label` | description
----------------------------  | -----------------------
0 - 15                        | reserved\*
65536 - 131071                | reserved - private use

- CIP-25 - [Media Token Metadata Standard `aka 721`]()
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
- CIP-60 - [Music Token Metadata](https://github.com/cardano-foundation/CIPs/tree/master/CIP-0060) - Extension Of CIP-25 & CIP-68 Metadata

