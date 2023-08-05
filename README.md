# ARO-automation
Azure RedHat Openshift Builder

## After Buildup

You can log into the cluster using the kubeadmin user. Run the following command to find the password for the kubeadmin user.

az aro list-credentials \
  --name $CLUSTER \
  --resource-group $RESOURCEGROUP
The following example output shows what the password will be in kubeadminPassword.

{
  "kubeadminPassword": "<generated password>",
  "kubeadminUsername": "kubeadmin"
}
You can find the cluster console URL by running the following command, which will look like https://console-openshift-console.apps.<random>.<region>.aroapp.io/.

 az aro show \
    --name $CLUSTER \
    --resource-group $RESOURCEGROUP \
    --query "consoleProfile.url" -o tsv
Launch the console URL in a browser and login using the kubeadmin credentials.
