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
| Name | TODO |
| Roll Number | TODO |
| GitHub Repository URL | TODO |
| Resource Group | `rg-sp26-TODO` |
| Assigned Region | TODO: `uaenorth` or `ukwest` |

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


Description: TODO: Explain that this is your working fork and that it contains the PA4 starter structure.

### Evidence 1.2: App Service Overview

TODO: Embed screenshot of the Web App overview page showing `webapp-<rollnum>` and Running status.
<img width="551" height="509" alt="image" src="https://github.com/user-attachments/assets/69356755-a777-4871-be03-7d71ada1e7b9" />


Description: TODO: State the resource group, region, runtime, and public URL.

### Evidence 1.3: Deployment Center / GitHub Actions

TODO: Embed screenshot of Deployment Center or the successful GitHub Actions deployment.
<img width="551" height="509" alt="image" src="https://github.com/user-attachments/assets/9925ee4c-32bd-4237-af18-259afe62f460" />


Description: TODO: Explain how the Web App is connected to your GitHub fork.

### Evidence 1.4: Live Web UI

TODO: Embed screenshot of the TaskFlow page loaded in a browser.
<img width="643" height="690" alt="image" src="https://github.com/user-attachments/assets/53f8fc79-d764-4cc0-af97-633bd5c8a004" />


Description: TODO: Explain that the App Service is serving the frontend successfully.

---

## Task 2: Azure Container Registry (15 points)

### Evidence 2.1: ACR Overview

TODO: Embed screenshot of `crpa4<rollnum>` overview.
<img width="940" height="411" alt="image" src="https://github.com/user-attachments/assets/5456d0e8-0f2e-4ed4-b7ac-4c7528ec2b96" />

<img width="940" height="411" alt="image" src="https://github.com/user-attachments/assets/ab719e1d-14d7-4491-8fc6-e51b06710483" />


Description: TODO: Identify the registry SKU and resource group.

### Evidence 2.2: Docker Builds

TODO: Embed screenshot showing successful local builds for `validate-api`, `report-job`, and `func-app`.
<img width="816" height="262" alt="image" src="https://github.com/user-attachments/assets/2ee111b6-0ae8-4c95-9542-807107ef6634" />


Description: TODO: Explain which folder produced each image.

### Evidence 2.3: ACR Repositories

TODO: Embed screenshot or CLI output showing all three repositories in ACR.

Description: TODO: Confirm `validate-api:v1`, `report-job:v1`, and `func-app:v1` were pushed.
<img width="940" height="172" alt="image" src="https://github.com/user-attachments/assets/a8faeca7-6eaf-44af-ba98-7cadbb60f11a" />

<img width="940" height="172" alt="image" src="https://github.com/user-attachments/assets/c6f96563-8d48-45d1-8732-6fd46c2fef35" />

<img width="940" height="172" alt="image" src="https://github.com/user-attachments/assets/4f9d6046-42b1-4fbb-b3c5-d5371be6d61d" />

---

## Task 3: Durable Function Implementation (12 points)

### Evidence 3.1: Completed Function Code

TODO: Link to your completed file: `[function_app.py](function-app/function_app.py)`.

Description: TODO: Summarize how your orchestrator chains validation and report generation.

### Evidence 3.2: Local Function Handler Listing

TODO: Embed screenshot of `func start` showing the HTTP starter, orchestrator, and activities.
<img width="692" height="710" alt="image" src="https://github.com/user-attachments/assets/6c89c920-065a-406f-b4d6-3ac610b3acd6" />



Description: TODO: Explain that the Durable Functions runtime discovered your handlers.

---

## Task 4: Function App Container Deployment (8 points)

### Evidence 4.1: Function App Container Configuration
<img width="692" height="710" alt="image" src="https://github.com/user-attachments/assets/5ac1c364-cbf4-42f9-8e0f-341d168d1c26" />


TODO: Embed screenshot showing the Function App uses your `func-app:v1` image from ACR.

Description: TODO: State the Function App name and image URI.

### Evidence 4.2: Orchestration Smoke Test
<img width="940" height="317" alt="image" src="https://github.com/user-attachments/assets/4a724925-d507-4ae4-ba04-771e23344df0" />


TODO: Embed screenshot of the `curl` output that starts an orchestration and returns status URLs.

Description: TODO: Explain what the returned `id` and `statusQueryGetUri` prove.

### Evidence 4.3: Expected Failed Status Before Downstream Wiring

<img width="940" height="179" alt="image" src="https://github.com/user-attachments/assets/95ab6963-8e00-45c7-a23c-3ecd4b566862" />

TODO: Embed screenshot of the status query JSON showing the expected failure before `VALIDATE_URL` is configured.

Description: TODO: Explain why this failure is expected at this stage.

---

## Task 5: AKS Validator (15 points)

### Evidence 5.1: AKS Cluster

TODO: Embed screenshot of AKS overview showing `aks-<rollnum>` succeeded.

Description: TODO: State node count, node size, region, and resource group.

### Evidence 5.2: Kubernetes Nodes and Pods

TODO: Embed screenshot of `kubectl get nodes` and `kubectl get pods`.
<img width="940" height="97" alt="image" src="https://github.com/user-attachments/assets/b5aa0075-4376-405d-a354-566d66ce6941" />

<img width="940" height="156" alt="image" src="https://github.com/user-attachments/assets/8ad945d6-cde2-4a32-ad2e-6850075b1e45" />


Description: TODO: Explain that the validator pod is scheduled and running.

### Evidence 5.3: Kubernetes Service

