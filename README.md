# Client-Server-Trading-System

## Overview
This project is an implementation of a Client-Server based Trading System using socket programming. Traders can log in to the system, view available items, send buy and sell requests, and check the status of their orders. The server manages order processing, trade matching, and client logins.

## Functionalty
The trading system provides the following functionalities:

* **Login to the System**: Traders can log in by providing their Trader ID and password stored in a file.

* **Send Buy Reques**t: Traders can send buy requests, specifying the item code, quantity, and unit price.

* **Send Sell Request**: Traders can send sell requests, specifying the item code, quantity, and unit price.

* **View Order Status**: Traders can view the current status of buy and sell orders, including the best sell and buy prices for each item.

* **View Trade Status**: Traders can view details of their matched trades, including order details, quantities, prices, and counterparty information.

## System Details
* Traders: A maximum of 5 traders can log in simultaneously, each with a unique code from 1 to 5.

* Items: There are ten known items with codes from 1 to 10 that traders can trade.

* Server: The server handles order processing, trade matching, logins, and client requests. It ensures that only one trader can work from one client at a time.

## Matching Rule

* When a buy request is received for an item I at price P and quantity Q, the server checks for pending sell orders for the same item with prices P' ≤ P.

* The match is made with the sell order having the least selling price among all pending sell orders.

* If both orders have the same quantity (Q' = Q), they are removed from their queues, and the trade details are stored.

* If Q' > Q, the buy request is fully traded, and the remaining part of the sell order remains in the queue.

* If Q' < Q, the sell order is fully traded, and the remaining buy order is tested for more matches.

* If the buy order cannot be matched, it remains in the buy queue.






