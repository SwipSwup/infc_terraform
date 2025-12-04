# infc_terraform

## Q: Why do we need Terraform Cloud (or another backend) when we use CI/CD?

**Answer:**
Even with CI/CD, we need a remote backend (like Terraform Cloud) to store the **Terraform State** file.
*   **Persistence:** CI/CD runners are usually temporary. When the pipeline completes, Terraform loses track of the infrastructure if the state is locally stored on the runner.
*   **Locking:** When multiple CI/CD pipelines attempt to run simultaneously, it locks the state to avoid conflicts.