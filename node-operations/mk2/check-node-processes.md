# CHECK NODE PROCESSES

---

## MAINNET-MK2 - Commands & Sample Outputs

#### HAPROXY
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-mainnet-haproxy-1 | jq
```
Output
```
{
  "Status": "healthy",
  "FailingStreak": 0,
  "Log": [
    {
      "Start": "2025-10-28T07:22:08.050219794-04:00",
      "End": "2025-10-28T07:22:08.212255449-04:00",
      "ExitCode": 0,
      "Output": ""
    },
    {
      "Start": "2025-10-28T07:22:18.871575064-04:00",
      "End": "2025-10-28T07:22:19.005198903-04:00",
      "ExitCode": 0,
      "Output": ""
    },
    {
      "Start": "2025-10-28T07:22:29.878034165-04:00",
      "End": "2025-10-28T07:22:30.082106865-04:00",
      "ExitCode": 0,
      "Output": ""
    },
    {
      "Start": "2025-10-28T07:22:40.358357366-04:00",
      "End": "2025-10-28T07:22:40.465247131-04:00",
      "ExitCode": 0,
      "Output": ""
    },
    {
      "Start": "2025-10-28T07:22:50.906315781-04:00",
      "End": "2025-10-28T07:22:51.029024861-04:00",
      "ExitCode": 0,
      "Output": ""
    }
  ]
}
```
#### OGMIOS
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-mainnet-cardano-node-ogmios-1 | jq
```
Ouptut
```
"Status": "healthy",
  "FailingStreak": 0,
  "Log": [
    {
      "Start": "2025-10-28T07:21:38.869858926-04:00",
      "End": "2025-10-28T07:21:38.974760752-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=mainnet\nOK - Node sync progress: 84.01 %"
    },
    {
      "Start": "2025-10-28T07:22:09.950692777-04:00",
      "End": "2025-10-28T07:22:10.023012784-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=mainnet\nOK - Node sync progress: 84.02 %"
    },
    {
      "Start": "2025-10-28T07:22:40.086079251-04:00",
      "End": "2025-10-28T07:22:40.310169727-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=mainnet\nOK - Node sync progress: 84.04 %"
    },
    {
      "Start": "2025-10-28T07:23:10.888460513-04:00",
      "End": "2025-10-28T07:23:10.962183767-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=mainnet\nOK - Node sync progress: 84.05 %"
    },
    {
      "Start": "2025-10-28T07:23:41.951222855-04:00",
      "End": "2025-10-28T07:23:42.017885905-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=mainnet\nOK - Node sync progress: 84.06 %"
    }
  ]
}

```
#### NGINX
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-mainnet-nginx-1 | jq
```
Output
```
{
  "Status": "",
  "FailingStreak": 0,
  "Log": null
}
```
#### UNIMATRIX
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-mainnet-unimatrix-1 | jq
```
Output
```
{
  "Status": "",
  "FailingStreak": 0,
  "Log": null
}
```
#### POSTGRESS
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-mainnet-postgress-1 | jq
```
Output
```
{
  "Status": "healthy",
  "FailingStreak": 0,
  "Log": [
    {
      "Start": "2025-10-28T07:23:57.94699191-04:00",
      "End": "2025-10-28T07:23:58.049077922-04:00",
      "ExitCode": 0,
      "Output": "/var/run/postgresql:5432 - accepting connections"
    },
    {
      "Start": "2025-10-28T07:24:13.121261909-04:00",
      "End": "2025-10-28T07:24:13.185340071-04:00",
      "ExitCode": 0,
      "Output": "/var/run/postgresql:5432 - accepting connections"
    },
    {
      "Start": "2025-10-28T07:24:28.87254868-04:00",
      "End": "2025-10-28T07:24:28.922831462-04:00",
      "ExitCode": 0,
      "Output": "/var/run/postgresql:5432 - accepting connections"
    },
    {
      "Start": "2025-10-28T07:24:43.977890173-04:00",
      "End": "2025-10-28T07:24:44.042684512-04:00",
      "ExitCode": 0,
      "Output": "/var/run/postgresql:5432 - accepting connections"
    },
    {
      "Start": "2025-10-28T07:24:59.885557899-04:00",
      "End": "2025-10-28T07:24:59.960595748-04:00",
      "ExitCode": 0,
      "Output": "/var/run/postgresql:5432 - accepting connections"
    }
  ]
}
```
#### DBSYNC
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-mainnet-cardano-db-sync-1 | jq
```
Output
```
{
  "Status": "starting",
  "FailingStreak": 1434,
  "Log": [
    {
      "Start": "2025-10-28T07:21:13.870371996-04:00",
      "End": "2025-10-28T07:21:13.96411874-04:00",
      "ExitCode": 1,
      "Output": "Block table available\nSyncing 112328399 > 3600"
    },
    {
      "Start": "2025-10-28T07:22:14.876046167-04:00",
      "End": "2025-10-28T07:22:14.953285348-04:00",
      "ExitCode": 1,
      "Output": "Block table available\nSyncing 112326389 > 3600"
    },
    {
      "Start": "2025-10-28T07:23:15.872624141-04:00",
      "End": "2025-10-28T07:23:15.975710494-04:00",
      "ExitCode": 1,
      "Output": "Block table available\nSyncing 112324255 > 3600"
    },
    {
      "Start": "2025-10-28T07:24:16.874198883-04:00",
      "End": "2025-10-28T07:24:16.941957146-04:00",
      "ExitCode": 1,
      "Output": "Block table available\nSyncing 112321952 > 3600"
    },
    {
      "Start": "2025-10-28T07:25:17.869252288-04:00",
      "End": "2025-10-28T07:25:17.9431153-04:00",
      "ExitCode": 1,
      "Output": "Block table available\nSyncing 112319664 > 3600"
    }
  ]
}
```
#### CRON
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-mainnet-cron-1 | jq
```
Output
```
{
  "Status": "",
  "FailingStreak": 0,
  "Log": null
}
```
#### GRAPHQL
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-mainnet-cardano-graphql-1 | jq
```
Output
```
{
  "Status": "",
  "FailingStreak": 0,
  "Log": null
}
```
---

