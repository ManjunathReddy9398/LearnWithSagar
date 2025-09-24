# ✅ `challenge_solution.md` 

# Season-1: Day 2: Advanced blob container Metadata Manipulation

**Name:** Manjunath K  
**Date:** 24 September 2025  

---

## ✅ Task 1 – Login to Azure

### Commands used:
```Powershell
az login
```

### Result:
Login into the Azure portal with pop on your personal mail id

---

## ✅ Task 2 – Create Resource Group & Storage Accounts

### Commands used:
```Powershell
# Variables
$RESOURCE_GROUP="rg-day2-demo"
$LOCATION="eastus"

# Create Resource Group
az group create --name $RESOURCE_GROUP --location $LOCATION

# Create Storage Accounts
az storage account create --name srechallengeeast --resource-group $RESOURCE_GROUP --location eastus --sku Standard_LRS
az storage account create --name srechallengewest --resource-group $RESOURCE_GROUP --location westus --sku Standard_LRS

```

### Result:
Created storage account using azure CLI

---

## ✅ Task 3 – Create Blob Containers & Upload Sample Data

### Commands used:
```Powershell
# Get connection strings
$eastConn = az storage account show-connection-string --name srechallengeeast --resource-group $RESOURCE_GROUP -o tsv
$westConn = az storage account show-connection-string --name srechallengewest --resource-group $RESOURCE_GROUP -o tsv

# Create blob containers
az storage container create --name logs --connection-string $eastConn
az storage container create --name backups --connection-string $westConn

# Upload dummy files (simulate data size)
echo "This is sample data" > sample.txt
az storage blob upload --account-name srechallengeeast --container-name logs --file sample.txt --name sample1.txt
az storage blob upload --account-name srechallengewest --container-name backups --file sample.txt --name sample2.txt

```


### Result:
This will create containers inside on each storage accounts and uploaded files inside each container

---

## ✅ Task 4 – Export Metadata into JSON (Azure version of buckets.json)

### Commands used:
```Powershell
# List storage accounts in the RG
$storageAccounts = az storage account list --resource-group $RESOURCE_GROUP --query '[].{name:name, location:primaryLocation, resourceGroup:resourceGroup}' -o json

# Save metadata to file (buckets.json)
$storageAccounts | Out-File -FilePath "buckets.json"

```

### Result:
Will get bucket details like created time period, container name, storage of each container

---

## ✅ Task 5 – Run Python Script for Analysis

### Commands used:
```bash
python buckets_analysis.py
```

### Result:
Uncommitted changes were safely stored using `git stash`, applied to another branch using `git cherry-pick`, and then restored using `git stash pop`.

---

## ✅ Submission Checklist

- ✅ Completed all tasks with commands and explanations
- ✅ Inserted screenshots under each command block
- ✅ Pushed code to GitHub
- ✅ Created PR titled **Day 4: Advanced blob container Metadata Manipulation**
- ✅ Shared on LinkedIn with hashtags: `#getfitwithsagar #DevOpsForAll`

---