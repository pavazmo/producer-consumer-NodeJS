# producer-consumer-test

This is a code repository for a producer-consumer-test in NodeJS.


## Instructions

LIMITED CONCURRENCY PRODUCER/CONSUMER CHALLENGE:

The challenge is to build an application using a
producer/consumer application that allows for a
configurable number of consumers processing
a queue that is being populated by a single producer.

Tasks:
1. Write a producer that will add items to a queue.
2. Write a consumer that will start up to a configurable
maximum number of consumers to process the queue concurrent.

The real challenge is the queue and the consumer.  The producer
should just call a method to add items to the queue.  Though there
is some challenge around how quickly the items are added, and
adding them in a way that it not blocking.

Requirements
1. The queue should be a simple array.  Items are added to the end of the array
   consumed from the start of the array (FIFO).  As items are consumed they
   should be removed from the array.

2. The application should define the maximum number of concurrent consumers when it
   starts.

3. When there are no items in the array, no consumers should be running.

4. When an item is added to the array it should start a consumer if necessary
  and the maximum number of consumers are not already running.

5. When a consumer finishes, it should consume the next item.  If there is
   not another item to consume, the consumer should exit.

6. Consumers should use a setTimeout() of a random amount of time less than 1
   second to simulate an asyncronous operation (otherwise the consumers will
   run syncronously).  The setTimeout() should occur before the output is written
   by the consumer indicating the item that was consumed.

7. The producer should use a counter to add values starting at 1 and ending
   at a value passed into the start function so that no two values are the same.

8. The producer should be asynchronous, adding each item with a pause of a random
   amount of time < 500ms to allow the consumers to consume while the producers
   produce.
   
9. If the producer is finished producing, and queue depth reaches zero,
   the process should exit.  Note that it should exit gracefully, not through
   the use of exit().

10. Create some ways to demonstrate that it is working, for example, a
    single consumer processes the queue serially.  Pausing the producer
    allows the queue to drain, and starting it fills the queue.  What scnarios
    would show that it is aryncronously processing the queue as intended
    whle limiting concurrency?

## Setup

* Just run
<code>node app</code>