## PREPROD-MK2 - Commands & Sample Outputs
#### HAPROXY
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-preprod-haproxy-1 | jq
```
Output
```
{
  "Status": "healthy",
  "FailingStreak": 0,
  "Log": [
    {
      "Start": "2025-10-28T07:37:33.868060288-04:00",
      "End": "2025-10-28T07:37:33.930200458-04:00",
      "ExitCode": 0,
      "Output": ""
    },
    {
      "Start": "2025-10-28T07:37:44.012522864-04:00",
      "End": "2025-10-28T07:37:44.161465634-04:00",
      "ExitCode": 0,
      "Output": ""
    },
    {
      "Start": "2025-10-28T07:37:54.87084307-04:00",
      "End": "2025-10-28T07:37:55.02600098-04:00",
      "ExitCode": 0,
      "Output": ""
    },
    {
      "Start": "2025-10-28T07:38:05.872055475-04:00",
      "End": "2025-10-28T07:38:05.939118639-04:00",
      "ExitCode": 0,
      "Output": ""
    },
    {
      "Start": "2025-10-28T07:38:15.991068174-04:00",
      "End": "2025-10-28T07:38:16.120612634-04:00",
      "ExitCode": 0,
      "Output": ""
    }
  ]
}
```
#### OGMIOS
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-preprod-cardano-node-ogmios-1 | jq
```
Output
```
{
  "Status": "healthy",
  "FailingStreak": 0,
  "Log": [
    {
      "Start": "2025-10-28T07:36:01.875546093-04:00",
      "End": "2025-10-28T07:36:01.949869786-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=preprod\nOK - Node sync progress: 100.00 %"
    },
    {
      "Start": "2025-10-28T07:36:32.873616165-04:00",
      "End": "2025-10-28T07:36:32.966855093-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=preprod\nOK - Node sync progress: 100.00 %"
    },
    {
      "Start": "2025-10-28T07:37:03.873934687-04:00",
      "End": "2025-10-28T07:37:03.942703353-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=preprod\nOK - Node sync progress: 100.00 %"
    },
    {
      "Start": "2025-10-28T07:37:34.007168064-04:00",
      "End": "2025-10-28T07:37:34.069995309-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=preprod\nOK - Node sync progress: 100.00 %"
    },
    {
      "Start": "2025-10-28T07:38:04.863331032-04:00",
      "End": "2025-10-28T07:38:04.928095482-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=preprod\nOK - Node sync progress: 100.00 %"
    }
  ]
}
```
#### NGINX
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-preprod-nginx-1 | jq
```
Output
```
{
  "Status": "",
  "FailingStreak": 0,
  "Log": null
}
```
#### UNIMATRIX
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-preprod-unimatrix-1 | jq
```
Output
```
{
  "Status": "",
  "FailingStreak": 0,
  "Log": null
}
```
#### POSTGRESS
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-preprod-postgress-1 | jq
```
Output
```
{
  "Status": "healthy",
  "FailingStreak": 0,
  "Log": [
    {
      "Start": "2025-10-28T07:37:59.869158215-04:00",
      "End": "2025-10-28T07:37:59.981584307-04:00",
      "ExitCode": 0,
      "Output": "/var/run/postgresql:5432 - accepting connections"
    },
    {
      "Start": "2025-10-28T07:38:15.94796742-04:00",
      "End": "2025-10-28T07:38:16.046920381-04:00",
      "ExitCode": 0,
      "Output": "/var/run/postgresql:5432 - accepting connections"
    },
    {
      "Start": "2025-10-28T07:38:31.090119394-04:00",
      "End": "2025-10-28T07:38:31.16575382-04:00",
      "ExitCode": 0,
      "Output": "/var/run/postgresql:5432 - accepting connections"
    },
    {
      "Start": "2025-10-28T07:38:46.87337052-04:00",
      "End": "2025-10-28T07:38:46.986941957-04:00",
      "ExitCode": 0,
      "Output": "/var/run/postgresql:5432 - accepting connections"
    },
    {
      "Start": "2025-10-28T07:39:02.89388558-04:00",
      "End": "2025-10-28T07:39:02.992657825-04:00",
      "ExitCode": 0,
      "Output": "/var/run/postgresql:5432 - accepting connections"
    }
  ]
}
```
#### DBSYNC
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-preprod-cardano-db-sync-1 | jq
```
Output
```
{
  "Status": "healthy",
  "FailingStreak": 0,
  "Log": [
    {
      "Start": "2025-10-28T07:34:48.131827505-04:00",
      "End": "2025-10-28T07:34:48.221424915-04:00",
      "ExitCode": 0,
      "Output": "Block table available\nOK 20 < 3600"
    },
    {
      "Start": "2025-10-28T07:35:48.873153245-04:00",
      "End": "2025-10-28T07:35:48.963716774-04:00",
      "ExitCode": 0,
      "Output": "Block table available\nOK 19 < 3600"
    },
    {
      "Start": "2025-10-28T07:36:49.874488556-04:00",
      "End": "2025-10-28T07:36:49.94076393-04:00",
      "ExitCode": 0,
      "Output": "Block table available\nOK 32 < 3600"
    },
    {
      "Start": "2025-10-28T07:37:50.878935952-04:00",
      "End": "2025-10-28T07:37:50.937690519-04:00",
      "ExitCode": 0,
      "Output": "Block table available\nOK 59 < 3600"
    },
    {
      "Start": "2025-10-28T07:38:51.874507188-04:00",
      "End": "2025-10-28T07:38:51.954897172-04:00",
      "ExitCode": 0,
      "Output": "Block table available\nOK 22 < 3600"
    }
  ]
}
```
#### CRON
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-preprod-cron-1 | jq
```
Output
```
{
  "Status": "",
  "FailingStreak": 0,
  "Log": null
}
```
#### GRAPHQL
Command
```
docker inspect --format "{{json .State.Health }}" dandolite-mk2-preprod-cardano-graphql-1 | jq
```
Output
```
{
  "Status": "",
  "FailingStreak": 0,
  "Log": null
}
```
