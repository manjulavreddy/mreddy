Steps to add to the Eclipse [Eclipse IDE for Java Developers Version: 2020-03 (4.15.0)] workspace and execute the program:

1. Import as a Maven project
2. JMS API and JMS provider(activeMQ) are used to send and receive messages. The dependencies related to activeMQ are in pom.xml.
3. MessageGeneratorQueue - Run this generator client which creates random numbers 0...N, based on the ramdom generator and sends the messages to the destination queue.
4. MessageReceiverQueue - Run this receiver client after the generator client is run which recieve one message at a time from the destination queue asynchronously.
5. MessageListenerFromQueue - This is a helper class that implements MessageListener that retrieves messages and creates a valid batch based on the batch size(i.e 5) and submits to the processor.
6. BatchProcessor - This is a place holder class that displays the batch details. This can be defined as an interface that can be used to implement other implementations like streaming or writing to a DB.

Sample Execution 
Input: For 0...519
Output :
Total batches processed: 0
Batch content: 
0
1
2
3
4
Total batches processed: 1
Batch content: 
5
6
7
8
9
.
.
.
.
.

Final batch processed: END
Total batches processed: 103
Batch content: 
515
516
517
518
