# 3D Density Inversion Using Gravity and Gravity-Gradient Tensor Data

**Research code for the study:** *3D Density Inversion of Gravity and Gravity Gradient Tensor Data: Application to the Wathlingen Salt Dome, Northwest German Basin*

**Authors:** Rahul Maurya and Chandra Prakash Dubey  
**Affiliation:** Department of Geology and Geophysics, Indian Institute of Technology Kharagpur, Kharagpur, West Bengal 721302, India  
**Corresponding author:** Chandra Prakash Dubey — [p.dubey48@gmail.com](mailto:p.dubey48@gmail.com)

---

## Overview

This repository contains Jupyter notebooks and supporting data files for three-dimensional (3D) subsurface density-inversion experiments using gravity and gravity-gradient tensor observations. It brings together two computational approaches:

1. **Adaptive Conjugate Gradient Least-Squares Regularization (ACGLSR)**
2. **Convolutional Neural Network (CNN)**

The experiments are arranged around synthetic single-prism and two-prism models. The ACGLSR collection also includes real-data inversion workflows. The repository contains component-wise inversion notebooks, notebooks for generating synthetic models and observations, kernel-matrix generation notebooks for the CNN experiments, convergence-analysis notebooks, and supporting profile/convergence spreadsheets.

The repository is organized as research code rather than as a single command-line application. Individual experiments are run from their corresponding Jupyter notebooks.

## Research scope

The notebooks and supporting files cover the following work:

- 3D density inversion using gravity and gravity-gradient tensor components.
- Synthetic experiments based on single-prism and two-prism models.
- Component-wise inversion workflows for the available observation components.
- ACGLSR synthetic-model experiments and real-data inversion workflows.
- CNN synthetic-model generation, observation/data generation, kernel-matrix generation, and component-wise inversion.
- Convergence-curve analysis using the supplied spreadsheet files.

The real-data ACGLSR notebooks are grouped under `ACGLSR_Method/Real_data_Inversion/`. The existing project title identifies the Wathlingen Salt Dome, Northwest German Basin, as the application area. Consult the relevant notebook and data documentation for the exact input data, processing choices, parameter values, and interpretation associated with each experiment.

## Methods and experiment groups

### 1. ACGLSR

The `ACGLSR_Method/` directory contains three experiment groups.

| Experiment group | Location | Contents |
|---|---|---|
| Single-prism synthetic model | `ACGLSR_Method/Single_Prism_Model/` | Component-wise inversion notebooks, XZ/YZ profile spreadsheets, and combined convergence analysis |
| Two-prism synthetic model | `ACGLSR_Method/Two_Prism_Model/` | Component-wise inversion notebooks, XZ/YZ profile spreadsheets, and combined convergence analysis |
| Real-data inversion | `ACGLSR_Method/Real_data_Inversion/` | Real-data inversion notebooks, `Fulldata.csv`, profile spreadsheets, and combined convergence analysis |

The synthetic single-prism and two-prism groups contain inversion notebooks for `Gz`, `Txx`, `Txy`, `Txz`/`Tzx`, `Tyy`, `Tyz`/`Tzy`, and `Tzz`. Their combined-convergence directories contain a notebook and component-specific Excel files.

The real-data group contains notebooks for `Gz`, `Txy`, `Tzx`, and `Tzy`, as well as a notebook for combined convergence analysis. The supplied tree also includes east–west and north–south profile spreadsheets.

### 2. CNN

The `CNN_Method/` directory contains synthetic single-prism and two-prism workflows.

| Experiment group | Location | Contents |
|---|---|---|
| Single-prism synthetic model | `CNN_Method/Single_Prism_Model/` | Density-model generation, component-wise data and kernel generation, component-wise CNN inversion, profile spreadsheets, and combined convergence analysis |
| Two-prism synthetic model | `CNN_Method/Two_Prism_Model/` | Two-prism model generation, component-wise data generation and inversion, profile spreadsheets, and combined convergence analysis |

For the single-prism experiment, `Generate_single_prism_density_model.ipynb` is the model-generation notebook. The component directories (`gz_inv`, `txx_inv`, `txy_inv`, `txz_inv`, `tyy_inv`, `tyz_inv`, and `tzz_inv`) contain the notebooks for the corresponding data-generation, kernel-generation, and/or inversion steps. The `combined_convergence_curve/` directory contains the combined convergence notebook and component-specific spreadsheets.

For the two-prism experiment, `generate_two_prism_model.ipynb` generates the model inputs. The component directories contain data-generation and inversion notebooks, and `Convergence_Curve_Combined_all_Components/` contains the combined convergence-analysis notebook and spreadsheets.

## Gravity and gravity-gradient components

The synthetic-model workflows include the following components:

