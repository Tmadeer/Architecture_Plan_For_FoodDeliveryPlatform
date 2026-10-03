# Food Ordering System

## Authors
* Sara Alshahrani
* Tumadhir Al-Fattah
* Shada Haddad

---

## Project Overview
The **Food Ordering System** is a backend-driven software architecture designed to streamline the interaction between users, restaurants, menus, and orders. It models the complete lifecycle of a food delivery process, from item selection and order placement to automated state transitions and real-time user notifications.

---

## System Requirements & Specifications

### Core Entities & Relationships
1. **User**: Registers, logs in, browses restaurant menus, groups items, and places orders.
2. **Restaurant**: Manages menus, receives incoming orders, confirms or rejects them, and updates order progression states.
3. **Menu**: Contains a categorized list of items with quantities and prices.
4. **Order**: Tracks unique tracking numbers, dynamic states, and associations with both users and restaurants.

### Order Lifecycle States
Orders progress through a strictly defined state machine:
* `created`: Order is initialized and placed by the user.
* `confirmed`: The restaurant accepts the order.
* `prepared`: The kitchen finishes preparing the food.
* `delivered`: The order reaches the user.
* `rejected`: Alternative fallback state if the restaurant declines the order.

---

## Use Cases

### Mandatory Use Cases
* **Place an Order**: 
  * *Actor*: User
  * *Description*: The user finalizes their selection, and the system creates and processes the order.

### Additional Use Cases
* **Add an Item to an Order**:
  * *Actor*: User
  * *Description*: The user selects a menu item and adds it dynamically to their active cart/order.
* **Update Order Status**:
  * *Actor*: Restaurant / System
  * *Description*: The system/restaurant transitions the order status through its lifecycle (`created` $\rightarrow$ `confirmed` $\rightarrow$ `prepared` $\rightarrow$ `delivered`), automatically triggering notifications to keep the user informed.
