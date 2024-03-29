Introduction
============

Instead of querying the blockchain or the Kenshi GraphQL endpoint, you can get the
events delivered to your application instead. This allows creating a completely serverless
flow of receiving and processing the blockchain data.

The Kenshi Reverse-API service allows you to define a query, a starting block and an API
endpoint (your HTTP[S] endpoint, AWS Lambda function...), then every time your query matches
a record the Reverse-API service sends it to your endpoint.

To use this service head to the Kenshi dashboard_, connect your wallet and register an endpoint using
the new Reverse-API form. Continue reading on to get help with the dashboard or see examples of
the Reverse-API service.

.. _dashboard: https://kenshi.io/dashboard
