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

## Deploy with Control Tower
You can deploy TIBCO JasperReports Server in a customized AWS Control Tower environment to help you set up a secure, multi-account AWS environment using AWS best practices. For details, see [Customizations for AWS Control Tower](https://aws.amazon.com/solutions/implementations/customizations-for-aws-control-tower/). 

The root directory of the TIBCO JasperReports Server Quick Start repo includes a `ct` folder with a `manifest.yaml` file to assist you with the AWS Control Tower deployment. This file has been customized for the TIBCO JasperReports Server Quick Start. 

In the following sections, you will review and update the settings in this file and then upload it to the S3 bucket that is used for the deployment.

### Review the manifest.yaml file

1. Navigate to the root directory of the TIBCO JasperReports Server Quick Start, and open the `manifest.yaml` file, located in the `ct` folder.
2. Confirm that the `region` attribute references the Region where AWS Control Tower is deployed. The default Region is us-east-1. You will update the `regions` attribute (located in the *resources* section) in a later step. 
3. Confirm that the `resource_file` attribute points to the public S3 bucket for the TIBCO JasperReports Server Quick Start. Using a public S3 bucket ensures a consistent code base across the different deployment options. 

If you prefer to deploy from your own S3 bucket, update the path as needed.

4. Review each of the `parameters` attributes and update them as needed to match the requirements of your deployment. 
5. Confirm that the `deployment_targets` attribute is configured for either your target accounts or organizational units (OUs). 
6. For the `regions` attribute, add the Region where you plan to deploy the TIBCO JasperReports Server Quick Start. The default Region is us-east-1.

### Upload the manifest.yaml file
1. Compress the `manifest.yaml` file and name it `custom-control-tower-configuration.zip`.
2. Upload the `custom-control-tower-configuration.zip` file to the S3 bucket that was created for the AWS Control Tower deployment (`custom-control-tower-configuration-<accountnumber>-<region>`).

The file upload initiates the customized pipeline that deploys the Quick Start to your target accounts.

To post feedback, submit feature ideas, or report bugs, use the **Issues** section of this GitHub repo.
If you'd like to submit code for this Quick Start, please review the [AWS Quick Start Contributor's Kit](https://aws-quickstart.github.io/).
