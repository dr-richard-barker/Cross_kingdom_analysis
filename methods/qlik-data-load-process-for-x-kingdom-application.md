# Qlik data load process for X-Kingdom application

The provided text appears to be a load script for a data processing system. The script is defining a series of "Syn" variables that represent different combinations of data fields and metadata to be used in the data processing pipeline. Here is a summary of what the script is doing:

### Data Fields and Metadata

The script defines the following groups of related data fields and metadata:

<table><thead><tr><th width="188">Syn Variable</th><th>Description</th></tr></thead><tbody><tr><td>$Syn 1</td><td>Fraction Expressing w/in Cluster, Fraction Expressing Outside Cluster, Cell markers, Promoter, Cluster</td></tr><tr><td>$Syn 2</td><td>single cells p-value, single cells average difference, Cell markers</td></tr><tr><td>$Syn 3</td><td>single cells p-value, single cells average difference, Fraction Expressing w/in Cluster, Fraction Expressing Outside Cluster, Cell markers, Promoter, Cluster</td></tr><tr><td>$Syn 4</td><td>Arabidopsis Gene stable ID, Cell markers</td></tr><tr><td>$Syn 5</td><td>Arabidopsis Gene stable ID, Fraction Expressing w/in Cluster, Fraction Expressing Outside Cluster, Cell markers, Promoter, Cluster</td></tr><tr><td>$Syn 6</td><td>Arabidopsis Gene stable ID, Fraction Expressing w/in Cluster, Fraction Expressing Outside Cluster, Cell markers, Promoter, Cluster, Average Difference</td></tr><tr><td>$Syn 7</td><td>Arabidopsis Gene stable ID, single cells p-value, single cells average difference, Cell markers</td></tr><tr><td>$Syn 8</td><td>Arabidopsis Gene stable ID, Brachy Gene stable ID, Brapa Gene stable ID, Tom Gene stable ID</td></tr><tr><td>$Syn 9</td><td>Arabidopsis Gene stable ID, Transcription Factor Filter</td></tr><tr><td>$Syn 10</td><td>Arabidopsis Gene stable ID, Short Description, Subgroup</td></tr><tr><td>$Syn 11</td><td>Arabidopsis Gene stable ID, ROS, SALT, METAL, HEAT, Short Description, Subgroup</td></tr><tr><td>$Syn 12</td><td>Arabidopsis Gene stable ID, Arabidopsis Gene Family Filters</td></tr><tr><td>$Syn 13</td><td>Arabidopsis Gene stable ID, Atha-Col-0-HypocotylCC-WT-FLT-Rep1, Atha-Col-0-HypocotylCC-WT-FLT-Rep2, Atha-Col-0-HypocotylCC-WT-FLT-Rep3, Atha-Col-0-HypocotylCC-WT-FLT-Rep4, Atha-Col-0-HypocotylCC-WT-FLT-Rep5, Atha-Col-0-HypocotylCC-WT-GC-Rep1, Atha-Col-0-HypocotylCC-WT-GC-Rep2, Atha-Col-0-HypocotylCC-WT-GC-Rep3, Atha-Col-0-HypocotylCC-WT-GC-Rep4, Atha-Col-0-HypocotylCC-WT-GC-Rep5</td></tr><tr><td>$Syn 14</td><td>Arabidopsis Gene stable ID, Arabidopsis Transcript stable ID</td></tr><tr><td>$Syn 15</td><td>Arabidopsis Gene stable ID, Arabidopsis Transcript stable ID, Gene Type, Description, Other Name(Type), Keywords</td></tr><tr><td>$Syn 16</td><td>Combination of $Syn 14 and $Syn 15</td></tr><tr><td>$Syn 17</td><td>Combination of $Syn 10 and $Syn 11</td></tr><tr><td>$Syn 18</td><td>Combination of $Syn 9 and $Syn 12</td></tr><tr><td>$Syn 19</td><td>Combination of $Syn 2, $Syn 4, and $Syn 7</td></tr><tr><td>$Syn 20</td><td>Combination of $Syn 1, $Syn 4, and $Syn 5</td></tr><tr><td>$Syn 21</td><td>Combination of $Syn 1, $Syn 4, $Syn 5, and $Syn 6</td></tr><tr><td>$Syn 22</td><td>Combination of $Syn 1, $Syn 2, and $Syn 3</td></tr><tr><td>$Syn 23</td><td>Combination of $Syn 1, $Syn 2, $Syn 3, $Syn 4, $Syn 5, and $Syn 7</td></tr><tr><td>$Syn 24</td><td>Combination of $Syn 20 and $Syn 21</td></tr><tr><td>$Syn 25</td><td>Combination of $Syn 19, $Syn 20, $Syn 22, and $Syn 23</td></tr><tr><td>$Syn 26</td><td>Human Gene name, Mitocarta filter</td></tr><tr><td>$Syn 27</td><td>Human Gene name, JAXA5_Pre - Normalized means</td></tr><tr><td>$Syn 28</td><td>Arabidopsis Transcript stable ID, BRIC20_Observed, BRIC20_Mr(expt), BRIC20_Mr(calc), BRIC20_Mass Error (ppm), Modification, BRIC20_S1:114.1 Intensity, BRIC20_S2:116.1 Intensity, BRIC20_S3:118.1 Intensity, BRIC20_GC1:115.1 Intensity, BRIC20_GC2:117.1 Intensity, BRIC20_GC3:119.1 Intensity</td></tr><tr><td>$Syn 29</td><td>Human Gene stable ID, Human Gene stable ID version</td></tr><tr><td>$Syn 30</td><td>Human Gene stable ID, Human Gene stable ID version, Human Transcript stable ID, Human Transcript stable ID version</td></tr><tr><td>$Syn 31</td><td>Mouse Gene stable ID, Human Gene stable ID, DROM Gene stable ID, Worm Gene stable ID, Rat Gene stable ID</td></tr><tr><td>$Syn 32</td><td>Combination of $Syn 29 and $Syn 30</td></tr><tr><td>$Syn 33</td><td>Combination of $Syn 29, $Syn 30, and $Syn 31</td></tr><tr><td>$Syn 34</td><td>Combination of $Syn 32 and $Syn 33</td></tr><tr><td>$Syn 35</td><td>Mouse Gene stable ID, Mmus_C57-6T_LVR_FLT_Rep1_F1, Mmus_C57-6T_LVR_FLT_Rep2_F2</td></tr><tr><td>$Syn 36</td><td>Accession, sample name</td></tr><tr><td>$Syn 37</td><td>Accession, organism</td></tr><tr><td>$Syn 38</td><td>Combination of $Syn 36 and $Syn 37</td></tr></tbody></table>

