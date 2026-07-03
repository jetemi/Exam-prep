# CSC 428 — Computer Graphics: Exam-Ready Answers

---

## QUESTION 1

### 1(a) Triangle transformations

The matrix `(2 4 4 / 2 2 4)` gives the vertices as **columns**: **A(2,2), B(4,2), C(4,4)**.

#### (i) 90° rotation about the origin

**Rule to remember: (x, y) → (−y, x)** for 90° **counter-clockwise.**

Rotation matrix (θ = 90°, cos 90° = 0, sin 90° = 1):

```
R = [ cos90  −sin90 ] = [ 0  −1 ]
    [ sin90   cos90 ]   [ 1   0 ]
```

Multiplication for A(2,2):

```
[ 0  −1 ] [ 2 ]   [ (0)(2) + (−1)(2) ]   [ −2 ]
[ 1   0 ] [ 2 ] = [ (1)(2) +  (0)(2) ] = [  2 ]
```

Multiplication for B(4,2):

```
[ 0  −1 ] [ 4 ]   [ (0)(4) + (−1)(2) ]   [ −2 ]
[ 1   0 ] [ 2 ] = [ (1)(4) +  (0)(2) ] = [  4 ]
```

Multiplication for C(4,4):

```
[ 0  −1 ] [ 4 ]   [ (0)(4) + (−1)(4) ]   [ −4 ]
[ 1   0 ] [ 4 ] = [ (1)(4) +  (0)(4) ] = [  4 ]
```


| Vertex | Original | After 90° rotation |
| ------ | -------- | ------------------ |
| A      | (2, 2)   | **(−2, 2)**        |
| B      | (4, 2)   | **(−2, 4)**        |
| C      | (4, 4)   | **(−4, 4)**        |


#### (ii) Reflection about the line y = −x

**Rule to remember: (x, y) → (−y, −x)** — swap the coordinates, then negate both.

```
M = [  0  −1 ]
    [ −1   0 ]
```

Applied to the **original** vertices:


| Vertex | Original | After reflection about y = −x |
| ------ | -------- | ----------------------------- |
| A      | (2, 2)   | **(−2, −2)**                  |
| B      | (4, 2)   | **(−2, −4)**                  |
| C      | (4, 4)   | **(−4, −4)**                  |


> 💡 **Transformation rules cheat-box**
>
> - 90° CCW rotation: (x, y) → (−y, x)
> - 90° CW rotation: (x, y) → (y, −x)
> - 180° rotation: (x, y) → (−x, −y)
> - Reflect about y = x: (x, y) → (y, x) (just swap)
> - Reflect about y = −x: (x, y) → (−y, −x) (swap + negate both)
> - Reflect about x-axis: (x, y) → (x, −y); about y-axis: (−x, y)

---

### 1(b) Electrostatic vs Magnetic deflection — 5 marks

In a CRT, the electron beam must be steered to hit any point on the phosphor-coated screen. Two deflection methods exist:


|                  | **Electrostatic deflection**                                                                    | **Magnetic deflection**                                                        |
| ---------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Field used       | Electric field                                                                                  | Magnetic field                                                                 |
| Produced by      | Two pairs of parallel **deflection plates** inside the tube (one pair horizontal, one vertical) | **Deflection coils (yoke)** wound around the neck of the CRT, outside the tube |
| Deflection ∝     | **Voltage** applied to the plates                                                               | **Current** through the coils                                                  |
| Speed            | Very fast — suits high-frequency use (oscilloscopes)                                            | Slower response                                                                |
| Deflection angle | Small (needs a longer tube for a big screen)                                                    | Large — allows short, wide tubes                                               |
| Typical use      | Oscilloscopes, high-speed displays                                                              | TV sets and computer monitors                                                  |


*One-line summary:* electrostatic deflection bends the beam with an electric field between plates (fast but small angle); magnetic deflection bends it with the magnetic field of external coils (larger angle, cheaper, used in TVs/monitors).

---

### 1(c) Define: resolution, refreshing, frame — 3 marks

- **Resolution** — the numbr of pixels a display can show (or an image contains), expressed as width × height, e.g. 1920×1080. Higher resolution → finer detail and sharper images.
- **Refreshing (refresh rate)** — the number of times per second the screen image is redrawn, measured in Hz (e.g. 60 Hz). Needed because phosphor glow decays quickly; a rate below the **critical fusion frequency (CFF)** causes visible flicker.
- **Frame (frame rate)** — a frame is one complete still image of a video/animation (the full pixel pattern held in the frame buffer). Frame rate is the number of frames displayed per second (fps) — e.g. 24 fps film, 60 fps games. Higher fps → smoother motion.

