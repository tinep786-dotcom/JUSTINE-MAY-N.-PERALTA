# Storage Types Research

## Comparison of Cloud Storage Types

| Storage Type | Description | Primary Use Case | Cloud Provider Example |
|---|---|---|---|
| **Block Storage** | Splits data into fixed-size blocks, each with a unique address. Blocks are managed independently and attached to a single virtual machine like a raw hard disk, giving the OS full control over how data is organized on it. | Databases, boot volumes for VMs, and any application that needs low-latency, high-performance read/write access to structured data. | AWS EBS (Elastic Block Store) |
| **File Storage** | Organizes data in a traditional hierarchical structure of files and folders, accessed through a shared file system over a network. Multiple servers or users can mount and access the same file system at once. | Shared application data, content management systems, home directories, and workloads where several instances need simultaneous access to the same files. | AWS EFS (Elastic File System) |
| **Object Storage** | Stores data as discrete, self-contained "objects," each bundled with its data, metadata, and a unique identifier, inside a flat address space (no folder hierarchy). Accessed over HTTP via an API rather than a traditional file system. | Storing massive volumes of unstructured data such as images, videos, backups, and static website assets, especially at web scale. | AWS S3 (Simple Storage Service) |

## Why Object Storage Is the Right Choice

For a photo-sharing application expecting millions of user-uploaded images, Object Storage is the clear fit. Each photo can be stored as an independent object with rich metadata (upload date, user ID, file type) and retrieved instantly over a simple HTTP URL, which is exactly how modern web and mobile apps serve media. Unlike Block Storage, it scales virtually without limit and doesn't require the images to live inside any single server or container, so the data survives even if the web server itself is destroyed or redeployed. It's also more cost-effective at this scale than Block or File Storage, since providers charge per gigabyte stored rather than for a fixed-size attached volume.
