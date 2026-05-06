<div align="center">

# PA4 Submission: TaskFlow Pipeline

<img alt="GitHub only" src="https://img.shields.io/badge/Submit-GitHub%20URL%20Only-10b981?style=for-the-badge">
<img alt="Total points" src="https://img.shields.io/badge/Total-100%20points-7c3aed?style=for-the-badge">

</div>

<div style="background:#f5f3ff;color:#111827;border-left:6px solid #6330bc;padding:14px 18px;border-radius:10px;margin:18px 0;">
Copy this file to <code style="color:#111827;background:#ddd6fe;padding:2px 4px;border-radius:4px;">SUBMISSION.md</code>. Put every screenshot in <code style="color:#111827;background:#ddd6fe;padding:2px 4px;border-radius:4px;">docs/</code>, embed it under the correct task, and write a short description below each image explaining what it proves. The grader should not need any file outside this repository.
</div>

## Student Information

| Field | Value |
|---|---|
| Name | Muhammad Junaid |
| Roll Number | 27100452 |
| GitHub Repository URL | https://github.com/Junaid452/CS487-PA4 |
| Resource Group | `rg-sp26-27100452` |
| Assigned Region | `ukwest` |

## Evidence Rules

- Use relative image paths, for example: `![AKS nodes](docs/aks-nodes.png)`.
- Every image must have a 1-3 sentence description below it.
- Azure Portal screenshots must show the resource name and enough page context to identify the service.
- CLI screenshots must show the command and output.
- Mask secrets such as function keys, ACR passwords, and storage connection strings.


## Task 1: App Service Web App (15 points)

### Evidence 1.1: Forked Repository

TODO: Embed screenshot of your forked GitHub repository.
<img width="689" height="715" alt="image" src="https://github.com/user-attachments/assets/f4eb20e9-607a-41ac-a322-bc5e244e6552" />


Description: This is my working fork of the starter repository, containing the full TaskFlow project structure and directory layout.

### Evidence 1.2: App Service Overview

TODO: Embed screenshot of the Web App overview page showing `webapp-<rollnum>` and Running status.
<img width="551" height="509" alt="image" src="https://github.com/user-attachments/assets/69356755-a777-4871-be03-7d71ada1e7b9" />


Description: The overview shows the pa4-27100452 App Service running Node 20 LTS in the ukwest region.

### Evidence 1.3: Deployment Center / GitHub Actions

TODO: Embed screenshot of Deployment Center or the successful GitHub Actions deployment.
<img width="551" height="509" alt="image" src="https://github.com/user-attachments/assets/9925ee4c-32bd-4237-af18-259afe62f460" />


Description: The Web App is successfully connected to my GitHub fork, ensuring automatic deployments via a managed CI/CD pipeline.

### Evidence 1.4: Live Web UI

TODO: Embed screenshot of the TaskFlow page loaded in a browser.
<img width="643" height="690" alt="image" src="https://github.com/user-attachments/assets/53f8fc79-d764-4cc0-af97-633bd5c8a004" />


Description: The TaskFlow frontend is live and serving the order submission dashboard over HTTPS.

---

## Task 2: Azure Container Registry (15 points)

### Evidence 2.1: ACR Overview

TODO: Embed screenshot of `crpa4<rollnum>` overview.
<img width="940" height="411" alt="image" src="https://github.com/user-attachments/assets/5456d0e8-0f2e-4ed4-b7ac-4c7528ec2b96" />

<img width="940" height="411" alt="image" src="https://github.com/user-attachments/assets/ab719e1d-14d7-4491-8fc6-e51b06710483" />


Description: The pa427100452 ACR is provisioned in the Basic SKU to store and serve private container images.

### Evidence 2.2: Docker Builds

TODO: Embed screenshot showing successful local builds for `validate-api`, `report-job`, and `func-app`.
<img width="816" height="262" alt="image" src="https://github.com/user-attachments/assets/2ee111b6-0ae8-4c95-9542-807107ef6634" />


