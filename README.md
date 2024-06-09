Minikube and Kind Cluster Setup
Table of Contents
1. #prerequisites
2. #installing-minikube
3. #installing-kind-cluster
4. #configuring-kind-cluster
5. #conclusion

Prerequisites
- Windows 11 VM (or local machine)
- Docker Desktop installed (if you haven't already)
- Basic understanding of command-line interfaces (CLI)

Installing Minikube
Step 1: Install Docker Desktop
- Download the Docker Desktop installer from the official Docker website (https://docs.docker.com/desktop/install/windows-install/)
- Follow the installation instructions to install Docker Desktop on your Windows 11 VM
- Once installed, open the Docker Desktop application to verify it's working correctly

Step 2: Install Minikube
- Open a new PowerShell terminal as an administrator
- Run the following command to download the Minikube installer:

shell
curl -Lo minikube.exe 

- Move the installer to a directory of your choice (e.g., C:\minikube)
- Run the installer:

C:\minikube\minikube.exe install


Step 3: Verify Minikube Installation
- Run the following command to verify Minikube is installed correctly:

minikube version

This should output the version of Minikube installed.

Installing Kind Cluster
Step 1: Install Kind Binary
- Open a new PowerShell terminal as an administrator
- Run the following command to download the Kind binary:

curl -Lo kind.exe 

- Move the binary to a directory of your choice (e.g., C:\kind)
- Add the directory to your system's PATH environment variable

Step 2: Create a Kind Cluster
- Run the following command to create a new Kind cluster:

kind create cluster --name mycluster

This will create a new Kind cluster named "mycluster".

Step 3: Verify Kind Cluster Installation
- Run the following command to verify the Kind cluster is up and running:

kind get nodes

This should output the nodes in your Kind cluster.

Configuring Kind Cluster
Step 1: Create a Kind Configuration File
- Create a new YAML file (e.g., kind-config.yaml) with the following contents:

kind: Cluster
apiVersion: 
nodes:
- role: control-plane
  extraPortMappings:
  - containerPort: 30080
    hostPort: 30080
    protocol: TCP

This configuration file defines a simple Kind cluster with a control plane node and an exposed port for accessing the Kubernetes dashboard.

Step 2: Apply the Configuration
- Run the following command to apply the configuration to your Kind cluster:

shell
kind apply kind-config.yaml

This will apply the configuration to your Kind cluster.

Conclusion
You have now successfully installed Minikube and Kind cluster on your Windows 11 VM. You have also configured a basic Kind cluster with an exposed port for accessing the Kubernetes dashboard.# windows-VM-MInikube-kindcluster-setup
