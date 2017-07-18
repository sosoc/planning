## What does raadtools offer? 

The approach used for `raadtools` has crystallized into 

* `bowerbird` - https://github.com/AustralianAntarcticDivision/bowerbird (supersedes `raadsync`)
* packages to organize, read from the bower - incudling 'raadtools' and [roc](https://github.com/mdsumner/roc). 

`bowerbird` can obtain all the source files, and ensure that any updates at the sources *invalidate the local copies* and trigger an update by download. This can be done at fine-grained level, i.e. all files in a day, or a week - or arbitrarily, whatever makes sense for the processing stream. 

`raadtools` and `roc` includes many examples that show how to organize and process input and output files, but there will be a variety of tools doing various things with those. SEADAS, Python and shell scripts will be among the stack. In particular ther steps in the chain are:

* identifying target source files (based on ephemeris catalogues, file dates, swath records)
* applying algorithms to raw sources at low levels (L1A, L1B?) SEADAS is used here, or bespoke or a mix?
* calculating geo-physical quantities from calibrated radiances (L2 products, here is where interference is idenfitied, cloud removal, sea ice detection, QA filters)
* target binned and map products, in the first instance these are NetCDF4 files like those at oceandata, but workflows with access to these Southern Ocean specific L2 files will use a host of different workflows, including some that cache to databases, or trigger monitoring summaries for reporting. 

The crux as I see it is designing the process to get the bulk source files in chunks, processing those and discarding the (large) sources as we go. Making that robust is the hardest thing I see.  

Up until now, all `raadtools` and related  workflows have used anything L3BIN or above (mapped/SMI), including Rob's algorithm from RRS.  The standard software stack, such as GDAL and HDF and NetCDF libs can be used to read L1 and lower, but the mission is to recreate L2 with Rob's calibration, and then replace the raad workflow for the algorithm for binned and mapped outputs.

