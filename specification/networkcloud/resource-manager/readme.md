# NetworkCloud

> see https://aka.ms/autorest

This is the AutoRest configuration file for NetworkCloud.

## Getting Started

To build the SDKs for My API, simply install AutoRest via `npm` (`npm install -g autorest`) and then run:

> `autorest readme.md`

To see additional help and options, run:

> `autorest --help`

For other options on installation see [Installing AutoRest](https://aka.ms/autorest/install) on the AutoRest github page.

---

## Configuration

### Basic Information

These are the global settings for NetworkCloud.

```yaml
openapi-type: arm
openapi-subtype: providerHub
tag: package-2025-07-01-preview
```

---

### Tag: package-2023-07-01

These settings apply only when `--tag=package-2023-07-01` is specified on the command line.

```yaml $(tag) == 'package-2023-07-01'
input-file:
  - Microsoft.NetworkCloud/stable/2023-07-01/networkcloud.json
```

### Tag: package-2024-07-01

These settings apply only when `--tag=package-2024-07-01` is specified on the command line.

```yaml $(tag) == 'package-2024-07-01'
input-file:
  - Microsoft.NetworkCloud/stable/2024-07-01/networkcloud.json
suppressions:
  - code: PatchBodyParametersSchema
    from: networkcloud.json
    reason: False positive based on Azure common types. Managed Service Identity requires type, and the Managed Service Identity can be patched.
    where: $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.NetworkCloud/clusters/{clusterName}"].patch.parameters[4].schema.properties.identity
  - code: PatchBodyParametersSchema
    from: networkcloud.json
    reason: False positive based on Azure common types. Managed Service Identity requires type, and the Managed Service Identity can be patched.
    where: $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.NetworkCloud/clusterManagers/{clusterManagerName}"].patch.parameters[4].schema.properties.identity
  - code: PatchBodyParametersSchema
    from: networkcloud.json
    reason: Nested objects that share a structure with PUT have required fields. The required field is present in the patch structure as well, because it reuses types. The nested structure needs to be updated in full by the user.
    where: $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.NetworkCloud/clusters/{clusterName}"].patch.parameters[4].schema.properties.properties
  - code: BodyTopLevelProperties
    from: networkcloud.json
    reason: Bug in Linter, see https://github.com/Azure/azure-openapi-validator/issues/722
```

### Tag: package-2024-10-01-preview

These settings apply only when `--tag=package-2024-10-01-preview` is specified on the command line.

```yaml $(tag) == 'package-2024-10-01-preview'
input-file:
  - Microsoft.NetworkCloud/preview/2024-10-01-preview/networkcloud.json
suppressions:
  - code: PatchBodyParametersSchema
    from: networkcloud.json
    reason: False positive based on Azure common types. Managed Service Identity requires type, and the Managed Service Identity can be patched.
    where: $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.NetworkCloud/clusters/{clusterName}"].patch.parameters[4].schema.properties.identity
  - code: PatchBodyParametersSchema
    from: networkcloud.json
    reason: False positive based on Azure common types. Managed Service Identity requires type, and the Managed Service Identity can be patched.
    where: $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.NetworkCloud/clusterManagers/{clusterManagerName}"].patch.parameters[4].schema.properties.identity
  - code: PatchBodyParametersSchema
    from: networkcloud.json
    reason: Nested objects that share a structure with PUT have required fields. The required field is present in the patch structure as well, because it reuses types. The nested structure needs to be updated in full by the user.
    where: $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.NetworkCloud/clusters/{clusterName}"].patch.parameters[4].schema.properties.properties
```

### Tag: package-2025-02-01

These settings apply only when `--tag=package-2024-02-01` is specified on the command line.

```yaml $(tag) == 'package-2025-02-01'
input-file:
  - Microsoft.NetworkCloud/stable/2025-02-01/networkcloud.json
suppressions:
  - code: PatchBodyParametersSchema
    from: networkcloud.json
    reason: False positive based on Azure common types. Managed Service Identity requires type, and the Managed Service Identity can be patched.
    where: $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.NetworkCloud/clusters/{clusterName}"].patch.parameters[4].schema.properties.identity
  - code: PatchBodyParametersSchema
    from: networkcloud.json
    reason: False positive based on Azure common types. Managed Service Identity requires type, and the Managed Service Identity can be patched.
    where: $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.NetworkCloud/clusterManagers/{clusterManagerName}"].patch.parameters[4].schema.properties.identity
  - code: PatchBodyParametersSchema
    from: networkcloud.json
    reason: Nested objects that share a structure with PUT have required fields. The required field is present in the patch structure as well, because it reuses types. The nested structure needs to be updated in full by the user.
    where: $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.NetworkCloud/clusters/{clusterName}"].patch.parameters[4].schema.properties.properties
```

### Tag: package-2025-07-01-preview

These settings apply only when `--tag=package-2025-07-01-preview` is specified on the command line.

```yaml $(tag) == 'package-2025-07-01-preview'
input-file:
  - Microsoft.NetworkCloud/preview/2025-07-01-preview/networkcloud.json
suppressions:
  - code: PatchBodyParametersSchema
    from: networkcloud.json
    reason: Nested objects that share a structure with PUT have required fields. The required field is present in the patch structure as well, because it reuses types. The nested structure needs to be updated in full by the user.
    where: $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.NetworkCloud/clusters/{clusterName}"].patch.parameters[4].schema.properties.properties
```
---

# Code Generation

## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

```yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-python-track2
  - repo: azure-sdk-for-java
  - repo: azure-sdk-for-go
  - repo: azure-sdk-for-js
  - repo: azure-resource-manager-schemas
  - repo: azure-cli-extensions
```

## Go

See configuration in [readme.go.md](./readme.go.md)

## Python

See configuration in [readme.python.md](./readme.python.md)

## TypeScript

See configuration in [readme.typescript.md](./readme.typescript.md)

## CSharp

See configuration in [readme.csharp.md](./readme.csharp.md)