### Linking Synchronization Steps

The script also defines relationships between the different "Syn" variables, indicating how they are combined to create more comprehensive data sets. For example:

* $Syn 16 = $Syn 14 + $Syn 15
* $Syn 24 = $Syn 20 + $Syn 21
* $Syn 25 = $Syn 19 + $Syn 20 + $Syn 22 + $Syn 23
* $Syn 32 = $Syn 29 + $Syn 30
* $Syn 33 = $Syn 29 + $Syn 30 + $Syn 31
* $Syn 34 = $Syn 32 + $Syn 33

This suggests that the data processing pipeline involves combining different sets of data fields and metadata in a structured way to create more comprehensive data sets for analysis.



The search results contain numerous lines that show the number of lines fetched for various data sources and tables.&#x20;

By summing up all the "Lines fetched:" values, the total comes out to **21,524,524.**



**Kingdom DataLoad summary: June 2022**

**Example data load**

**Started loading data**

**Connected RestConnectorMasterTable << RestConnectorMasterTable**

**Lines fetched: 2,947 \_shards << RestConnectorMasterTable**

**Lines fetched: 1 Study Person << RestConnectorMasterTable**

**Lines fetched: 390 Mission << RestConnectorMasterTable**

**Lines fetched: 390 \_source << RestConnectorMasterTable**

**Lines fetched: 390 all << RestConnectorMasterTable**

**Lines fetched: 994 highlight << RestConnectorMasterTable**

**Lines fetched: 390 hits << RestConnectorMasterTable**

**Lines fetched: 390 hits\_u0 << RestConnectorMasterTable**

**Lines fetched: 1 root << RestConnectorMasterTable**

**Lines fetched: 1 root-1 << Mouse Lines fetched: 999 Human**

**Lines fetched: 999 Sheet1**

**Lines fetched: 999 Sheet1**

**Lines fetched: 65,535 MEM\_All**

**Lines fetched: 2,951 PreservativeRNAdata-Transcriptl**

**Lines fetched: 40,587 Sheet1**

**Lines fetched: 65,535 ?study.factor%20value**

**Lines fetched: 9,818 ?study.factor%20value << ?study.factor%20value**

**Lines fetched: 19,636 ?study.factor%20value << ?study.factor%20value**

**Lines fetched: 29,353 ?study.factor%20value << ?study.factor%20value**

**Lines fetched: 39,171 rep\_species\_accssion\_file**

**Lines fetched: 30,528 GL\_matrix\_SamG**

**Lines fetched: 999 ?study.factor%20value**

**Lines fetched: 9,447 HUMAN-ARATH**

**Lines fetched: 12,779 GLDS-1\_array\_differential\_expression**

**Lines fetched: 12,622 GLDS-3\_array\_differential\_expression**

**Lines fetched: 12,622 GLDS-7\_array\_differential\_expression**

**Lines fetched: 20,149 GLDS-17\_array\_differential\_expression**

**Lines fetched: 20,149 GLDS-34\_array\_differential\_expression**

**Lines fetched: 12,622 GLDS-36\_array\_differential\_expression**

**Lines fetched: 11,504 GLDS-37\_rna\_seq\_differential\_expression**

**Lines fetched: 28,064 GLDS-38\_rna\_seq\_differential\_expression**

**Lines fetched: 27,723 GLDS-46\_array\_differential\_expression**

**Lines fetched: 20,149 GLDS-47\_rna\_seq\_differential\_expression**

**Lines fetched: 20,493 GLDS-48\_rna\_seq\_differential\_expression**

**Lines fetched: 22,196 GLDS-49\_rna\_seq\_differential\_expression**

**Lines fetched: 18,535 GLDS-52\_array\_differential\_expression**

**Lines fetched: 18,763 GLDS-70\_array\_differential\_expression**

**Lines fetched: 12,622 GLDS-71\_array\_differential\_expression**

**Lines fetched: 18,762 GLDS-78\_array\_differential\_expression**

**Lines fetched: 12,321 GLDS-85\_rna\_seq\_differential\_expression**

**Lines fetched: 15,087 GLDS-91\_rna\_seq\_differential\_expression**

**Lines fetched: 16,868 GLDS-98\_rna\_seq\_differential\_expression**

**Lines fetched: 23,264 GLDS-99\_rna\_seq\_differential\_expression**

**Lines fetched: 21,598 GLDS-100\_rna\_seq\_differential\_expression**

**Lines fetched: 26,452 GLDS-101\_rna\_seq\_differential\_expression**

**Lines fetched: 22,591 GLDS-102\_rna\_seq\_differential\_expression**

**Lines fetched: 24,035 GLDS-103\_rna\_seq\_differential\_expression**

**Lines fetched: 22,255 GLDS-104\_rna\_seq\_differential\_expression**

**Lines fetched: 21,778 GLDS-105\_rna\_seq\_differential\_expression**

**Lines fetched: 22,098 GLDS-120\_rna\_seq\_differential\_expression**

**Lines fetched: 24,501 GLDS-121\_array\_differential\_expression**

**Lines fetched: 9,470 GLDS-124\_array\_differential\_expression**

**Lines fetched: 26,229 GLDS-125\_array\_differential\_expression**

**Lines fetched: 19,251 GLDS-127\_rna\_seq\_differential\_expression**

**Lines fetched: 22,378 GLDS-136\_array\_differential\_expression**

**Lines fetched: 20,149 GLDS-137\_rna\_seq\_differential\_expression**

**Lines fetched: 22,228 GLDS-138\_rna\_seq\_differential\_expression**

**Lines fetched: 4,429 GLDS-141\_rna\_seq\_differential\_expression**

