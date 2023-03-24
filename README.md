# Edge traces

This repository contains a [Jupyter notebook](Edge_traces.ipynb) that can be
used to generate traces for research in the area of edge computing.

The generated traces are based on the [Alibaba cluster-trace-microservices-v2021
dataset](https://github.com/alibaba/clusterdata/tree/master/cluster-trace-microservices-v2021).
These traces are not geo-localized, so the notebook takes the traces for the most
used microservices and considers each one as the trace of a different app in a
different region.

To generate the trace file, you have to run [the notebook](Edge_traces.ipynb):

```bash
pip install -r requirements.txt
jupyter notebook
```

It downloads the original traces, processes them, and generates a new file
called `edge_1h.csv`. This file contains data grouped by hour. This is the start
of the file:

```csv
timestamp,reg,app,reqs
1970-01-01 00:00:00,0,0,4827602
1970-01-01 01:00:00,0,0,11731750
1970-01-01 02:00:00,0,0,22109809
1970-01-01 03:00:00,0,0,15124156
...
```

This data can be used with the [Edarop](https://github.com/asi-uniovi/edarop/)
package to obtain optimal allocations in edge architectures.
