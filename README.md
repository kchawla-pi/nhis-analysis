To use the data downloaded from the [website](https://nhis.ipums.org/nhis-action/extract_requests/download), do the following:

* download the 2 files "DOWNLAD.DAT" and "DDI".

* Install R
```
sudo apt-get install r-base
```

* In R (just `R`)

```R
install.packages('ipumsr') # install the ipums package
require("ipumsr")
ddi <- read_ipums_ddi("nhis_00001.xml")
data <- read_ipums_micro(ddi)
install.packages('feather')
require(feather)
write_feather(data, "data.feather")
```

* In python (using version >3.5)

```python
import pandas as pd
df = pd.read_feather("data.feather")
```
