---
layout: default
description: ArangoDB v3.10 Release Notes New Features
---
Features and Improvements in ArangoDB 3.10
==========================================

The following list shows in detail which features have been added or improved in
ArangoDB 3.10. ArangoDB 3.10 also contains several bug fixes that are not listed
here.

ArangoSearch
------------



UI
--

### Rebalance shards

The rebalance shards section displays a button for rebalancing shards. A new DB-Server will not have any shards. With the rebalance functionality, 
the cluster will start to rebalance shards including empty DB-Servers. You can specify the maximum number of shards that can be 
moved in each operation by using the `--cluster.max-number-of-move-shards` flag in arangod (the default value is 10).
When the button is clicked, the number of scheduled move shards operations is shown, or it is displayed that 
no move operations have been scheduled if they are not necessary.


AQL
---



Server options
--------------

### Rebalance shards

The `--cluster.max-number-of-move-shards` flag limits the maximum number of move shards operations which can be made when the **Rebalance Shards** button is clicked in the web UI. For backwards compatibility purposes, the default value is 10. If the value is 0, the tab containing this button will be inactive and the button cannot be clicked.


Miscellaneous changes
---------------------



Client tools
------------


### arangobench

Histograms are now switched off by default (the `--histogram.generate` flag set to `false`). To display them, set the flag to `true`.
If this option is disabled, but other histogram flags are used to invoke arangobench (e.g. `--histogram.interval-size 500`), everything will still run normally, but a warning message will be displayed, stating that histograms are switched off by default and using other histogram options has no effect.


Internal changes
----------------

### C++20 

ArangoDB is now compiled using the `-std=c++20` compile option on Linux and MacOS.
A compiler with c++-20 support is thus needed to compile ArangoDB from source.

### Upgraded bundled library versions

The bundled version of the RocksDB library has been upgraded from 6.8.0 to 6.27.0.

The bundled version of the Boost library has been upgraded from 1.71.0 to 1.77.0.

The bundled version of the immer library has been upgraded from 0.6.2 to 0.7.0.