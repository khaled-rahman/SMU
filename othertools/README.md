# Gephi's Forceatlas2 and OpenOrd
Gephi has many algorithms for generating layout. Here, we describe how to run Forceatlas2 and OpenOrd using Gephi's toolkit.

## System Requirements ##
Users need to have following softwares/tools installed in their PC.
```
JDK >= 1.8
```

## How to run Forceatlas2 ##
This tool is in executable format. So, you do not need to do any extra works. Go back to SMU directory and just type the following:
```
java -jar othertools/GephiLayouts-1.0.jar forceatlas2 -i datasets/input/3elt_dual.gml -o datasets/output/3elt_dual.forceatlas2.gml -threads 8 -maxiters 600
```
Here, `-i` indicates input file, `-o` indicates output file, `-threads` indicates number of threads to use and `-maxiters` indicates maximum number of iterations to run. If `-barneshut true` is used, then it will run `O(nlogn)` barnes-hut approximation.

## How to run OpenOrd ##

This tool is in executable format. So, you do not need to do any extra works. Go back to SMU directory and just type the following:
```
java -jar othertools/GephiLayouts-1.0.jar openord -i datasets/input/3elt_dual.gml -o datasets/output/3elt_dual.openord.gml -threads 8 -maxiters 600 -edgecut 0
```
Here, `-i` indicates input file, `-o` indicates output file, `-threads` indicates number of threads to use and `-maxiters` indicates maximum number of iterations to run. When `-edgecut 0` is used, then it will not cut any edge from the graph. It also supports other parameters which will be described later.

# How to run tsNET #

tsNET is a graph layout version of t-SNE (details can be found in [tsNET](https://github.com/HanKruiger/tsNET)). This tool can be run using following command:
```
python othertools/tsNET/tsnet.py datasets/input/3elt_dual.vna --output datasets/output/3elt_dual.tsNET_600.txt
```
Here, `--output` indicates output files where coordinates will be saved. It also supports other parameters like `--perplexity`, `--learning_rate` which are currently set as default values.

If you have questions, please don't hesitate to ask me (Md. Khaledur Rahman) by sending email to morahma@iu.edu
