# New vs Old Architecture

## Old architecture overview

### The Bridge

The bridge in the old architecture works by serializing all data that must be passed from JavaScript to native.

The Bridge have some limitations:

- It is asynchronous: one layer submits data to a bridge and waits for the data to be processed by the other layer, even when it’s unnecessary.

- It is single threaded: JavaScript used to be single-threaded, so computation that takes place has to be performed on that single thread.

- Overhead costs: each time one layer communicates with another, it must serialize the data. The other layer must deserialize it. JSON was chosen for its simplicity and human readability, despite being a lightweight format it has a cost associated with it.

## New architecture overview