---

### 1(d) Brief definition of computer graphics — 2 marks

**Computer graphics is the creation, storage and manipulation of models and images of objects using computers.** It covers the algorithms and techniques for modeling, rendering and animating 2D/3D images, and is used in entertainment, CAD, visualization, GUIs, etc.

---

### 1(e) How is LCD different from LED? — 3 marks

- **LCD (Liquid Crystal Display):** liquid crystals do **not emit light**; they only modulate (block or pass) light from a separate **backlight**. An electric field changes the orientation of the crystals, controlling how much light passes through each pixel; colour filters give R, G, B subpixels.
- **LED (Light Emitting Diode) display:** uses light-emitting diodes, semiconductor devices that **emit their own light** when current passes through them — either as the backlight of an LCD ("LED TV") or as self-emitting pixels (OLED/MicroLED), which gives true blacks and higher contrast.
- **Key difference:** an LCD is *transmissive* (modulates external backlight, cannot show true black), while an LED display is *emissive* (each diode generates its own light and can switch fully off).

---

### 1(f) List ten (10) input devices — 5 marks

1. Keyboard
2. Mouse
3. Trackball
4. Joystick
5. Light pen
6. Graphics tablet (digitizer)
7. Touch screen
8. Scanner
9. Webcam / digital camera
10. Microphone (voice input)

*(Spares: barcode reader, data glove, OMR/OCR reader.)*

---

### 1(g) The two types of graphics software — 2 marks

1. **General programming packages** — libraries of graphics functions used from a programming language to build graphics applications (functions for drawing primitives, transformations, filling, interaction). *Examples: OpenGL, GKS, PHIGS.*
2. **Special-purpose application packages** — ready-made applications for non-programmers who just create graphics. *Examples: Photoshop, AutoCAD (CAD packages), paint and animation packages.*

---

## QUESTION 2 (theory)

### 2(a) Five applications of computer graphics — 5 marks

1. **Entertainment** — movies (CGI/special effects), video games, animation.
2. **Computer-Aided Design (CAD/CAM)** — mechanical, electronic, architectural and product design.
3. **Scientific/data visualization** — medical imaging, simulation results, charts, GIS.
4. **Graphical User Interfaces (GUIs)** — windows, icons, menus, cursors.
5. **Education & training** — flight/medical simulators, virtual laboratories, VR/AR.

*(Spares: digital art & advertising, image processing, e-commerce product visualization.)*

### 2(b) Briefly describe — 2 marks each

- **(i) Pixel** — *picture element*: the smallest addressable unit of a raster image or display; a single point of colour in the grid that makes up an image.
- **(ii) Screen resolution** — the total number of pixels the display device can physically show, given as width × height (e.g. 1920×1080); determines how much detail the screen can present.
- **(iii) Image resolution** — the amount of pixel detail stored *in an image*: its pixel dimensions, or its pixel density (PPI/DPI for print). Higher image resolution → more captured detail.
- **(iv) Dot pitch** — the distance (in mm) between the centres of two adjacent phosphor dots/triads of the same colour on the screen. **Smaller dot pitch → sharper image.**
- **(v) Aspect ratio** — the ratio of width to height of an image or display, e.g. 16:9 (widescreen), 4:3 (standard). It describes the shape of the display, not its size.

### 2(c) Five broad categories of display devices — 2½ marks

1. Cathode Ray Tube (CRT) displays
2. Liquid Crystal Displays (LCD)
3. LED displays (including OLED)
4. Plasma display panels
5. Projectors

*(Spares: e-paper displays, head-mounted displays (VR), field-emission displays.)*

### 2(d) Five advantages of voice recognition as an input system — 2½ marks

1. **Hands-free operation** — usable while hands are busy (driving, surgery, factory work).
2. **Accessibility** — enables users with physical disabilities to operate the computer.
3. **Speed** — dictation is faster than typing for most people.
4. **Natural and intuitive** — speaking needs no special training, unlike keyboard skills.
5. **Multitasking/efficiency** — commands can be given while performing other tasks, streamlining workflows.

---

## QUESTION 3 — DDA (calculation + theory)

### 3(a) Line from (2,3) to (6,15) with DDA — how many points? — 7 marks

**Working:**

