# Image Features

Coarse appearance descriptions and computed lossy global statistics for two input images. Each image has 101 values for the head region and 101 for the visible-person region. Original images, crops, pixel arrays, and face-recognition templates are not stored.

These descriptions and statistics do not establish identity or the behavior and evaluations in the person record.

## Image 1

Dark hair is pulled back. A dark gray, high-collared quilted jacket and a band running diagonally across the chest are visible in a frontal upper-body close-up. The lower body is outside the frame, the full hair length cannot be determined, and blur limits detail.

- [Structured description](b4a63e2d-d9f0-48e5-ba3f-a2c776cd7821.spec.json)
- [Numeric statistics](ext/b4a63e2d-d9f0-48e5-ba3f-a2c776cd7821.features.npz)
- [Algorithm metadata](ext/b4a63e2d-d9f0-48e5-ba3f-a2c776cd7821.features.meta.json)

Observation limits: Blur limits detail; no fine facial characteristics are assessed. The hairstyle obscures full hair length and natural texture; the lower body is outside the frame.

## Image 2

Dark hair is worn in an updo with a small light-colored hair accessory. A light-colored short-sleeved top and a dark floral skirt are visible in a nearly full-length rear view, with the head turned slightly to one side and the arms near a railing. The face is only partly visible, and full hair length cannot be determined.

- [Structured description](1868267e-f836-4a65-b686-ea19006aed69.spec.json)
- [Numeric statistics](ext/1868267e-f836-4a65-b686-ea19006aed69.features.npz)
- [Algorithm metadata](ext/1868267e-f836-4a65-b686-ea19006aed69.features.meta.json)

Observation limits: The face is only partly visible; fine facial characteristics and eyewear are not assessed. The updo obscures full hair length and natural texture. The head region has limited original detail; resizing does not add real detail.

## Computation and Scope

- Preprocessing: decode to RGB in display orientation, preserve aspect ratio and resize to a 256-pixel longest edge; apply CLAHE to grayscale.
- Per region: 64 H-S color counts, 10 and 18 uniform-LBP counts, and 9 magnitude-weighted Sobel orientation sums.
- Regions are coarse Agent estimates and may include some background; region coordinates and intermediate images are not stored.
- Each image uses its own local `p001`; no cross-image identity association is made.
- Clothing, pose, lighting, and background affect these statistics. They are not evidence of identity or behavior.
