# Spring kafka example
A spring kafka consumer. The example uses `EmbeddedKafka` to demonstrate one option to test kafka services.
The service consumes `TransferEvent` from `basic.topic.1` and produces a new event to `test-topic`.
To try it:
Make sure docker kafka container is stopped `docker stop <CONTAINER ID>`
Run `TransferEventListenerTest` from the ide to start the test. Or you can run it using: `./gradlew :test --tests "com.transferwise.springkafkaclient.consumer.TransferEventListenerTest.shouldHandleTransferEvent"`.

`TransferEventListenerTest` contains a custom producer that produces test TransferEvents and validates the service results 
by checking the events from `test-topic`