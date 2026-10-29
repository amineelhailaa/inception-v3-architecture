# InceptionV3, one operation at a time

Open `index.html` in a modern browser. Everything needed for the animations is included in the file, so it also works offline.

- Right / Left: next / previous slide
- Space: one animation step
- P: play or pause the current animation
- R: replay the current animation
- F: full screen
- N: show or hide teaching notes

Use the chapter menu to jump to any slide. Animations stop at the end of each slide so the presenter controls the pace. On the scan slide, select any cell to inspect its calculation.

The 4×4 examples use invented values and weights to make the arithmetic visible. Architecture dimensions use the Keras InceptionV3 implementation for a 299×299 RGB input. Slide 4 continues the 4×4×3 toy example: 32 filters produce 32 complete 4×4 maps, giving a 4×4×32 output. Filter 1 exactly matches the preceding slide. The later 192-to-32 example is the pooling branch of `mixed0`. Convolution calculations show the linear operation separately from BatchNorm and ReLU. Standard dense convolution (`groups=1`) is assumed throughout.

Sources are linked inside the presentation. A browser presentation preserves these interactions; a PDF export would be static.

## Slide 9: overview and block details

Slide 9 opens with a compact, vertically scrollable network overview. It shows the stem, three separate early Inception blocks, the first reduction, four middle blocks, the second reduction, two final blocks, and the classifier. Arrows between rectangles represent sequential flow.

Click any rectangle to zoom into only that block. Its branches, filters, strides, padding, and tensor shapes are then visible. **Overview** returns to the network and restores your scroll position. The block picker can also open a section directly. Entering slide 9 again starts at the overview.

**Play flow**, **Step**, and **Replay** operate at the current level: between blocks in the overview, or through layers and parallel branches inside the selected block. Detail playback stops at that block's output. **Follow flow** optionally scrolls with the animation. Teal shows sequential flow, purple shows independent paths, and orange shows concatenation. Joins wait for their inputs. Colors illustrate dependencies, not literal hardware timing. The Functional API describes the whole graph.

Architecture details follow standard Keras InceptionV3 with 299×299 RGB input and the ImageNet head. Every convolution includes BatchNorm and ReLU. Dense and softmax are shown separately for teaching.
