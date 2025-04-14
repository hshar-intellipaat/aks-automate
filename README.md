# AKS Cluster Manager Script

This is a simple interactive Bash script to manage an Azure Kubernetes Service (AKS) cluster.  
It supports:

- Creating a 3-node AKS cluster using Standard_B2s VM size
- Automatically setting up `kubectl` access
- Deleting the cluster and its resource group
- User-friendly prompts
- Minimal flags (`start` or `stop`)

---

## 🔧 Prerequisites

- Azure CLI installed and logged in (`az login`)
- `kubectl` installed
- Azure subscription with necessary permissions

---

## 📜 Usage

```bash
chmod +x manage-aks-cluster.sh
```

To **create** a new AKS cluster:
```bash
./manage-aks-cluster.sh start
```

To **delete** an existing AKS cluster and its resource group:
```bash
./manage-aks-cluster.sh stop
```

---

## 🚀 What It Does

### `start`:
- Prompts for:
  - Resource Group name
  - AKS Cluster name
  - Azure region
- Creates the resource group and AKS cluster
- Sets up `kubectl` context automatically

### `stop`:
- Prompts for:
  - Resource Group name
  - AKS Cluster name
- Asks for confirmation before deleting the entire resource group and associated resources

---

## 💡 Customization

- The VM size is fixed to `Standard_B2s`
- Node count is fixed to `3`
- You can modify these in the script if needed

---

## 📎 Example

```bash
./manage-aks-cluster.sh start
# Enter: myResourceGroup
# Enter: myAKSCluster
# Enter: eastus
```

---

## 📄 License

MIT