**Lines fetched: 18,126 GLDS-147\_array\_differential\_expression**

**Lines fetched: 20,149 GLDS-154\_array\_differential\_expression**

**Lines fetched: 12,317 GLDS-161\_rna\_seq\_differential\_expression**

**Lines fetched: 25,416 GLDS-162\_rna\_seq\_differential\_expression**

**Lines fetched: 28,760 GLDS-163\_rna\_seq\_differential\_expression**

**Lines fetched: 32,074 GLDS-164\_rna\_seq\_differential\_expression**

**Lines fetched: 21,615 GLDS-168\_rna\_seq\_differential\_expression**

**Lines fetched: 30,379 GLDS-173\_rna\_seq\_differential\_expression**

**Lines fetched: 18,432 GLDS-188\_array\_differential\_expression**

**Lines fetched: 23,177 GLDS-194\_rna\_seq\_differential\_expression**

**Lines fetched: 26,234 GLDS-202\_rna\_seq\_differential\_expression**

**Lines fetched: 27,007 GLDS-203\_rna\_seq\_differential\_expression**

**Lines fetched: 28,920 GLDS-205\_array\_differential\_expression**

**Lines fetched: 20,149 GLDS-207\_rna\_seq\_differential\_expression**

**Lines fetched: 13,885 GLDS-208\_rna\_seq\_differential\_expression**

**Lines fetched: 20,664 GLDS-211\_rna\_seq\_differential\_expression**

**Lines fetched: 27,110 GLDS-214\_rna\_seq\_differential\_expression**

**Lines fetched: 20,314 GLDS-217\_rna\_seq\_differential\_expression**

**Lines fetched: 23,251 GLDS-235\_rna\_seq\_differential\_expression**

**Lines fetched: 35,138 GLDS-236\_rna\_seq\_differential\_expression**

**Lines fetched: 26,836 GLDS-237\_rna\_seq\_differential\_expression**

**Lines fetched: 28,262 GLDS-238\_rna\_seq\_differential\_expression**

**Lines fetched: 28,047 GLDS-239\_rna\_seq\_differential\_expression**

**Lines fetched: 28,201 GLDS-240\_rna\_seq\_differential\_expression**

**Lines fetched: 27,634 GLDS-241\_rna\_seq\_differential\_expression**

**Lines fetched: 27,377 GLDS-242\_rna\_seq\_differential\_expression**

**Lines fetched: 22,703 GLDS-243\_rna\_seq\_differential\_expression**

**Lines fetched: 31,732 GLDS-244\_rna\_seq\_differential\_expression**

**Lines fetched: 36,114 GLDS-245\_rna\_seq\_differential\_expression**

**Lines fetched: 26,335 GLDS-246\_rna\_seq\_differential\_expression**

**Lines fetched: 35,895 GLDS-247\_rna\_seq\_differential\_expression**

**Lines fetched: 30,486 GLDS-248\_rna\_seq\_differential\_expression**

**Lines fetched: 31,729 GLDS-251\_rna\_seq\_differential\_expression**

**Lines fetched: 24,088 GLDS-253\_rna\_seq\_differential\_expression**

**Lines fetched: 29,148 GLDS-254\_rna\_seq\_differential\_expression**

**Lines fetched: 31,759 GLDS-272\_rna\_seq\_differential\_expression**

**Lines fetched: 29,509 GLDS-273\_rna\_seq\_differential\_expression**

**Lines fetched: 26,426 GLDS-274\_rna\_seq\_differential\_expression**

**Lines fetched: 25,133 GLDS-288\_rna\_seq\_differential\_expression**

**Lines fetched: 20,724 GLDS-289\_rna\_seq\_differential\_expression**

**Lines fetched: 22,619 GLDS-347\_rna\_seq\_differential\_expression**

**Lines fetched: 11,228 Sheet1**

**Lines fetched: 8,692**

**Lunar\_PhenotypeGroup\_stress\_4ql**

**Lines fetched: 1,429 Lunar\_LocationGrouped\_4qlik**

**Lines fetched: 652 Lunar\_cordinately\_expressed\_byM**

**Lines fetched: 10 Lunar\_cordinately\_expressed\_byM << Lunar\_Coordinatly\_expressed\_by\_ Lines fetched: 52 Lunar\_cordinately\_expressed\_byM << Lunar\_Coordinately\_expressed\_by Lines fetched: 68 pub?output=csv**

**Lines fetched: 1,851 Agris\_TF\_List**

**Lines fetched: 67 Sheet1**

**Lines fetched: 60 Ca family genes v1**

**Lines fetched: 1,212 Agris\_TF\_List**

**Lines fetched: 67 Space\_methalome\_41526\_2018\_46\_MOESM1\_ESM\_4Qlik**

**Lines fetched: 149 Sheet1**

**Lines fetched: 41,671 Keg pathway**

**Lines fetched: 3,200 GoBio**

**Lines fetched: 206,341 GoMolecularFunction**

**Lines fetched: 76,418 GoCellularSite**

**Lines fetched: 53,508 64samples\_3group\_totalcount...**

**Lines fetched: 26,845 TGB\_050\_1\_2\_64samples\_9grou...**

**Lines fetched: 26,845 Astronauts**

**Lines fetched: 606 Mission**

**Lines fetched: 999 Gravitropism**

**Lines fetched: 53 Gravity\_response**

**Lines fetched: 213 Possitive\_gravitropism**

**Lines fetched: 71 Negative\_gravitopism**

**Lines fetched: 55 Arabidopsis\_mart\_export\_GeneStartSite**

**Lines fetched: 32,833 Human\_mart\_export\_GeneStartSite**

**Lines fetched: 66,832 FLY\_DM\_mart\_export**

**Lines fetched: 17,753 Sheet1**

**Lines fetched: 232,148 Sheet1**

**Lines fetched: 1,962 Sheet1**

**Lines fetched: 78,956 Sheet1**

**Lines fetched: 158,436 Ensemble\_plants\_mart\_export\_v1**

**Lines fetched: 571,955 Ensemble\_plants\_mart\_export\_v1 <\<Brachypodium\_Ensemble\_Orthologue\_mart\_export**

