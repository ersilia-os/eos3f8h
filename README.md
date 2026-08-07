# eu-openscreen-hts

High throughput screening of the EU OpenScreen library (~100.000 compounds) against 7 pathogens of reference (A. baumannii, C. albicans, E. coli, E. faecalis, K. pneumoniae, P. aeruginosa, S. aureus). Assays were obtained from the European Chemical Biology Database and correspond to single point inhibitions with cut-offs ranging from 50 to 70% and incubation concentrations between 41.7 to 50 uM. Models were trained by Ersilia using LazyQSAR v3, achieving a mean AUROC of 0.94 (range 0.84-0.99) upon 5-fold crossvalidation.



## Information
### Identifiers
- **Ersilia Identifier:** `eos3f8h`
- **Slug:** `eu-openscreen-hts`

### Domain
- **Task:** `Annotation`
- **Subtask:** `Activity prediction`
- **Biomedical Area:** `Antimicrobial resistance`, `Candidiasis`, `Fungal infections`
- **Target Organism:** `Acinetobacter baumannii`, `Candida albicans`, `Escherichia coli`, `Enterococcus faecalis`, `Klebsiella pneumoniae`, `Pseudomonas aeruginosa`, `Staphylococcus aureus`
- **Tags:** `Antimicrobial activity`, `Antifungal activity`, `ESKAPE`, `Gram-negative bacteria`, `Gram-positive bacteria`, `Fungi`

### Input
- **Input:** `Compound`
- **Input Dimension:** `1`

### Output
- **Output Dimension:** `7`
- **Output Consistency:** `Fixed`
- **Interpretation:** Rank score per pathogen between 0 and 1; higher values indicate greater predicted probability of growth inhibition.

Below are the **Output Columns** of the model:
| Name | Type | Direction | Description |
|------|------|-----------|-------------|
| abaumannii | float | high | LazyQSAR rank score for growth inhibition of Acinetobacter baumannii in EU OpenScreen primary screen EOS300185 (60% growth inhibition at 41.7 uM; 57 actives of 101023 compounds; 5-fold CV AUROC 0.977; recommended threshold 0.932) |
| calbicans | float | high | LazyQSAR rank score for growth inhibition of Candida albicans in EU OpenScreen primary screen EOS300076 (70% growth inhibition at 50 uM; 171 actives of 100943 compounds; 5-fold CV AUROC 0.958; recommended threshold 0.906) |
| ecoli | float | high | LazyQSAR rank score for growth inhibition of Escherichia coli in EU OpenScreen primary screen EOS300158 (50% growth inhibition at 50 uM; 78 actives of 101022 compounds; 5-fold CV AUROC 0.897; recommended threshold 0.909) |
| efaecalis | float | high | LazyQSAR rank score for growth inhibition of Enterococcus faecalis in EU OpenScreen primary screen EOS300080 (70% growth inhibition at 50 uM; 125 actives of 100991 compounds; 5-fold CV AUROC 0.979; recommended threshold 0.936) |
| kpneumoniae | float | high | LazyQSAR rank score for growth inhibition of Klebsiella pneumoniae in EU OpenScreen primary screen EOS300180 (50% growth inhibition at 41.7 uM; 139 actives of 101023 compounds; 5-fold CV AUROC 0.841; recommended threshold 0.897) |
| paeruginosa | float | high | LazyQSAR rank score for growth inhibition of Pseudomonas aeruginosa in EU OpenScreen primary screen EOS300155 (50% growth inhibition at 41.7 uM; 14 actives of 101022 compounds; 5-fold CV AUROC 0.985 - based on only 14 actives so the AUROC carries very large variance; recommended threshold 0.933) |
| saureus | float | high | LazyQSAR rank score for growth inhibition of Staphylococcus aureus in EU OpenScreen primary screen EOS300078 (70% growth inhibition at 50 uM; 378 actives of 100780 compounds; 5-fold CV AUROC 0.959; recommended threshold 0.889) |


### Source and Deployment
- **Source:** `Local`
- **Source Type:** `Internal`

### Resource Consumption


### References
- **Source Code**: [https://github.com/ersilia-os/eu-openscreen-antimicrobial-tasks](https://github.com/ersilia-os/eu-openscreen-antimicrobial-tasks)
- **Publication**: [https://doi.org/10.1093/nar/gkae904](https://doi.org/10.1093/nar/gkae904)
- **Publication Type:** `Peer reviewed`
- **Publication Year:** `2024`
- **Ersilia Contributor:** [GemmaTuron](https://github.com/GemmaTuron)

### License
This package is licensed under a [GPL-3.0](https://github.com/ersilia-os/ersilia/blob/master/LICENSE) license. The model contained within this package is licensed under a [GPL-3.0-or-later](LICENSE) license.

**Notice**: Ersilia grants access to models _as is_, directly from the original authors, please refer to the original code repository and/or publication if you use the model in your research.


## Use
To use this model locally, you need to have the [Ersilia CLI](https://github.com/ersilia-os/ersilia) installed.
The model can be **fetched** using the following command:
```bash
# fetch model from the Ersilia Model Hub
ersilia fetch eos3f8h
```
Then, you can **serve**, **run** and **close** the model as follows:
```bash
# serve the model
ersilia serve eos3f8h
# generate an example file
ersilia example -n 3 -f my_input.csv
# run the model
ersilia run -i my_input.csv -o my_output.csv
# close the model
ersilia close
```

## About Ersilia
The [Ersilia Open Source Initiative](https://ersilia.io) is a tech non-profit organization fueling sustainable research in the Global South.
Please [cite](https://github.com/ersilia-os/ersilia/blob/master/CITATION.cff) the Ersilia Model Hub if you've found this model to be useful. Always [let us know](https://github.com/ersilia-os/ersilia/issues) if you experience any issues while trying to run it.
If you want to contribute to our mission, consider [donating](https://www.ersilia.io/donate) to Ersilia!
