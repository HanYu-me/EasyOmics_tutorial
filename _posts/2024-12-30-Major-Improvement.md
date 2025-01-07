---
title: EasyOmics v1.4.0 Major Improvement of Whole App
type: major
---

This version beautify the layout of EasyOmics, explain the analysis ability of each function, and improve the analysis logic.

The container of EasyOmics is released on Docker Hub yuhan2000/EasyOmics.

**Features:**
- Display feedback for every step’s results on the screen.
- Add a homepage with the main graphic and logical connections between functions, referencing other Shiny software.
- Add a help interface linking to the menu of EasyOmics.
- Add a contact page to the menu of EasyOmics.
- Provide a textual explanation for all inputs and outputs for each function.
- Add generalized mixed linear model, linear regression model, and multi-loci mixed linear model.
- Additional visualization methods for multi-omics WAS.
- Integrate multi-omics QTL with multi-omics visualization.
- Consolidate results of different types of variations + standardize VCF formats.
- Enable customization of analysis parameters.
- Add time suffixes to all outputs.

**Fixes:**
- Modify text size for themes.
- Increase input restriction up to 300GB.
- Set feedback for warnings to red.
- Remove the display of results from the previous analysis.
- Handle parameter residues when switching between functions.
- Files are not removed to avoid long upload times.
- Process long phenotype strings for trait names.
