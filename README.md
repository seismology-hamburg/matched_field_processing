# Matched Field Processing using numerical Green's Functions from pre-computed databases

<img align="left" src="assets/mfp.png" width="400px">

Matched Field Processing (MFP) is a technique to locate the source of a recorded wave field. It is the generalization of beamforming, allowing for curved wavefronts. In the standard approach to MFP, simple analytical Green's functions are used as synthetic wave fields that the recorded wave fields are matched against. We introduce an advancement of MFP by utilizing Green's functions computed numerically for real Earth structure as synthetic wave fields. This allows in principle to incorporate the full complexity of elastic wave propagation, and through that provide more precise estimates of the recorded wave field's origin. 

This repository acts as the development platform for this approach.

A manuscript describing the method in detail is available as a pre-print at EarthArXiv (---) and submitted to Geophyiscal Journal International. A separate repository contains the information (what data was used, settings files, figure scripts) to reproduce the results we present in our manuscript: [seismology-hamburg/schippkus_hadziioannou_2022](https://github.com/seismology-hamburg/schippkus_hadziioannou_2022).

## TODO

- [ ] A smarter way of optimizing the grid/processing needs than manually-selected rounding
- [ ] Move multiprocessing logic to separate function & enable single-core runs
- [ ] Beampower computation based on acoular
### Requirements

- python 3.8+
- [obspy](https://github.com/obspy/obspy/wiki/) to read seismic data
- [cartopy](https://scitools.org.uk/cartopy/docs/latest/index.html) to plot maps
- [tqdm](https://tqdm.github.io) to get progressbars
- [pyyaml](https://pypi.org/project/PyYAML/) to parse the `settings.yml`
- [instaseis](https://instaseis.net) to read the Green's function database
- local green's function database readable by instaseis, e.g., downloaded from [syngine](http://ds.iris.edu/ds/products/syngine/)
- [global_land_mask](https://pypi.org/project/global-land-mask/) for fast checks whether cells are on land
