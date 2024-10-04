# OCI Resource Usage Policy

### Overview

OCI Resource Usage Policy is used to monitor the cores and clusters of OCI resources that are predefined for a user.

### Prerequisites

- Before adding the OCI Resource Usage Policy in the Template, ensure you have the following prerequisites:      
  
  Admin access to [CloudLabs Admin Portal](https://admin.cloudlabs.ai/) (If access is unavailable, kindly reach out to your point of contact or [CloudLabs Support](https://docs.cloudlabs.ai/RequestSupport)).

### Adding OCI Resource Usage Policy

1. Log in to the CL portal and navigate to the required tenant (WIZ). On the left-hand side of the page, you will see the Template section.

2. Navigate to the **Templates (1)** section in the left menu and click on the **edit (2)** button.

   ![](./img/01.png)

3. Scroll down to the **Usage Policy** section and provide the Usage Policy URL for the respective OCI resource. 
   
   ![](./img/02.png)

4. Then, click the **Submit** button.

   ![](./img/03.png)

### Usage Policy Uand Alerts Outputs

Below are the Resource Usage Policy and Alerts outputs for the respective resources.

1. **Instance:** The metric used is the **count of instances.**

   - Policy:

      ```
      [
        {
          "ResourceType": "OCI.Instance",
      
          "Parameter": [
            {
              "Name": "max-ocpu-cores",
      
              "Value": "1"
            },
      
            {
              "Name": "max-memory-gb",
      
              "Value": "32"
            },
      
            {
              "Name": "max-instance-count",
      
              "Value": "1"
            }
          ]
        }
      ] 
      ```

   - Output:

       Cloud Screenshot: 

       ![](./img/04.png)

       Alerts Received: 
        
       ![](./img/05.png)

   **Instance:** The metrics used are **OCPU Cores** and **Memory (GB).**

   - Output:

       Cloud Screenshot: 

       ![](./img/06.png)

       Alerts Received: 

       ![](./img/07.png)

2. **Bucket:** The metric used is the **Storage (GB).** 

   - Policy:

      ```
      [
        {
        "ResourceType": "OCI.Bucket",
        "Parameter": [
            {
            "Name": "max-storage-gb",
            "Value": "1"
            }
          ]
        }
      ]
      ```

   - Output:

       Cloud Screenshot: 

       ![](./img/08.png)

       Alerts : Not received.      

3. **Boot Volume:** The metric used is **VPUs (per GB)** and **Volume (GB).**

   - Policy:

      ```
      [
        {
          "ResourceType": "OCI.BootVolume",
          "Parameter": [
            {
              "Name": "max-volume-gb",
              "Value": "50"
            },
            {
              "Name": "max-vpus",
              "Value": "10"
            }
          ]
        }
      ]
      ```

   - Output:

       Cloud Screenshot: 

       ![](./img/09.png)

       Alerts Received: 
        
       ![](./img/10.png)

4. **Block Volume:** The metric used is **VPUs (per GB)** and **Volume (GB).**

   - Policy:

      ```
      [
        {
          "ResourceType": "OCI.Volume",
      
          "Parameter": [
            {
              "Name": "max-volume-gb",
      
              "Value": "50"
            },
      
            {
              "Name": "max-vpus",
      
              "Value": "10"
            }
          ]
        }
      ]
      ```

   - Output:

       Cloud Screenshot: 

       ![](./img/11.png)

       Alerts Received: 
        
       ![](./img/12.png)

5. **Boot Volume Backup:** The metric used is **Volume (GB).**

   - Policy:

      ```
      [
        {
          "ResourceType": "OCI.BootVolumeBackup",
          "Parameter": [
            {
              "Name": "max-volume-gb",
              "Value": "4"
            }
          ]
        }
      ]
      ```

   - Output:

       Cloud Screenshot: 

       ![](./img/13.png)

       Alerts Received: 
        
       ![](./img/14.png)

6. **Block Volume Backup:** The metric used is **Volume (GB).** 

   - Policy:

      ```
      [
        {
          "ResourceType": "OCI.VolumeBackup",
      
          "Parameter": [
            {
              "Name": "max-volume-gb",
      
              "Value": "6"
            }
          ]
        }
      ]
      
      ```

   - Output:

       Cloud Screenshot: 

       ![](./img/16.png)

       Alerts: Not Received.

     
7. **File System** : The metric used is **Storage (GB).**

   - Policy
   
     ```
     [
       {
          "ResourceType": "OCI.FileSystem",
          "Parameter": [
            {
              "Name": "max-storage-gb",
              "Value": "1"
             }
            ]
         }
      ]
     
     ```
   
   - Output
       Cloud Screenshot:
     
       ![](./img/18.png)
        
       Alerts:

       ![](./img/17.png)
     
   
    
8. Below is the usage policy URL for all OCI resources, which includes: VolumeBackup, BootVolumeBackup, BootVolume, Functions, DB System, Autonomous Database, PostgreSQL DB System, File System, Volume, Bucket, and Instance.

   - Policy URL: https://cloudlabs-prod-templates-s3.s3.amazonaws.com/WIZ/test/OCI+Usage+Policy/usagepolicyOCI.json 

   - Output:

       Alerts Received: 

       **PostgreSQL DB System, DB System, Autonomous Database:**
        
       ![](./img/15.png)




