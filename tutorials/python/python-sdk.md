# Python 3 SDK - PyQuerystal
The official python sdk of [Querystal](https://www.querystal.com).

## Quick Start
### Pre-requisits
This SDK works with python3.

To successfully submit a query, please find your client credentials in [Querystal - Profle](https://www.querystal.com/meta).

Before using the python sdk, please locate the target dataset in [Querystal - MetaStation](https://www.querystal.com/meta).

### Installation
```bash
pip install pyquerystal
```

### Query a Dataset
Import the sdk and initialise a client.
```python
from pyquerystal import Querystal

client = Querystal(
    clientId="<client id>",
    clientSecret="<client secret>")
```

Query a dataset with json response by default.
```python
# query platform table
jsonDict = client.table(
    "community",
    "eth_blocks",
    'number,miner'.split(','),
    "date=2016-05-20".split(",")) \
    .dict()
```

Query a dataset with pandas dataframe response.
```python
# query by ticker
df = client.metrics(
    "ETH_VOLUME",
    'date,volume'.split(',') \
    .dataframe()

# query by database name and dataset name
df = client.metrics_by_name(
    "community",
    "eth_blocks",
    'number,miner'.split(','),
    "date=2016-05-20".split(",")) \
    .dataframe()
```

## SDK Documentation
### Client
Import the sdk package.
```python
from pyquerystal import Querystal
```
Client credentials settings. This is the identity of a client and it is used by access control, billing. Please use the proper client credentials and keep it safely.
```python
Querystal(
    clientId=<client id>
    clientSecret=<client secret>
)
```

### Functions
Read a platform table
```python
table(databaseName:str, datasetName:str, columns:list, filters:list)
```

Read a metrics
```python
# query by ticker
metrics(ticker:str, measures:list, dimensions:list)

# query by dataset info
metrics_by_name(databaseName:str, datasetName:str, measures:list, dimensions:list)
```

### Parameters - Columns & Measures
Columns and measures are the same in term of functionalities but naming convention in platform tables and metrics respectively.

A valid list of columns or measures are as below:
```python
['miner','timestamp']

'miner,timestamp,hash'.split(',')
```

### Parameters - Filters
Filters and dimensions are the same in term of functionalities but naming convention in platform tables and metrics respectively.

A valid list of filters or dimensions are as below:
```python
['block_number > 14000231,block_number < 15002123, hash IS NOT NULL']

'block_number >= 14000231,block_number <= 15002123'.split(',')
```

Support Operators
```python
>,<,>=,<=,=,!=,IN, NOT IN, IS NULL, IS NOT NULL
```