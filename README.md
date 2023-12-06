# TRR289 A03

## ℹ️ Information
*This repository is the Github sibling of the corresponding [DataLad](https://www.datalad.org/) dataset, i.e. it **does not** contain the data itself.*
The GitHub sibling, nevertheless, provides insights into the general data structure (directory tree, filenames) and serves as a starting point to download, share and discuss the dataset.
 Data is in BIDS format and may include behavioral, questionnaire and derivative data, too.
Data is stored in a special S3 remote provided by [Coscine](https://coscine.rwth-aachen.de/) and can't be downloaded without the dataset specific secret token.
Token is available at project Z03 for members of TRR289 and collaborators upon reasonable request.

See `dataset_description.json` for project related meta-data.

## ⬇️ How to download dataset

#### 1. Install it with DataLad based on the github handle
This does not download the actual data, only the gin-annex "skeleton".
```bash
datalad install -s git@github.com:pni-data/<dataset_name>.git <dataset_name>
```
#### 2. Set up the security token to access the actual data
Token is available at project Z03 for members of TRR289 and collaborators upon reasonable request.
```bash
export AWS_ACCESS_KEY_ID="XXXXX-XXXX-XXXX-XXXX-XXXX"
export AWS_SECRET_ACCESS_KEY="XXXXXXXX"
```

#### 2. Change to the dataset directory and download the file(s) you want
You can selectively download what you need (e.g. derivatives only).
```bash
cd <dataset_name>
datalad get <path/to/file*>
```


See our [documentation](https://github.com/pni-data/.github/blob/master/profile/README.md) for more detail.

Comments added by the SFB289 Z03 project coordinators
====================================================================

General Comments
--------------------------------------------------------------------
ToDo:
description of the dataset,ilncuding n, link to the openly available SFB proposal/some publication
eg: This dataset was acquired by the team of the SFB289 xx project. It includes yy subjects and the common sequences within the SFB289 project, namely a high resolution T1w, resting state fMRI, 133 direction multi shell DWI, and 2 fieldmaps for the functional data (one reversed phase encoding direction, one Siemens deafult fieldmap sequnce) and one fieldmap for the DWI (reversed field encoding direction). An additional reference image of the resting state fMRI is included without multiband factor.

Questionnaires data are also acquired and can be found in the ... fodler.

The proposal can be found here: link

The BIDS conversion was done with heudiconv by the yy project coordinators supported by the Z03 project coordinators.

Defacing
--------------------------------------------------------------------
Defacing was done by the A03 project cooridnator.
SPM was used on all anatomical images to ensure deindentification of subjects.


Known Issues
--------------------------------------------------------------------
subject-335r2r4ju resting state run had to be canceled. It was repeated and all the fmaps before it as well. However, the first run was manually removed and the second (full) run was renamed to minimise the output of the bids-validator. 

--------------------------------------------------------------------
## bids-validator@1.14.0
	[33m1: [WARN] Not all subjects contain the same files. Each subject should contain the same number of files with the same naming unless some files are known to be missing. (code: 38 - INCONSISTENT_SUBJECTS)[39m
		./sub-39q7t9jbz/dwi/sub-39q7t9jbz_run-01_dwi.bval
			This file is missing for subject sub-39q7t9jbz, but is present for at least one other subject.
			Evidence: Subject: sub-39q7t9jbz; Missing file: sub-39q7t9jbz_run-01_dwi.bval
		./sub-39q7t9jbz/dwi/sub-39q7t9jbz_run-01_dwi.bvec
			This file is missing for subject sub-39q7t9jbz, but is present for at least one other subject.
			Evidence: Subject: sub-39q7t9jbz; Missing file: sub-39q7t9jbz_run-01_dwi.bvec
		./sub-39q7t9jbz/dwi/sub-39q7t9jbz_run-01_dwi.json
			This file is missing for subject sub-39q7t9jbz, but is present for at least one other subject.
			Evidence: Subject: sub-39q7t9jbz; Missing file: sub-39q7t9jbz_run-01_dwi.json
		./sub-39q7t9jbz/dwi/sub-39q7t9jbz_run-01_dwi.nii.gz
			This file is missing for subject sub-39q7t9jbz, but is present for at least one other subject.
			Evidence: Subject: sub-39q7t9jbz; Missing file: sub-39q7t9jbz_run-01_dwi.nii.gz

[36m	Please visit https://neurostars.org/search?q=INCONSISTENT_SUBJECTS for existing conversations about this issue.[39m

        [34m[4mSummary:[24m[39m                   [34m[4mAvailable Tasks:[24m[39m                     [34m[4mAvailable Modalities:[39m[24m 
        1095 Files, 12.92GB        rest                                 MRI                   
        52 - Subjects              TODO: full task name for rest                              
        1 - Session                                                                           


[36m	If you have any questions, please post on https://neurostars.org/tags/bids.[39m
