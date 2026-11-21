# COMSOL models for 2D dielectric metamaterial plates


This repository contains 22 MATLAB scripts for the COMSOL models that support Figures 2–12 of the manuscript *Flexural wave manipulation in 2D dielectric metamaterial plates via integrated flexoelectricity and LC circuits* by Zhuangzhuang He, Haoyang Zhao, Xiangyu Li, Weiqiu Chen, and Chunli Zhang.

## Requirements

- **MATLAB** runs the export scripts. All 22 scripts were tested on Windows with MATLAB R2026b.
- **COMSOL Multiphysics 6.4** opens the exported MPH files. Scripts that export models with **COMSOL batch tools** also require a licensed 64-bit Windows installation of COMSOL with `comsolcompile.exe` and `comsolbatch.exe`. The tested COMSOL build was 6.4.0.429.
- Scripts with an **embedded MPH model** use MATLAB alone for the export step. Each script contains the model data needed for export.

## Export a model

1. Open the desired `.m` file in MATLAB and click **Run**. To run it from the MATLAB Command Window, set the current folder to the folder containing this README and use a command such as

   ```matlab
   run(fullfile('Figure_12', 'Fig12c_Line_Defect_Wave_Guiding.m'))
   ```

2. The script writes `Fig12c_Line_Defect_Wave_Guiding.mph` next to the example script. Each script uses its corresponding model's original filename. Rerunning a script replaces an existing MPH file of the same name in that folder.
3. Open the exported file in COMSOL. To regenerate field plots, mode shapes, or other quantities based on a solution dataset, compute the corresponding study in COMSOL.

If a script reports that COMSOL cannot be found, point `COMSOL_ROOT` to the installation directory that contains `bin/win64`. For example, run the following in MATLAB before running that script.

```matlab
setenv('COMSOL_ROOT', 'C:\Program Files\COMSOL\COMSOL64\Multiphysics')
```

## What the MPH files contain

The scripts export unsolved models with compacted histories. The MPH files retain the geometry, mesh, physics, study and sweep settings, and plot definitions. Stored result tables are retained where present.
