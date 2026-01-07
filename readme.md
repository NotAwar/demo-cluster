# Self-hosted demo cluster

This kubernetes cluster is intended to demonstate some self-hosting capabilities in kubernetes.
For convenience, the setup includes services like flux operator to simplify deployment of applications.
The initial setup is primarily intended for local demo and testing of kagent using Ollama locally in a kind cluster.
With that being the case, some security best practices may be relaxed for convenience, such as using self-signed certificates.
This setup is not intended for production use without further hardening and security considerations.

## Included Applications

- [kagent](https://kagent.dev) - Kubernetes agent for LLMs and AI workloads
- [Ollama](https://ollama.com) - Local LLM hosting
- [cert-manager](https://cert-manager.io) - Certificate management in Kubernetes
- [flux](https://fluxcd.io) - GitOps operator for Kubernetes
- [flux controlplane](https://fluxcd.control-plane.io/) - Operator and control plane for flux

## Manual operations

For initial setup, some manual configuration steps are required, please see [notes](./note.md) for details.

## Setup

While most of this setup can be copied to run locally, this repo is currently not made to be run directly as-is.
When setting up a similar cluster, please ensure to adjust configurations such as namespaces, secrets, and certificates as needed for your environment.
The current setup is ran on Kubernetes in Docker and has some configuration to work around those limitations for a local setup.
