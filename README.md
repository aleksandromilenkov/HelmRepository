# 🧭 HelmRepository

This repository hosts **Helm charts** that can be used to deploy applications to Kubernetes.  
It is structured as a **Helm chart repository**, served via **GitHub Pages**, and can be added directly using the `helm repo add` command.

---

## 📦 Available Charts

| Chart               | Version | Description                                           |
|--------------------|---------|-------------------------------------------------------|
| `mymicroserviceapp` | 0.1.x   | A Helm chart for deploying the MyMicroservice app    |
| `ourchart`          | 0.1.0   | A basic sample Helm chart                             |

The packaged `.tgz` files and the `index.yaml` file are stored in the root of this repository so Helm can consume them.

---

## 🚀 Adding the Repository to Helm

Add the repository:

```bash
helm repo add myrepo https://aleksandromilenkov.github.io/HelmRepository
helm repo update
```

Verify available charts:

```bash
helm search repo myrepo
```

---

## 📥 Installing a Chart

Install the latest version of `mymicroserviceapp`:

```bash
helm install mymicroservice myrepo/mymicroserviceapp
```

Install a specific version:

```bash
helm install mymicroservice myrepo/mymicroserviceapp --version 0.1.1
```

Uninstall the release:

```bash
helm uninstall mymicroservice
```

---

## 🏗️ Repository Structure

```
HelmRepository/
├── index.yaml
├── mymicroserviceapp-0.1.0.tgz
├── mymicroserviceapp-0.1.1.tgz
├── ourchart-0.1.0.tgz
└── README.md
```

`index.yaml` is generated using:

```bash
helm repo index . --url https://aleksandromilenkov.github.io/HelmRepository
```

---

## 🔄 Updating Charts

1. Package the chart:

    ```bash
    helm package <chart-folder>
    ```

2. Copy the `.tgz` file into this repository.

3. Regenerate the index:

    ```bash
    helm repo index . --url https://aleksandromilenkov.github.io/HelmRepository
    ```

4. Commit and push:

    ```bash
    git add .
    git commit -m "Add new chart version"
    git push
    ```

---

## 🌐 GitHub Pages Hosting

This repository is served via GitHub Pages:

```
https://aleksandromilenkov.github.io/HelmRepository/
```

---

## 📚 More About Helm

Helm documentation: https://helm.sh/docs/
