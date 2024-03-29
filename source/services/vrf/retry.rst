Retry Policy
------------

Kenshi has a generous approach for delivering randomness to your smart contracts.
In case of failure we retry twice within 2 minutes of the first try, if all fails we
log an entry for it in our db and queue it for a retry in 15 minutes, if that also
fails we reschedule again for a retry in 1 hour, then 2 hours, 4 hours, 8 hours,
24 hours and finally 48 hours until we give up.

That's a total of 10 retries. Failure can happen for variety of reasons, for example
if you don't have enough Kenshi tokens stored in your smart contract for paying the
delivery fees or when the network is down. If the failure is from our side, we will
resolve the issues as soon as possible and deliver the results out of schedule.

.. note::
  A feature to notify contract owners of such failures is planned for the future.

We use multiple RPC endpoints for delivering your results. These endpoints are chosen
based on their uptime and latency. To check the status of the RPC endpoints or average
VRF delivery times you can check our status_ page.

.. _status: https://kenshi.io/status