**Lines fetched: 1,934,302 Ensemble\_plants\_mart\_export\_v1 \<Ensemble\_Tom\_Ortho\_mart\_export**

**Lines fetched: 3,031,358 Ensemble\_Rice\_Ortholgy\_mart\_export**

**Lines fetched: 1,224,633 Ensemble\_plants\_mart\_export\_v1 << Ensemble\_BRapa\_orthologs\_mart\_export**

**Lines fetched: 3,419,289 Ensemble\_Human\_mart\_export\_ortho\_v2**

**Lines fetched: 3,728,305 Ensemble\_Mouse\_mart\_export**

**Lines fetched: 409,003 Ensemble\_Mouse\_mart\_export << Ensemble\_Rat\_Orthlogues\_mart\_export**

**Lines fetched: 746,370 Mitocarta-Afshin**

**Lines fetched: 1,797 Mito pathways**

**Lines fetched: 989 OXPHOS Complex mito genes**

**Lines fetched: 994 plant\_mito**

**Lines fetched: 1,079 Human\_mart\_export\_V12**

**Lines fetched: 934,417 Arabidopsis\_mart\_export\_V12**

**Lines fetched: 441,508 Hoja1**

**Lines fetched: 1,341 ROS for Qlik**

**Lines fetched: 18 ROS chemicals**

**Lines fetched: 30 ROS interactome**

**Lines fetched: 323 Berimbau root map**

**Lines fetched: 22,743 AGL42**

**Lines fetched: 999 AGL42 << APL**

**Lines fetched: 1,998 AGL42 << SUC2**

**Lines fetched: 2,997 AGL42 << SCR5**

**Lines fetched: 3,996 AGL42 << S32**

**Lines fetched: 4,995 AGL42 << S18**

**Lines fetched: 5,994 AGL42 << S17**

**Lines fetched: 6,993 AGL42 << S4**

**Lines fetched: 8,014 AGL42 << RM1000**

**Lines fetched: 9,013 AGL42 << PET111**

**Lines fetched: 10,012 AGL42 << LRC**

**Lines fetched: 11,011 AGL42 << JO121**

**Lines fetched: 12,010 AGL42 << J2661**

**Lines fetched: 13,009 AGL42 << GL2**

**Lines fetched: 14,008 AGL42 << CORTEX**

**Lines fetched: 15,007 AGL42 << COBL9**

**Lines fetched: 16,006 RNAseq Li et al RNAseq Fig9**

**Lines fetched: 62,927 Hair cells**

**Lines fetched: 999 Hair cells << Stele IV**

**Lines fetched: 1,998 Hair cells << Stele III**

**Lines fetched: 2,997 Hair cells << Stele II**

**Lines fetched: 3,996 Stele I**

**Lines fetched: 999 Endodermis II**

**Lines fetched: 999 Hair cells << Endodermis I**

**Lines fetched: 4,995Hair cells << Cortex Hair cells II**

**Lines fetched: 5,994Hair cells << CortexHaircell**

**Lines fetched: 6,993Hair cells << Cortex II**

**Lines fetched: 7,992Hair cells << Cortex I**

**Lines fetched: 8,991 Hair cells << Columella II**

**Lines fetched: 9,990 Hair cells << Columella I**

**Lines fetched: 10,989 Hair cells << Non-hair cells IV**

**Lines fetched: 11,988 Hair cells << Non-hair cells III**

**Lines fetched: 12,987 Non-hair cells I**

**Lines fetched: 999 Hair cells << Non-hair cells II**

**Lines fetched: 13,986 Sucrose response**

**Lines fetched: 3,699 mc4\_endo**

**Lines fetched: 999 Supplemental Table S3**

**Lines fetched: 21,431 PTM database**

**Lines fetched: 48,359 Ara-cyc-genes**

**Lines fetched: 27,655 fit3**

**Lines fetched: 53,617 4GY 4hrs BioJupies**

**Lines fetched: 18,008 10GY 4hrs BioJupies**

**Lines fetched: 17,509 arabidopsis\_compartment\_integrated\_full**

**Lines fetched: 550,546 human\_compartment\_integrated\_full**

**Lines fetched: 1,150,572 fly\_compartment\_integrated\_full**

**Lines fetched: 310,997 mouse\_compartment\_integrated\_full**

**Lines fetched: 708,750 rat\_compartment\_integrated\_full**

**Lines fetched: 516,050 worm\_compartment\_integrated\_full**

**Lines fetched: 355,606 yeast\_compartment\_integrated\_full**

**Lines fetched: 198,578**

**$Syn 1 = Fraction Expressing w/in Cluster+Fraction Expressing Outside Cluster+Cell markers+Promoter+Cluster $Syn 2 = single cells p-value+single cells average difference+Cell markers $Syn 3 = single cells p-value+single cells average difference+Fraction Expressing w/in Cluster+Fraction Expressing Outside Cluster+Cell markers+Promoter+Cluster $Syn 4 = Arabidopsis Gene stable ID+Cell markers $Syn 5 = Arabidopsis Gene stable ID+Fraction Expressing w/in Cluster+Fraction Expressing Outside Cluster+Cell markers+Promoter+Cluster $Syn 6 = Arabidopsis Gene stable ID+Fraction Expressing w/in Cluster+Fraction Expressing Outside Cluster+Cell markers+Promoter+Cluster+Average Difference $Syn 7 = Arabidopsis Gene stable ID+single cells p-value+single cells average difference+Cell markers $Syn 8 = Arabidopsis Gene stable ID+Brachy Gene stable ID+Brapa Gene stable ID+Tom Gene stable ID**