| Symbol used in this README | Description |
|---|---|
| \(G_z\) | Vertical component of gravitational acceleration |
| \(T_{xx}\) | \(x x\) component of the gravity-gradient tensor |
| \(T_{xy}\) | \(x y\) component of the gravity-gradient tensor |
| \(T_{xz}\) | \(x z\) component of the gravity-gradient tensor |
| \(T_{yy}\) | \(y y\) component of the gravity-gradient tensor |
| \(T_{yz}\) | \(y z\) component of the gravity-gradient tensor |
| \(T_{zz}\) | \(z z\) component of the gravity-gradient tensor |

Some filenames use `tzx` and `tzy` where the corresponding component is written as `txz` and `tyz` in other folders. Preserve the filenames when navigating the repository; check the notebook contents for the exact component and variable convention used by that workflow.

The supplied real-data ACGLSR directory contains workflows for \(G_z\), \(T_{xy}\), \(T_{zx}\), and \(T_{zy}\).

## Repository structure

The following tree summarizes the principal folders and notebook groups. Supporting `.xlsx`, `.csv`, `.dat`, and `.zip` files are stored alongside the notebooks that use them.

```text
Gravity-Gradient-Inversion/
├── README.md
├── ACGLSR_Method/
│   ├── Real_data_Inversion/
│   │   ├── Fulldata.csv
│   │   ├── Real_gz_Inv/
│   │   ├── Real_txy_Inv/
│   │   ├── Real_tzx_Inv/
│   │   ├── Real_tzy_Inv/
│   │   └── Combined_Convergence_all_components/
│   ├── Single_Prism_Model/
│   │   ├── S_Gz_Inv/
│   │   ├── S_txx_Inv/
│   │   ├── S_txy_Inv/
│   │   ├── S_txz_Inv/
│   │   ├── S_tyy_Inv/
│   │   ├── S_tyz_Inv/
│   │   ├── S_tzz_Inv/
│   │   └── Single_Prism_Combined_Convergence_all_components/
│   └── Two_Prism_Model/
│       ├── Two_P_Gz_Inv/
│       ├── Two_P_txx_Inv/
│       ├── Two_P_txy_Inv/
│       ├── Two_P_txz_Inv/
│       ├── two_P_tyy_Inv/
│       ├── Two_P_tyz_Inv/
│       ├── Two_P_tzz_Inv/
│       └── Two_Prism_Combined_Convergence_all_components/
└── CNN_Method/
    ├── Single_Prism_Model/
    │   ├── Generate_single_prism_density_model.ipynb
    │   ├── model58.dat
    │   ├── model.zip
    │   ├── gz_inv/
    │   ├── txx_inv/
    │   ├── txy_inv/
    │   ├── txz_inv/
    │   ├── tyy_inv/
    │   ├── tyz_inv/
    │   ├── tzz_inv/
    │   └── combined_convergence_curve/
    └── Two_Prism_Model/
        ├── generate_two_prism_model.ipynb
        ├── 1model10.dat
        ├── 2model10.dat
        ├── model.zip
        ├── gz_inv/
        ├── txx_inv/
        ├── txy_inv/
        ├── txz_inv/
        ├── tyy_inv/
        ├── tyz_inv/
        ├── tzz_inv/
        └── Convergence_Curve_Combined_all_Components/
```

## File types

The repository includes the following types of files:

| File type | Role in the supplied repository |
|---|---|
| `.ipynb` | Jupyter notebooks for model generation, data generation, kernel generation, inversion, and convergence analysis |
| `.xlsx` | Component-wise convergence data and XZ/YZ or east–west/north–south profile data |
| `.csv` | Tabular real-data input (`Fulldata.csv`) in the ACGLSR real-data directory |
| `.dat` | Model files used by the synthetic-model workflows |
| `.zip` | Archived model files included in the CNN single-prism and two-prism directories |

The presence of a notebook does not necessarily mean that every external input or intermediate output referenced by that notebook is included. Check the notebook's input paths before running it.

## Software requirements

The notebook sources use Python scientific-computing and plotting packages. The imports found across the supplied notebooks indicate the following packages may be required, depending on the experiment:

- Python
- Jupyter Notebook or JupyterLab
- NumPy
- SciPy
- Matplotlib
- Pandas
- OpenPyXL (for Excel spreadsheet access through Pandas)
- Pillow
- scikit-learn
- seaborn
- h5py
- PyTorch (CNN workflows)
- `torchsummary` (CNN notebooks that import it)

ACGLSR notebooks primarily use NumPy, SciPy, Matplotlib, Pandas, and image/plotting utilities. CNN notebooks additionally use PyTorch and several machine-learning/data utilities. Not every package is required for every notebook.

