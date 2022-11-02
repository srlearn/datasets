# roofworld20

`roofworld20` is a collection of 15 training buildings + 5 test buildings, where buildings are represented as graphs. The goal is to determine a 3D structure from a 2D image.

Nodes represent keypoints in an image of a building seen from above, and edges represent lines connecting those keypoints.

Consider the following:

```console
*---*---*
|   |   |
|   |   |
|   |   |
|   |   |
*---*---*
```

This shows six points: a belt of three points at the top and three similar points at the bottom, where each point connects to the one beneath it. If you were asked what shape this building has, you might infer that this is a gable-style roof where two planes slope away from one another.

This problem may be posed as collective binary classification: for each node in the graph, decide whether the node is higher than its neighbors.

## Task

**Binary Classification**: Is a keypoint higher than its neighbors?

```prolog
highpoint(+node).
connected(+node,-node).
connected(-node,+node).
nneighbors(+node,#neighborcount).
angledegrees(+node,+node,-node,#angletype).
angledegrees(+node,-node,+node,#angletype).
angledegrees(+node,-node,-node,#angletype).
```

The target variable is `highpoint(+node)` and represents whether a node is a higher point than other nodes that are nearby. Facts include the nodes each point is connected to (`connected(_,_)`), the number of neighbors a node has (`nneighbors(_,_)`), and the type of angle formed by nodes (acute, right, obtuse, or a straight line).

## Notes

This dataset was created as an example for infusing prior knowledge in computer vision models. Describing buildings as graphs produces a representation that is translation-invariant and rotation-invariant.

Further details are included with the "[RoofWorldGUI](https://github.com/hayesall/RoofWorldGUI) project."
