# NORT-QC-tools
 
To install: 

`git clone https://github.com/m-crown/NORT-QC-tools.git
cd NORT-QC-tools
conda env create -f environment.yml
conda activate NORT-QC-tools
cp plate_qc $CONDA_PREFIX/bin`

To run:

`conda activate NORT-QC-tools
plate_qc sample_sheet.csv qc.csv experiment_name`

Example CLI outputs:

**Non-fatal Sample sheet - QC file mismatches**

WARNING: Sample sheet and QC file merged, the following IDs were not matched and will be marked as failed to sequence if NORT IDs (is this correct?):

index       | sample_name | COG-UK_identifier | merged 
----------- | ----------- | ----------------- | ---------
1534        | NaN         | BLANK-8           | right_only
1535        | NaN         | NORT-ABCDEF       | right_only

**NEG STATS**

index       | RNA plate         | sample_name | num_aligned_reads 
----------- | ----------------- | ----------- | ---------
1529        | SOURCE_PLATE_ID_1 | NEG-1234    | 5.0

**POS STATS**

index       | RNA plate         | sample_name | num_aligned_reads 
----------- | ----------------- | ----------- | ---------
1529        | SOURCE_PLATE_ID_1 | POS-1234    | 240704

**Blank Stats**

index       | RNA plate         | sample_name | num_aligned_reads 
----------- | ----------------- | ----------- | ---------
1529        | SOURCE_PLATE_ID_1 | BLANK-8     | 0.0

**PLATE PASS FAIL STATS**

index | RNA plate         | QC      | # Samples 
----- | ----------------- | ------- | --------
0     | SOURCE_PLATE_ID_1 | QC Fail | 10
1     | SOURCE_PLATE_ID_1 | QC Pass | 83

**Fatal Sample sheet - QC file mismatches**

FATAL: Merging failed, the following QC sample_ids could not be matched to IDs in the sample sheet (sample_id from QC, COG-UK_identifier from sample sheet, merge = left_only is only in QC):

index       | sample_name | COG-UK_identifier | merged 
----------- | ----------- | ----------------- | ---------
1534        | NaN         | BLANK-8           | right_only
1535        | NaN         | NORT-ABCDEF       | right_only
