# ReMASC Curated Splits

## About

This repository provides metadata and programs for a redesigned evaluation framework based on the [ReMASC](https://www.isca-archive.org/interspeech_2019/gong19_interspeech.html) corpus, enabling fair comparison across recording devices and independent analysis of individual recording conditions.

> **Note:** The SCIS 2026 version is archived on the [`scis2026` branch](https://github.com/shiotalab-tmu/remasc_curated_splits/tree/scis2026).

## Repository Structure

```
remasc_curated_splits/
├── curated_metadata/          # Cleaned and split metadata
│   ├── README.md              #   Documentation
│   ├── fully_closed/          #   Fully-closed split
│   └── open_keys/             #   Partially-open splits
└── src/                       # Data cleaning & splitting programs
    └── README.md              #   Documentation
```

## Documentation

- [Metadata Documentation](curated_metadata/README.md) — Data cleaning methodology, CSV format, and split details
- [Program Documentation](src/README.md) — How to run data cleaning and splitting programs

## Baseline Results

EER (%) of mch-SSL-AASIST for each split condition. Average values calculated for all subset splits for each recording device and macro average values for all recording devices are shown. The results are reproduced from Table 3 of the [IFIP SEC 2026 paper](#citation), except for the `Original` row, which is quoted from the [APSIPA ASC 2025 paper](#citation).

| Split Type | Unknown Condition | D2 | D3 | D4 | Avg. |
|:-----------|:------------------|-----:|-----:|-----:|-----:|
| Fully-closed | – | 3.66 | 0.47 | 1.17 | 1.77 |
| Partially-open | Recording Env. | 26.37 | 24.51 | 27.50 | 26.13 |
| Partially-open | Playback Device | 11.96 | 2.33 | 15.77 | 10.02 |
| Partially-open | Position (Env1) | 32.56 | 8.99 | 21.10 | 20.88 |
| Partially-open | Position (Env2) | 6.04 | 0.39 | 16.11 | 7.51 |
| Partially-open | Position (Env4) | 13.33 | 5.98 | 16.13 | 11.82 |
| Partially-open | Replay Source Rec. | 7.98 | 2.03 | 8.22 | 6.07 |
| Partially-open | Speaker | 10.39 | 1.41 | 10.74 | 7.52 |
| Original | Speaker | 7.6 | 10.6 | 8.3 | 8.8 |

> **Note on sampling rate**: The IFIP SEC 2026 paper states that all audio was downsampled to 16 kHz. This is an error in the paper. The actual conditions are as follows:
>
> - Fully-closed and partially-open rows: D2 and D3 were trained and evaluated on 44.1 kHz audio, and D4 on 16 kHz audio.
> - `Original` row: all recording devices were trained and evaluated on 16 kHz audio.

## Citation

If you use this evaluation framework, please cite:

```bibtex
@inproceedings{yamaguchi2026remasc,
  author    = {Takuo Yamaguchi and Sayaka Shiota and Naohiro Tawara},
  title     = {Evaluation Framework for Multi-Channel Spoofing Detection Through Redesign of the {ReMASC} Corpus},
  booktitle = {IFIP TC11 International Conference on Information Security and Privacy (IFIP SEC 2026)},
  year      = {2026},
}
```

The mch-SSL-AASIST model used in [Baseline Results](#baseline-results), and the `Original` row quoted there, are from:

```bibtex
@inproceedings{yamaguchi2025mchsslaasist,
  author    = {Takuo Yamaguchi and Sayaka Shiota and Naohiro Tawara},
  title     = {Investigating Self-Supervised Learning-Based Front-End for Multi-Channel Replay Attack Detection},
  booktitle = {Proc. APSIPA ASC},
  pages     = {2098--2103},
  year      = {2025},
}
```

## References

- ReMASC corpus: [IEEE DataPort](https://ieee-dataport.org/open-access/remasc-realistic-replay-attack-corpus-voice-controlled-systems)
- Original paper: [Gong *et al.*, Interspeech 2019](https://www.isca-archive.org/interspeech_2019/gong19_interspeech.html)
