---
layout: default
permalink: /legacy/plot_styles
title: Plot Styles
---
[← Back to start](/legacy)
<!-- markdownlint-disable MD031 MD033 -->
## Plot Styles <!-- omit in toc -->

### Line colors

All plots that are generated in Glotaran has same rules for using line colors and line styles.

The sequence in which colors are used for plots in Glotaran is the following:

| #   | Name      | RGB code        | Hex code | Example                |
| --- | ---       | :-:             | ---      |  :-:                   |
| 1   | BLACK     | (0, 0, 0)       | \#000000 | $\color{#000000}{■■■}$ |
| 2   | RED       | (255, 0, 0)     | \#FF0000 | $\color{#FF0000}{■■■}$ |
| 3   | BLUE      | (0, 0, 255)     | \#0000FF | $\color{#0000FF}{■■■}$ |
| 4   | GREEN     | (0, 255, 0)     | \#00FF00 | $\color{#00FF00}{■■■}$ |
| 5   | MAGENTA   | (255, 0, 255)   | \#FF00FF | $\color{#FF00FF}{■■■}$ |
| 6   | CYAN      | (0, 255, 255)   | \#00FFFF | $\color{#00FFFF}{■■■}$ |
| 7   | YELLOW    | (255, 255, 0)   | \#FFFF00 | $\color{#FFFF00}{■■■}$ |
| 8   | GREEN4    | (0, 139, 0)     | \#008B00 | $\color{#008B00}{■■■}$ |
| 9   | ORANGE    | (255, 140, 0)   | \#FF8C00 | $\color{#FF8C00}{■■■}$ |
| 10  | BROWN     | (150, 75, 0)    | \#964B00 | $\color{#964B00}{■■■}$ |
| 11  | GREY      | (128, 128, 128) | \#808080 | $\color{#808080}{■■■}$ |
| 12  | VIOLET    | (148, 0, 211)   | \#9400D3 | $\color{#9400D3}{■■■}$ |
| 13  | TURQUOISE | (64, 224, 208)  | \#40E0D0 | $\color{#40E0D0}{■■■}$ |
| 14  | MAROON    | (128, 0, 0)     | \#800000 | $\color{#800000}{■■■}$ |
| 15  | INDIGO    | (75, 0, 130)    | \#4B0082 | $\color{#4B0082}{■■■}$ |

It means that the first line in the plot will be BLACK, the second will
be RED, etc. After the INDIGO color it starts again from BLACK.

## Line styles

The sequence in which line styles is used in the plots in Glotaran is the following:

- Solid <!-- "―――" -->
- Dashed <!-- "– – –" -->
- Dotted <!-- ". . ." -->
- Dash-Dot-Dash <!-- "– . –" -->

It means that during analysis comparison the lines that correspond to
first dataset will be drawn with solid lines, second with dotted etc.
After 4 datasets it will again start with solid lines. The order of the
datasets is the same as was used during node selection.
