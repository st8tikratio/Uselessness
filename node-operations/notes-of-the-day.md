## RUNNING NOTES OF THE DAY

## 25 APRIL 2025
### MAARTEN; Discord; 0746 UTC
I have deployed an experimental background service where I have removed the metadata asset worker. I have synced proprod with it and am now syncing mainnet. It is using a modified graphql branch you can find here.
  - https://github.com/M2tec/cardano-graphql/tree/feat/no-offchain-metadata

You can try it yourself by dropping your postgres volume and changing  the following line in your .env

CARDANO_GRAPHQL_BACKGROUND_IMAGE=m2tec/cardano-graphql-background:${CARDANO_GRAPHQL_VERSION:-8.0.3}-${NETWORK} 
