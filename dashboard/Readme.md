# Create dashboard by ARM template

```shell
az deployment group create --resource-group rg-nemedpet-dashboard --template-file dashboard-new-api.json
```

## Warning

The template uses intentionally the older API "2019-01-01-preview" to make it work with the dashboard definition files downloaded from portal.
Starting from 2020-09-01-preview the different structure of the JSON file defining the dashboard comes to play. To get the dashboard definition formatted according to the latest API use armclient get. More info in [fix_json_new_api.md](fix_json_new_api.md).

The value of lenses and parts is no longer object but with new API they are required to be the data type of list.

```json
{
  "type": "Microsoft.Portal/dashboards",
  "apiVersion": "2020-09-01-preview",
  "name": "string",
  "location": "string",
  "tags": {
    "tagName1": "tagValue1",
    "tagName2": "tagValue2"
  },
  "properties": {
    "lenses": [         <<< list
      {
        "metadata": {},
        "order": "int",
        "parts": [      <<< list
          {
            "metadata": {
              "type": "string"
              // For remaining properties, see DashboardPartMetadata objects
            },
            "position": {
              "colSpan": "int",
              "metadata": {},
              "rowSpan": "int",
              "x": "int",
              "y": "int"
            }
          }
        ]
      }
    ],
    "metadata": {}
  }
}
```

More information on how to convert the JSON file to meet the requirements for the API 2020-09-01-preview can be found in [fix_json_new_api.md](fix_json_new_api.md).
