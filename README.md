# DevOps Development Container Image

A comprehensive development container image optimized for DevOps workflows, providing a pre-configured environment with essential tools and extensions for cloud-native development.

## 🚀 Overview

This repository creates and maintains a DevOps development container image that includes a curated set of tools commonly used in modern DevOps practices. The image is automatically built and published to GitHub Container Registry, making it easy to use in various development environments.

## 📦 What's Included

### Base Environment
- **Base Image**: Ubuntu (Microsoft DevContainers)
- **Docker-in-Docker**: Latest Docker with Moby support for containerized development

### Development Tools
- **Azure CLI**: Command-line interface for Azure services
- **Node.js**: JavaScript runtime for modern web development
- **Python**: Python programming language and ecosystem
- **Git**: Version control system
- **GitHub CLI**: Command-line interface for GitHub
- **Terraform**: Infrastructure as Code tool for cloud provisioning

### VS Code Extensions
- **Azure Resource Groups**: Manage Azure resources directly from VS Code
- **YAML**: Enhanced YAML language support
- **Terraform**: Syntax highlighting and IntelliSense for Terraform files

## 🛠️ Usage

### Using with VS Code Dev Containers

1. **Create a `.devcontainer/devcontainer.json` file in your project:**

```json
{
    "name": "DevOps Development Environment",
    "image": "ghcr.io/josiahsiegel/devops-image:latest"
}
```

2. **Open your project in VS Code and use the Command Palette:**
   - Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac)
   - Select "Dev Containers: Reopen in Container"

### Using with Docker

```bash
# Pull the latest image
docker pull ghcr.io/josiahsiegel/devops-image:latest

# Run interactively
docker run -it --rm ghcr.io/josiahsiegel/devops-image:latest

# Run with volume mounting for persistent development
docker run -it --rm -v $(pwd):/workspace ghcr.io/josiahsiegel/devops-image:latest
```

### Using with GitHub Codespaces

Create a `.devcontainer/devcontainer.json` file in your repository and reference this image. GitHub Codespaces will automatically use the pre-built image for faster startup times.

## 🎯 Use Cases

This development container is ideal for:

- **Cloud Infrastructure Development**: Terraform, Azure CLI, and related tools
- **DevOps Pipeline Development**: CI/CD workflows and automation scripts
- **Multi-language Development**: Python and Node.js projects
- **Container-based Development**: Docker-in-Docker for building and testing containers
- **Azure Development**: Pre-configured Azure tooling and extensions

## 🔄 Automatic Updates

The image is automatically maintained through:

- **Dependabot**: Weekly updates for Docker and GitHub Actions dependencies
- **GitHub Actions**: Automatic rebuilds on code changes
- **Latest Tool Versions**: Features are configured to use the latest stable versions

## 🏗️ Building Locally

To build the image locally:

```bash
# Clone the repository
git clone https://github.com/josiahsiegel/devops-image.git
cd devops-image

# Build using VS Code Dev Containers CLI
devcontainer build .

# Or build manually with Docker
docker build -t devops-image .devcontainer/
```

## 📋 Requirements

- **Docker**: Required for running the container
- **VS Code with Dev Containers extension**: For the best development experience
- **Git**: For cloning and version control

## 🔧 Customization

You can extend this image by:

1. **Creating a custom devcontainer.json** that inherits from this image
2. **Adding additional features** from the [DevContainers Feature registry](https://containers.dev/features)
3. **Installing additional tools** in your derived container

Example custom configuration:

```json
{
    "name": "Custom DevOps Environment",
    "image": "ghcr.io/josiahsiegel/devops-image:latest",
    "features": {
        "ghcr.io/devcontainers/features/kubectl-helm-minikube:1": {}
    },
    "customizations": {
        "vscode": {
            "extensions": [
                "ms-kubernetes-tools.vscode-kubernetes-tools"
            ]
        }
    }
}
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues and pull requests to improve the development container configuration.

## 📄 License

This project is open source and available under standard open source licensing terms.

## 🔗 Registry

The built image is available at: `ghcr.io/josiahsiegel/devops-image:latest`

## 📚 Additional Resources

- [Development Containers Documentation](https://containers.dev/)
- [VS Code Dev Containers Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
- [GitHub Codespaces Documentation](https://docs.github.com/en/codespaces)
- [Docker Documentation](https://docs.docker.com/)