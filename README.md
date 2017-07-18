# planning

1. Scope out data volumes. 
2. Establish cloud allocation. 
3. Prototype schemes. 
4. Publish products. 

# Prototype 1

* obtain L3 bin RRS files (`raadsync` package)
* apply algorithm calculation at daily bins (`roc` package)
* apply bin aggregation schemes up to regional and local maps at 8Day and Monthly time steps

## Tasks

- [ ]  add 'SNPP_RRS' NASA algorithm to `roc` https://github.com/mdsumner/roc/issues/6
- [x]  obtain SeaWiFS, MODISA, VIIRS L3bin files
- [x] automate scheme for aggregation

The latest workflow for this is still in Mike's scripts and head, but it's pretty well-exercised and has been used to deliver products for K-axis, and various animal tracking projects (long climatologies and recent monthly maps). 

There is process to calculate "johnson" and "nasa" chl from L3BIN RRS in the `roc` package, and this is dumped to workspace files (a temporary workaround prior to db-nouse) and catalogued by a function `raadtools::chla_johnsonfiles`. The downstream mapping of this is all in `roc`, but is mostly generic bin-aggregation and re-mapping for the final product. None of this takes much time, the entire L3BIN archive can be reprocessed in hours, and climatologies of the calculated bins from the entire MODISA era take about an hour (without parallelization). 


# Prototype 2

* obtain L2 files (enough to illustrate creation of L3 bin products)
* apply bin aggregation to daily bins
* aggregate coverage as a measure, and perhaps others


# Prototype 3

* establish SEADAS processing stack
* obtain L1B files, with scheme to discard
* produce SO L2 files, discarding L1B incrementally

