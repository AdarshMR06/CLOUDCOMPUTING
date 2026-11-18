

\# LAB EVALUATION 2

\## Experiment: Pod Scheduling Using Node Affinity



\### 1. Objective

To deploy an application in a Kubernetes cluster and configure Node Affinity to schedule Pods on a specific worker node using node labels.



\### 2. Tools Used

\- Docker Desktop

\- Kubernetes

\- kubectl

\- kind

\- NGINX

\- Windows PowerShell



\### 3. Cluster Configuration

\- 1 Control Plane Node

\- 2 Worker Nodes



\### 4. Implementation Steps



\*\*Step 1: Check Kubernetes Nodes\*\*

```powershell

kubectl get nodes -o wide

```



\*\*Step 2: Assign Label to Worker Node\*\*

```powershell

kubectl label nodes kind-worker lab-role=preferred --overwrite

```



\*\*Step 3: Create Deployment YAML\*\*



File: affinity-deployment.yaml



\*\*Step 4: Apply Deployment\*\*

```powershell

kubectl apply -f "$HOME\\Desktop\\affinity-deployment.yaml"

```



\*\*Step 5: Verify Deployment\*\*

```powershell

kubectl get deployments

```



\*\*Step 6: Verify Pod Placement\*\*

```powershell

kubectl get pods -l app=affinity-demo -o wide

```



\### 5. Node Affinity Configuration



The deployment uses:

\- Key: lab-role

\- Operator: In

\- Value: preferred

\- Rule: requiredDuringSchedulingIgnoredDuringExecution



\### 6. Result

Two NGINX Pods were successfully deployed and scheduled on the labelled worker node, kind-worker.



\### 7. Screenshots

Refer to the screenshots folder for execution evidence.



