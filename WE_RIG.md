
# We_Rig Project

We_Rig is a class that allows the creation/modification of a rigged chain,
hierarchical or not, with or without additional features.

The rig is always active; any attribute modification will update the result.

The minimal rig is a single control (with or without an origin).
There's no limit in terms of the number of controls or layers.

## Usage

If We_Rig is called on an existing rig, it will automatically find its current
properties, fill all the class variables, and rebuild the result.

If some arguments are given directly during class creation, the rig will be
rebuilt to accommodate the changes. Any class attribute can then be set, either
globally or by individual control indices.

Calling build() after defining some attributes will only rebuild the necessary
parts to accommodate the changes.

A We_Rig consists of one or more modules.
A module consists of one or more layers.
A layer has a length N, an associated surface, and an associated joint chain.

A Tree consists of one or more branches.
A branch consists of one or more nodes.

## Composition

- **main_grp**: main group of the rig.

- **geo_grp**: group containing the geometry deformed by the rig.

- **root_grp**: group containing the rig's root.

- **module_grp**: group containing the main modules that make up the rig.

- **extra_grp**: group containing the rig's extra components.

- **connections_grp**: group containing the rig's inter-modular connections.

- **skeleton_grp**: group containing the rig's joint tree.

- **ctl_set**: set containing the rig's controllers.

- **geo_set**: set containing the geometry deformed by the ri

## Options

Attributes that can be specified by the chain element's index
(dictionaries in the {index:value} format)

If a single value is given, the class will assume that all elements should have
the same state.

If a dictionary with only partial index: value pairs is given, only these
elements will be rebuilt.

### Various ways to name/rename a node (Node)

- **convention**: order in which tokens are placed to generate the node's name.

- **side_options**: list of sides, index 0=left, 1=middle, 2=right.

- **name_token**: main name token of the node.

- **subname_token**: sub-name or index token of the node.

- **side_token**: side token of the node.

- **type_token**: type token of the node.

- **namespace**: namespace of the node (optional).

- **name**: name of the node without the namespace.

- **full_name**: complete name of the node, with the namespace if it exists.

### Attributes common to all nodes (Node)

- **parent**: hierarchical parent of the node.

- **is_hierarchical**: whether the node is hierarchical or not.

- **children**: hierarchical children of the node.

- **shapes**: hierarchical children of the node (related shape).

- **branch_index**: index of the node in the branch.

- **outliner_level**: index of the node in the entire outliner.

- **world_matrix**: world matrix of the node.

- **matrix**: local matrix of the node.

- **lr_position**: position of the nodes (left/middle/right).

- **node_type**: type of node.

- **exists**: if the node exists.

- **has_transform**: if the node has transforms.

- **visible**: if the node is visible.

- **locked**: if lockNode().

- **attribute_names**: list of the names of each attribute of the node.

- **attribute_count**: number of attributes on the node.

- **attribute_values**: value of each attribute of the node.

- **attributes_without_value**: attributes whose value can't be retrieved.

- **rotate_order**: rotate order of the node.

### Various ways to name/rename a branch (Branch)

- **names**: list containing each name_token of each node in the branch.

- **subnames**: list containing each subname_token of each node in the branch.

### Attributes common to all branches (Branch)

- **length**: number of elements.

- **are_hierarchical**: whether to create a hierarchy or individual elements.

- **level**: level of the branch in a tree (Tree).

- **items**: items of the branch.

- **node_types**: types of nodes that make up the branch.

- **root**: first node of the branch.

- **tip**: last node of the branch.

### Attributes common to all trees (Tree)

- **branches**: list of branches that make up the tree.

- **len_branches**: number of branches that make up the tree.

- **main_branch**: main branch of the tree.

- **root**: root node of the tree.

- **branch_roots**: list of root nodes of each branch in the tree.

- **branch_tips**: list of tip nodes of each branch in the tree.

- **are_branches_hierarchical**: whether the tree is hierarchical or not.

- **mergeable_branches**: list of lists of branches that could be merged.

### Attributes common to all layers (Layer)

- **segments** : number of segments in the layer
- **surface** : associated surface of the layer
- **chain** : associated joint chain of the layer

### Attributes common to all modules (Module)

- **layers_group** : group containing the layers of the module
- **layers** : list of layers in the module
- **num_layers** : number of layers in the module
- **input_layer** : first layer of the module
- **output_layer** : last layer of the module
- **skin_joints** : list of joints that will be used for skinning
