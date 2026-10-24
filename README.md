# JUDY public overview

A static overview of JUDY, a research prototype for AI-assisted garment measurement from photos. It explains the workflow, aggregate historical results, and limits of the evidence.

Intended GitHub Pages address: `https://sohitqwer-del.github.io/judy-overview/`.

Public overview repository: [sohitqwer-del/judy-overview](https://github.com/sohitqwer-del/judy-overview).

## Files

- `index.html` — semantic page content and an original, labelled SVG schematic.
- `styles.css` — responsive layout, system fonts, keyboard focus states, reduced-motion support, and print styles.
- `favicon.svg` — original JUDY icon.
- `.nojekyll` — serves this directory as plain static files on GitHub Pages.
- `README.md` — this overview and maintenance notes.

There is no build step. Open `index.html` in a browser. All local asset references are relative, including under the intended GitHub Pages project path. No JavaScript, dependencies, CDNs, analytics, forms, uploads, backend, or external image services are used.

## Public scope

Only this overview and its static assets belong in the public repository. JUDY's research code, models, and data remain private. The schematic is an illustration, not real model output. The public page contains no research photos, datasets, model files, checkpoints, private repository links, local filesystem paths, garment identifiers, server details, or institution names.

The two outbound page links lead to the public GitHub profile and this overview repository. No research downloads are provided.

## Reading the results

- YOLOv8-small, YOLO11-nano, and YOLO26-nano were trained for 60 epochs each: 180 total.
- Training used 38 real photos plus 76 appearance variants. Variants are not independent examples.
- Development used 10 photos from 2 garments.
- The repeated historical test used 12 photos from 3 garments, with 81 measurements computable from labels. It is not fresh independent validation.

| Measure | Current profile | YOLO26 candidate |
| --- | ---: | ---: |
| Returned | 48 / 81 | 61 / 81 |
| Within 5% error | 22 | 36 |
| Over 5% error | 26 | 25 |
| Missing | 33 | 20 |
| Coverage | 59.3% | 75.3% |
| Median error | 5.42% | 3.77% |
| 90th-percentile error | 15.14% | 21.14% |

Coverage uses all 81 label-computable measurements. Error summaries describe returned measurements; the profiles return different sets. Scores compare annotations and pixel geometry, not verified physical measurements in millimetres. Small sample size, repeated testing, and known label issues limit interpretation.

YOLO26 is the most promising new candidate. Defaults remain unchanged, and human review is required. This is not a system for automatic production grading.

## Maintenance

Keep the full comparison and its caveats together when updating the page. Do not describe coverage as accuracy, count appearance variants as independent photos, or imply physical validation. Check navigation anchors, relative asset paths, keyboard focus, narrow-screen layouts, and the outbound-link allowlist after edits. Publish only the five files listed above.
