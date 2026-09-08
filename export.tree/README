# MET: Music-Induced EEG Dataset

## Overview

The MET (Music-Induced EEG Dataset) contains EEG recordings collected from 20 participants during resting-state and music-listening experiments.

Each participant completed:
- One resting-state recording session (`ses-rest`)
- Twenty music-listening sessions (`ses-t01` to `ses-t20`)

Each music session corresponds to a different song. The total recording duration for each song is 130 seconds, including:

- 5 seconds before music onset
- 120 seconds of music playback
- 5 seconds after music offset

EEG signals were originally recorded using a 128-channel EEG system at a sampling rate of 1000 Hz. After preprocessing and channel selection, 66 EEG channels are provided in this dataset.

The dataset follows the Brain Imaging Data Structure (BIDS) specification for EEG recordings.

---

## Repository Structure

Each EEG session contains the following files:

*_eeg.eeg: EEG signal data in BrainVision format. (Unit: µV [microvolts])

*_eeg.vhdr: BrainVision header file containing acquisition parameters.

*_eeg.vmrk: Event marker file.

*_eeg.json: EEG recording metadata.

*_channels.tsv: Information about EEG channels, including channel names and units.

*_events.tsv: Timing information for experimental events.

*_events.json: Description of event variables stored in events.tsv.

*_electrodes.tsv: Spatial coordinates of EEG electrodes.

*_coordsystem.json: Coordinate system used for electrode locations.

*_scans.tsv: List of files acquired during the session.

---

## Sample Code (PTTHON):

```py

from mne_bids import BIDSPath, read_raw_bids

# 1. Set file path and file name
bids_path = BIDSPath(
    subject='01',          # subject index (eg. 01)
    session='t01',          # trial index (eg. t01)
    task='music',
    datatype='eeg',
    root='/Users/kathy/Documents/EEG data/EGI_preprocessed_bids' # directory root path
)

# 2. Load BIDS file
raw_read = read_raw_bids(bids_path=bids_path, extra_params={'preload': True})

# 3. Check Info
print(raw_read.info)

```

---



References
----------
Appelhoff, S., Sanderson, M., Brooks, T., Vliet, M., Quentin, R., Holdgraf, C., Chaumon, M., Mikulan, E., Tavabi, K., Höchenberger, R., Welke, D., Brunner, C., Rockhill, A., Larson, E., Gramfort, A. and Jas, M. (2019). MNE-BIDS: Organizing electrophysiological data into the BIDS format and facilitating their analysis. Journal of Open Source Software 4: (1896). https://doi.org/10.21105/joss.01896

Pernet, C. R., Appelhoff, S., Gorgolewski, K. J., Flandin, G., Phillips, C., Delorme, A., Oostenveld, R. (2019). EEG-BIDS, an extension to the brain imaging data structure for electroencephalography. Scientific Data, 6, 103. https://doi.org/10.1038/s41597-019-0104-8