TODO: Embed screenshot of `kubectl get service validate-service`.
<img width="940" height="180" alt="image" src="https://github.com/user-attachments/assets/5c0cd133-e044-4059-a3ec-0e4e26ded142" />


Description: TODO: Identify the external IP and port exposed by the LoadBalancer.

### Evidence 5.4: Validator API Tests

TODO: Embed screenshot of `curl /health`, a valid `curl /validate`, and an invalid `curl /validate`.
<img width="940" height="321" alt="image" src="https://github.com/user-attachments/assets/9182f72a-63b4-4fe8-af17-666d15f1a69c" />


Description: TODO: Explain the accepted path and the `qty > 100` rejection rule.

### Evidence 5.5: Function App `VALIDATE_URL`
<img width="940" height="670" alt="image" src="https://github.com/user-attachments/assets/06b8154e-6d2f-417a-ae23-a516ce3dad0c" />


TODO: Embed screenshot showing the Function App application setting `VALIDATE_URL`.

Description: TODO: Explain how the Durable Function reaches the AKS validator.

### Evidence 5.6: AKS Idle Behavior

TODO: Embed AKS metrics screenshot and/or `kubectl` output after the service is idle.

Description: TODO: Explain that the AKS node remains running even when there are no orders.

---

## Task 6: ACI Report Job (15 points)

### Evidence 6.1: Blob Container

TODO: Embed screenshot of the `reports` blob container.
<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/b62b49b3-9320-4a87-804b-146275e72ae3" />


Description: TODO: Explain where generated PDFs are stored.

### Evidence 6.2: Manual ACI Run

TODO: Embed screenshot of `az container show` for `ci-report-test`.

Description: TODO: State the final container state and why the job exits.

### Evidence 6.3: ACI Logs

TODO: Embed screenshot of `az container logs`.
<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/1175eb16-1dc5-4982-ac4b-c114c102d015" />


Description: TODO: Explain what the report job printed after generating and uploading the PDF.

### Evidence 6.4: Generated PDF
<img width="940" height="267" alt="image" src="https://github.com/user-attachments/assets/b627d7fd-86c8-459a-8398-c54310618917" />

TODO: Embed screenshot showing `TEST-001.pdf` in Blob Storage or opened from Blob Storage.

Description: TODO: Explain how this proves the ACI wrote to storage.

### Evidence 6.5: Function App Managed Identity and IAM

TODO: Embed screenshots of system-assigned identity enabled and Contributor role assignment on your resource group.

Description: TODO: Explain why the Function App needs this permission to create ACIs.

### Evidence 6.6: Report App Settings
<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/e00595f8-5309-4b0e-91f8-2ec2a128bb34" />

<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/2b81676c-1894-4ed9-aaa6-9d53413d118a" />


TODO: Embed screenshot of `REPORT_*`, `ACR_*`, `STORAGE_CONN`, and `SUBSCRIPTION_ID` settings.

Description: TODO: Explain what each group of settings is used for. Mask secrets.

---

## Task 7: End-to-End Pipeline (15 points)

### Evidence 7.1: Web App Wiring

TODO: Embed screenshot showing `FUNCTION_START_URL` and `FUNCTION_STATUS_URL` configured on the Web App.

Description: TODO: Explain how the frontend starts and polls the Durable orchestration.

### Evidence 7.2: Happy Path UI

TODO: Embed screenshots of the form before submit, Running status, and Completed status with report URL.
<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/dc9717b0-79f5-49d6-9e8d-e438f6aca4b8" />
<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/9a77a3d4-3e45-4062-b44d-639f9ae84bc4" />
<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/4ea7538d-dfce-494f-98d2-60d7668bbf46" />

<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/e117fb1d-8101-4455-be93-c3dc9d3720dd" />



Description: TODO: Explain the valid order payload and final result.

### Evidence 7.3: Backend Participation
<img width="940" height="113" alt="image" src="https://github.com/user-attachments/assets/d5f02b66-c33d-49de-b74c-da1648d7a7e1" />


TODO: Embed screenshots showing Function App invocation, AKS validator evidence, ACI evidence, and Blob PDF evidence.

Description: TODO: Trace the same order ID across services.

### Evidence 7.4: Reject Path UI

TODO: Embed screenshot of an order with `qty > 100` being rejected.

Description: TODO: Explain why no report ACI should be created for this order.
<img width="940" height="601" alt="image" src="https://github.com/user-attachments/assets/1f035434-6c18-4e48-b3bf-e20e4655de33" />

---

## Task 8: Write-up and Architecture Diagram (5 points)

### Evidence 8.1: Architecture Diagram

TODO: Embed your architecture diagram from `docs/`.

Description: TODO: Confirm that it shows GitHub, App Service, Durable Function, AKS, ACI, Blob Storage, ACR, and IAM.

### Question 8.2: Service Selection

TODO: In 3-4 sentences each, explain why TaskFlow uses App Service, Durable Functions, AKS, and ACI for their specific roles.

### Question 8.3: ACI vs AKS

TODO: Compare idle behavior, cost behavior, and operational model for AKS and ACI using your screenshots.

### Question 8.4: Durable Functions vs Plain HTTP

TODO: Explain at least two problems that Durable Functions solves for this sequential workflow.

### Question 8.5: Cost Review

TODO: Embed Cost Management screenshot scoped to your resource group.

Description: TODO: Identify the most expensive resource and explain why.

### Question 8.6: Challenges Faced

TODO: Describe at least two real issues you hit and how you debugged them.



---

