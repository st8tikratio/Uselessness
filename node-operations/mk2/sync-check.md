# TESTS FOR SYNC
```
1. These tests can be ran on any Dando nodes
2. You will need to know your node's IP address, or use localhost, for the following processes
```
## with BLOCKFROST
Command
```
<node url>/blockfrost/api/v0/blocks/latest
```
## with OGMIOS
Command
```
<url>/ogmios/health 
```
Sample Output
```
startTime	"2025-10-28T13:11:51.594872822Z"
lastKnownTip	
slot	140298863
id	"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
height	11106320
lastTipUpdate	"2025-10-28T14:09:12.464038986Z"
networkSynchronization	0.88336
currentEra	"conway"
metrics	
activeConnections	1
runtimeStats	
cpuTime	129734617487
currentHeapSize	25913
gcCpuTime	3372930422
maxHeapSize	24282
sessionDurations	
max	0
mean	0
min	0
totalConnections	1
totalMessages	24
totalUnrouted	0
connectionStatus	"connected"
currentEpoch	522
slotInEpoch	158063
version	"v6.11.2 (58c28c14)"
network	"mainnet"
```
## with GRAPHQL
> this is on your node's main page
Query
```
query {
  cardanoDbMeta {
    syncPercentage
    initialized
  }
}
```
Sample Output
```
{
  "data": {
    "cardanoDbMeta": {
      "syncPercentage": 35.046416274509625,
      "initialized": false
    }
  }
}
```
## with TERMINAL/CONSOLE
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-mainnet-cardano-node-ogmios-1 | jq
```
Sample Output
```
{
  "Status": "healthy",
  "FailingStreak": 0,
  "Log": [
    {
      "Start": "2025-10-28T11:04:56.877907116-04:00",
      "End": "2025-10-28T11:04:57.101347254-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=mainnet\nOK - Node sync progress: 88.99 %"
    },
    {
      "Start": "2025-10-28T11:05:27.868486023-04:00",
      "End": "2025-10-28T11:05:28.177965408-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=mainnet\nOK - Node sync progress: 89.00 %"
    },
    {
      "Start": "2025-10-28T11:05:58.87212335-04:00",
      "End": "2025-10-28T11:05:59.056193591-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=mainnet\nOK - Node sync progress: 89.00 %"
    },
    {
      "Start": "2025-10-28T11:06:29.875364115-04:00",
      "End": "2025-10-28T11:06:30.345131439-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=mainnet\nOK - Node sync progress: 89.01 %"
    },
    {
      "Start": "2025-10-28T11:07:00.891750808-04:00",
      "End": "2025-10-28T11:07:01.014232924-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=mainnet\nOK - Node sync progress: 89.02 %"
    }
  ]
}
```
