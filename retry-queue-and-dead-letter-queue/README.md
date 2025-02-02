To gracefully handle failures, we utilize the retry queue and dead letter queue as shown in Figure.

![IMG_4923](https://github.com/user-attachments/assets/1975a2bd-5703-4a61-8e2c-ed3ae0e8185f)

* Retry queue: retryable errors such as transient errors are routed to a retry queue.

## Transient Errors: These are temporary failures that might succeed if retried. Examples:

* Network timeouts
* Database connection failures
* API rate limits
* Temporary service unavailability

* Dead letter queue: If a message fails repatedly, it eventually lands in the dead letter queue. A dead letter queue is useful for debuggin and isolating problematic messages for inspection to determine why they were not processed successfully.