1. dx = x₂ − x₁ = 6 − 2 = **4**
2. dy = y₂ − y₁ = 15 − 3 = **12**
3. steps = max(|dx|, |dy|) = max(4, 12) = **12**
4. x-increment = dx/steps = 4/12 = **0.333**;  y-increment = dy/steps = 12/12 = **1**

**Answer: the algorithm runs 12 steps, so 13 points in total are needed to generate the line (the starting point (2,3) + 12 generated points, ending exactly at (6,15)).**

Full table ( round x to nearest integer):


| Step | x (real) | y   | Plot (round x, y) |
| ---- | -------- | --- | ----------------- |
| 0    | 2.000    | 3   | (2, 3)            |
| 1    | 2.333    | 4   | (2, 4)            |
| 2    | 2.667    | 5   | (3, 5)            |
| 3    | 3.000    | 6   | (3, 6)            |
| 4    | 3.333    | 7   | (3, 7)            |
| 5    | 3.667    | 8   | (4, 8)            |
| 6    | 4.000    | 9   | (4, 9)            |
| 7    | 4.333    | 10  | (4, 10)           |
| 8    | 4.667    | 11  | (5, 11)           |
| 9    | 5.000    | 12  | (5, 12)           |
| 10   | 5.333    | 13  | (5, 13)           |
| 11   | 5.667    | 14  | (6, 14)           |
| 12   | 6.000    | 15  | (6, 15)           |


### 3(b) Three merits and three demerits of DDA — 6 marks

**Merits:**

1. **Simple** to understand and implement.
2. **Incremental** — uses only additions per step (no multiplication in the loop), so it is faster than evaluating y = mx + b directly for every pixel.
3. Easy to implement in both **hardware and software**.

**Demerits:**

1. Uses **floating-point arithmetic**, which is slower than integer arithmetic.
2. The **round()** operation at every step is time-consuming.
3. **Cumulative round-off error** — over long lines the plotted pixels can drift away from the true line path.

### 3(c) Given pixel (xᵢ, yᵢ) on the line yᵢ = mxᵢ + b, develop the DDA algorithm — 7 marks

**Derivation:**

For a unit step in x, the next pixel is at xᵢ₊₁ = xᵢ + 1. Substituting into the line equation:

```
yᵢ₊₁ = m·xᵢ₊₁ + b
     = m(xᵢ + 1) + b
     = (m·xᵢ + b) + m
∴ yᵢ₊₁ = yᵢ + m
```

So each unit step in x increases y by exactly the slope m — the next point is obtained by **addition only** (this is what makes DDA incremental). Similarly, stepping in y: xᵢ₊₁ = xᵢ + 1/m.

**Algorithm:**

1. Input the endpoints; compute dx = x₂−x₁, dy = y₂−y₁, m = dy/dx.
2. **Case |m| ≤ 1** (x is the major axis): starting from (x₁, y₁), repeat until x = x₂:
  - xᵢ₊₁ = xᵢ + 1
  - yᵢ₊₁ = yᵢ + m
  - plot (xᵢ₊₁, round(yᵢ₊₁))
3. **Case |m| > 1** (y is the major axis): repeat until y = y₂:
  - yᵢ₊₁ = yᵢ + 1
  - xᵢ₊₁ = xᵢ + 1/m
  - plot (round(xᵢ₊₁), yᵢ₊₁)
4. Stop when the endpoint is reached.

---

## QUESTION 4 — Bresenham

### 4(a) Develop Bresenham's line algorithm for P₁(x₁′, y₁′) followed by P₂ in the horizontal direction — 10 marks

"Horizontal direction" means the line's major axis is x (slope 0 ≤ m ≤ 1), so **x increases by 1 every step** and the only decision is whether y stays or increases.

**Derivation of the decision parameter:**

After plotting pixel (xₖ, yₖ), the next column is xₖ+1 and the true line there is y = m(xₖ+1) + b. The candidates are the pixel **E** = (xₖ+1, yₖ) and the pixel **NE** = (xₖ+1, yₖ+1). The two distances are:

```
d_lower = y − yₖ            (gap below the line to E)
d_upper = (yₖ + 1) − y      (gap above the line to NE)
```

Define the decision parameter pₖ = Δx·(d_lower − d_upper). Expanding with m = Δy/Δx and keeping integers:

```
pₖ = 2Δy·xₖ − 2Δx·yₖ + c        (c is a constant that cancels out)
```

- If **pₖ < 0**: the line is closer to E → keep y; and pₖ₊₁ = pₖ + 2Δy
- If **pₖ ≥ 0**: the line is closer to NE → y = y + 1; and pₖ₊₁ = pₖ + 2Δy − 2Δx
- Initial value: **p₀ = 2Δy − Δx**

