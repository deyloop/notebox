# Incremental Integer node ids for KEG nodes

***Advantages***

Can be created and assigned in batch very easily.

Links to new nodes can be pre-created since their ids can be generated prior to the node's creation and assigned. This is helpful when creating lists of links to "sub-sections", as one does.

Smaller numbers, easier to remember ids if needed.

***Disadvantages***

If a user has multiple `keg`s and wants to move one node between kegs, a new id for the node will have to be generated. This would change at any links the node had (assuming the linked nodes are also moved, as a whole sub-graph)


Related:

* [20221202135423](../20221202135423/README.md) isosec as KEG node identifier
