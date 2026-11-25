<h1 align="center">BDF to mne/raw</h1>

<p align="center">
  Converts an EEG recording in BioSemi BDF format to an MNE-Python raw FIF file with mne.io.read_raw_bdf.
</p>

<p align="center">
  <a href="https://github.com/brainlife/abcd-spec"><img src="https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg" alt="ABCD Spec v1.1"></a>
  <a href="https://doi.org/10.25663/brainlife.app.635"><img src="https://img.shields.io/badge/Brainlife-brainlife.app.635-blue.svg" alt="Run on brainlife.io"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-see_LICENSE-lightgrey.svg" alt="License"></a>
</p>

## At a glance

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Converts an EEG recording in BioSemi BDF format to an MNE-Python raw FIF file with mne.io.read_raw_bdf.**

Reads the bdf file with MNE-Python and saves it unchanged as raw.fif so that MNE-based MEG/EEG Apps can use it. The BIDS sidecar files (channels, electrodes, events) carried by the input are not used. Use it as the import step for BioSemi EEG data.

| | |
|---|---|
| **Inputs** | `neuro/eeg/bdf` |
| **Outputs** | `neuro/meeg/mne/raw` |
| **Container** | `brainlife/mne:0.23dev` |
| **Resources** | 8 CPUs |
| **Run it** | [doi.org/10.25663/brainlife.app.635](https://doi.org/10.25663/brainlife.app.635) |

#### Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `bdf1` | `neuro/eeg/bdf` | yes | EEG recording in BioSemi BDF format (with optional BIDS sidecars, which are not read). |

#### Outputs

| Output | Datatype | Description |
|---|---|---|
| `out_dir` | `neuro/meeg/mne/raw` | MNE Raw data in FIF format |

<!-- brainlife-app:end -->

## Running the App

### On brainlife.io

Open the App at [doi.org/10.25663/brainlife.app.635](https://doi.org/10.25663/brainlife.app.635), choose `neuro/eeg/bdf` from your project and press **Execute**. The results are saved to your project as `neuro/meeg/mne/raw`.

### Locally

You need [Singularity/Apptainer](https://apptainer.org/) (the App runs in `brainlife/mne:0.23dev`), [`jq`](https://jqlang.github.io/jq/).

1. Clone this repository.
2. Create `config.json` with the paths to your inputs and the parameters:

   ```json
   {
       "bdf": "/path/to/bdf1/bdf",
       "channels": "/path/to/bdf1/channels",
       "electrodes": "/path/to/bdf1/electrodes",
       "coordsystem": "/path/to/bdf1/coordsystem",
       "events": "/path/to/bdf1/events",
       "events_json": "/path/to/bdf1/events_json"
   }
   ```

3. Run `./main`.

## Citing

If you use this App, please cite it, the software it builds on and brainlife.io:

- BDF to mne/raw. brainlife.io App. [doi:10.25663/brainlife.app.635](https://doi.org/10.25663/brainlife.app.635)
- Gramfort A et al. MEG and EEG data analysis with MNE-Python. Frontiers in Neuroscience 7:267 (2013). [doi:10.3389/fnins.2013.00267](https://doi.org/10.3389/fnins.2013.00267)
- Hayashi S, Caron BA, Heinsfeld AS, et al. brainlife.io: a decentralized and open-source cloud platform to support neuroscience research. *Nature Methods* 21:809–813 (2024). [doi:10.1038/s41592-024-02237-2](https://doi.org/10.1038/s41592-024-02237-2)
- Avesani P, McPherson B, Hayashi S, et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. *Scientific Data* 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Authors

- Guiomar Niso, Instituto Cajal, CSIC, Spain

## Funding

[![Wellcome-226486/Z/22/Z](https://img.shields.io/badge/Wellcome-226486%2FZ%2F22%2FZ-purple.svg)](https://wellcome.org/)
[![NIH-NINDS-U24NS140384](https://img.shields.io/badge/NIH_NINDS-U24NS140384-green.svg)](https://reporter.nih.gov/project-details/11261037)
[![NIH-NINDS-UM1NS132207](https://img.shields.io/badge/NIH_NINDS-UM1NS132207-green.svg)](https://reporter.nih.gov/project-details/11411328)
[![NIH-NIBIB-R01EB029272](https://img.shields.io/badge/NIH_NIBIB-R01EB029272-green.svg)](https://reporter.nih.gov/project-details/10262925)
[![NIH-NIBIB-R01EB030896](https://img.shields.io/badge/NIH_NIBIB-R01EB030896-green.svg)](https://reporter.nih.gov/project-details/10428625)
[![NIH-NIMH-R01MH126699](https://img.shields.io/badge/NIH_NIMH-R01MH126699-green.svg)](https://reporter.nih.gov/project-details/10460628)
[![NIH-NIDCD-R01DC020088](https://img.shields.io/badge/NIH_NIDCD-R01DC020088-green.svg)](https://reporter.nih.gov/project-details/11140284)
[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-2203524](https://img.shields.io/badge/NSF_BCS-2203524-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2203524)
[![NSF-IIS-1636893](https://img.shields.io/badge/NSF_IIS-1636893-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-OAC-2148729](https://img.shields.io/badge/NSF_OAC-2148729-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2148729)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NSF-IIS-2148700](https://img.shields.io/badge/NSF_IIS-2148700-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2148700)
[![NSF-OAC-1916518](https://img.shields.io/badge/NSF_OAC-1916518-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1916518)

<sub>brainlife.io, which runs this App, is publicly funded by Wellcome, the U.S. National Institutes of Health and the U.S. National Science Foundation; acknowledging that support helps keep it running.</sub>

## License

See [LICENSE](LICENSE).
