## Objective

Youtube Demo: https://youtu.be/q-sloyiKO6s 

Build a **serverless image metadata processing pipeline** using **Azure Durable Functions** in **Python**. This assignment challenges you to use **blob triggers**, **activity functions**, and **output bindings**, and to **deploy** a complete solution to Azure. You'll simulate a real-world event-driven system.

---

## Scenario

A fictional content moderation team wants to analyze the metadata of user-uploaded images. Your Durable Functions app should:

- Automatically **trigger** when a new image is uploaded to blob storage.
- **Extract metadata** (e.g., file size, format, dimensions).
- **Store the metadata** in an Azure SQL Database.

---

## Workflow Requirements

### Step 1: Blob Trigger (Client Function)

- Create a blob-triggered function that starts the orchestration.
- The blob container (e.g., `images-input`) should accept `.jpg`, `.png`, or `.gif` images.

### Step 2: Orchestrator Function

- The orchestrator should:
  1. Call an activity function to extract metadata from the image.
  2. Call a second activity function to store that metadata in Azure SQL DB via output binding.

### Step 3: Activity Function – Extract Metadata

- Extract the following from each image:
  - File name
  - File size in KB
  - Width and height (in pixels)
  - Image format (e.g., JPEG, PNG)

### Step 4: Activity Function – Store Metadata

- Use **Azure SQL output binding** to store the image metadata.
