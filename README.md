# Resiliency Patterns in Microservices

Suppose there is no proper resiliency pattern for interservice communciaton. In that case, it can cause a cascading failure in that the Order service also becomes unreachable, 
even though it should be able to handle other types of requests that do not depend on the Payment service.

* They should fail fast now and retry later
* Microservices has to be fault tolerant

## Timeouts

Timeout pattern is good but down side of it is it waits undefined time which maybe something not wanted if the service is already got back to up and running.

## Circuit Breaker Pattern

Fail fast in case of errors and enables you to perform the default or fallback operations

## Retry Pattern

There are temproary errors which heals itself in short amount of time

* Instant network failures
* Temproarily unavailable services
* Resource exhaustion of service due to load

The retry pattern enables us to retry a failed call automatically.

## Health Checks

Monitor the remote services and remove from the load balancer automatically or stop routing requests when it is 
unhealthy

## Fail-over and Redundancy

Redundancy and failover capabilities ensures that if one instance or component fails, another can take over.

## Fallback Mechanism

Fallback mechanisms provide an alternative response or behaviour when a remote operation is failing. 
