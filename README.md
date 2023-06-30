# Azure
## The aim of the project is to configure and deploy a Kubernetes cluster in Azure Kubernetes Service and run applications in containers within the cluster.

The project aims to provide a scalable and reliable environment for running applications, leveraging the management and automation capabilities offered by Kubernetes. Deploying applications in the cluster allows for flexible scaling, resource management, monitoring, and application isolation. Additionally, the project focuses on utilizing various tools and features available in Azure, such as Azure CLI and kubectl, to effectively manage Kubernetes clusters and handle applications securely and efficiently.

The next part of the project involves introducing modifications and improvements. As part of these changes, a deployment of the application with two replicas has been added, which can contribute to improved performance and system reliability.

Furthermore, a Service has been added using a manifest. This Service will act as an access point to the application, enabling communication with it from outside the cluster.

Additionally, Git Actions have been implemented in the project, automating the process of building a new application image and pushing it to the repository.


1. Created Azure Kubernetes Service with 1 Node.
![1](https://github.com/Ulania/Azure/assets/96245511/80b2ca0f-f40c-4f28-881c-cf00c7f53ca1)

2. Established a connection to the cluster using az cli and kubectl.
![2](https://github.com/Ulania/Azure/assets/96245511/d643fb66-7537-4e48-92af-7139acdcd99b)

After executing the command:
'az aks get-credentials --resource-group lab10 --name lab_10_cluster',
information was returned indicating that the Kubernetes controller is running at the specified URL and that other components like CoreDNS and Metrics-server are also running.

3. Created a namespace - "test_namespace".
[3](https://github.com/Ulania/Azure/assets/96245511/8cde50e8-12c0-4e2d-9423-ee55011f1073)

A namespace is an isolated area within the cluster where applications can be run.

4. Switched to the newly created namespace as the default.
![4](https://github.com/Ulania/Azure/assets/96245511/12454d00-1f0a-4765-9312-977c26bd7c8d)

Now all subsequent operations performed by kubectl will take place within the "test-namespace" namespace.

5. Created a secret in Kubernetes for the Docker Hub repository.
![5](https://github.com/Ulania/Azure/assets/96245511/a359fced-0b9d-4c91-9b49-b0b20d4ed512)

A secret is an encrypted credential used for pulling container images from the Docker Hub repository.

6. Added a pod (using a manifest) using an application from the Docker Hub.
![6](https://github.com/Ulania/Azure/assets/96245511/d8804a76-190d-4257-8d00-f425e48a2356)

![7](https://github.com/Ulania/Azure/assets/96245511/6a0b081f-b184-447c-97d6-b60700676d10)

7. Checked logs to ensure everything is working correctly.
![8](https://github.com/Ulania/Azure/assets/96245511/537687ec-f7d6-4dc4-95c1-519daa20492b)

8. Executed the describe command to confirm that everything is fine with the pod.
![9](https://github.com/Ulania/Azure/assets/96245511/05d1f1f7-1b25-4e54-8cc0-f7c7883340b7)

...

![10](https://github.com/Ulania/Azure/assets/96245511/7dc15806-c00f-4f2c-9bec-f3e6a63aac3f)

9. Performed port forwarding between the Kubernetes cluster and the local network.
![11](https://github.com/Ulania/Azure/assets/96245511/c6b99780-bdc5-4708-a0e2-7e718ed61d38)

10. Communicated with the application (sent a request).
Successfully redirected traffic from port 8080 on the local machine to port 80 inside the Kubernetes cluster, where a container with the nginx server is running.
Opened a web browser and entered the address http://localhost:8080 to see the page served by nginx.

![12](https://github.com/Ulania/Azure/assets/96245511/b379a8c0-6d10-4dbb-a7dc-fa1f27b3410a)

11. Added a deployment (using a manifest) using an application from Docker Hub - 2 instances
![7](https://github.com/Ulania/Azure/assets/96245511/c170f930-7b50-4912-919c-73e8f9dc13f0)

12. Added a Service using a manifest
![8](https://github.com/Ulania/Azure/assets/96245511/aa5cab9b-2422-4313-a329-db5da772a000)

13. Added Git Actions, which, after building a new image and pushing it to the repository, will update the pod in Azure Kubernetes Service (AKS)
![9](https://github.com/Ulania/Azure/assets/96245511/df2e20db-b78b-4127-8305-4453512c8779)

![10](https://github.com/Ulania/Azure/assets/96245511/68d2d046-0504-4fd8-8dbf-20cff900a604)

14. Removed all components on Azure after completing the task.
![13](https://github.com/Ulania/Azure/assets/96245511/e05108a8-efa5-4d28-ae05-059c59ba054f)

![14](https://github.com/Ulania/Azure/assets/96245511/44588358-54bb-493e-9d0c-185cc1fa0c97)


