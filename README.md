<h2>CLUST analysis tutorial (for Windows)</h2>

<h4>python code and data example to analyze clust result</h4>

```
https://github.com/managene7/clust_analysis_for_RNA_seqs.git
```

<h4>Install clust in Windows</h4>

```
pip install clust
```

<h4>Go to data directory</h4>
<h4>Command to run clust</h4>

```
clust --no-optimisation Col_Wounding_RNA_seq.txt -t 10 -o clust_test_result -r replicates_info.txt
```

<h4>copy “replicates_info.txt” and “Col_Wounding_fitted_value_RNA_seq.txt” files to the result folder.</h4>
<h4>copy the “RNA_seq_tools_cluster-clusterheatmap-boxplot_consensus_v2.0_py3.py” python code to the result folder.</h4>


<h4>Command to see options.</h4>

```
python3 RNA_seq_tool-clust_result_processor_v2.0_py3.py -help
```
```
___________________________________________________________________________________________

Usage;

This code is for analysis of RNA-seq and data visualization
-def    cl: generate individual files for cluster in teh clust result.
            -clust      file name of cluster info by clust analysis (default is 'Clusters_Objects.tsv')
            -dge        file name of digital gene expression
            -rep        file name of replicate info if applicable (option)
            -log2       yes => convert dge into log2 value, no => do not convert (default is 'no')
        hmap: generate clustered heat map
            -consensus  consensus of names for multiple running
            -fig_w      width of the figure (default is 10)
            -fig_h      height of the figure (default is 20)
            -dpi        resolution of figure (default is 300)
        hmap_fc: generate clustered heat map by fold change
            -consensus  consensus of names for multiple running
            -fig_w      width of the figure (default is 10)
            -fig_h      height of the figure (default is 20)
            -dpi        resolution of figure (default is 300)
        bp: generate box plot
            -consensus  consensus of names for multiple running
            -fig_w      width of the figure (default is 10)
            -fig_h      height of the figure (default is 20)
            -dot_size   size of dots in the plot (default is 1.0)
            -dpi        resolution of figure (default is 300)
        vp: generate violin plot
            -consensus  consensus of names for multiple running
            -fig_w      width of the figure (default is 10)
            -fig_h      height of the figure (default is 20)
            -dot_size   size of dots in the plot (default is 1.0)
            -dpi        resolution of figure (default is 300)

        convert: convert replicates into single values by average (and log2 value).
            -dge        file name of digital gene expression
            -rep        file name of replicate info (optional)
            -log2       yes => convert dge into log2 value, no => do not convert (default is 'no')
            -min        minimum value threshold of dges in each gene (default is 0)
___________________________________________________________________________________________
```

<h4>Command to separate clusters with gene expression data.</h4>
            
```
python3 RNA_seq_tool-clust_result_processor_v2.0_py3.py -def cl -clust Clusters_Objects.tsv -dge Col_Wounding_RNA_seq.txt -rep replicates_info.txt -log2 yes
```

<h4>Command for heat map drawing</h4>
            
```
python3 RNA_seq_tool-clust_result_processor_v2.0_py3.py -def hmap -consensus .csv -fig_w 8 -fig_h 16 -dpi 200
```

<h4>Command for heat map drawing with fold change data</h4>
            
```
python3 RNA_seq_tool-clust_result_processor_v2.0_py3.py -def hmap_fc -consensus .csv -fig_w 8 -fig_h 16 -dpi 200
```

<h4>Command for box plot drawing</h4>
            
```
python3 RNA_seq_tool-clust_result_processor_v2.0_py3.py -def bp -consensus .csv -fig_w 8 -fig_h 16 -dpi 200 -dot_size 1.0
```

<h4>Command for violin plot drawing</h4>
            
```
python3 RNA_seq_tool-clust_result_processor_v2.0_py3.py -def vp -consensus .csv -fig_w 8 -fig_h 16 -dpi 200 -dot_size 1.0
```

<h4>#Command for raw data filtering and (or) converting to average value.</h4>

```
python3 RNA_seq_tool-clust_result_processor_v2.0_py3.py -def convert -dge Col_Wounding_RNA_seq.txt -rep replicates_info.txt -log2 yes -min 10
```
