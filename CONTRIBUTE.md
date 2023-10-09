# Adding and updating charts in this repository

## Adding a chart to the repository

To add a chart to the repository, do either of the following:

 1. Copy the complete chart from your development environment to the `/charts` folder.
 2. Create a new chart from templates generated by this helm command.

``` bash
cd charts
helm create one37id-[newchartname]
```

 1. Edit the `Chart.yaml` file to add/modify the chart name, version, and description etc.
 2. Modify the `values.yaml` file to add the default values for the chart.
 3. Add any additional `/template` files required by the chart.

## Publishing charts in the repository

To publish a chart in the repository, do the following:
 1. Create/Update the chart packages by running the following command from the `/packages` folder.

 ``` bash
 helm package ../charts/[chartname]
 ```

 2. Update the chart repo `index.yaml` file by running the following command from the `/` folder.

 ``` bash
  helm repo index --url https://fedoraman137.github.io/helm-test/ .
 ```

 3. Create a pull request to merge the chart into the `main` branch.
 4. After the pull request is merged, the chart is automatically published to the repository.