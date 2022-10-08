Terraform is an infrastructure as code tool that allows you to define cloud and on-premises resources in human-readable configuration files that can be versioned, reused, and shared. After that, you can use a standardized workflow to provision and manage all of your infrastructure throughout its lifecycle. Terraform can manage both low-level components such as compute, storage, and networking resources and high-level components such as DNS entries and SaaS features.

**The state file**

You should keep your Terraform state file in a safe and convenient location. It is secure because it contains sensitive information. Central, because you may want to work on the same project with your entire team. Speaking of Azure, the best place to store it is in a Blob Storage Account, which Terraform supports by default. You must first create the Blob Storage account, which you can easily do with the scripts below.

**Secrets and IDs**

Terraform will require the credentials to access your state file if you use a Blob Storage Account to store it. Whether you run the CLI manually, as a script, or as part of a pipeline. You should not keep the credentials in your code! It is preferable to keep them in a safe place and retrieve them as needed. Because you work with Azure, Azure Vault may be the best option for you.

Below are some useful snippets for retrieving secrets from the Azure Vault and using them with Terraform.

**A service account**

Depending on your needs, you may prefer to run Terraform on behalf of a service account rather than your personal account. You can then limit access rights to only those required for that specific deployment. However, you can grant your service account additional privileges that your personal account may not be granted.

This is accomplished by creating a Service Principal and configuring it in your Terraform configuration. Check out the script below to learn how to create a Service Principal.

**Some useful scripts**

You like the Infrastructure-as-Code principles that allow you to store everything in code, so you use Terraform. Creating the required dependencies manually in the Azure Portal is thus out of the question!