**Algorithm:**

1. Input endpoints (x₁, y₁) and (x₂, y₂); compute Δx = x₂−x₁, Δy = y₂−y₁.
2. Compute p₀ = 2Δy − Δx and plot the first pixel (x₁, y₁).
3. At each step, x = x + 1, then:
  - if p < 0: plot (x, y);  p = p + 2Δy
  - else: y = y + 1; plot (x, y);  p = p + 2Δy − 2Δx
4. Repeat step 3 until x reaches x₂.

*(Note: only integer arithmetic is used — no floats, no rounding. For a falling line, y steps by −1 instead of +1.)*

### 4(b) Line from (1,1) to (8,5) — find the intermediate points — 5 marks

Δx = 7, Δy = 4 → **p₀ = 2Δy − Δx = 8 − 7 = 1**. Constants: 2Δy = 8, 2Δy − 2Δx = −6.


| k   | pₖ  | pₖ < 0? | Action     | Next p     | Plot       |
| --- | --- | ------- | ---------- | ---------- | ---------- |
| —   | —   | —       | plot start | —          | **(1, 1)** |
| 0   | 1   | no      | x+1, y+1   | 1 − 6 = −5 | **(2, 2)** |
| 1   | −5  | yes     | x+1        | −5 + 8 = 3 | **(3, 2)** |
| 2   | 3   | no      | x+1, y+1   | 3 − 6 = −3 | **(4, 3)** |
| 3   | −3  | yes     | x+1        | −3 + 8 = 5 | **(5, 3)** |
| 4   | 5   | no      | x+1, y+1   | 5 − 6 = −1 | **(6, 4)** |
| 5   | −1  | yes     | x+1        | −1 + 8 = 7 | **(7, 4)** |
| 6   | 7   | no      | x+1, y+1   | —          | **(8, 5)** |


**Points: (1,1), (2,2), (3,2), (4,3), (5,3), (6,4), (7,4), (8,5)** ✅ (verified — the p-sequence is 1, −5, 3, −3, 5, −1, 7)

### 4(c) Three advantages and two disadvantages of Bresenham's algorithm — 5 marks

**Advantages:**

1. Uses **only integer arithmetic** (addition, subtraction, comparison) — no floats, no rounding.
2. **Faster and more efficient** than DDA for the same reason.
3. **Accurate** — no accumulated round-off error; the plotted points stay closest to the true line.

**Disadvantages:**

1. The **derivation of the decision parameter is more complex** and less intuitive than DDA.
2. The basic algorithm handles one octant; **other slopes need separate cases/symmetry handling**, and lines still show aliasing (jaggies) without anti-aliasing.

---

## QUESTION 5 — Circles, attributes & effects

### 5(a) Mid-Point Circle algorithm: three advantages, two disadvantages — 5 marks

**Advantages:**

1. Uses **only integer arithmetic** → fast and efficient.
2. Exploits **8-way symmetry** — computes only one octant and mirrors it to the other seven.
3. **Avoids square roots and trigonometric functions** needed by direct methods.

**Disadvantages:**

1. **Works only for circles** (and arcs) — ellipses and other curves need different algorithms.
2. The **decision-parameter derivation is complex**, and the circle still shows staircase effects (aliasing).
  *
  1. **Assumes integer centre and radius** — non-integer inputs need adaptation.)*

### 5(b) Define attribute parameter — 1 mark

An **attribute parameter** is any parameter that controls how a primitive is displayed — e.g. **colour, intensity, line style** (solid/dashed/dotted), **line width, fill style, text font**.

### 5(c) What is the purpose of clipping? — 2 marks

Clipping **removes the portions of primitives (lines, polygons, text) that lie outside a defined region** (the clip window/viewport). Purpose: display only what is visible, avoid wasting processing on invisible parts, and keep drawing inside window boundaries.

### 5(d) Describe — 2 marks each

- **(i) Overstriking effect** — when the same pixels are drawn over more than once (e.g. a line redrawn on itself), their intensity builds up, so the repeated part appears **brighter/thicker** than intended.
- **(ii) Unequal intensity** — lines of different slopes appear to have different brightness because the pixel spacing varies with the slope: a 45° diagonal places pixels √2 units apart, while horizontal/vertical lines place them 1 unit apart — so a diagonal line has **fewer pixels per unit length** and therefore **looks dimmer** than a horizontal or vertical line of the same length.
- **(iii) Aliasing effect** — the **staircase ("jaggies")** appearance of slanted lines and curves, caused by approximating a continuous shape with a discrete grid of pixels. Reduced by **anti-aliasing** (blending edge pixel colours / supersampling).