**$Syn 9 = Arabidopsis Gene stable ID+Transcription Factor Filter $Syn 10 = Arabidopsis Gene stable ID+Short Description+Subgroup $Syn 11 = Arabidopsis Gene stable ID+ROS+SALT+METAL+HEAT+Short Description+Subgroup $Syn 12 = Arabidopsis Gene stable ID+Arabidopsis Gene Family Filters $Syn 13 = Arabidopsis Gene stable ID+Atha-Col-0-HypocotylCC-WT-FLT-Rep1+Atha-Col-0-HypocotylCC-WT-FLT-Rep2+Atha-Col-0-HypocotylCC-WT-FLT-Rep3+Atha-Col-0-HypocotylCC-WT-FLT-Rep4+Atha-Col-0-HypocotylCC-WT-FLT-Rep5+Atha-Col-0-HypocotylCC-WT-GC-Rep1+Atha-Col-0-HypocotylCC-WT-GC-Rep2+Atha-Col-0-HypocotylCC-WT-GC-Rep3+Atha-Col-0-HypocotylCC-WT-GC-Rep4+Atha-Col-0-HypocotylCC-WT-GC-Rep5 $Syn 14 = Arabidopsis Gene stable ID+Arabidopsis Transcript stable ID $Syn 15 = Arabidopsis Gene stable ID+Arabidopsis Transcript stable ID+Gene Type+Description+Other Name(Type)+Keywords**

**$Syn 16 = $Syn 14+$Syn 15**

**$Syn 17 = $Syn 10+$Syn 11**

**$Syn 18 = $Syn 9+$Syn 12**

**$Syn 19 = $Syn 2+$Syn 4+$Syn 7**

**$Syn 20 = $Syn 1+$Syn 4+$Syn 5**

**$Syn 21 = $Syn 1+$Syn 4+$Syn 5+$Syn 6**

**$Syn 22 = $Syn 1+$Syn 2+$Syn 3**

**$Syn 23 = $Syn 1+$Syn 2+$Syn 3+$Syn 4+$Syn 5+$Syn 7**

**$Syn 24 = $Syn 20+$Syn 21**

**$Syn 25 = $Syn 19+$Syn 20+$Syn 22+$Syn 23**

**$Syn 26 = Human Gene name+Mitocarta filter $Syn 27 = Human Gene name+JAXA5\_Pre - Normalized means $Syn 28 = Arabidopsis Transcript stable ID+BRIC20\_Observed+BRIC20\_Mr(expt)+BRIC20\_Mr(calc)+BRIC20\_Mass Error (ppm)+Modification+BRIC20\_S1:114.1 Intensity+BRIC20\_S2:116.1 Intensity+BRIC20\_S3:118.1 Intensity+BRIC20\_GC1:115.1 Intensity+BRIC20\_GC2:117.1 Intensity+BRIC20\_GC3:119.1 Intensity $Syn 29 = Human Gene stable ID+Human Gene stable ID version**

**$Syn 30 = Human Gene stable ID+Human Gene stable ID version+Human Transcript stable ID+Human Transcript stable ID version**

**$Syn 31 = Mouse Gene stable ID+Human Gene stable ID+DROM Gene stable ID+Worm Gene stable ID+Rat Gene stable ID**

**$Syn 32 = $Syn 29+$Syn 30**

**$Syn 33 = $Syn 29+$Syn 30+$Syn 31**

**$Syn 34 = $Syn 32+$Syn 33**

**$Syn 35 = Mouse Gene stable ID+Mmus\_C57-6T\_LVR\_FLT\_Rep1\_F1+Mmus\_C57-6T\_LVR\_FLT\_Rep2\_F2 $Syn 36 = Accession+sample name $Syn 37 = Accession+organism $Syn 38 = $Syn 36+$Syn 37**

**Creating search index**

**Search index creation completed successfully**

**App saved**

**Finished with error(s) and/or warning(s)**

**0 forced error(s)**

**38 synthetic key(s)**

**December 29th (added disease database)**

**Started loading data**

**disease\_associations Lines fetched: 30,170 disease\_mappings**

**Lines fetched: 242,889 disease\_mappings\_to\_attributes**

**Lines fetched: 30,293 vdisease\_associations**

**Lines fetched: 14,155 gene\_associations Lines fetched: 21,671**

**variant\_associations**

**Lines fetched: 194,515**

**variant\_to\_gene\_mappings**

**Lines fetched: 361,967 Group PostMission vs. PreMissio Lines fetched: 25,028 Group-PostMission-PreMission\_an**

**Lines fetched: 25,028 Diff\_expression\_all\_comparisons (JAXA6\_FLvs\_Pre\_results) Lines fetched: 26,844 Diff\_expression\_all\_comparisons\_(JAXA\_Pre+Mission vs Recorvery) Lines fetched: 26,844 JAXA5\_3group\_loci\_for\_venn\_meta Lines fetched: 509 Flight-PostMission Down, 4448 g Lines fetched: 4,448 Flight-PreMission UP, 12 genes Lines fetched: 12 PreMission-PostMission UP, 11 g Lines fetched: 11 PreMission-PostMission Down, 10 Lines fetched: 106 Flight-PreMission Down, 551 gen Lines fetched: 551 Connected**

**RestConnectorMasterTable << RestConnectorMasterTable Lines fetched: 2,690 \_shards << RestConnectorMasterTable Lines fetched: 1 Mission << RestConnectorMasterTable Lines fetched: 412 Study Person << RestConnectorMasterTable Lines fetched: 412 \_source << RestConnectorMasterTable Lines fetched: 412 all << RestConnectorMasterTable Lines fetched: 627 highlight << RestConnectorMasterTable Lines fetched: 412 hits << RestConnectorMasterTable Lines fetched: 412 hits\_u0 << RestConnectorMasterTable Lines fetched: 1 root << RestConnectorMasterTable Lines fetched: 1**

**root-26 << ?investigation**

**Lines fetched: 19,348 Accesssion Factors Lines fetched: 374 Mouse Lines fetched: 30,769 Mouse << Arabidopsis Lines fetched: 35,915 Mouse << FruitFly Lines fetched: 38,539 Mouse << Human Lines fetched: 41,797**

**Mouse << B.subtlilus Lines fetched: 42,141 Mouse << Yeast Lines fetched: 42,300 ?study.factor%20value Lines fetched: 9,717**

**?study.factor%20value << ?study.factor%20value Lines fetched: 19,535**

**?study.factor%20value << ?study.factor%20value Lines fetched: 29,353**

**?study.factor%20value << ?study.factor%20value Lines fetched: 39,171 E-GEOD-5638-A-AFFY-2-analytics Lines fetched: 20,599**

