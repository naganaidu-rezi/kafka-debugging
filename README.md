# kafka-debugging

Not able to start kafka-broker with following error's
```
ERROR Shutdown broker because all log dirs in path(in /etc/kafka/server.properties) have failed (kafka.log.LogManager)

Steps to resolve :

1. Stop the Kafka
    ```
    systemctl stop confluent-kafka
    ```
2.  Delete the content in the log directory
    ```
    cd logdir
    rm -rf *
    ```
3. Start the kafka 
   ```
   systemctl start confluent-kafka
   ```
```





After enabling JMX metrics and not able to see those metrics may be it is blocked by local iptables

JMX enable locations:

vi /etc/systemd/system/confluent-kafka.service.d/override.conf

use the following command

```
iptables -F
```


