---

# Alteryx Workflow for Streamlining Student Placement Eligibility

## Project Overview

As a Placement Coordinator, a significant portion of my time was consumed by the highly repetitive and often error-prone task of filtering student responses to job opportunities. This manual process involved cross-referencing multiple criteria: **CGPA, backlog status, 10th and 12th percentages**, and most critically, ensuring students hadn't already been placed, adhering to our single placement policy.

To combat this inefficiency and enhance accuracy, I developed an **Alteryx workflow** that automates the eligibility screening process. This project significantly reduces manual effort, accelerates the placement cycle, and ensures only eligible candidates are presented to companies.

## Workflow Breakdown

The Alteryx workflow is designed with a clear, two-branch structure, converging to provide a final, filtered list of eligible candidates.

### Branch 1: Master Placed Candidates Data

The upper branch of the workflow focuses on our **master file of already placed candidates**. This branch includes several crucial steps:

* **Data Input:** The workflow starts by ingesting the master list of placed students.
* **Data Cleaning:** Essential cleaning steps are applied to this dataset to ensure consistency and accuracy. This might involve standardizing College ID formats, handling missing values, or correcting data entry errors.

### Branch 2: Student Responses to Opportunity XXXX

The lower branch processes the **student responses for a specific company opportunity (Company XXXX)**. Similar to the master file branch, this includes:

* **Data Input:** The raw student responses for Company XXXX are brought into the workflow.
* **Data Cleaning:** A series of cleaning operations are performed on this dataset. This includes steps like parsing relevant academic scores (CGPA, 10th/12th percentages), identifying backlog status, and standardizing student IDs.

### Combining and Filtering Data

The core of the workflow's logic lies in how these two cleaned branches are combined:

* **Join Tool:** A **Right Join** is performed, with the **cleaned master placed candidates file** as the **Left input (L)** and the **cleaned student responses file** as the **Right input (R)**. The join key for this operation is the **College ID**.
* **Filtering Logic:** By using a Right Join, the workflow effectively identifies and retains only those records from the student responses (Right input) whose College IDs **do not** have a match in the placed candidates file (Left input). In simpler terms, this ensures that **only candidates who are NOT already placed are included in the final output**. This is a critical step in enforcing our single placement policy.

### Manual Verification (Optional)

Understanding the importance of human oversight, especially when dealing with crucial data like student eligibility, a **Browse feature** has been incorporated after the filtering step. This allows for **manual verification** of the results if needed, providing an opportunity to quickly review the filtered list and ensure accuracy before proceeding.

## Benefits and Impact

This Alteryx workflow has transformed the student placement eligibility process by:

* **Saving Time:** Dramatically reduces the hours spent on manual data filtering and cross-referencing.
* **Increasing Accuracy:** Minimizes human error, ensuring precise identification of eligible candidates.
* **Ensuring Compliance:** Automatically enforces the single placement policy, preventing accidental double placements.
* **Improving Efficiency:** Accelerates the overall placement cycle, allowing us to respond to company needs more quickly.
* **Empowering Coordinators:** Frees up time for Placement Coordinators to focus on more strategic tasks like student counseling and industry engagement.

This project is a testament to how automation, even for seemingly simple tasks, can have a profound impact on operational efficiency and effectiveness.

I AM ACTUALLY USING THIS WORKFLOW TO FILTER DATA (AN UPDATED ONE WITH MORE CLARITY AND MINIMAL USE OF FUNCTIONS)