**Sheet1 Lines fetched: 222 GLDS-1\_array\_differential\_expression Lines fetched: 12,622 GLDS-3\_array\_differential\_expression Lines fetched: 12,622 GLDS-7\_array\_differential\_expression**

**Lines fetched: 20,149 GLDS-17\_array\_differential\_expression Lines fetched: 20,149 GLDS-34\_array\_differential\_expression**

**Lines fetched: 12,622 GLDS-36\_array\_differential\_expression Lines fetched: 11,504 GLDS-37\_rna\_seq\_differential\_expression**

**Lines fetched: 28,064 GLDS-38\_rna\_seq\_differential\_expression Lines fetched: 27,723 GLDS-46\_array\_differential\_expression**

**Lines fetched: 20,149 GLDS-47\_rna\_seq\_differential\_expression**

**Lines fetched: 20,493 GLDS-48\_rna\_seq\_differential\_expression Lines fetched: 22,196 GLDS-49\_rna\_seq\_differential\_expression Lines fetched: 18,535 GLDS-52\_array\_differential\_expression Lines fetched: 18,763 GLDS-70\_array\_differential\_expression**

**Lines fetched: 12,622 GLDS-71\_array\_differential\_expression Lines fetched: 18,762 GLDS-78\_array\_differential\_expression Lines fetched: 12,321 GLDS-85\_rna\_seq\_differential\_expression**

**Lines fetched: 15,087 GLDS-91\_rna\_seq\_differential\_expression Lines fetched: 16,868 GLDS-98\_rna\_seq\_differential\_expression Lines fetched: 23,264 GLDS-99\_rna\_seq\_differential\_expression Lines fetched: 21,598 GLDS-100\_rna\_seq\_differential\_expression Lines fetched: 26,452 GLDS-101\_rna\_seq\_differential\_expression Lines fetched: 22,591 GLDS-102\_rna\_seq\_differential\_expression Lines fetched: 24,035 GLDS-103\_rna\_seq\_differential\_expression**

**Lines fetched: 22,255 GLDS-104\_rna\_seq\_differential\_expression Lines fetched: 21,778 GLDS-105\_rna\_seq\_differential\_expression Lines fetched: 22,098 GLDS-120\_rna\_seq\_differential\_expression**

**Lines fetched: 24,501 GLDS-121\_array\_differential\_expression Lines fetched: 9,470 GLDS-124\_array\_differential\_expression Lines fetched: 26,229 GLDS-125\_array\_differential\_expression**

**Lines fetched: 19,251 GLDS-127\_rna\_seq\_differential\_expression Lines fetched: 22,378 GLDS-136\_array\_differential\_expression Lines fetched: 20,149 GLDS-137\_rna\_seq\_differential\_expression Lines fetched: 22,228 GLDS-138\_rna\_seq\_differential\_expression Lines fetched: 4,429 GLDS-141\_rna\_seq\_differential\_expression**

**Lines fetched: 18,126 GLDS-147\_array\_differential\_expression Lines fetched: 20,149 GLDS-154\_array\_differential\_expression**

**Lines fetched: 12,317 GLDS-161\_rna\_seq\_differential\_expression Lines fetched: 25,416 GLDS-162\_rna\_seq\_differential\_expression Lines fetched: 28,760 GLDS-163\_rna\_seq\_differential\_expression Lines fetched: 32,074 GLDS-164\_rna\_seq\_differential\_expression**

**Lines fetched: 21,615 GLDS-168\_rna\_seq\_differential\_expression**

**Lines fetched: 30,379 GLDS-173\_rna\_seq\_differential\_expression Lines fetched: 18,432**

**GLDS-188\_array\_differential\_expression Lines fetched: 23,177 GLDS-194\_rna\_seq\_differential\_expression Lines fetched: 26,234 GLDS-202\_rna\_seq\_differential\_expression**

**Lines fetched: 27,007**

**GLDS-203\_rna\_seq\_differential\_expression**

**Lines fetched: 28,920 GLDS-205\_array\_differential\_expression**

**Lines fetched: 20,149 GLDS-207\_rna\_seq\_differential\_expression Lines fetched: 13,885 GLDS-208\_rna\_seq\_differential\_expression Lines fetched: 20,664**

**GLDS-211\_rna\_seq\_differential\_expression Lines fetched: 27,110 GLDS-214\_rna\_seq\_differential\_expression Lines fetched: 20,314 GLDS-217\_rna\_seq\_differential\_expression**

**Lines fetched: 23,251 GLDS-235\_rna\_seq\_differential\_expression**

**Lines fetched: 35,138**

**GLDS-236\_rna\_seq\_differential\_expression**

**Lines fetched: 26,836 GLDS-237\_rna\_seq\_differential\_expression**

**Lines fetched: 28,262 GLDS-238\_rna\_seq\_differential\_expression**

**Lines fetched: 28,047 GLDS-239\_rna\_seq\_differential\_expression**

**Lines fetched: 28,201 GLDS-240\_rna\_seq\_differential\_expression Lines fetched: 27,634 GLDS-241\_rna\_seq\_differential\_expression Lines fetched: 27,377 GLDS-242\_rna\_seq\_differential\_expression**

**Lines fetched: 22,703 GLDS-243\_rna\_seq\_differential\_expression**

**Lines fetched: 31,732 GLDS-244\_rna\_seq\_differential\_expression Lines fetched: 36,114**

**GLDS-245\_rna\_seq\_differential\_expression Lines fetched: 26,335 GLDS-246\_rna\_seq\_differential\_expression**

**Lines fetched: 35,895 GLDS-247\_rna\_seq\_differential\_expression**

**Lines fetched: 30,486 GLDS-248\_rna\_seq\_differential\_expression Lines fetched: 31,729 GLDS-251\_rna\_seq\_differential\_expression**

**Lines fetched: 24,088 GLDS-253\_rna\_seq\_differential\_expression**

**Lines fetched: 29,148 GLDS-254\_rna\_seq\_differential\_expression**

**Lines fetched: 31,759 GLDS-272\_rna\_seq\_differential\_expression**

**Lines fetched: 29,509 GLDS-273\_rna\_seq\_differential\_expression**

**Lines fetched: 26,426 GLDS-274\_rna\_seq\_differential\_expression**

