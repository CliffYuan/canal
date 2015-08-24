
1. 消费记录

/otter/canal/destinations/example/1001/cursor

input:
    get /otter/canal/destinations/example/1001/cursor
output:
    {
        "@type": "com.alibaba.otter.canal.protocol.position.LogPosition",
        "identity": {
            "slaveId": -1,
            "sourceAddress": {
                "address": "172.16.82.174",
                "port": 3306
            }
        },
        "postion": {
            "included": false,
            "journalName": "mysql-bin.000004",
            "position": 46836,
            "timestamp": 1440403423000
        }
    }
