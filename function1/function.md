
# Create resource group
```
az group create --name MSWorkShop --location westeurope
```

# Create storage 
```
az storage account create --name msworkshopstoragebp --location westeurope --resource-group MSWorkShop --sku Standard_LRS
```

# Create function
```
az functionapp create --deployment-source-url https://github.com/codefactoryhu/MS-Workshop-Function.git  \
--resource-group MSWorkShop --consumption-plan-location westeurope \
--name MSWorkShopFunctionZool --storage-account msworkshopstoragebp
```