### 5(e) Understanding of these terms — 2 marks each

- **(i) Transparency** — the property of letting light pass through an object so that objects behind it remain visible; implemented with an **alpha value** (α = 1 opaque, α = 0 fully transparent, in-between = translucent). Used for glass, water, overlays and blending.
- **(ii) Shadow** — a dark region formed where an object blocks light from a source. Shadows give scenes **depth and realism**; generated with techniques like **shadow mapping** or shadow volumes (hard shadows from point lights, soft shadows from area lights).
- **(iii) Texture** — an image (bitmap of *texels*) **mapped onto the surface** of a model to add surface detail (wood grain, brick, skin) without adding geometry. Texture mapping dramatically increases realism at low cost; variants include bump/normal maps.

---

## ADDITIONAL QUESTIONS (From assignment)

### A1 — Difference between Gouraud and Phong shading

Both are **smooth-shading** methods that make a polygon mesh look like a curved surface. The difference is **what gets interpolated across the polygon** and **where the lighting equation is evaluated**.


|                                      | **Gouraud shading**                                                                                                                                                                                    | **Phong shading**                                                                                                                                                                    |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| What is interpolated across the face | **Colour/intensity** values                                                                                                                                                                            | **Surface normal** vectors                                                                                                                                                           |
| Where lighting is computed           | Once **per vertex**                                                                                                                                                                                    | Once **per pixel (fragment)**                                                                                                                                                        |
| Method                               | 1. Find vertex normals (average of adjacent face normals). 2. Apply the lighting model at each vertex → a colour. 3. Linearly interpolate those **colours** across the polygon during scan conversion. | 1. Find vertex normals. 2. Interpolate the **normals** across the polygon → a normal at each pixel. 3. Apply the lighting model at **every pixel** using its (re-normalized) normal. |
| Cost                                 | Cheap, fast                                                                                                                                                                                            | Expensive (lighting per pixel)                                                                                                                                                       |
| Quality                              | Lower — a **specular highlight** landing inside a polygon is missed or smeared; can show **Mach banding**                                                                                              | Higher — accurate specular highlights, smoother, no Mach banding                                                                                                                     |


### A2 — Why is modeling done in computer graphics?

**Modeling** is creating the geometric/mathematical description (the "model") of an object or scene — its vertices, edges, polygons/surfaces plus attributes like colour, material and texture — **before** it is rendered. It is done because:

1. **The computer cannot display a real object directly** — it must first be represented in a form the machine can store and process.
2. **It supplies the input the rendering pipeline needs** to synthesize an image (no model → nothing to render).
3. **It separates the object's description from its display** — one model can be viewed from any angle, distance or lighting, so it is reusable, device-independent and resolution-independent.
4. **It enables transformation, animation and simulation** — the model can be moved, rotated, scaled, deformed or physically simulated over time.
5. **It lets complex scenes be built from simple primitives**, combined hierarchically (a car from cylinders, boxes, etc.).
6. **It supports analysis** — in CAD, models allow measurement, tolerance checking, volume and stress calculations.

*One-liner:* modeling turns a real or imagined object into structured data the computer can store, transform and render into images.

### A3 — Purpose of homogeneous coordinates

Homogeneous coordinates represent an *n*-dimensional point with *n + 1* numbers: a 2D point (x, y) becomes **(x, y, 1)** and a 3D point (x, y, z) becomes **(x, y, z, 1)**; in general (x, y, z, w) means the Cartesian point **(x/w, y/w, z/w)**. Their purposes:

1. **Make translation a matrix multiplication.** Translation is *not* linear, so it cannot be done by an ordinary 2×2 / 3×3 matrix. Adding the extra coordinate lets translation — and therefore **all** affine transforms (translate, rotate, scale, shear, reflect) — be written **uniformly as one matrix multiply**.
2. **Allow transforms to be concatenated (composed).** Because every transform is now a matrix, a whole sequence can be **multiplied into a single matrix** and applied to each vertex once → an efficient pipeline.
3. **Represent perspective projection as a matrix.** The final divide by *w* produces the perspective foreshortening (distant objects appear smaller).
4. **Represent points at infinity** (w = 0) — useful for directions/vectors and for vanishing points.

> 💡 The single sentence to remember: *homogeneous coordinates let translation (and perspective) be expressed as matrix multiplications, so every transformation is uniform and can be combined into one matrix.*

