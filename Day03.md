
# Day 03 – Container Image and Image Registry

## Introduction to Containers
Containers are lightweight and portable units that package an application along with all its dependencies such as libraries, configuration files, and runtime.

Containers ensure that an application runs the same way in different environments such as development, testing, and production.

Example container platforms:
- Docker
- Podman

---

## What is a Container Image?

A container image is a lightweight, standalone, and executable package that includes everything required to run an application.

It contains:
- Application code
- Runtime environment
- System libraries
- Dependencies
- Configuration files

Container images are **read-only templates** used to create containers.

Example:
A Docker image for a Python web application includes Python runtime, required libraries, and the application code.

---

## Image vs Container

Container Image:
- Blueprint or template
- Used to create containers
- Stored in an image registry

Container:
- Running instance of an image
- Executes the application

Example:
If an image is like a **class**, then a container is like an **object** created from that class.

---

## Layers in Container Images

Container images are built in layers.

Each instruction in a Dockerfile creates a new layer.

Example layers:
1. Base OS layer
2. Language runtime layer
3. Application dependencies
4. Application code

Advantages of layered images:
- Faster builds
- Efficient storage
- Layer reuse

---

## What is an Image Registry?

An image registry is a storage and distribution system for container images.

It allows developers to:
- Store container images
- Share images with teams
- Download images for deployment

Image registries are similar to **GitHub but for container images**.

---

## Types of Image Registries

### Public Registry
Anyone can access and download images.

Example:
Docker Hub

### Private Registry
Access is restricted to specific users or organizations.

Used by companies for internal applications.

Examples:
- AWS Elastic Container Registry (ECR)
- Google Container Registry (GCR)
- Azure Container Registry (ACR)

---

## Example Workflow

1. Developer creates an application
2. Builds a container image using Docker
3. Pushes the image to an image registry
4. Deployment systems pull the image
5. Containers are created from the image

---

## Benefits of Container Images

- Consistent application environment
- Faster deployment
- Easy scalability
- Portability across systems

---

## Conclusion

Container images are the foundation of containerized applications. Image registries store and distribute these images, enabling efficient deployment in DevOps and cloud environments.