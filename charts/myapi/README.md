# Define variables
ALIAS=Charlessin-k8s-summit-2024
ORGNAME=Charlessin
CHART_NAME=myapi
REPO_NAME=k8s-summit-2024

# Use sed to replace placeholders and redirect to the chart
sed -e "s/<alias>/$ALIAS/g" \
    -e "s/<orgname>/$ORGNAME/g" \
    -e "s/<chart-name>/$CHART_NAME/g" \
    -e "s/helm-charts/$REPO_NAME/g" << 'EOT' > charts/$CHART_NAME/README.md

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

    helm repo add <alias> https://<orgname>.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve the latest versions of the packages.  You can then run `helm search repo <alias>` to see the charts.

To install the <chart-name> chart:

    helm install <orgname>-<chart-name> <alias>/<chart-name>

To uninstall the chart:

    helm delete <orgname>-<chart-name>
EOT
