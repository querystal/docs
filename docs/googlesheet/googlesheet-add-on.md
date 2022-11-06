# Google Sheet Add-on

Querystal provides native support of google sheet add-on in order to leverage one of the most commonly used analytics
tools. As a business analyst, you can seamlessly integrate the querystal datasets with your own sheets.

## Installation
1. Open the add-on marketplace, and search "querystal". 
2. Find the one pulished by querystal.com and install.
3. Refresh the google sheet.
4. Get the client info grant to your account in Querystal.com personal page.
5. Go back to the google sheet and select 'Querystal' add-on.
6. Click 'Settings' > 'Client Authentication', and key in client id and client secret.
7. Start to use built-in formulas.

## Formulas

There are three built-in formulas to use.

| Formula        |Description| Example                                      |
|----------------|---|----------------------------------------------|
| QS_CLIENT_INFO |show the client id of the sheet to inspect the client identity applied| -                                            |
| QS_DATASET     |query a dataset from Querystal| QS_DATASET(dbName, dsName, selects, filters) |
| QS_TICKER      |query a dataset by ticker, which is assigned by platform to those high quality datasets.| QS_TICKER(ticker, selects, filters)          |

### Limitation
There are some known limitations of google sheet add-on. Please review them and make a decision. 
* formula execution duration must be less than 45s.
