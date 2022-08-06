# fin_data_adf: Azure Data Factory for Market data ETL orchestration

Data Factory in this repo is only used for scheduling and triggering a single Databricks notebook which runs a full cycle ETL describeed in [fin_data_databricks](https://github.com/SenYaEn/fin_data_databricks) repo - from performing API calls to merging the data into Staging Delta tables.

![image](https://user-images.githubusercontent.com/58121577/183256061-7e42d7c8-9b85-4d18-999a-0ab6f7b50207.png)

At present the ADF has a single pipeline - **marketstack_api**. The pipeline has the following parameters:

`file_path` : Path to a location on Azure Data Lake containing the YAML configuration file. A sample path would look like this: _Config/config_dim_tables_biweekly.yml_

YAML config files are saved for source control purposes in the [configFiles](https://github.com/SenYaEn/fin_data_adf/tree/main/fin-data-adf/configFiles) folder.

`notebook_base_path` : A string path in case if a notebook is located in an individual user's workspace (e.g. /Users/user@email.com'). Default value should be '/'.

`update_tables_main_notebook_path` : A string path to the main Databricks notebook: _/fin_data/update_tables_main_
