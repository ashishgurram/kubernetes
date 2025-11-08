# Kubernetes Learning Workspace

This repository contains organized resources, manifests, and documentation to help you learn and experiment with Kubernetes.


## Structure

- `example-manifests/` — Example Kubernetes YAML manifests for deployments and services.
- `demo-kubernetes-components/` — Additional demo manifests and resources, e.g., for MongoDB and other components (for experimentation and reference).
- `docs/` — Markdown documentation covering Kubernetes concepts, architecture, commands, and configuration. Start with `docs/index.md` for a recommended reading order.
- `images/` — All images referenced in the documentation.

## Getting Started

1. **Read the Docs:**
   - Begin with `docs/index.md` to follow the suggested learning path.
2. **Try the Manifests:**
   - Apply the manifests in `example-manifests/` to your Kubernetes cluster using `kubectl apply -f <file>`.
3. **Explore and Experiment:**
   - Edit the YAML files and see how changes affect your cluster.

## Requirements
- Kubernetes cluster (local with Minikube or remote)
- `kubectl` installed

## Contributing
Feel free to open issues or submit pull requests to improve the documentation or add new examples.

---

Happy learning!
