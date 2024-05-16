# Example count merging codes

You can use the following basic syntax to import and merge multiple CSV files located in the same folder into R:

<pre><code><strong>df &#x3C;- list.files(path='C:/my/path/to/files') %>% 
</strong><strong>  lapply(read_csv) %>% 
</strong><strong>  bind_rows
</strong></code></pre>

The following step-by-step example shows how to use this syntax in practice.

#### **Step 1: Create & Export Multiple Data Frames**

First, we’ll use the following code to create and export three data frames to CSV files:

<pre><code><strong>#create three data frames
</strong><strong>df1 &#x3C;- data.frame(points=c(4, 5, 5, 6, 8, 9),
</strong><strong>                  assists=c(3, 2, 4, 4, 6, 3))
</strong>
<strong>df2 &#x3C;- data.frame(points=c(2, 10, 14, 15),
</strong><strong>                  assists=c(3, 2, 9, 3))
</strong>
<strong>df3 &#x3C;- data.frame(points=c(6, 8, 9),
</strong><strong>                  assists=c(10, 6, 4))
</strong>
<strong>#export all three data frames to CSV files
</strong><strong>write.csv(df1, 'C:/Users/bob/Documents/my_data_files/df1.csv', row.names=FALSE)
</strong><strong>write.csv(df2, 'C:/Users/bob/Documents/my_data_files/df2.csv', row.names=FALSE)
</strong><strong>write.csv(df3, 'C:/Users/bob/Documents/my_data_files/df3.csv', row.names=FALSE)
</strong></code></pre>

I can navigate to this folder and see that the three CSV files were successfully exported:

![](https://www.statology.org/wp-content/uploads/2022/04/mergecsv1.jpg)

#### **Step 2: Import & Merge Multiple CSV Files**

Next, we’ll use the following code to import and merge all three CSV files into one data frame in R:

<pre><code><strong>library(dplyr)
</strong><strong>library(readr)
</strong>
<strong>#import and merge all three CSV files into one data frame
</strong><strong>df &#x3C;- list.files(path='C:/Users/bob/Documents/my_data_files') %>% 
</strong><strong>  lapply(read_csv) %>% 
</strong><strong>  bind_rows 
</strong>
<strong>#view resulting data frame
</strong><strong>df
</strong>
<strong># A tibble: 13 x 2
</strong><strong>   points assists
</strong><strong>       
</strong><strong> 1      4       3
</strong><strong> 2      5       2
</strong><strong> 3      5       4
</strong><strong> 4      6       4
</strong><strong> 5      8       6
</strong><strong> 6      9       3
</strong><strong> 7      2       3
</strong><strong> 8     10       2
</strong><strong> 9     14       9
</strong><strong>10     15       3
</strong><strong>11      6      10
</strong><strong>12      8       6
</strong><strong>13      9       4
</strong></code></pre>

Notice that all three CSV files have been successfully merged into one data frame.

We can see that the resulting data frame has 13 rows and 2 columns.

**Note**: If the data frames do not have matching column names, R will still merge all of the data frames and simply fill in missing values with **NA** values.



### **Now we can do the same thing for a list of studies downloaded from the Open Science Archive**



**Processed Mouse count merge…**

**Example selection:** GLDS-379, 401, 289, 273, 272, 254, 253, 248, 246, 214, 245, 244, 243

_`#Load libraries`_

`library(tidyverse)`

`library(data.table)`

_`#Set working directory`_

`setwd("mouse_merge")`

_**`#Define URLs and destination files for downloading RNA-seq/microarray DEG datasets`**_

`URLs<-c("https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-243_rna_seq_Normalized_Counts.csv?version=5", "https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-289_rna_seq_Normalized_Counts.csv?version=5", "https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-379_rna_seq_Normalized_Counts.csv?version=3",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-401_rna_seq_Normalized_Counts.csv?version=2",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-273_rna_seq_Normalized_Counts.csv?version=5",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-272_rna_seq_Normalized_Counts.csv?version=7",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-254_rna_seq_Normalized_Counts.csv?version=13", "https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-253_rna_seq_Normalized_Counts.csv?version=8",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-248_rna_seq_Normalized_Counts.csv?version=11",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-246_rna_seq_Normalized_Counts.csv?version=11",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-214_rna_seq_Normalized_Counts.csv?version=5",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-245_rna_seq_Normalized_Counts.csv?version=14",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-244_rna_seq_Normalized_Counts.csv?version=12")`





`## Pipe the .csv files into a “destFiles” group`

`destFiles<-c(“GLDS-389_rna_seq_Normalized_Counts.csv",`

`"GLDS-379_rna_seq_Normalized_Counts.csv",`

`"GLDS-401_rna_seq_Normalized_Counts.csv",`

`"GLDS-273_rna_seq_Normalized_Counts.csv",`

`"GLDS-272_rna_seq_Normalized_Counts.csv",`

`"GLDS-254_rna_seq_Normalized_Counts.csv",`

`"GLDS-253_rna_seq_Normalized_Counts.csv",`

`"GLDS-248_rna_seq_Normalized_Counts.csv",`

`"GLDS-246_rna_seq_Normalized_Counts.csv",`

`"GLDS-214_rna_seq_Normalized_Counts.csv"',`

`"GLDS-245_rna_seq_Normalized_Counts.csv",`

`"GLDS-244_rna_seq_Normalized_Counts.csv”)`



_`#Download files from URLs and save them to destination files`_

`for (i in 1:length(URLs)) { download.file(URLs[i],`` `**`destFiles`**`[i]) }`



_`##How do you merge rnaseq_NormalizedCounts`_

`AWG_Mouse_merged_transcriptional_data <-`` `**`merge.data.frame`**`(destFiles, by = 'Gene.ID', all = TRUE)`



`#Merged Export`

`write.csv(AWG_Mouse_merged_transcriptional_matrix ,'/AWG_Mouse_merged_transcriptional_matrix .csv')`





Load the expression matrix into iDEP shiny application…&#x20;

http://bioinformatics.sdstate.edu/idep/

{% embed url="http://bioinformatics.sdstate.edu/idep/" %}



End off R code brain storm…

