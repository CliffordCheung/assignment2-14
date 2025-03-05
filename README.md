# assignment2-14

Q1. Does SNS guarantee exactly once delivery to subscribers?

A: No, Amazon SNS does not guarntee exactly once delivery to subscribers. SNS quarantees at least once delivery to its subscribers, meaning that each message will be delivered to the subscribes at least one time, but it may be delivered more than once in certain acses, such as network issues or retries during failures. This is often referre to as "at least once" delivery.

Q2. What is the purpose of the Dead-letter Queue (DLQ)? This is a feature available to SQS/SNS/EventBridge.

A: The Dead-letter Queue is used in the messaging systems to handle messages that cannot be successfully processed after multiple attempts. The main purpose of a DLQ is to store failed messages so that they can be analyzed, debugged and managed without impacting the main processing flow.

Q3. How would you enable a notification to your email when messages are added to the DLQ?

A: To enable email notifications when messages are added to a Dead-letter Queue (DLQ), you can use Amazon SNS (Simple Notification Service) in combination with Amazon SQS (Simple Queue Service).
  1. Create an SNS Topic for Notifications (e.g. DLQ-Notification-Topic)
  2. Subscripe email to the SNS topic
  3. Setup the DLQ in Amazon SQS
  4. Create the main queue in SQS with DLQ configuration
