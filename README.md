# PD-vs-MS

`LNG + QMUL ❤️ Open Science 😍`

 - **Project:** Is there genetic overlap between MS and PD?
 - **Author(s):** Cornelis B., Ben J.
 - **Date Last Updated:** December 2020

---
### Quick Description: 
PD and MS are two brain disorders with both a potential immunesystem component, here we assess whether there is genetic overlap.

### Motivation/Goals:
1) Perform a genome-wide comparison between PD and MS sumstats...
2) Perform a localized comparison between PD and MS GWAS regions...
3) ...

### Background:
TBD

### Link to Manuscript:
TBD

## Structure of README:
### Perform a genome-wide comparison between PD and MS sumstats...
LDSCORE
### Perform a localized comparison between PD and MS GWAS regions...
Bedtools overlap





## Perform a localized comparison between PD and MS GWAS regions...
```
Taking sumstats from here https://pubmed.ncbi.nlm.nih.gov/31604244/
Using Sup Table 7 (only autosomals) => 197 signals
Using PD GWAS hits from GWAS browser => Nalls et al 2019 https://pdgenetics.shinyapps.io/GWASBrowser/

cd /data/CARD/projects/MS_PD/
module load bedtools

cut -f 1-3 MS_GWAS.bed > MS_short.bed #plus remove header
cut -f 1-3 PD_GWAS.bed > PD_short.bed #plus remove header

bedtools window -w 500000 -a MS_short.bed -b PD_short.bed 
```

```
MS-SIDE                             | PD SIDE                                | Distance (MS-PD)
1 154983036 154983036 > ZBTB7B area | 1 154898185 154898185 > GBA area       | 84851
1 154983036 154983036 > ZBTB7B area | 1 155135036 155135036 > GBA area       | -152000
1 154983036 154983036 > ZBTB7B area | 1 155205634 155205634 > GBA area       | -222598
3 18798848 18798848 > SATB1 area    | 3 18361759 18361759 => SATB1 area      | 437089
3 121765368 121765368 > CD86        | 3 122196892 122196892 => KPNA1 area    | -431524
3 121783015 121783015 > CD86        | 3 122196892 122196892 => KPNA1 area    | -413877
5 133891282 133891282 > JADE2       | 5 134199105 134199105 => C5orf24 area  | -307823
12 123604053 123604053 > PITPNM2    | 12 123326598 123326598 => HIP1R area   | 277455
14 88523488 88523488 > LINC01146    | 14 88464264 88464264 => GALC area      | 59224
17 40529835 40529835 > STAT3        | 17 40741013 40741013 => RETREG3 area   | -211178
17 43407670 43407670 > MAP3K14      | 17 43744203 43744203 => MAPT area      | -336533
17 43407670 43407670 > MAP3K14      | 17 43798308 43798308 => MAPT area      | -390638

```
```
# LD link comparison MS + PD => R2 = XX D' = XX
--chr 1 region ZBTB7B:
rs112344141 + rs114138760	=> R2 = 0.0006 D' = 0.0454
rs112344141 + rs35749011	=> R2 = 0.0009 D' = 1.0 # warning low freq variant
rs112344141 + rs76763715	=> R2 = 0.0001 D' = 1.0 # warning low freq variant
--chr 3 region SATB1 :
rs9863496 + rs73038319	=> R2 = 0.0154 D' = 0.3911
--chr 3 region CD86 :
rs200866143 + rs55961674	=> R2 = XX D' = XX # rs200866143 not in 1K genomes
rs75937181 + rs55961674	=> R2 = 0.002 D' = 0.0634
--chr 5 region JADE2 :
rs2084007 + rs11950533	=> R2 = 0.1159 D' = 0.8675
--chr 12 region PITPNM2 :
rs7975763 + rs10847864	=> R2 = 0.0294 D' = 0.4562
--chr 14 region LINC01146 :
rs116899835 + rs979812	=> R2 = 0.0669 D' = 0.9654
--chr 17 region STAT3 :
rs1026916 + rs12951632	=> R2 = 0.0849 D' = 0.3681
--chr 17 region MAP3K14 :
rs7222450 + rs62053943	=> R2 = 0.0011 D' = 0.0777
rs7222450 + rs117615688	=> R2 = 0.0142 D' = 0.4597
# nothing really convincing to be honest....

```

### Comparison of the GALC signals MS vs PD


![alt text](https://github.com/neurogenetics/PD-vs-MS/blob/main/MS_PD_GALC.jpg)



