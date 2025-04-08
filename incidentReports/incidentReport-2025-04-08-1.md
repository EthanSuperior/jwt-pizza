# Incident: 2025-04-08 18-54-49 UTC

## Summary

Between the hour of 18:54:49 to 20:02:38 UTC on 2025-04-08, 92 users encountered failed pizza orders. The event was triggered by a schedueled attack at 12:54. The attack contained a command that caused all pizza orders to fail.

A this code caused 92 customers to have failed orders and 386 pizzas. The event was detected by Grafana. The team started working on the event by looking through the relavent logs. This critical incident affected 100% of users.

## Detection

The team discovered the incident when there previous class ended at 19:51 UTC. It was obvious from the sharp change in the pizza failure rate. By having another user on call we could have another user on call during the duration of the teams classes, furthermore properly configured alerts could have been looking for responses that returned an unexpected status code, one that did not match the expected errors.

## Impact

For 1 hr 8 minutes between 18:54:49 UTC and 20:02:38 UTC on 04/08/25, all customers pizza orders failed.

This incident affected 92 customers (100% of JWT Pizza users), who experienced failed pizza orders.

0 issues were reported by customers.

## Timeline

All times are UTC.

- 18:51 - On call dev-ops left for a dance class
- 18:54 - Attack begins
- 18:59 - Alerts fail to notify dev team as alerts were observing the auth requests not the outgoing to pizza requests.
- 19:50 - Dance class finishes
- 19:51 - On call developer observes unusual graphs on Grafana dashboard.
- 19:52 - Developer recognizes it as an error and begins observing logs.
- 20:01 - Developer reads though 'Line' sent by server to logs and finds 'reportPizzaCreationErrorToPizzaFactoryUrl'.
- 20:02 - Developer sends report to JWT Pizza Factory, who resolve the error.

## Response

After noticing the error within the Grafana dashboard at 19:52. EthanSuperior, the on call developer started to observe the problematic time period.

This engineer did not understand what caused the issue at first so additional tiem was spent to analyze the issue.

## Root cause

A bug in jwt-pizza-factory led to failure responses being sent to users of jwt-pizza. Poor alert configurations led to nonimmediate notifications.

## Resolution

The Line label of the log was inspect until a reporting URL was found by the developer. This was then sent to repor the issue to the factory.

## Prevention

The given chaos endpoint also causes similar fail points, however the JWT Pizza Team chose to obser the auth paths rather than the pizza creation status codes.

## Action items

1. Configure additonal alerts for all remaining graphs.
2. Further test the provided chaos endpoint
