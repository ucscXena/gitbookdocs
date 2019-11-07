# Accessing data through python

You can use the python API, [**xenaPython**](https://github.com/ucscXena/xenaPython), to programmatically access data in the public Xena Data Hubs.

## Installation

```text
pip install xenaPython pip install --upgrade xenaPython
```

## Usage

```text
import xenaPython as xena  
```

## Example

```text
import xenaPython as xenahub = "https://toil.xenahubs.net"dataset = "tcga_RSEM_gene_tpm"samples = xena.dataset_samples (hub, dataset, None)samples = xena.dataset_samples (hub, dataset, 10)samples = ["TCGA-02-0047-01","TCGA-02-0055-01","TCGA-02-2483-01"]probes = ['ENSG00000282740.1', 'ENSG00000000005.5'][position, [ENSG00000282740_1, ENSG00000000005_5]] = xena.dataset_probe_values (hub, dataset, samples, probes)ENSG00000282740_1[-9.9658, -2.8262, -9.9658]
```

## Help

```text
import xenaPythonhelp(xenaPython)
```

## [Jupyter notebook example](https://gist.github.com/acthp/f9828f57eb795404eddb85006375af8d)

## More Information

[https://github.com/ucscXena/xenaPython](https://github.com/ucscXena/xenaPython)

