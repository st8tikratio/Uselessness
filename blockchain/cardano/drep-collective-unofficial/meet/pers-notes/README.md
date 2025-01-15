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
#### Brief  
```
Each asset name must be prefixed by a label. The intent of this label is to identify the purpose of the token. For
example, a reference NFT is identified by the label 100 and so every token considered a reference NFT should start its
asset name with the hex `000643b0`. This is
following [CIP-0067](https://github.com/cardano-foundation/CIPs/tree/master/CIP-0067), which specifies how the label
prefix should be formatted.

Examples of asset names:

| asset_name_label | asset_name_content | resulting_label_hex | resulting_content_hex | resulting_asset_name_hex     |
|------------------|--------------------|---------------------|-----------------------|------------------------------|
| 100              | GenToken           | 000643b0            | 47656e546f6b656e      | 000643b047656e546f6b656e     |
| 100              | NeverGonna         | 000643b0            | 4e65766572476f6e6e61  | 000643b04e65766572476f6e6e61 |
| 222              | GiveYouUp          | 000de140            | 47697665596f755570    | 000de14047697665596f755570   |
```
#### 333 FT Standard
`**Note** Since `version >= 1``

The second introduced standard is the `333` FT standard with the registered `asset_name_label` prefix value

| asset_name_label | class | description                                                                                      |
|------------------|-------|--------------------------------------------------------------------------------------------------|
| 333              | FT    | FT hold by the user's wallet making use of Cardano foundation off-chain registry inner structure |

**Class**

The `user token` is an FT (fungible token).

**Pattern**

The `user token` and `reference NFT` MUST have an identical name, preceded by the `asset_name_label` prefix.

Example:\
`user token`: `(333)Test123`\
`reference NFT`: `(100)Test123`
```


### [CIP-60](https://github.com/cardano-foundation/CIPs/tree/master/CIP-0060) - Music Token Metadata
- Extension of CIP-25 & CIP-68
