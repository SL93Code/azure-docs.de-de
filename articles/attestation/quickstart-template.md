---
title: Erstellen eines Azure Attestation-Zertifikats mithilfe einer Azure Resource Manager-Vorlage
description: Hier erfahren Sie, wie Sie ein Azure Attestation-Zertifikat mithilfe einer Azure Resource Manager-Vorlage erstellen.
services: azure-resource-manager
author: msmbaldwin
ms.service: azure-resource-manager
ms.topic: quickstart
ms.custom: subject-armqs, devx-track-azurepowershell
ms.author: mbaldwin
ms.date: 05/20/2021
ms.openlocfilehash: 2aa4c1b95677dd2257751fd27270d927d700bdb6
ms.sourcegitcommit: 1b19b8d303b3abe4d4d08bfde0fee441159771e1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "109750553"
---
# <a name="quickstart-create-an-azure-attestation-provider-with-an-arm-template"></a>Schnellstart: Erstellen eines Azure Attestation-Anbieters mit einer ARM-Vorlage

[Microsoft Azure Attestation](overview.md) ist eine Lösung für den Nachweis von Trusted Execution Environments (TEEs). In dieser Schnellstartanleitung geht es um die Bereitstellung einer Azure Resource Manager-Vorlage (ARM-Vorlage) zum Erstellen einer Microsoft Azure Attestation-Richtlinie.

[!INCLUDE [About Azure Resource Manager](../../includes/resource-manager-quickstart-introduction.md)]

Wenn Ihre Umgebung die Voraussetzungen erfüllt und Sie mit der Verwendung von ARM-Vorlagen vertraut sind, klicken Sie auf die Schaltfläche **In Azure bereitstellen**. Die Vorlage wird im Azure-Portal geöffnet.

[![In Azure bereitstellen](../media/template-deployments/deploy-to-azure.svg)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fquickstarts%2Fmicrosoft.attestation%2Fattestation-provider-create%2Fazuredeploy.json)

## <a name="prerequisites"></a>Voraussetzungen

Wenn Sie kein Azure-Abonnement besitzen, können Sie ein [kostenloses Konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) erstellen, bevor Sie beginnen.

## <a name="review-the-template"></a>Überprüfen der Vorlage

Die in dieser Schnellstartanleitung verwendete Vorlage stammt von der Seite mit den [Azure-Schnellstartvorlagen](https://azure.microsoft.com/resources/templates/101-attestation-provider-create).

:::code language="json" source="~/quickstart-templates/quickstarts/microsoft.attestation/attestation-provider-create/azuredeploy.json":::

In der Vorlage sind die folgenden Azure-Ressourcen definiert:

- Microsoft.Attestation/attestationProviders

## <a name="deploy-the-template"></a>Bereitstellen der Vorlage

1. Wählen Sie das folgende Image aus, um sich bei Azure anzumelden und die Vorlage zu öffnen.

    [![In Azure bereitstellen](../media/template-deployments/deploy-to-azure.svg)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fquickstarts%2Fmicrosoft.attestation%2Fattestation-provider-create%2Fazuredeploy.json)

1. Wählen Sie die folgenden Werte aus, bzw. geben Sie sie ein.

    Verwenden Sie den Standardwert, um den Nachweisanbieter zu erstellen, sofern kein anderer Wert angegeben ist.

    - **Name des Nachweisanbieters**: Wählen Sie einen Namen für den Azure Attestation-Anbieter aus.
    - **Standort**: Wählen Sie einen Standort aus. Beispiel: **USA, Mitte**.
    - **Tags**: Wählen Sie einen Standort aus. Beispiel: **USA, Mitte**.

1. Wählen Sie die Option **Kaufen**. Nach erfolgreicher Bereitstellung der Nachweisressource erhalten Sie eine Benachrichtigung.

Zum Bereitstellen der Vorlage wird das Azure-Portal verwendet. Neben dem Azure-Portal können Sie auch Azure PowerShell, die Azure-Befehlszeilenschnittstelle (Azure CLI) und die REST-API verwenden. Informationen zu anderen Bereitstellungsmethoden finden Sie unter [Bereitstellen von Vorlagen](../azure-resource-manager/templates/deploy-powershell.md).

## <a name="review-deployed-resources"></a>Überprüfen der bereitgestellten Ressourcen

Sie können die Nachweisressource über das Azure-Portal überprüfen.

## <a name="clean-up-resources"></a>Bereinigen von Ressourcen

Andere Azure Attestation-Szenarien bauen auf dieser Schnellstartanleitung auf. Falls Sie mit weiteren Schnellstartanleitungen und Tutorials fortfahren möchten, sollten Sie die Ressourcen nicht bereinigen.

Wenn Sie die Ressourcen nicht mehr benötigen, löschen Sie die Ressourcengruppe. Dadurch wird auch die Attestation-Ressource gelöscht. Die Ressourcengruppe kann über die Azure-Befehlszeilenschnittstelle oder mithilfe von Azure PowerShell gelöscht werden:

# <a name="cli"></a>[BEFEHLSZEILENSCHNITTSTELLE (CLI)](#tab/CLI)

```azurecli-interactive
echo "Enter the Resource Group name:" &&
read resourceGroupName &&
az group delete --name $resourceGroupName &&
echo "Press [ENTER] to continue ..."
```

# <a name="powershell"></a>[PowerShell](#tab/PowerShell)

```azurepowershell-interactive
$resourceGroupName = Read-Host -Prompt "Enter the Resource Group name"
Remove-AzResourceGroup -Name $resourceGroupName
Write-Host "Press [ENTER] to continue..."
```

---

## <a name="next-steps"></a>Nächste Schritte

In dieser Schnellstartanleitung haben Sie mithilfe einer ARM-Vorlage eine Nachweisressource erstellt und die Bereitstellung überprüft. Weitere Informationen zu Azure Attestation finden Sie unter [Übersicht über Azure Attestation](overview.md).
