---
author: ggailey777
ms.service: azure-functions
ms.topic: include
ms.date: 03/25/2020
ms.author: glenga
ms.openlocfilehash: 7a390c0d19a37ea18f9eac8636683ec35ecbc844
ms.sourcegitcommit: 2aeb2c41fd22a02552ff871479124b567fa4463c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "107880696"
---
## <a name="configure-your-local-environment"></a>Konfigurieren Ihrer lokalen Umgebung

Bevor Sie mit diesem Lernprogramm beginnen können, benötigen Sie Folgendes:

+ Ein Azure-Konto mit einem aktiven Abonnement. Sie können [kostenlos ein Konto erstellen](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=docs&utm_campaign=visualstudio).

::: zone pivot="programming-language-csharp,programming-language-javascript,programming-language-typescript,programming-language-powershell,programming-language-java,programming-language-other"  
+ [Azure Functions Core Tools](../articles/azure-functions/functions-run-local.md#v2), ab Version 2.7.1846.
::: zone-end  
::: zone pivot="programming-language-python"
+ Die Azure Functions Core Tools-Version, die Ihrer installierten Python-Version entspricht:

   | Python-Version | Core Tools-Version |
   | -------------- | ------------------ |
   | Python 3.8     | [Version 3.x](../articles/azure-functions/functions-run-local.md#v2) |
   | Python 3.6<br/>Python 3.7 | [Version 2.7.1846 oder höher](../articles/azure-functions/functions-run-local.md#v2) |
  
::: zone-end

+ [Azure-Befehlszeilenschnittstelle](/cli/azure/install-azure-cli) ab Version 2.4 
::: zone pivot="programming-language-javascript,programming-language-typescript"
+ [Node.js](https://nodejs.org/), Active LTS- und Maintenance LTS-Versionen (8.11.1 und 10.14.1 empfohlen)
::: zone-end

::: zone pivot="programming-language-python"
+ [Python 3.8 (64 Bit)](https://www.python.org/downloads/release/python-382/), [Python 3.7 (64 Bit)](https://www.python.org/downloads/release/python-375/), [Python 3.6 (64 Bit)](https://www.python.org/downloads/release/python-368/). Diese Versionen werden von Azure Functions unterstützt. 
::: zone-end
::: zone pivot="programming-language-powershell"
+ Das [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)
::: zone-end
::: zone pivot="programming-language-java"  
+ [Java Developer Kit](/azure/developer/java/fundamentals/java-jdk-long-term-support), Version 8 oder 11. 

+ [Apache Maven](https://maven.apache.org), Version 3.0 oder höher

::: zone-end
::: zone pivot="programming-language-other"
+ Entwicklungstools für die von Ihnen verwendete Sprache. In diesem Tutorial wird als Beispiel die [Programmiersprache R](https://www.r-project.org/) verwendet.
::: zone-end