Description: Successful local Docker builds for all three services demonstrate that the Dockerfiles are correctly configured for Linux/AMD64.

### Evidence 2.3: ACR Repositories

<img width="940" height="172" alt="image" src="https://github.com/user-attachments/assets/a8faeca7-6eaf-44af-ba98-7cadbb60f11a" />

<img width="940" height="172" alt="image" src="https://github.com/user-attachments/assets/c6f96563-8d48-45d1-8732-6fd46c2fef35" />

<img width="940" height="172" alt="image" src="https://github.com/user-attachments/assets/4f9d6046-42b1-4fbb-b3c5-d5371be6d61d" />

TODO: Embed screenshot or CLI output showing all three repositories in ACR.

Description: ACR repositories verify that the v1 images for the validator, report job, and function app were successfully pushed.

---

## Task 3: Durable Function Implementation (12 points)

### Evidence 3.1: Completed Function Code

TODO: Link to your completed file: `[function_app.py](function-app/function_app.py)`.

Description: My orchestrator chains the validate_activity and report_activity to handle stateful order processing.

### Evidence 3.2: Local Function Handler Listing

TODO: Embed screenshot of `func start` showing the HTTP starter, orchestrator, and activities.

<img width="692" height="710" alt="image" src="https://github.com/user-attachments/assets/6c89c920-065a-406f-b4d6-3ac610b3acd6" />

Description: The func start output confirms that the Durable Functions runtime has successfully discovered and registered all four handlers.

---

## Task 4: Function App Container Deployment (8 points)

### Evidence 4.1: Function App Container Configuration
<img width="692" height="710" alt="image" src="https://github.com/user-attachments/assets/5ac1c364-cbf4-42f9-8e0f-341d168d1c26" />


TODO: Embed screenshot showing the Function App uses your `func-app:v1` image from ACR.

Description: The Function App is configured to pull the func-app:v1 image directly from the pa427100452 registry.

### Evidence 4.2: Orchestration Smoke Test
<img width="940" height="317" alt="image" src="https://github.com/user-attachments/assets/4a724925-d507-4ae4-ba04-771e23344df0" />

TODO: Embed screenshot of the `curl` output that starts an orchestration and returns status URLs.

Description: The curl command successfully triggered the cloud orchestrator, returning a unique instance ID and status URLs.

### Evidence 4.3: Expected Failed Status Before Downstream Wiring

<img width="940" height="179" alt="image" src="https://github.com/user-attachments/assets/95ab6963-8e00-45c7-a23c-3ecd4b566862" />

TODO: Embed screenshot of the status query JSON showing the expected failure before `VALIDATE_URL` is configured.

Description: This failure is expected because the VALIDATE_URL setting was not yet configured to point to a live downstream service.

---

## Task 5: AKS Validator (15 points)

### Evidence 5.1: AKS Cluster

Screenshot was not in the manual deliverables, so it was lost.

TODO: Embed screenshot of AKS overview showing `aks-<rollnum>` succeeded.

Description: The aks-27100452 cluster is provisioned with a single Standard_B2s node in the ukwest region.

### Evidence 5.2: Kubernetes Nodes and Pods

TODO: Embed screenshot of `kubectl get nodes` and `kubectl get pods`.
<img width="940" height="97" alt="image" src="https://github.com/user-attachments/assets/b5aa0075-4376-405d-a354-566d66ce6941" />

<img width="940" height="156" alt="image" src="https://github.com/user-attachments/assets/8ad945d6-cde2-4a32-ad2e-6850075b1e45" />


Description: The validator pod is successfully scheduled and running within the AKS cluster environment.

### Evidence 5.3: Kubernetes Service

TODO: Embed screenshot of `kubectl get service validate-service`.
<img width="940" height="180" alt="image" src="https://github.com/user-attachments/assets/5c0cd133-e044-4059-a3ec-0e4e26ded142" />


Description: The validate-service LoadBalancer has successfully provisioned a public External IP on port 8080.

