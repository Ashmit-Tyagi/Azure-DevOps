# Path-Based Routing with Azure Application Gateway and Custom Domain


## This project demonstrates how to host two separate web applications on Azure and route traffic to them using a single public endpoint. We deploy two Ubuntu Virtual Machines—each serving its own application—and place them behind an Azure Application Gateway


### Set up an Azure Application Gateway that routes HTTP requests based on the request path:


`http://<your-domain-or-AGW-IP>/app1  → forwarded to Backend Pool A`

`http://<your-domain-or-AGW-IP>/app2  → forwarded to Backend Pool B`


### 1.Create Two Virtual Machines


**VM1 – serves content for /app1**


**VM2 – serves content for /app2**


<img width="1864" height="1044" alt="Screenshot from 2025-09-14 14-59-51" src="https://github.com/user-attachments/assets/c5bcbddf-e452-4d70-8beb-82f9fe4e8ddb" />


#### Install a web server (e.g., Nginx) on both and configure different content for each path.



### 2. Prepare Backend Pools


Backend Pool A: add the private IP of VM1.

Backend Pool B: add the private IP of VM2.


### 3. Create an Azure Application Gateway


#### i. In the Azure Portal, create a new Application Gateway.

    - Tier: Standard v2 or WAF v2 (path-based routing is supported in v2).

    - Frontend IP: Public, Static.

    - Virtual Network: Use the same VNet as the VMs, but create a dedicated subnet for the gateway.

#### ii. During creation:

    - Add the two backend pools created earlier.

    - Create an HTTP setting using port 80.


<img width="1864" height="1044" alt="Screenshot from 2025-09-14 16-11-44" src="https://github.com/user-attachments/assets/fd213caa-ebd3-4603-93d8-9020208a8a8e" />


### 4. Configure Listener & Path-Based Routing


#### i. Create a listener:

    - Protocol: HTTP

    - Port: 80
  
    - Frontend IP: the static public IP of the gateway.


#### ii. Add a routing rule:


    - Path rule 1: /app1/* → forward to Backend Pool A.

    - Path rule 2: /app2/* → forward to Backend Pool B.


### 5.  Test the Routing


#### Use the gateway’s public IP to test:

`http://<AGW-IP>/app1` → **shows VM1 content.**




`http://<AGW-IP>/app2` → **shows VM2 content.**





### 6. Map Domain


#### i. In Azure DNS, create a DNS Zone for your domain.

#### ii. Update the registrar (e.g., Hostinger) to use the Azure DNS nameservers.

#### iii. In the DNS zone, add an A record pointing to the Application Gateway’s static public IP.


<img width="1864" height="1044" alt="Screenshot from 2025-09-14 16-11-33" src="https://github.com/user-attachments/assets/4a096cb1-48a3-4196-9d88-548b64f23319" />





<img width="1920" height="1200" alt="Screenshot from 2025-09-14 14-44-53" src="https://github.com/user-attachments/assets/02d39237-1040-4054-9160-bff5ebf46387" />



## In this task, I learned how to deploy multiple web applications on separate Azure Virtual Machines and manage traffic to them using Azure Application Gateway with path-based routing. I gained hands-on experience in setting up backend pools, listeners, and routing rules, as well as mapping a custom domain using Azure DNS. This setup is helpful because it allows multiple applications to be served from a single public endpoint, centralizes traffic management, and prepares the infrastructure for future scalability and HTTPS implementation.

