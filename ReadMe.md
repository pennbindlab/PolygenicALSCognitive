This repository contains the code necessary to reproduce analyses from
Placek et al. (2020) "Machine learning suggests polygenic risk for
cognitive dysfunction in amyotrophic lateral sclerosis" available
[here](https://www.medrxiv.org/content/10.1101/2019.12.23.19014407v3) on
medRXiv.

#### Data Availability

Associated datasets used in the code can be obtained as follows:

-   Clinical Research in ALS and Related Disorders for Therapeutic
    Development (CReATe) Consortium Phenotype-Genotype Biomarker (PGB)
    Study

    The CReATe PGB Study data will be deposited at the NIH-supported
    Data Management and Coordinating Center (DMCC) and the Database of
    Genotypes and Phenotypes (dbGaP) using procedures outlined by the
    Rare Disease Clinical Research Network (RDCRN) of the National
    Institutes of Health (NIH). As detailed in the patient consent
    process “Only researchers with an approved study may be able to see
    and use your information…Only de-identified data, which does not
    include anything that might directly identify you, will be shared
    with study investigators and approved investigators from the general
    scientific community for research purposes.” If you would like to
    access this data, please contact the CReATe Consortium at
    <ProjectCReATe@miami.edu> for a data request form.

-   University of Pennsylvania Biobank Neuroimaging Cohort

    De-identified raw T1-weighted MRI and voxelwise cortical thickness
    images will be made available to reseachers through an approved
    request pending review by the Penn Neurodegenerative Data Sharing
    Committee. To request access please complete the following online
    data request form: <https://www.pennbindlab.com/data-sharing>.

-   University of Pennsylvania Biobank Autopsy Cohort

    Neuropathological data and associated data fields have been
    deposited along with associated statistical code in this repository.

#### 1\_CReATe\_data\_cleaning.Rmd

Contains code used to:

-   Clean data fields and define final patient cohort from the CReATe
    Phenotype-Genotype Biomarker study (*Table 1*)

-   Run linear-mixed effects to derive adjusted estimates of baseline
    performance and longitudinal rate on clinical measures

-   Visualize longitudinal performance on clinical measures and genotype
    variation at selected single nucleotide polymorphisms (SNPs)
    (*Figure 1, Appendix Figure S1*)

#### 2\_CReATe\_sCCA.Rmd

Contains code used to:

-   Run all sCCA analyses, including:

    -   Gridsearch for sCCA parameters (*Figure EV1*)

    -   Run bootstrap sCCA analyses using the full CReATe PGB study
        cohort and define weights for the weighted polygenic risk score
        (wPRS) (*Figure EV2, Appendix Figure S2, Figure EV3, Figure 2*)

    -   Run bootstrap sCCA analyses excluding individuals with
        ALS-related disorders (i.e. PLS, PMA) (*Appendix Figure S3*)

    -   Run bootstrap sCCA analyses excluding SNPs in high linkage
        disequilibrium (LD) and define weights for a polygenic risk
        score excluding high LD SNPs (noLD\_wPRS)

#### 3\_CReATe\_PRS.Rmd

Contains code used to:

-   Calculate the wPRS and unweighted PRS (uPRS) for each individual in
    the CReATe PGB study cohort

-   Plot the wPRS which was derived using all SNPs relative to
    noLD\_wPRS which was derived excluding high LD SNPs (*Appendix
    Figure S4*)

-   Conduct Spearman rank-order correlations between the wPRS and
    adjusted esimates of baseline performance and longitudinal rate on
    clinical measures (*Figure 3*)

-   Run linear mixed-effects models to investigate fixed effects of each
    SNP on each clinical variable (*Figure EV4*)

#### 4\_UPenn\_Pathology\_PRS.Rmd

Contains code used to:

-   Clean data fields and define characteristics for patient cohort
    (*Table 2B*)

-   Calculate the wPRS and uPRS for each individual in the UPenn
    Biomarker pathology cohort

-   Run ordinal logistic regression to investigate the wPRS and uPRS in
    each sampled brain region for relationship to neuron loss and TDP-43
    burden (*Figure 4B, Figure EV5, Appendix Figure S6*)
