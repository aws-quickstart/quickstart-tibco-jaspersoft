# quickstart-tibco-jaspersoft
## TIBCO JasperReports Server on the AWS Cloud

This Quick Start deploys TIBCO JasperReports Server, a reporting and analytics server, on the Amazon Web Services (AWS) Cloud in about 35 minutes. Options include the deployment of a cluster or of a single instance.

This Quick Start is for developers, IT professionals, architects, and other technical users who plan to implement or extend their deployment of JasperReports Server to the AWS Cloud.

Using JasperReports Server, you can create, share, and manage reports, dashboards, and data visualizations. JasperReports Server can run as a standalone server, or it can be embedded into web applications. JasperReports Server is designed with automatic detection functionality for connecting to Amazon Relational Database Service (Amazon RDS), Amazon Redshift, and Amazon EMR. 

You can use the AWS CloudFormation templates included with the Quick Start to deploy TIBCO JasperReports Server into a new or existing virtual private cloud (VPC) in your AWS account. The Quick Starts automates the following:

- Deploying TIBCO JasperReports Server, cluster, in a new virtual private cloud (VPC)
- Deploying TIBCO JasperReports Server, cluster, in an existing VPC
- Deploying TIBCO JasperReports Server, single-instance, in a new VPC
- Deploying TIBCO JasperReports Server, single-instance, in an existing VPC

![Quick Start architecture for TIBCO JasperReports Server on the AWS Cloud](https://d0.awsstatic.com/partner-network/QuickStart/datasheets/tibco-jasperreports-server-on-aws-architecture-diagram.png)

For architectural details, best practices, and step-by-step instructions, see the [deployment guide](https://fwd.aws/m38X5) for TIBCO JasperReports Server on AWS.

## Deploying with Control Tower
This QuickStart can be deployed in a Control Tower environment. To accomplish this, we make use of [Customizations for AWS Control Tower](https://aws.amazon.com/solutions/implementations/customizations-for-aws-control-tower/?did=sl_card&trk=sl_card) solution. A folder labeled "ct" has been provided in the repository for this Quick Start to aid in the deployment.

After the [Customization for AWS Control Tower](https://aws.amazon.com/solutions/implementations/customizations-for-aws-control-tower/?did=sl_card&trk=sl_card) solution has been deployed, use the contents of the "ct" folder (located in the root of the GitHub repositoy) to customize your deployment.
```
└── ct
   ├── custom-control-tower-configuration
   │   └── manifest.yaml
   └── custom-control-tower-configuration.zip
```
The manifest.yaml file has been customized for this Quick Start. 

### Review the manifest file.

Open and review the *manifest.yaml* file

**region:** Ensure the _region_ attribute references the region where the Customization for AWS Control Tower has been deployed. (The default region is "us-east-1")

NOTE: There is a second _region_ attribute located under the _resources_ section, that attribute is used to define the region where the Quick Start will be deployed. 

#### Review the _resources_ section
**resource_file:** The _resource_file_ attribute points to the public S3 bucket for this Quick Start, if you are deploying from your own s3 bucket, update this reference appropriately.

NOTE: There are other methods for deploying this QuickStart using Customization for AWS Control Tower, we have chosen to make use of the public s3 repository to ensure a consistent code base across the different deployment options. Visit the [Customizations for AWS Control Tower](https://aws.amazon.com/solutions/implementations/customizations-for-aws-control-tower/?did=sl_card&trk=sl_card) solution page for additional information.

**parameters:** Update The _parameters_ attribute to suit your deployment. 

NOTE: Carefuly review and update these attributes, to ensure the deployment is successful.

**deployment_targets:** Ensure your _deployment_targets_ is configured for either your target account(s) or target OU(s)

**region:** Enter the _region_ where you wish to deploy the Quick Start. (The default region is "us-east-1")

### Upload the manifest file
Compress the "manifest.yaml" file and name it *custom-control-tower-configuration.zip*
Upload the *custom-control-tower-configuration.zip* to the s3 bucket that was created by the Customization for AWS Control Tower solution. (custom-control-tower-configuration-_accountnumber_-_region_)
The file upload will trigger the customized pipeline that will deploy the Quick Start to your target accounts.

Visit the [Customizations for AWS Control Tower](https://aws.amazon.com/solutions/implementations/customizations-for-aws-control-tower/?did=sl_card&trk=sl_card) solution page for additional information.


To post feedback, submit feature ideas, or report bugs, use the **Issues** section of this GitHub repo.
If you'd like to submit code for this Quick Start, please review the [AWS Quick Start Contributor's Kit](https://aws-quickstart.github.io/).
