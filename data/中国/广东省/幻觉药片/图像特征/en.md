# Image Features

Coarse appearance descriptions and computed lossy global statistics for the foreground subject in three input screenshots. Each image has 101 values for the head region and 101 for the visible-person region, for 606 values in total. Only descriptions, structured attributes, numeric aggregates, and algorithm metadata are stored.

These results do not establish identity or the behavior and evaluations in the person record. This processing has not archived original images, screenshot copies, crops, pixel arrays, or face-recognition templates.

## Image 1

Long brown hair is worn loose. A gray quilted coat and a plaid scarf in blue, yellow, and reddish-brown tones are visible. The body faces sideways while the head turns toward the camera in an upper-body view. The scarf partly obscures the neck and lower face, and the lower body is not fully shown.

- [Structured description](7ddc936e-223e-4839-8d6e-00e4f188aa20.spec.json)
- [Numeric statistics](ext/7ddc936e-223e-4839-8d6e-00e4f188aa20.features.npz)
- [Algorithm metadata](ext/7ddc936e-223e-4839-8d6e-00e4f188aa20.features.meta.json)

Observation limits: The scarf partly obscures the neck and lower face; the lower body is not fully visible. Screenshot compression, outdoor lighting, and visible white particles may affect color and texture statistics.

## Image 2

Long brown hair is worn loose, with strands across the forehead. A white openwork knitted top is visible. The subject is seated and holds one hand beside the face in a V gesture, in an upper-body close-up viewed slightly from above. The lower body is not fully visible, and other people appear in the background.

- [Structured description](53de1106-a65b-4b73-a957-30e781eb6cd1.spec.json)
- [Numeric statistics](ext/53de1106-a65b-4b73-a957-30e781eb6cd1.features.npz)
- [Algorithm metadata](ext/53de1106-a65b-4b73-a957-30e781eb6cd1.features.meta.json)

Observation limits: The lower body is not fully visible; the close, elevated viewpoint may affect apparent proportions. Background people are not processed individually. Background clothing may enter the edges of the coarse subject region and affect aggregate statistics.

## Image 3

Long dark-brown hair is worn loose. A light-blue knitted top, a large hoop earring on one visible side, and a dark diagonal band across the chest are visible in a nearly frontal upper-body close-up. The lighting is dim, and the lower body is outside the frame.

- [Structured description](7a5dbb39-d25a-47ca-b981-bf6bcd900ca2.spec.json)
- [Numeric statistics](ext/7a5dbb39-d25a-47ca-b981-bf6bcd900ca2.features.npz)
- [Algorithm metadata](ext/7a5dbb39-d25a-47ca-b981-bf6bcd900ca2.features.meta.json)

Observation limits: Dim lighting may affect judgments of hair and clothing color; the lower body is outside the frame. Hair and the diagonal band obscure parts of the top, limiting assessment of its full structure.

## Computation and Scope

- Preprocessing: decode to RGB in display orientation, preserve aspect ratio and resize to a 256-pixel longest edge. Apply CLAHE to grayscale with clipLimit=2.0 and tileGridSize=(8,8).
- Per region: 64 H-S color counts, 10 and 18 uniform-LBP counts, and 9 magnitude-weighted Sobel orientation sums.
- Regions are coarse Agent estimates that avoid the phone interface and black margins but may include background. Background people are not processed individually.
- Each p001 is local to its own image; no cross-image identity confirmation is made.
- Intermediate images, crop bounds, and region coordinates are used only in memory and are not written to the derived outputs.
- Lighting, clothing, pose, screenshot compression, and background affect the aggregates. They are not evidence of identity or behavior.
