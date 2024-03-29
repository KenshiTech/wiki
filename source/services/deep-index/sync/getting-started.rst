Getting Started
===============

To get started with the Kenshi Deep Indexing Sync tasks, go to the Kenshi dashboard_ and
connect your wallet. Then click on the "New Sync Task" button and fill in the "New Deep Indexing Task"
form.

.. figure:: ../../../_static/images/dashboard/sync.png
  
  New Deep Indexing Task form

How to fill the form?
---------------------

The Sync task form lets you choose what blockchain data is relevant to you. How you fill the form
depends on your use case, but we can give you some tips and info about each one of the fields in
this form.

1. **Chain**: Here you need to choose the chain where your data is. For example, if you deployed your
   smart contract to the Fantom chain and you want to sync the events from this smart contract to the
   Kenshi blockchain data clusters, then you'll need to choose the Fantom chain here. This value cannot
   be changed after the task is created.

2. **Starting block**: This field specifies from which block the sync task should look for the events
   you want to sync. Following the example of the **Chain** field, if your smart contract is deployed
   at block XYZ (eg. block 39176717) you'd want to put that number in this field. This value cannot be
   changed after the task is created.

3. **Interval**: The sync task runs at specific periods to look for new events, for example it can run
   every 5 seconds, or every 5 minutes. The lower the interval is the lower the data sync latency will
   be. If you're creating the task for archiving purposes, it won't matter if the interval is too high,
   but if you're making a dApp then you don't want to keep your users waiting. This value cannot be
   changed after the task is created.

4. **Step**: How many blocks at a time should this task process at each run? This needs to be adjusted
   depending on the **Interval**, for example the block time on the Fantom chain is about 1 second, so
   in 10 seconds there will be 10 new blocks. That means if your task is running every 10 seconds and
   processing 6 blocks at a time it won't be able to catch up to the new data fast enough. This value
   cannot be changed after the task is created.

5. **Timeout**: How many seconds should the task run before it gives up? This value should be adjusted
   depending on the **Step** field, the more blocks you're processing at a time the more time you need
   for the timeout. This value cannot be changed after the task is created.

6. **Duration**: This field defines how many month should the service run. You can extend the Sync duration,
   but you cannot cancel or end the task.

7. **Contract address**: The source of the events you want to sync to the Kenshi blockchain data clusters.
   This is usually the address of your smart contract, or the smart contract that emits the events you are
   looking for.

8. **Contract ABI**: Put ABI of the smart contract (from the **Contract address**) field here. You can
   either put the entire ABI, or just inlcude the ABI of the event you are interested in. The ABI can be
   Human-Readable ABI or the ABI emitted by the Solidity compiler, in JSON format.

9. **Event signature**: After filling the **Contract ABI** field, the ABI is parsed and the ABI event
   signatures will be available in this field to choose from. Here you need to choose the event you
   are interested in.

10. **Arguments**: Once you provide the ABI and choose the event signature, a list of arguments available
    for the chosen event will appear here. If you are looking for events that have a specific value for
    one of the arguments, you can put that value in front of the argument name. If you want to sync all
    events of this kind regardless of the value of the arguments, just leave the argument values empty.

.. _dashboard: https://kenshi.io/dashboard