### Create a Conda environment

For example:

```bash
conda create -n gravity-inversion python=3.10
conda activate gravity-inversion
```

Install the common scientific and notebook packages:

```bash
python -m pip install numpy scipy matplotlib pandas jupyter ipykernel openpyxl pillow
```

For notebooks that use the additional CNN utilities:

```bash
python -m pip install scikit-learn seaborn h5py torchsummary
```

Install PyTorch separately using the official instructions for the operating system and CPU/GPU configuration: [PyTorch — Get Started](https://pytorch.org/get-started/locally/).

These commands provide a starting environment, not a fully pinned or verified environment specification. The uploaded notebooks do not provide one common, repository-wide `requirements.txt` or exact package-version lock file. If a notebook reports a missing package, install the package in the active environment and record the version used for reproducibility.

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/rahul-2002-hub/Gravity-Gradient-Inversion.git
cd Gravity-Gradient-Inversion
```

### 2. Activate the environment

```bash
conda activate gravity-inversion
```

### 3. Start Jupyter

```bash
jupyter notebook
```

Alternatively, use:

```bash
jupyter lab
```

### 4. Open the experiment you want to run

- **ACGLSR — single prism:** `ACGLSR_Method/Single_Prism_Model/`
- **ACGLSR — two prisms:** `ACGLSR_Method/Two_Prism_Model/`
- **ACGLSR — real data:** `ACGLSR_Method/Real_data_Inversion/`
- **CNN — single prism:** `CNN_Method/Single_Prism_Model/`
- **CNN — two prisms:** `CNN_Method/Two_Prism_Model/`

Open the relevant notebook in the corresponding component or convergence-analysis subdirectory.

## Running the notebooks and data-path considerations

1. Start with the model-generation or data-generation notebook when the workflow requires those inputs.
2. Check the notebook's first setup/configuration cells to identify input files, output directories, grid dimensions, and model/data parameters.
3. Run the notebook cells in their intended order.
4. Run the relevant inversion notebook after its required model, observation, and kernel files are available.
5. Run the combined-convergence notebook after the component-wise convergence spreadsheets have been generated or supplied.

**Important portability note:** Inspection of the supplied notebook sources found references to absolute Windows paths (for example, paths under `C:\Users\...`) as well as relative paths such as `./data/...` and `./parameters.pth`. Absolute paths from the original computer will not work unchanged on another computer, Linux workstation, or HPC system. Update those paths to locations on your system, preferably using paths relative to the notebook or repository root.

Some notebooks also refer to generated files such as kernel matrices, `.mat` observation files, training/validation datasets, saved model parameters, and result archives. These files are not all present in the supplied repository tree. Generate them using the corresponding generation notebooks or provide the required files before running the inversion notebooks.

## Data, outputs, and reproducibility

The repository includes selected model files, spreadsheets, and a real-data CSV alongside the notebooks. The notebooks may create additional intermediate products, including synthetic observations, kernel matrices, training/validation data, trained model parameters, inversion outputs, and figures.

For a reproducible experiment, record:

- The notebook and experiment directory used.
- The input model and observation files.
- The gravity/tensor component and its data convention.
- Grid dimensions, cell spacing, observation geometry, and model parameters.
- Training/validation settings and random seeds for CNN experiments, where applicable.
- ACGLSR inversion and regularization settings, where applicable.
- Python and package versions, hardware, and whether CPU or GPU execution was used.
- The generated outputs and any post-processing steps.

Do not assume that an output file is included simply because a notebook refers to it. Verify the required inputs and generated outputs for each experiment.

## Data availability and use

The repository contains the files that were included in the uploaded ACGLSR and CNN project directories. The availability of any additional field observations, kernel matrices, trained weights, or intermediate datasets should be checked in the relevant notebook and project directory.

Before redistributing field data or other third-party material, confirm that you have permission to share it. No claim is made here that every external dataset or intermediate file referenced by the notebooks is included.

## Citation

If you use this code in academic work, please cite the associated research publication when its bibliographic details are available. The project title and author information currently supplied with this repository are listed at the top of this README.

## Contact

For questions about the research code, contact:

**Rahul Maurya**  
Department of Geology and Geophysics  
Indian Institute of Technology Kharagpur  
Kharagpur, West Bengal 721302, India

For correspondence identified in the project information:

**Chandra Prakash Dubey** — [p.dubey48@gmail.com](mailto:p.dubey48@gmail.com)

---

## Notes for users

- Folder and notebook names are retained as they appear in the repository; some names use abbreviations or legacy spelling.
- Run each workflow from a directory in which its relative input/output paths resolve, or update those paths before execution.
- The notebooks are research workflows and may require experiment-specific inputs and parameter adjustments.
