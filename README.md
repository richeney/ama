# Azure Monitor Agent and Data Collection Rules

Reference repo using a baseline DCR called `default_data_collection_rule` using the default example used in the [create REST API call for data collection rules](https://docs.microsoft.com/en-gb/rest/api/monitor/data-collection-rules/create#create-or-update-data-collection-rule).

## Log Analytics workspace

All deployment a pre-existing Log Analytics workspace and take the workspace ID as a parameter.

1. Resource group

    ```bash
    az group create --name ama --location westeurope
    ```

1. Create the `ama` workspace

    ```bash
    az monitor log-analytics workspace create --name ama-workspace --resource-group ama --location westeurope
    ``

1. Set a variable to the resource ID

    ```bash
    workspaceId=$(az monitor log-analytics workspace show --name ama-workspace --resource-group ama --query id --output tsv)
    ```
