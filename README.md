# 🗃️ Alfredo's Inventory DynamoDB Table - CloudFormation Template - Cloud Guru Lab

This AWS CloudFormation template creates a DynamoDB table named **`Inventory`**, designed to support inventory tracking for Alfredo's application or system.

---

## 📄 Template Summary

- Provisions a **DynamoDB table** named `Inventory`
- Uses customizable **Hash Key** name and type via parameters
- Configures **provisioned throughput** with:
  - 5 Read Capacity Units
  - 5 Write Capacity Units

---

## 📥 Parameters

| Parameter             | Type   | Default      | Description          |
|-----------------------|--------|--------------|----------------------|
| `HashKeyElementName`  | String | `InventoryId`| Name of the Hash Key |
| `HashKeyElementType`  | String | `S`          | Type of the Hash Key (e.g., `S` for String, `N` for Number) |

---

## 🚀 Deployment

You can deploy the stack using the AWS CLI:

```bash
aws cloudformation create-stack \
  --stack-name alfredo-inventory-table \
  --template-body file://inventory-table.yaml \
  --parameters ParameterKey=HashKeyElementName,ParameterValue=InventoryId \
               ParameterKey=HashKeyElementType,ParameterValue=S \
  --capabilities CAPABILITY_NAMED_IAM
```

##Outputs
| Output Name | Description                    |
| ----------- | ------------------------------ |
| `Inventory` | Reference to the created table |

## Cleanup
To delete the stack and avoid charges:
```bash
aws cloudformation delete-stack --stack-name alfredo-inventory-table
```

