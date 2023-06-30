# Azure
## The aim of the project is to configure and deploy a Kubernetes cluster in Azure Kubernetes Service and run applications in containers within the cluster.

The project aims to provide a scalable and reliable environment for running applications, leveraging the management and automation capabilities offered by Kubernetes. Deploying applications in the cluster allows for flexible scaling, resource management, monitoring, and application isolation. Additionally, the project focuses on utilizing various tools and features available in Azure, such as Azure CLI and kubectl, to effectively manage Kubernetes clusters and handle applications securely and efficiently.

The next part of the project involves introducing modifications and improvements. As part of these changes, a deployment of the application with two replicas has been added, which can contribute to improved performance and system reliability.

Furthermore, a Service has been added using a manifest. This Service will act as an access point to the application, enabling communication with it from outside the cluster.

Additionally, Git Actions have been implemented in the project, automating the process of building a new application image and pushing it to the repository.


1. Created Azure Kubernetes Service with 1 Node.
![Screenshot 1]

2. Established a connection to the cluster using az cli and kubectl.
(https://github.com/Ulania/Azure/assets/96245511/c00d6085-a872-47b6-adcf-cdbd73922563)

After executing the command:
'az aks get-credentials --resource-group lab10 --name lab_10_cluster',
information was returned indicating that the Kubernetes controller is running at the specified URL and that other components like CoreDNS and Metrics-server are also running.

3. Created a namespace - "test_namespace".
![Screenshot 3]

A namespace is an isolated area within the cluster where applications can be run.

4. Switched to the newly created namespace as the default.
![Screenshot 4]

Now all subsequent operations performed by kubectl will take place within the "test-namespace" namespace.

5. Created a secret in Kubernetes for the Docker Hub repository.
![Screenshot 5]

A secret is an encrypted credential used for pulling container images from the Docker Hub repository.

6. Added a pod (using a manifest) using an application from the Docker Hub.
![Screenshot 6]

![Screenshot 7]

7. Checked logs to ensure everything is working correctly.
![Screenshot 8]

8. Executed the describe command to confirm that everything is fine with the pod.
![Screenshot 9]

...

![Screenshot 10]

9. Performed port forwarding between the Kubernetes cluster and the local network.
![Screenshot 11]

10. Communicated with the application (sent a request).
Successfully redirected traffic from port 8080 on the local machine to port 80 inside the Kubernetes cluster, where a container with the nginx server is running.
Opened a web browser and entered the address http://localhost:8080 to see the page served by nginx.

![Screenshot 12]
--------------------------------------------------

11. Added a deployment (using a manifest) using an application from Docker Hub - 2 instances
![Screenshot 7]

12. Added a Service using a manifest
![Screenshot 8]

13. Added Git Actions, which, after building a new image and pushing it to the repository, will update the pod in Azure Kubernetes Service (AKS)
![Screenshot 9]

![Screenshot 10]


------------------------------------

14. Removed all components on Azure after completing the task.
![Screenshot 13]

![Screenshot 14]