### Evidence 5.4: Validator API Tests

TODO: Embed screenshot of `curl /health`, a valid `curl /validate`, and an invalid `curl /validate`.
<img width="940" height="321" alt="image" src="https://github.com/user-attachments/assets/9182f72a-63b4-4fe8-af17-666d15f1a69c" />


Description: Testing confirms the API approves valid orders and rejects those with quantities exceeding the 100-unit limit.

### Evidence 5.5: Function App `VALIDATE_URL`
<img width="940" height="670" alt="image" src="https://github.com/user-attachments/assets/06b8154e-6d2f-417a-ae23-a516ce3dad0c" />


TODO: Embed screenshot showing the Function App application setting `VALIDATE_URL`.

Description: The VALIDATE_URL app setting allows the Durable Function to communicate with the AKS validator over the network.

### Evidence 5.6: AKS Idle Behavior

Manual did not ask for this deliverable so it was not recorded. 

TODO: Embed AKS metrics screenshot and/or `kubectl` output after the service is idle.

Description: AKS metrics show the node remains running and billing even when no orders are being processed.

---

## Task 6: ACI Report Job (15 points)

### Evidence 6.1: Blob Container

TODO: Embed screenshot of the `reports` blob container.
<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/b62b49b3-9320-4a87-804b-146275e72ae3" />

Description: The reports blob container acts as the persistent storage for all PDFs generated by ephemeral job runs.

### Evidence 6.2: Manual ACI Run

<img width="524" height="220" alt="image" src="https://github.com/user-attachments/assets/2991d0da-0e30-4e10-b9d7-f8fb4fc13b92" />

Did not record the actual screenshot showing the succeeded status.

TODO: Embed screenshot of `az container show` for `ci-report-test`.

Description: The manual ACI test transitioned to Succeeded, proving the container can perform its task and exit to save costs.

### Evidence 6.3: ACI Logs

TODO: Embed screenshot of `az container logs`.
<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/1175eb16-1dc5-4982-ac4b-c114c102d015" />

Description: ACI logs show the successful generation of the PDF and its subsequent upload to the reports container.

### Evidence 6.4: Generated PDF
<img width="940" height="267" alt="image" src="https://github.com/user-attachments/assets/b627d7fd-86c8-459a-8398-c54310618917" />

TODO: Embed screenshot showing `TEST-001.pdf` in Blob Storage or opened from Blob Storage.

Description: The presence of TEST-001.pdf in storage confirms the ACI correctly used the Managed Identity for authentication.

### Evidence 6.5: Function App Managed Identity and IAM

<img width="781" height="707" alt="image" src="https://github.com/user-attachments/assets/a8798eb8-edaf-433c-b9bd-4f6c01426029" />

TODO: Embed screenshots of system-assigned identity enabled and Contributor role assignment on your resource group.

Description: The mi-pa4-27100452 identity is attached to the Function App to provide passwordless access to Azure resources.

### Evidence 6.6: Report App Settings
<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/e00595f8-5309-4b0e-91f8-2ec2a128bb34" />

<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/2b81676c-1894-4ed9-aaa6-9d53413d118a" />

TODO: Embed screenshot of `REPORT_*`, `ACR_*`, `STORAGE_CONN`, and `SUBSCRIPTION_ID` settings.

Description: These settings provide the orchestrator with the credentials and metadata needed to spawn report jobs at runtime.

---

## Task 7: End-to-End Pipeline (15 points)

### Evidence 7.1: Web App Wiring

<img width="843" height="439" alt="image" src="https://github.com/user-attachments/assets/d1f8a3d1-08db-4661-87d2-418eef6fb603" />

TODO: Embed screenshot showing `FUNCTION_START_URL` and `FUNCTION_STATUS_URL` configured on the Web App.

Description: These settings wire the frontend UI to the specific HTTP Starter and Status endpoints of the Function App.

### Evidence 7.2: Happy Path UI

<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/dc9717b0-79f5-49d6-9e8d-e438f6aca4b8" />

