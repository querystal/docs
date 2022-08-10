# Dataset

Dataset are the first-class entity of Querystal.
Following the traditional data warehouse modeling, there are three types of datasets:

## Category

*Operational Data*
> Operational data are those created and maintained by Querystal platform, which are in raw format, such as on-chain
> blocks, events, transactions, logs. They drive the development of application-layer metrics.

> However, those tables are not essential in most of analytical works. They are relatively large in terms of size, and
> highlightely, they are updated in real-time.

*Business Details Data*
> Business detail tables are classified by business line and topics, such as NFT, stable coins or Dapps. In general, the
> business detail data are also maintained by Querystal platform.

*Application Data*
> Application data are those with business insights, and it is encouraged to apply analytics directly on top of metrics.
> When consumers read any metrics, the cost will be shared by querystal and metrics producer as the incentive.

> Metrics are relatively small in terms of size and with clear dimensions, as the filters, and measures, as the business
> indicators.

## Ticker

Ticker is a unique identity of a dataset which is easy to be remembered. Also it simplifies the parameters used in
built-in formula of google sheet and sdk. The ticker is granted by the platform to those dataset with high quality and
usages.

*By default, a new dataset has no ticker.*