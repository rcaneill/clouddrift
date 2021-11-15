# Process data

To use the CloudDrift library in a local environment, the library requires a ragged array (stored in the `process/` folder) that regroups the individual drifter trajectories.

For *most users*, the netCDF dataset `gdp_1.04c.nc`, can be retrieved from [link]() and stored in the `process/` folder (or any convenient location).

For *advanced users*, the preprocessing routines are made available (`preprocess.ipynb`) to manually create the netCDF ragged array (`gdp_1.04c.nc`) from the individual trajectory files. This requires downloading the raw dataset which is explained below.

# Raw data

The raw dataset of the [Hourly Drifter Data](https://www.aoml.noaa.gov/phod/gdp/hourly_data.php) is composed of 17,324 netCDF (Nov 3rd, 2021) and is located on the AOML [FTP server](ftp://ftp.aoml.noaa.gov/pub/phod/lumpkin/hourly/v1.04/netcdf/).

### Manually
The FTP server contains 9 `tar.gz` files of the different block of data stored in folders (`argos_block1/`, `argos_block2/`, `argos_block3/`, `argos_block4/`, `argos_block5/`, `argos_block6/`, `argos_block7/`, `argos_block8/`, and `gps/`). The 9 compressed files have to be downloaded, and extracted to `cloudrift/raw/` before performing the preprocessing.

### Automatically
Alternatively, the script *sync_gdp_hourly.sh* can be used to automatically retrieve (or update to) the current dataset. It requires the `lftp` command available on most Linux Distribution or through [Homebrew](https://formulae.brew.sh/formula/lftp) for macOS users.

## Reference
Elipot, S., R. Lumpkin, R. C. Perez, J. M. Lilly, J. J. Early, and A. M. Sykulski (2016), "A global surface drifter dataset at hourly resolution", J. Geophys. Res. Oceans, 121, [doi:10.1002/2016JC011716](doi:10.1002/2016JC011716) [(Archived pdf)](https://www.aoml.noaa.gov/phod/gdp/papers/Elipot_et_al-2016.pdf)