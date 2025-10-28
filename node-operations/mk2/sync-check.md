# TESTS FOR SYNC
> you will need to know your node's IP address for the following processes
## with Blockfrost
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

```
Output