### A4 — Geometry (3D) pipeline vs Imaging (2D) pipeline


|                  | **Geometry (3D) pipeline**                                                                                                         | **Imaging (2D) pipeline**                                                                           |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Also called      | Rendering / synthesis / geometric pipeline                                                                                         | Image-processing pipeline                                                                           |
| **Input**        | **3D geometric models** — vertices, primitives, surfaces                                                                           | **Existing images** — 2D arrays of pixels / sampled data                                            |
| **What it does** | Transforms & projects 3D geometry (modeling → viewing → lighting → projection → clipping → rasterization) to **create** a 2D image | Applies image operations — filtering, convolution, warping, scaling, colour correction, compositing |
| **Direction**    | **3D geometry → image** (synthesizes a new picture)                                                                                | **image → image** (processes an existing picture)                                                   |
| Works with       | Vector / geometric primitives                                                                                                      | Raster / pixel (sampled) data                                                                       |
| Example use      | Rendering a 3D game scene or CAD model                                                                                             | Photoshop filters, medical-image enhancement, compositing                                           |


*Key difference:* the geometry pipeline **builds** an image from a 3D scene description, while the imaging pipeline **transforms** already-sampled pixel data into another image — no 3D geometry is involved.

### A5 — Stages of the basic rendering pipeline

The pipeline turns a 3D scene description into pixels, in four broad blocks — **Application → Geometry → Rasterization → Display**. Expanded stages:

1. **Modeling / Application** — objects are defined in their own **local (model/object) coordinates**; the scene is assembled.
2. **Modeling transformation** — place each object into a common **world coordinate** system (model → world).
3. **Viewing (camera) transformation** — transform the scene from world into **eye / camera / view coordinates** (position the camera).
4. **Lighting / Shading** — apply the illumination model to compute colours (per-vertex in the basic pipeline).
5. **Projection** — project 3D → 2D onto the view plane (perspective or orthographic).
6. **Clipping** — remove or trim primitives lying outside the view volume (frustum).
7. **Viewport (window-to-viewport) transformation** — map normalized device coordinates to **screen / device (pixel) coordinates**.
8. **Rasterization / Scan conversion** — convert primitives into fragments/pixels, interpolate attributes, do **hidden-surface removal** (z-buffer) and texturing.
9. **Display** — write the final pixels to the **frame buffer** for output on screen.

> 💡 Coordinate-system journey to memorize: **Model → World → View/Eye → Projection → Normalized device → Screen.**
> (Note: lighting is usually computed in world or eye space, so stages 3–4 are sometimes drawn in either order.)

---

## ⚡ Last-minute cram sheet

**Transformations:** 90° CCW (x,y)→(−y,x) · y=−x reflection (x,y)→(−y,−x) · y=x reflection (x,y)→(y,x)

**DDA:** steps = max(|dx|,|dy|); x-inc = dx/steps, y-inc = dy/steps; **total points = steps + 1**. Development key line: yᵢ₊₁ = yᵢ + m.

**Bresenham:** p₀ = 2Δy − Δx · p<0 → East, p += 2Δy · p≥0 → North-East (y+1), p += 2Δy − 2Δx. Integer-only.

**(2,3)→(6,15):** steps 12 → **13 points**.  **(1,1)→(8,5):** p₀=1 → (1,1),(2,2),(3,2),(4,3),(5,3),(6,4),(7,4),(8,5).

**Two types of graphics software:** general programming packages (OpenGL, GKS, PHIGS) vs special-purpose application packages (Photoshop, AutoCAD).

**Deflection:** electrostatic = plates + voltage + fast + small angle (oscilloscopes); magnetic = coils + current + big angle (TVs).

**LCD vs LED:** LCD modulates a backlight (transmissive); LED emits its own light (emissive).

**Gouraud vs Phong shading:** Gouraud interpolates **colours** (lighting per **vertex**, cheap, misses highlights); Phong interpolates **normals** (lighting per **pixel**, costly, accurate highlights).

**Homogeneous coords:** add a coordinate ((x,y)→(x,y,1)) so **translation & perspective become matrix multiplies** and all transforms combine into one matrix.

**Geometry (3D) pipeline** = 3D geometry → image (synthesis). **Imaging (2D) pipeline** = image → image (pixel processing: filter, warp, composite).

**Rendering pipeline:** Model → World → View → Projection → Clip → Screen → Rasterize → Display.

**Modeling:** turns a real/imagined object into structured data the computer can store, transform and render.