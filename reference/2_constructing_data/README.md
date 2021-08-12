# Constructing data

In this section, we will demonstrate methods of constructing & initializing simple data structures in Cranq.

By default, Cranq provides utility nodes for working with arrays & key-value pairs. As a result, enumerable structures are represented as variable-length arrays, while records (eg. a typical OO entity or DTO) are dictionaries under the hood.

Generally, these structures can be constructed by using: 
- their dedicated builder node types
- or assembled from their building blocks with the flow/Syncer node.