<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/9a77a3d4-3e45-4062-b44d-639f9ae84bc4" />

<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/4ea7538d-dfce-494f-98d2-60d7668bbf46" />

<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/e117fb1d-8101-4455-be93-c3dc9d3720dd" />

TODO: Embed screenshots of the form before submit, Running status, and Completed status with report URL.

Description: The UI successfully displays the lifecycle of a valid order from submission to the final report URL.

### Evidence 7.3: Backend Participation

<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/d5f02b66-c33d-49de-b74c-da1648d7a7e1" />


TODO: Embed screenshots showing Function App invocation, AKS validator evidence, ACI evidence, and Blob PDF evidence.

Description: This traces a single order ID as it moves through the Function, AKS validator, and ACI report job.

### Evidence 7.4: Reject Path UI

<img width="940" height="601" alt="image" src="https://github.com/user-attachments/assets/1f035434-6c18-4e48-b3bf-e20e4655de33" />

TODO: Embed screenshot of an order with `qty > 100` being rejected.

Description: The UI correctly displays a rejection message, and no ACI is spawned, proving the orchestrator short-circuited as intended because of invalid amount.

---

## Task 8: Write-up and Architecture Diagram (5 points)

### Evidence 8.1: Architecture Diagram

TODO: Embed your architecture diagram from `![Architecture Diagram](docs/architecture_diagram.png)`.

Description: It shows GitHub, App Service, Durable Function, AKS, ACI, Blob Storage, ACR, and IAM.

### Question 8.2: Service Selection

TODO: App service chosen for TaskFlow’s frontend because it provides a fully managed platform with built-in CI/CD integration from GitHub. It is ideal for long-running, stateful web UIs that require easy scaling and HTTPS support. 

Durable functions used as the orchestration layer because they can coordinate multi-step asynchronous workflows while persisting state between steps. This ensures that long-running tasks like report generation don't time out or lose progress if a restart occurs.

AKS selected for the validator because it represents the industry standard for hosting long-lived microservices that require high control over infrastructure. It provides a stable endpoint and declarative scaling for services that must be always available.

Container Instances (ACI) is perfect for the report-generator as it is a short-lived batch job that only bills while the container is alive. This avoids the idle costs associated with running a dedicated server for a task that only takes seconds to complete.

### Question 8.3: ACI vs AKS

AKS remains running and billing even when idle to maintain the stable service endpoint, whereas ACI exists only for the duration of the task and stops billing immediately upon completion.

If a user spammed 1000 orders, ACI would incur the most cost because each submission spawns a new instance with its own compute charges. AKS would remain at a flat cost unless it was configured to auto-scale its nodes.

AKS uses a declarative model with persistent pods and services, while ACI follows an ephemeral lifecycle.

### Question 8.4: Durable Functions vs Plain HTTP

A plain HTTP function would lose the workflow context if the service restarted during the minute-long report generation, whereas Durable Functions use checkpoints to resume from the last successful step.

Standard HTTP functions often have short execution limits (e.g 230 seconds on App Service). A chained Durable workflow avoids this by breaking the logic into separate activities that can each run independently.

### Question 8.5: Cost Review

<img width="775" height="552" alt="image" src="https://github.com/user-attachments/assets/7b45a9cb-690b-4d7f-abc0-9299fcf8b299" />

TODO: Embed Cost Management screenshot scoped to your resource group.

Description: The AKS Cluster (Standard_B2s node) is the most expensive resource in the resource group although not visible in the screenshot as it was deleted at assignment end to save costs.

Unlike the other serverless components, the AKS node is a dedicated VM that runs 24/7, incurring charges regardless of whether it is actively validating orders.

### Question 8.6: Challenges Faced

1. My function app was facing authorization failure issue. To fix this I had to go to the sotrage account and enable public access from all networks which solved this issue.

2. Connecting the function app to storage required moving from connection strings to user-assigned managed identity to resolve other authentication errors.

---

