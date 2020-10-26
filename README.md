# Data of COVID-19 assessment Centres

This repository contains CSV files of Ontario COVID-19 assessment centre locations.

## Repository Structure

Datasets are organized in directory by ownership and provenance. All datasets have their publication dates attached in
filenames.

* `/ODC` directory: contains all versions of COVID-19 assessment centre locations fetched from [Ontario Data Catalogue](https://data.ontario.ca/dataset/covid-19-assessment-centre-locations).

* `/WeCount` directory: contains all datasets used by [the WeCount project](https://wecount.inclusivedesign.ca/).

* `latest.json` in each directory: a JSON schema that indicates the latest dataset used by that ownership.

## Linting

Run `npm run lint` or `grunt lint` to lint.

## Auto-commit New Data Files Published by Ontario Digital Service

A cron job is set up to run every day at 11PM UTC to:

1. Check and download the new data file published at
[the ODS website](https://data.ontario.ca/dataset/covid-19-assessment-centre-locations) into the local directory `/ODC`;
2. If there is a new file, automatically commit the file into the main branch.

The script for this job is located at [`.github/workflows/commitNewDataFile.yml`](.github/workflows/commitNewDataFile.yml).

The shortcoming of this solution is, according to the Github policy, if a repository stays idle for 14 days, cron jobs
will be stopped. This limitation determines the approach of using Github cron job is only a temporary solution. A long
term solution targeting at hosting our own cron job independently from Github is in development.

## License

This data is distributed under the Creative Commons Attribution 4.0 International license. Portions of the data set
were provided by the [Ontario Digital Service](https://www.ontario.ca/page/ontario-digital-service), and contains
information licensed under the [Open Government Licence - Ontario](https://www.ontario.ca/page/open-government-licence-ontario).
