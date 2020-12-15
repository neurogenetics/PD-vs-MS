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
MS SIDE                                             | PD SIDE  
1	154983036	154983036	>	ZBTB7B area							1	154898185	154898185 > GBA area
1	154983036	154983036	>	ZBTB7B area							1	155135036	155135036 > GBA area
1	154983036	154983036	>	ZBTB7B area							1	155205634	155205634 > GBA area
3	18798848	18798848 > SATB1 area										3	18361759	18361759 => SATB1 area
3	121765368	121765368 > CD86											   3	122196892	122196892 => KPNA1 area
3	121783015	121783015 > CD86											   3	122196892	122196892 => KPNA1 area
5	133891282	133891282 > JADE2											  5	134199105	134199105 => C5orf24 area
12	123604053	123604053 > PITPNM2										12	123326598	123326598 => HIP1R area
14	88523488	88523488 > LINC01146									 14	88464264	88464264 => GALC area
17	40529835	40529835 > STAT3										  	 17	40741013	40741013 => RETREG3 area
17	43407670	43407670 > MAP3K14									 		17	43744203	43744203 => MAPT area
17	43407670	43407670 > MAP3K14											 17	43798308	43798308 => MAPT area
```



