# How to setup Terraform for OCI


### Pre-requiste

1. Computer to run terraform

2. OCI Tenancy :
Login to Oracle Cloud Infrastructure (The administrator should be able to give you access and create credentials for you in respective tenancy) and get OCID (Oracle cloud Id) of your tenancy.

3. API SSL Key :
SSL key pair is required to enable Terraform to connect to the OCI API under your identity. Follow below steps to generate the SSL key pair:
   
   * Lets create a directory named oci-ssl-key and execute below commands:
openssl genrsa -out oci_api_key.pem 2048

   * set file access
chmod 600 oci_api_key.pem

   * Generate the public half of the key pair
openssl rsa -pubout -in oci_api_key.pem -out oci_api_key_public.pem

   * The generated public key needs to be added to your user account in the OCI console

   * After adding public key, the fingerprint is listed in the “API Keys” list. keep the fingerprint for later use.

4. Download terraform
Download Terraform from the HashiCorp download page. Ensure that you download the correct binary file for your system.

### Installing Terraform ~> 0.12
   brew install terraform (make sure you have homebrew installed)
   or also you can do manually as :
   Download binary zip from HashiCorp download page.
   Unzip and copy binary file in the path such as /usr/local/bin/terraform
   cp $HOME/Downloads/terraform /usr/local/bin/
   Verify the terraform installation (terraform v0.12.24 version used)
   terraform --version