**Lines fetched: 25,133 GLDS-288\_rna\_seq\_differential\_expression Lines fetched: 20,724 GLDS-289\_rna\_seq\_differential\_expression**

**Lines fetched: 22,619 GLDS-347\_rna\_seq\_differential\_expression Lines fetched: 11,228 overview 2 << overview 2 Lines fetched: 21 q-value < 0.01 << q-value < 0.01 Lines fetched: 75**

**GSEA q < 0.01 << GSEA q < 0.01**

**Lines fetched: 243,236**

**All DEGs**

**Lines fetched: 115,493 Mouse Lines fetched: 999 Human Lines fetched: 999 Sheet1 Lines fetched: 999**

**Sheet1**

**Lines fetched: 65,535**

**MEM\_All Lines fetched: 2,951 PreservativeRNAdata-Transcriptl**

**Lines fetched: 40,587 Sheet1**

**Lines fetched: 65,535**

**gene\_go\_table**

**Lines fetched: 47,675 gene\_pathway\_table Lines fetched: 4,810**

**datasets\_value\_table Lines fetched: 27,008**

**gene\_mesh\_table Lines fetched: 12,530**

**Sheet1**

**Lines fetched: 8,692 Arabidopsis\_mart\_export\_GeneStartSite Lines fetched: 32,833 Human\_mart\_export\_GeneStartSite Lines fetched: 66,832 FLY\_DM\_mart\_export Lines fetched: 17,753 Mouse\_mart\_export\_GeneStartSite Lines fetched: 56,393 Human\_mart\_export\_V12**

**Lines fetched: 934,417 Arabidopsis\_mart\_export\_V12 Lines fetched: 441,508 Mouse\_mart\_export\_V12**

**Lines fetched: 567,192 DROM\_mart\_export**

**Lines fetched: 284,932 arabidopsis\_compartment\_integrated\_full Lines fetched: 550,546 human\_compartment\_integrated\_full Lines fetched: 1,150,572**

**fly\_compartment\_integrated\_full Lines fetched: 310,997 mouse\_compartment\_integrated\_full Lines fetched: 708,750**

**AGL42 Lines fetched: 999 AGL42 << APL Lines fetched: 1,998**

**AGL42 << SUC2 Lines fetched: 2,997 AGL42 << SCR5 Lines fetched: 3,996**

**AGL42 << S32 Lines fetched: 4,995 AGL42 << S18 Lines fetched: 5,994 AGL42 << S17 Lines fetched: 6,993**

**AGL42 << S4 Lines fetched: 8,014**

**AGL42 << RM1000 Lines fetched: 9,013**

**AGL42 << PET111 Lines fetched: 10,012 AGL42 << LRC Lines fetched: 11,011 AGL42 << JO121 Lines fetched: 12,010 AGL42 << J2661 Lines fetched: 13,009**

**AGL42 << GL2 Lines fetched: 14,008 AGL42 << CORTEX Lines fetched: 15,007 AGL42 << COBL9 Lines fetched: 16,006**

**RNAseq Li et al RNAseq Fig9**

**Lines fetched: 62,927**

**Hair cells Lines fetched: 999**

**Hair cells << Stele IV Lines fetched: 1,998 Hair cells << Stele III Lines fetched: 2,997 Hair cells << Stele II Lines fetched: 3,996**

**Stele I Lines fetched: 999**

**Endodermis II Lines fetched: 999**

**Hair cells << Endodermis I Lines fetched: 4,995**

**Hair cells << Cortex Hair cells II Lines fetched: 5,994 Hair cells << CortexHaircell Lines fetched: 6,993**

**Hair cells << Cortex II Lines fetched: 7,992**

**Hair cells << Cortex I Lines fetched: 8,991**

**Hair cells << Columella II Lines fetched: 9,990**

**Hair cells << Columella I Lines fetched: 10,989**

**Hair cells << Non-hair cells IV Lines fetched: 11,988**

**Hair cells << Non-hair cells III Lines fetched: 12,987**

**Non-hair cells I Lines fetched: 999**

**Hair cells << Non-hair cells II Lines fetched: 13,986**

**Sucrose response Lines fetched: 3,699**

**mc4\_endo Lines fetched: 999**

**PTM database**

**Lines fetched: 48,359**

**Ara-cyc-genes**

**Lines fetched: 27,655 E-GEOD-5638-A-AFFY-2-analytics << E-GEOD-5638-A-AFFY-2-analytics Lines fetched: 41,198**

**Sheet1 Lines fetched: 222 Ensemble\_plants\_mart\_export\_v1**

**Lines fetched: 571,955 Ensemble\_Human\_mart\_export\_ortho\_v2**

**Lines fetched: 3,728,305 HUMAN-ARATH Lines fetched: 12,779**

**Lunar\_PhenotypeGroup\_stress\_4ql Lines fetched: 1,429**

**Lunar\_LocationGrouped\_4qlik Lines fetched: 652**

**Lunar\_cordinately\_expressed\_byM Lines fetched: 10**

**Lunar\_cordinately\_expressed\_byM << Lunar\_Coordinatly\_expressed\_by\_ Lines fetched: 52 Lunar\_cordinately\_expressed\_byM << Lunar\_Coordinately\_expressed\_by Lines fetched: 68**

**pub?output=csv Lines fetched: 1,851 Agris\_TF\_List Lines fetched: 67 Sheet1 Lines fetched: 60**

**Ca family genes v1 Lines fetched: 1,212 pub?output=csv << Agris\_TF\_List Lines fetched: 1,918 Space\_methalome\_41526\_2018\_46\_MOESM1\_ESM\_4Qlik Lines fetched: 149**

**Sheet1**

**Lines fetched: 41,671**

**Keg pathway Lines fetched: 3,200**

**GoBio**

**Lines fetched: 206,341**

**GoMolecularFunction**

**Lines fetched: 76,418**

**GoCellularSite Lines fetched: 53,508**

**Astronauts Lines fetched: 606**

**Mission Lines fetched: 999**

**Gravitropism Lines fetched: 53 Gravity\_response Lines fetched: 213**

**Possitive\_gravitropism Lines fetched: 71**

**Negative\_gravitopism Lines fetched: 55**

