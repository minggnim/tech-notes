### Install package sf
```
brew install gcc
brew install gdal

spat_config <- '--with-proj-lib=/usr/local/lib/ --with-proj-include=/usr/local/include/'
options(configure.args = c("sf" = spat_config, "rgdal" = spat_config))

install.packages(c("sf", "rgdal"), type = "source")
```
