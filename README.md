# InceptionV3, one operation at a time

Open `index.html` in a modern browser. Everything needed for the animations is included in the file, so it also works offline.

- Right / Left: next / previous slide
- Space: one animation step
- P: play or pause the current animation
- R: replay the current animation
- F: full screen
- N: show or hide teaching notes

Use the chapter menu to jump to any slide. Animations stop at the end of each slide so the presenter controls the pace. On the scan slide, select any cell to inspect its calculation.

The 4×4 examples use invented values and weights to make the arithmetic visible. Architecture dimensions use the Keras InceptionV3 implementation for a 299×299 RGB input. The 192-to-32 example is the pooling branch of `mixed0`. Convolution calculations show the linear operation separately from BatchNorm and ReLU. Standard dense convolution (`groups=1`) is assumed throughout.

Sources are linked inside the presentation. A browser presentation preserves these interactions; a PDF export would be static.
