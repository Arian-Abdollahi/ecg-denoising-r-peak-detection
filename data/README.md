# ECG data setup

Dataset source: https://www.kaggle.com/datasets/protobioengineering/mit-bih-arrhythmia-database-modern-2023/data

Download it through your own Kaggle account and observe the dataset's access and reuse terms. Keep credentials outside this repository. Extract the signal CSVs directly into `data/mit-bih-arrhythmia-database-modern-2023/`, or set the `ECG_DATA_DIR` environment variable to their directory before starting Jupyter.

The loader sorts filenames and accepts only CSVs with an `MLII` column. Each accepted record is trimmed or padded to 650,000 samples. The saved run used 46 accepted records and one augmentation per record, producing 92 interleaved columns: original 0, augmentation 0, original 1, augmentation 1, and so on.

`patient_split.json` stores column indices in that expanded matrix. It contains 60 training columns, 8 validation columns, and 8 test columns. With source group `column_index // 2`, there are 30/8/8 disjoint record groups. Only one version of each validation/test record is selected. The remaining augmented columns are unused.

Do not reinterpret these indices as filenames, verified patient identifiers, or indices into the unaugmented 46-column matrix. If the dataset version, filenames, filtering, or augmentation count changes, rebuild the split using explicit record identities. Raw signals are intentionally excluded from Git.
