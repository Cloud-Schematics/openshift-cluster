# cluster
Simple template to deploy an IBM Cloud Kubernetes Openshift cluster


# Prerequisite 
1) Download [Terraform binary](https://www.terraform.io/downloads.html).  Unzip it and keep the binary in path ex- /usr/local/bin.
2) Download [IBM Cloud Provider Plugin](https://github.com/IBM-Bluemix/terraform-provider-ibm/releases). Unzip it and keep the binary in path in the same directory where you placed Terraform binary in previous step. You can also build the binary yourself. Please look into [documentation](https://github.com/IBM-Bluemix/terraform-provider-ibm/blob/master/README.md).

# To run this project on schematics execute the following steps:

- Log in to IBM Cloud.
- Navigate to IBM Cloud schematics from menu.
- Create a workspace.
- In the settings page configure the git URL with this repo.
- You can override default values that are in your variables.tf file.
- Run `Generate Plan` 
- Review the Plan and Run `Apply the Plan`
Click [here](https://cloud.ibm.com/docs/schematics?topic=schematics-workspace-setup#create-workspace) to get the detail description about creating workspaces in schematics.

# To run this project locally execute the following steps:

- Clone this project.
- You can override default values that are in your variables.tf file.
  - Alternatively these values can be supplied via the command line or environment variables, see https://www.terraform.io/intro/getting-started/variables.html.
  
  ## Environment Variables using IBMid credentials
  You'll need to export the following environment variables:

  - `IC_API_KEY` - your IBM Cloud api key

On OS X this is achieved by entering the following into your terminal, replacing the `<value>` characters with the actual values (remove the `<>`):
- `export IC_API_KEY=<value>`


# Variables

|Variable Name|Description|Default Value|
|-------------|-----------|-------------|
|machine_type| The type of the machine flavor|b3c.4x16| 
|hardware   |  The level of hardware isolation for your worker node|shared|
|datacenter|The datacenter to provision cluster |wdc04|
|default_pool_size| No of workers in default pool | 2 |
|private_vlan_id|The private vlan ID. Run ic ks vlans `datacenter` to retrieve vlans||
|public_vlan_id|The public vlan ID.Run ic ks vlans `datacenter` to retrieve vlans||
|kube_version|The desired Kubernetes openshift version of the created cluster.|4.3_openshift|