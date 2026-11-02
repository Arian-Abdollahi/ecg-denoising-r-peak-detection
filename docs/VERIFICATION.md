# Packaging verification

Verified on 2026-11-02.

- Parsed all 6 notebook JSON files and 105 code cells; IPython shell commands were omitted only for the syntax check.
- Confirmed project-oriented notebook outputs are cleared and executable hosted paths have been replaced.
- Scanned deliverable files for the known supplied credential value and Telegram token patterns; no matches remain. The credential JSON is excluded.
- Checked local Markdown links and required report/figure paths.
- Rendered and visually inspected the first published report page. The report body is retained after omission of its introductory page.
- Inspected the README's saved result figure visually; figures were extracted from historical notebook outputs.

- Checked NumPy preprocessing on synthetic traces: augmentation shape/interleaving, 50-sample clean/noisy window shape and order, GRU window labels, and equivalent labels in the combined pipeline.
- Verified the split JSON has 60/8/8 expanded columns, mapping to 30/8/8 disjoint source-record groups across all 46 records under the one-augmentation layout.
- Confirmed the three historical notebooks and split JSON are byte-for-byte copies of the supplied files.

Full model training, dependency installation, GPU execution, and external-service integration were not run. The dataset and model weights were absent. Historical results are not newly reproduced benchmarks. Compatibility ranges are not a tested environment lock.
