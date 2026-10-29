# PeptideScouter Peptide Price Index

Monthly aggregate price statistics for research peptides, published with each
issue of the [PeptideScouter](https://peptidescouter.com) Peptide Price Index.
A new pair of files is added every month, starting with August 2026.

- Series page, with every issue's report and DOI: https://peptidescouter.com/data/price-index
- Method and known limits: https://peptidescouter.com/methodology
- DOI (resolves to the newest issue): https://doi.org/10.5281/zenodo.22262438

## Files

- `<YYYY-MM>-summary.csv` - headline figures for the issue, in long format
- `<YYYY-MM>-compounds.csv` - one row per compound in the closing window
- [README.txt](README.txt) - definitions for every column and metric

These are aggregates only. No file carries vendor names, vendor prices or
per-listing rows. Each file is byte-identical to the copy on
peptidescouter.com and on Zenodo.

Before comparing two issues, read "Reading across issues" in README.txt. Raw
levels and raw spreads are not comparable from month to month.

## Citation

PeptideScouter Peptide Price Index, <Month YYYY> issue, peptidescouter.com,
figures as of the last day of the covered month.
https://doi.org/10.5281/zenodo.22262438

To cite a single issue, use its version DOI from the series page.

## License

[CC BY 4.0](LICENSE). Attribution: PeptideScouter (https://peptidescouter.com).
