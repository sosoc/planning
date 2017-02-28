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

- [ ]  add 'SNPP_RRS' NASA algorith to `roc`
- [ ]  obtain SeaWiFS, MODISA, VIIRS L3bin files
- [ ] automate scheme for aggregation

# Prototype 2

* obtain L2 files (enough to illustrate creation of L3 bin products)
* apply bin aggregation to daily bins
* aggregate coverage as a measure, and perhaps others


# Prototype 3

* establish SEADAS processing stack
* obtain L1B files, with scheme to discard
* produce SO L2 files, discarding L1B incrementally

