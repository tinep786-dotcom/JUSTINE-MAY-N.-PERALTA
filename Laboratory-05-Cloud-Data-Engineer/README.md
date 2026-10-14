# Laboratory 05 – Cloud Data Engineer

## Mission Overview

This laboratory activity simulates a real-world cloud engineering task: a client building a photo-sharing application needs somewhere to store millions of user-uploaded images. Since containers are ephemeral and cannot be relied on for persistent storage, this lab covers deploying an S3-compatible Object Storage server (MinIO) using Docker, creating a secure storage bucket, and uploading a test file to prove the setup works.

## Objectives

- Differentiate between Block, File, and Object Storage.
- Deploy an S3-compatible Object Storage server (MinIO) using Docker.
- Access a cloud service via a web interface using port forwarding.
- Create a storage bucket and upload objects (files) to the cloud.
- Document cloud storage operations using Markdown.
- Continue expanding a professional GitHub Cloud Computing Portfolio.

## Tools Used

- **KillerCoda Playground** (Ubuntu/Docker environment)
- **Docker** — used to pull and run the MinIO container
- **MinIO** — S3-compatible object storage server
- **GitHub** — version control and portfolio hosting
- **Markdown** — documentation format

## Skills Learned

- Differentiating storage architectures (Block vs. File vs. Object) and matching them to real-world use cases.
- Deploying a containerized storage service with Docker, including port mapping and environment-variable-based configuration.
- Navigating a web-based admin console (MinIO Console) via port forwarding in a remote/cloud playground environment.
- Creating and managing storage buckets, and uploading objects through both a web UI and command-line workflow.
- Writing clear technical documentation for infrastructure work.