**Sheet1**

**Lines fetched: 232,148 Sheet1 Lines fetched: 1,962**

**Sheet1**

**Lines fetched: 78,956**

**Sheet1**

**Lines fetched: 158,436**

**Mitocarta-Afshin Lines fetched: 1,797**

**Mito pathways Lines fetched: 989**

**OXPHOS Complex mito genes Lines fetched: 994**

**plant\_mito Lines fetched: 1,079**

**fit3**

**Lines fetched: 53,617**

**4GY 4hrs BioJupies**

**Lines fetched: 18,008**

**10GY 4hrs BioJupies**

**Lines fetched: 17,509**

**Supplemental Table S3**

**Lines fetched: 21,431**

**Hoja1 Lines fetched: 1,341**

**ROS for Qlik Lines fetched: 18**

**ROS chemicals Lines fetched: 30**

**ROS interactome Lines fetched: 323**

**$Syn 1 = Fraction Expressing w/in Cluster+Fraction Expressing Outside Cluster+Cell markers+Promoter+Cluster $Syn 2 = single cells p-value+single cells average difference+Cell markers $Syn 3 = single cells p-value+single cells average difference+Fraction Expressing w/in Cluster+Fraction Expressing Outside Cluster+Cell markers+Promoter+Cluster $Syn 4 = Arabidopsis Gene stable ID+Cell markers $Syn 5 = Arabidopsis Gene stable ID+Fraction Expressing w/in Cluster+Fraction Expressing Outside Cluster+Cell markers+Promoter+Cluster $Syn 6 = Arabidopsis Gene stable ID+Fraction Expressing w/in Cluster+Fraction Expressing Outside Cluster+Cell markers+Promoter+Cluster+Average Difference $Syn 7 = Arabidopsis Gene stable ID+single cells p-value+single cells average difference+Cell markers $Syn 8 = Arabidopsis Gene stable ID+Arabidopsis Gene Family Filters $Syn 9 = Arabidopsis Gene stable ID+Arabidopsis Transcript stable ID**

**$Syn 10 = Arabidopsis Gene stable ID+Arabidopsis Transcript stable ID+Gene Type+Description+Other Name(Type)+Keywords $Syn 11 = Arabidopsis Gene stable ID+Atha-Col-0-HypocotylCC-WT-FLT-Rep1+Atha-Col-0-HypocotylCC-WT-FLT-Rep2+Atha-Col-0-HypocotylCC-WT-FLT-Rep3+Atha-Col-0-HypocotylCC-WT-FLT-Rep4+Atha-Col-0-HypocotylCC-WT-FLT-Rep5+Atha-Col-0-HypocotylCC-WT-GC-Rep1+Atha-Col-0-HypocotylCC-WT-GC-Rep2+Atha-Col-0-HypocotylCC-WT-GC-Rep3+Atha-Col-0-HypocotylCC-WT-GC-Rep4+Atha-Col-0-HypocotylCC-WT-GC-Rep5 $Syn 12 = $Syn 9+$Syn 10**

**$Syn 13 = $Syn 2+$Syn 4+$Syn 7 $Syn 14 = $Syn 1+$Syn 4+$Syn 5 $Syn 15 = $Syn 1+$Syn 4+$Syn 5+$Syn 6 $Syn 16 = $Syn 1+$Syn 2+$Syn 3 $Syn 17 = $Syn 1+$Syn 2+$Syn 3+$Syn 4+$Syn 5+$Syn 7 $Syn 18 = $Syn 14+$Syn 15 $Syn 19 = $Syn 13+$Syn 14+$Syn 16+$Syn 17**

**$Syn 20 = Arabidopsis Transcript stable ID+BRIC20\_Observed+BRIC20\_Mr(expt)+BRIC20\_Mr(calc)+BRIC20\_Mass Error (ppm)+Modification+BRIC20\_S1:114.1 Intensity+BRIC20\_S2:116.1 Intensity+BRIC20\_S3:118.1 Intensity+BRIC20\_GC1:115.1 Intensity+BRIC20\_GC2:117.1 Intensity+BRIC20\_GC3:119.1 Intensity $Syn 21 = Coefficients-Comparison+Twin\_ExperimentType $Syn 22 = Coefficients-Comparison+Cell Type-CellType $Syn 23 = $Syn 21+$Syn 22 $Syn 24 = Mouse Gene stable ID+Mouse Gene stable ID version $Syn 25 = Mouse Gene stable ID+Mmus\_C57-6T\_LVR\_FLT\_Rep1\_F1+Mmus\_C57-6T\_LVR\_FLT\_Rep2\_F2**

**$Syn 26 = Arabidopsis Gene stable ID+Short Description+Subgroup $Syn 27 = Arabidopsis Gene stable ID+ROS+SALT+METAL+HEAT+Short Description+Subgroup $Syn 28 = $Syn 26+$Syn 27 $Syn 29 = Accession+assay name+sample name $Syn 30 = Accession+organism $Syn 31 = Accession+Study Assay Technology Type+Study Assay Technology Platform+Study Factor Type+Study Factor Name+Study Assay Measurement Type+Project Title+Project Link+organism+#accession $Syn 32 = $Syn 30+$Syn 31 $Syn 33 = $Syn 29+$Syn 30 $Syn 34 = Human Gene stable ID+Human Gene stable ID version**

**$Syn 35 = Human Gene stable ID+Human Gene stable ID version+Human Transcript stable ID+Human Transcript stable ID version**

**$Syn 36 = Human Gene name+Human Gene stable ID**

**$Syn 37 = $Syn 34+$Syn 35**

**$Syn 38 = $Syn 34+$Syn 35+$Syn 36**

**$Syn 39 = $Syn 37+$Syn 38 $Syn 40 = Human Gene name+Mitocarta filter $Syn 41 = Human Gene name+source**

**$Syn 42 = diseaseId+Disease name $Syn 43 = diseaseId+diseaseName+diseaseType+diseaseClass+diseaseSemanticType+NofPmids**

**Creating search index**

**Search index creation completed successfully**

**App saved**

**Finished with error(s) and/or warning(s)**

**0 forced error(s)**

**43 synthetic key(s)**
