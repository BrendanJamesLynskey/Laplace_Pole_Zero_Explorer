# Linear Transformation Visualiser

An interactive tool for exploring how 2x2 matrices transform two-dimensional space. Watch grids warp, circles stretch into ellipses, and basis vectors swing to new directions -- all in real time.

### [Launch App](https://brendanjameslynskey.github.io/Linear_Transformation_Visualiser/)

---

## What is this?

Every 2x2 matrix defines a geometric operation on the plane. Multiplication by a matrix can rotate, scale, shear, reflect, or project two-dimensional figures, and most real transformations combine several of these at once. This visualiser lets you type in any 2x2 matrix (or choose a preset) and immediately see the effect on a coordinate grid, a unit circle, and the standard basis vectors **e1** and **e2**.

The **determinant** of a matrix is the signed area scaling factor of the transformation. If the unit square has area 1 before the transformation, the parallelogram it maps to has area |det(A)|. A positive determinant means orientation is preserved (e.g. a counter-clockwise loop stays counter-clockwise); a negative determinant means orientation is reversed (the loop becomes clockwise); and a zero determinant means the transformation collapses the plane down to a line or a point -- the matrix is singular.

**Eigenvectors** are the special directions that the matrix does not rotate -- it can only scale them. If **v** is an eigenvector with eigenvalue lambda, then **Av** = lambda **v**: the vector stays on its own line, stretched by a factor of lambda (or flipped, if lambda is negative). Not every matrix has real eigenvectors; a pure rotation, for example, has complex eigenvalues, meaning no direction in the real plane is left unrotated. The **Singular Value Decomposition (SVD)** reveals the geometry of any matrix by factoring it as **A = U Sigma V^T** -- first rotate the space (V^T) to align with the directions of greatest stretching, then scale along those axes (Sigma), then rotate again (U) to the final orientation. The visualiser shows each of these three steps in separate plots so you can see exactly how the transformation is built up.

## Presets

| Preset | Description |
|--------|-------------|
| **Identity** | The do-nothing transformation. Every point maps to itself; the grid, circle, and basis vectors are unchanged. |
| **Rotation 45 deg** | Rotates the entire plane 45 degrees counter-clockwise about the origin. Distances and angles are preserved; the determinant is 1. |
| **Rotation 90 deg** | Rotates 90 degrees counter-clockwise. The basis vector **e1** maps to **e2**, and **e2** maps to **-e1**. |
| **Shear X** | Slides points horizontally in proportion to their y-coordinate. Horizontal lines stay fixed; vertical lines tilt. The determinant is 1, so areas are preserved. |
| **Shear Y** | Slides points vertically in proportion to their x-coordinate. Vertical lines stay fixed; horizontal lines tilt. Area is preserved. |
| **Reflect x-axis** | Mirrors the plane across the x-axis. The determinant is -1, reversing orientation while preserving area. |
| **Reflect y = x** | Mirrors the plane across the line y = x, swapping coordinates. The determinant is -1. |
| **Scale (2, 0.5)** | Stretches horizontally by a factor of 2 and compresses vertically by a factor of 0.5. The unit circle becomes an ellipse aligned with the axes. |
| **Project x-axis** | Collapses the plane onto the x-axis. All y-information is lost; the determinant is 0 (singular). |
| **Squeeze** | An area-preserving mapping that stretches one axis while compressing the other by the same factor, keeping det = 1. |
| **Rot + Scale** | A rotation combined with uniform scaling. The circle maps to a larger (or smaller) circle, and the determinant equals the square of the scale factor. |
| **Hyperbolic Rot** | A Lorentz-boost-style transformation (hyperbolic rotation). It stretches along one diagonal and compresses along the other, preserving the hyperbola xy = const. |

## Features

- **Side-by-side plots** -- the original space (grid, unit circle, unit square, basis vectors) and the transformed space are shown next to each other for direct comparison.
- **Live matrix entry** -- edit any of the four entries of the 2x2 matrix and see the transformation update instantly.
- **Preset library** -- 12 classic transformations loaded with a single click, each triggering a smooth animation from the identity.
- **Animated interpolation slider** -- a slider interpolates continuously from the identity matrix **I** (0%) to the target matrix **A** (100%), so you can watch the transformation unfold. A Play/Pause button auto-animates the slider back and forth.
- **Determinant display with parallelogram overlay** -- the numerical determinant is shown in the info panel, and the transformed unit square is drawn as a filled parallelogram on the "After" plot. Positive determinants are shaded blue; negative determinants are shaded red.
- **Eigenvalue and eigenvector overlay** -- toggle dashed lines along eigenvector directions in both plots. The info panel shows eigenvalues, including complex ones. For real eigenvalues, you can see that the eigenvectors are exactly the directions that the transformation only stretches without rotating.
- **SVD decomposition view** -- toggle three mini-plots that show the three stages of the SVD: (1) V^T rotates the input to align with the principal axes, (2) Sigma scales along those axes, (3) U rotates to the final output orientation.
- **Transformation type classification** -- the info panel identifies the transformation as Rotation, Diagonal, Rotation + Scale, Singular, Orientation-reversing, or General.
- **Responsive dark theme** -- works on desktop and mobile with a dark colour scheme.

## Built with

- [Plotly.js](https://plotly.com/javascript/) for interactive 2D plotting
- Vanilla HTML, CSS, and JavaScript -- no frameworks, no build step
- Deployed with GitHub Pages
