---
title: 'Schnellstart: QnA Maker-Clientbibliothek für Node.js'
description: Dieser Schnellstart zeigt Ihnen die ersten Schritte mit der QnA Maker-Clientbibliothek für Node.js.
ms.topic: quickstart
ms.date: 06/18/2020
ms.custom: devx-track-js
ms.openlocfilehash: 0d0522be53ec9b1008f18725308c91a19ee24156
ms.sourcegitcommit: 73d80a95e28618f5dfd719647ff37a8ab157a668
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "105609493"
---
# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

Verwenden Sie die QnA Maker-Clientbibliothek für Node.js für folgende Zwecke:

* Erstellen einer Wissensdatenbank
* Aktualisieren einer Wissensdatenbank
* Veröffentlichen einer Wissensdatenbank
* Abrufen von Endpunktschlüsseln der Vorhersage-Runtime
* Warten auf Aufgaben mit langer Ausführungsdauer
* Herunterladen einer Wissensdatenbank
* Abrufen einer Antwort aus einer Wissensdatenbank
* Löschen einer Wissensdatenbank

[Referenzdokumentation](/javascript/api/@azure/cognitiveservices-qnamaker/) | [Quellcode der Bibliothek](https://github.com/Azure/azure-sdk-for-js/tree/master/sdk/cognitiveservices/cognitiveservices-qnamaker) | [Paket (npm)](https://www.npmjs.com/package/@azure/cognitiveservices-qnamaker) | [Node.js-Beispiele](https://github.com/Azure-Samples/cognitive-services-quickstart-code/blob/master/javascript/QnAMaker/sdk/qnamaker_quickstart.js)

# <a name="qna-maker-managed-preview-release"></a>[QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

Verwenden Sie die QnA Maker-Clientbibliothek für Node.js für folgende Zwecke:

* Erstellen einer Wissensdatenbank
* Aktualisieren einer Wissensdatenbank
* Veröffentlichen einer Wissensdatenbank
* Warten auf Aufgaben mit langer Ausführungsdauer
* Herunterladen einer Wissensdatenbank
* Abrufen einer Antwort aus einer Wissensdatenbank
* Löschen einer Wissensdatenbank

[Referenzdokumentation](/javascript/api/@azure/cognitiveservices-qnamaker/) | [Quellcode der Bibliothek](https://github.com/Azure/azure-sdk-for-js/tree/master/sdk/cognitiveservices/cognitiveservices-qnamaker) | [Paket (npm)](https://www.npmjs.com/package/@azure/cognitiveservices-qnamaker) | [Node.js-Beispiele](https://github.com/Azure-Samples/cognitive-services-quickstart-code/blob/master/javascript/QnAMaker/sdk/preview-sdk/quickstart.js)

---

[!INCLUDE [Custom subdomains notice](../../../../includes/cognitive-services-custom-subdomains-note.md)]

## <a name="prerequisites"></a>Voraussetzungen

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

* Azure-Abonnement – [Erstellen eines kostenlosen Kontos](https://azure.microsoft.com/free/cognitive-services)
* Die aktuelle Version von [Node.js](https://nodejs.org).
* Sobald Sie über Ihr Azure-Abonnement verfügen, erstellen Sie im Azure-Portal eine [QnA Maker-Ressource](https://ms.portal.azure.com/#create/Microsoft.CognitiveServicesQnAMaker), um Ihren Erstellungsschlüssel und die Ressource zu erhalten. Wählen Sie nach Abschluss der Bereitstellung **Zu Ressource wechseln** aus.
    * Sie benötigen den Schlüssel und Ressourcennamen aus der von Ihnen erstellten Ressource, um Ihre Anwendung mit der QnA Maker-API zu verbinden. Ihren Schlüssel und Ressourcennamen werden Sie weiter unten in der Schnellstartanleitung in den Code einfügen.
    * Sie können den kostenlosen Tarif (`F0`) verwenden, um den Dienst zu testen, und später für die Produktion auf einen kostenpflichtigen Tarif upgraden.

# <a name="qna-maker-managed-preview-release"></a>[QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

* Azure-Abonnement – [Erstellen eines kostenlosen Kontos](https://azure.microsoft.com/free/cognitive-services)
* Die aktuelle Version von [Node.js](https://nodejs.org).
* Sobald Sie über Ihr Azure-Abonnement verfügen, erstellen Sie im Azure-Portal eine [QnA Maker-Ressource](https://ms.portal.azure.com/#create/Microsoft.CognitiveServicesQnAMaker), um Ihren Erstellungsschlüssel und Endpunkt zu erhalten.
    * HINWEIS: Das Kontrollkästchen **Verwaltet** muss aktiviert sein.
    * Wählen Sie nach der Bereitstellung der QnA Maker-Ressource **Zu Ressource wechseln** aus. Sie benötigen den Schlüssel und Endpunkt der von Ihnen erstellten Ressource, um Ihre Anwendung mit der QnA Maker-API zu verbinden. Der Schlüssel und der Endpunkt werden weiter unten in der Schnellstartanleitung in den Code eingefügt.
    * Sie können den kostenlosen Tarif (`F0`) verwenden, um den Dienst zu testen, und später für die Produktion auf einen kostenpflichtigen Tarif upgraden.

---

## <a name="setting-up"></a>Einrichten

### <a name="create-a-new-nodejs-application"></a>Erstellen einer neuen Node.js-Anwendung

Erstellen Sie in einem Konsolenfenster (etwa cmd, PowerShell oder Bash) ein neues Verzeichnis für Ihre App, und rufen Sie es auf.

```console
mkdir qnamaker_quickstart && cd qnamaker_quickstart
```

Führen Sie den Befehl `npm init -y` aus, um eine Knotenanwendung mit der Datei `package.json` zu erstellen.

```console
npm init -y
```

### <a name="install-the-client-library"></a>Installieren der Clientbibliothek

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

Installieren Sie die folgenden NPM-Pakete:

```console
npm install @azure/cognitiveservices-qnamaker
npm install @azure/cognitiveservices-qnamaker-runtime
npm install @azure/ms-rest-js
```

# <a name="qna-maker-managed-preview-release"></a>[QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

Installieren Sie die folgenden NPM-Pakete:

```console
npm install @azure/cognitiveservices-qnamaker
npm install @azure/ms-rest-js
```

---

Die Datei `package.json` Ihrer App wird mit den Abhängigkeiten aktualisiert.

Erstellen Sie eine Datei mit dem Namen „index.js“, öffnen Sie sie, und importieren Sie die folgenden Bibliotheken:

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

[!code-javascript[Dependencies](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=Dependencies)]

# <a name="qna-maker-managed-preview-release"></a>[Mit QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

[!code-javascript[Dependencies](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/preview-sdk/quickstart.js?name=Dependencies)]

---

Erstellen Sie eine Variable für den Azure-Schlüssel Ihrer Ressource und den Ressourcennamen.

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

- Die Begriffe „Abonnementschlüssel“ und Erstellungsschlüssel“ werden synonym verwendet. Ausführlichere Informationen zum Erstellungsschlüssel finden Sie unter [Schlüssel in QnA Maker](../concepts/azure-resources.md?tabs=v1#keys-in-qna-maker).

- Der Wert von „QNA_MAKER_ENDPOINT“ hat das Format `https://YOUR-RESOURCE-NAME.cognitiveservices.azure.com`. Navigieren Sie zum Azure-Portal, und suchen Sie die unter „Voraussetzungen“ erstellte QnA Maker-Ressource. Klicken Sie unter **Ressourcenverwaltung** auf die Seite **Schlüssel und Endpunkt**, um den Schlüssel für die Erstellung (Abonnement) und QnA Maker Endpunkt zu suchen.

 ![Endpunkt für die QnA Maker Erstellung](../media/keys-endpoint.png)

- Der Wert von „QNA_MAKER_RUNTIME_ENDPOINT“ hat das Format `https://YOUR-RESOURCE-NAME.azurewebsites.net`. Navigieren Sie zum Azure-Portal, und suchen Sie die unter „Voraussetzungen“ erstellte QnA Maker-Ressource. Klicken Sie auf die Seite " **Vorlage exportieren** " unter **Automation**, um den Lauf Zeit Endpunkt zu suchen.

 ![QnA Maker-Laufzeitendpunkt](../media/runtime-endpoint.png)
   
- In der Produktionsumgebung sollten Sie eine sichere Methode zum Speichern Ihrer Anmeldeinformationen sowie zum Zugriff darauf verwenden. Beispielsweise bietet der [Azure-Schlüsseltresor](../../../key-vault/general/overview.md) sichere Aufbewahrung von Schlüsseln.

[!code-javascript[Set the resource key and resource name](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=Resourcevariables)]

# <a name="qna-maker-managed-preview-release"></a>[QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

- Die Begriffe „Abonnementschlüssel“ und Erstellungsschlüssel“ werden synonym verwendet. Ausführlichere Informationen zum Erstellungsschlüssel finden Sie unter [Schlüssel in QnA Maker](../concepts/azure-resources.md?tabs=v2#keys-in-qna-maker).

- Der Wert von „QNA_MAKER_ENDPOINT“ hat das Format `https://YOUR-RESOURCE-NAME.cognitiveservices.azure.com`. Navigieren Sie zum Azure-Portal, und suchen Sie die unter „Voraussetzungen“ erstellte QnA Maker-Ressource. Klicken Sie unter **Ressourcenverwaltung** auf die Seite **Schlüssel und Endpunkt**, um den Schlüssel für die Erstellung (Abonnement) und QnA Maker Endpunkt zu suchen.

 ![Endpunkt für die QnA Maker Erstellung](../media/keys-endpoint.png)
 
- In der Produktionsumgebung sollten Sie eine sichere Methode zum Speichern Ihrer Anmeldeinformationen sowie zum Zugriff darauf verwenden. Beispielsweise bietet der [Azure-Schlüsseltresor](../../../key-vault/general/overview.md) sichere Aufbewahrung von Schlüsseln.

[!code-javascript[Set the resource key and resource name](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/preview-sdk/quickstart.js?name=Resourcevariables)]

---

## <a name="object-models"></a>Objektmodelle

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

Von [QnA Maker](/javascript/api/@azure/cognitiveservices-qnamaker/) werden zwei unterschiedliche Objektmodelle verwendet:
* **[QnAMakerClient](#qnamakerclient-object-model)** ist das Objekt zum Erstellen, Verwalten, Veröffentlichen und Herunterladen der Wissensdatenbank.
* **[QnAMakerRuntime](#qnamakerruntimeclient-object-model)** ist das Objekt, das für Abfragen der Wissensdatenbank mit der GenerateAnswer-API und zum Senden neuer vorgeschlagener Fragen mithilfe der Train-API (im Rahmen des [aktiven Lernens](../how-to/use-active-learning.md)) verwendet wird.

# <a name="qna-maker-managed-preview-release"></a>[QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

Von [QnA Maker](/javascript/api/@azure/cognitiveservices-qnamaker/) wird das folgende Objektmodell verwendet:
* **[QnAMakerClient](#qnamakerclient-object-model)** ist das Objekt zum Erstellen, Verwalten, Veröffentlichen, Herunterladen und Abfragen der Wissensdatenbank.

---

### <a name="qnamakerclient-object-model"></a>QnAMakerClient-Objektmodell

Der erstellende QnA Maker-Client ist ein [QnAMakerClient](/javascript/api/@azure/cognitiveservices-qnamaker/qnamakerclient)-Objekt, das mithilfe Ihrer Anmeldeinformationen, in denen Ihr Schlüssel enthalten ist, bei Azure authentifiziert wird.

Verwenden Sie nach dem Erstellen des Clients die [Wissensdatenbank](/javascript/api/@azure/cognitiveservices-qnamaker/qnamakerclient#knowledgebase), um Ihre Wissensdatenbank zu erstellen, zu verwalten und zu veröffentlichen.

Verwalten Sie Ihre Knowledge Base durch Senden eines JSON-Objekts. Bei sofortigen Vorgängen gibt eine Methode in der Regel ein JSON-Objekt zurück, das den Status angibt. Bei zeitintensiven Vorgängen ist die Antwort die Vorgangs-ID. Rufen Sie die [client.Operations.getDetails](/javascript/api/@azure/cognitiveservices-qnamaker/operations#getdetails-string--msrest-requestoptionsbase-)-Methode mit der Vorgangs-ID auf, um den [Status der Anforderung](/javascript/api/@azure/cognitiveservices-qnamaker/operation) zu bestimmen.

### <a name="qnamakerruntimeclient-object-model"></a>QnAMakerRuntimeClient-Objektmodell

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

Der QnA Maker-Vorhersageclient ist ein QnAMakerRuntimeClient-Objekt, das sich bei Azure mithilfe von Microsoft.Rest.ServiceClientCredentials authentifiziert, die Ihren Schlüssel für die Vorhersage-Runtime enthalten, der nach dem Veröffentlichen der Wissensdatenbank vom Aufruf [client.EndpointKeys.getKeys](/javascript/api/@azure/cognitiveservices-qnamaker/endpointkeys#getkeys-msrest-requestoptionsbase-) des erstellenden Clients zurückgegeben wurde.

# <a name="qna-maker-managed-preview-release"></a>[QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

Für eine von QnA Maker verwaltete Ressource muss das Objekt „QnAMakerRuntimeClient“ nicht verwendet werden. Stattdessen kann [generateAnswer](/javascript/api/@azure/cognitiveservices-qnamaker/knowledgebase#generateAnswer_string__QueryDTO__msRest_RequestOptionsBase_) direkt für das Objekt [QnAMakerClient](/javascript/api/@azure/cognitiveservices-qnamaker/qnamakerclient) aufgerufen werden.

---

## <a name="code-examples"></a>Codebeispiele

Mit den Codeausschnitten wird veranschaulicht, wie folgende Vorgänge mit der QnA Maker-Clientbibliothek für .NET durchgeführt werden:

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

* [Authentifizieren des Erstellungsclients](#authenticate-the-client-for-authoring-the-knowledge-base)
* [Erstellen einer Wissensdatenbank](#create-a-knowledge-base)
* [Aktualisieren einer Wissensdatenbank](#update-a-knowledge-base)
* [Herunterladen einer Knowledge Base](#download-a-knowledge-base)
* [Veröffentlichen einer Wissensdatenbank](#publish-a-knowledge-base)
* [Löschen einer Wissensdatenbank](#delete-a-knowledge-base)
* [Abrufen des Abfrage-Runtimeschlüssels](#get-query-runtime-key)
* [Abrufen des Status eines Vorgangs](#get-status-of-an-operation)
* [Authentifizieren des Abfrage-Runtimeclients](#authenticate-the-runtime-for-generating-an-answer)
* [Generieren einer Antwort auf der Grundlage der Wissensdatenbank](#generate-an-answer-from-the-knowledge-base)

# <a name="qna-maker-managed-preview-release"></a>[QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

* [Authentifizieren des Erstellungsclients](#authenticate-the-client-for-authoring-the-knowledge-base)
* [Erstellen einer Wissensdatenbank](#create-a-knowledge-base)
* [Aktualisieren einer Wissensdatenbank](#update-a-knowledge-base)
* [Herunterladen einer Knowledge Base](#download-a-knowledge-base)
* [Veröffentlichen einer Wissensdatenbank](#publish-a-knowledge-base)
* [Löschen einer Wissensdatenbank](#delete-a-knowledge-base)
* [Abrufen des Status eines Vorgangs](#get-status-of-an-operation)
* [Generieren einer Antwort auf der Grundlage der Wissensdatenbank](#generate-an-answer-from-the-knowledge-base)

---

## <a name="authenticate-the-client-for-authoring-the-knowledge-base"></a>Authentifizieren des Clients zum Erstellen der Wissensdatenbank

Instanziieren Sie einen Client mit Ihrem Endpunkt und Schlüssel. Erstellen Sie ein ServiceClientCredentials-Objekt mit Ihrem Schlüssel, und verwenden Sie es mit Ihrem Endpunkt, um ein [QnAMakerClient](/javascript/api/@azure/cognitiveservices-qnamaker/qnamakerclient)-Objekt zu erstellen.

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

[!code-javascript[Create QnAMakerClient object with key and endpoint](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=AuthorizationAuthor)]

# <a name="qna-maker-managed-preview-release"></a>[Mit QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

[!code-javascript[Create QnAMakerClient object with key and endpoint](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/preview-sdk/quickstart.js?name=AuthorizationAuthor)]

---

## <a name="create-a-knowledge-base"></a>Erstellen einer Wissensdatenbank

Eine Wissensdatenbank speichert Frage- und Antwortpaare für das [CreateKbDTO](/javascript/api/@azure/cognitiveservices-qnamaker/createkbdto)-Objekt aus drei Quellen:

* Für **redaktionellen Inhalt** verwenden Sie das [QnADTO](/javascript/api/@azure/cognitiveservices-qnamaker/qnadto)-Objekt.
    * Verwenden Sie für Metadaten und Folgeaufforderungen den redaktionellen Kontext, da diese Daten auf der Ebene der einzelnen QnA-Paare hinzugefügt werden.
* Für **Dateien** verwenden Sie das [FileDTO](/javascript/api/@azure/cognitiveservices-qnamaker/filedto)-Objekt. Dieses Objekt enthält den Dateinamen sowie die öffentliche URL für den Zugriff auf die Datei.
* Verwenden Sie für **URLs** eine Liste von Zeichenfolgen zur Darstellung von öffentlich verfügbaren URLs.

Der Erstellungsschritt umfasst auch Eigenschaften für die Wissensdatenbank mit Folgendem:
* `defaultAnswerUsedForExtraction`: die Rückgabe, wenn keine Antwort gefunden wird
* `enableHierarchicalExtraction`: automatisches Erstellen von Aufforderungsbeziehungen zwischen extrahierten QnA-Paaren
* `language`: bei der Erstellung der ersten Wissensdatenbank für eine Ressource Festlegen der Sprache, die im Azure-Suchindex verwendet werden soll

Rufen Sie die [create](/javascript/api/@azure/cognitiveservices-qnamaker/knowledgebase#create-createkbdto--servicecallback-operation--)-Methode mit den Informationen der Wissensdatenbank auf. Bei den Informationen der Wissensdatenbank handelt es sich im Grunde um ein JSON-Objekt.

Übergeben Sie bei Rückgabe der create-Methode die zurückgegebene Vorgangs-ID an die [wait_for_operation](#get-status-of-an-operation)-Methode, um den Status abzurufen. Die Rückgabe der Methode „wait_for_operation“ erfolgt bei Abschluss des Vorgangs. Analysieren Sie den `resourceLocation`-Headerwert des zurückgegebenen Vorgangs, um die neue Wissensdatenbank-ID abzurufen.

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

[!code-javascript[Create knowledgebase](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=CreateKBMethod)]

# <a name="qna-maker-managed-preview-release"></a>[Mit QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

[!code-javascript[Create knowledgebase](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/preview-sdk/quickstart.js?name=CreateKBMethod)]

---

Zum erfolgreichen Erstellen einer Wissensdatenbank muss die Funktion [`wait_for_operation`](#get-status-of-an-operation) eingeschlossen werden, auf die im obigen Code verwiesen wird.

## <a name="update-a-knowledge-base"></a>Aktualisieren einer Wissensdatenbank

Sie können eine Wissensdatenbank aktualisieren, indem Sie die Wissensdatenbank-ID und ein [UpdateKbOperationDTO](/javascript/api/@azure/cognitiveservices-qnamaker/updatekboperationdto)-Element, das [add](/javascript/api/@azure/cognitiveservices-qnamaker/updatekboperationdto#add)-, [update](/javascript/api/@azure/cognitiveservices-qnamaker/updatekboperationdto#update)- und [delete](/javascript/api/@azure/cognitiveservices-qnamaker/updatekboperationdto#deleteproperty)-DTO-Objekte enthält, als Eingabe an die [update](/javascript/api/@azure/cognitiveservices-qnamaker/knowledgebase#update-string--updatekboperationdto--msrest-requestoptionsbase-)-Methode übergeben. Die DTOs sind im Grunde ebenfalls JSON-Objekte. Verwenden Sie die [wait_for_operation](#get-status-of-an-operation)-Methode, um zu bestimmen, ob das Update erfolgreich war.

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

[!code-javascript[Update a knowledge base](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=UpdateKBMethod)]

# <a name="qna-maker-managed-preview-release"></a>[Mit QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

[!code-javascript[Update a knowledge base](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/preview-sdk/quickstart.js?name=UpdateKBMethod)]

---

Nehmen Sie zum erfolgreichen Aktualisieren einer Wissensdatenbank unbedingt die Funktion [`wait_for_operation`](#get-status-of-an-operation) mit auf, auf die im Code oben verwiesen wird.

## <a name="download-a-knowledge-base"></a>Herunterladen einer Knowledge Base

Verwenden Sie die [download](/javascript/api/@azure/cognitiveservices-qnamaker/knowledgebase#download-string--models-environmenttype--msrest-requestoptionsbase-)-Methode, um die Datenbank als Liste von [QnADocumentsDTO](/javascript/api/@azure/cognitiveservices-qnamaker/qnadocumentsdto) herunterzuladen. Dies entspricht _nicht_ dem Export des QnA Maker-Portals von der Seite **Einstellungen**, da das Ergebnis dieser Methode keine TSV-Datei ist.

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

[!code-javascript[Download a knowledge base](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=DownloadKB)]

# <a name="qna-maker-managed-preview-release"></a>[Mit QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

[!code-javascript[Download a knowledge base](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/preview-sdk/quickstart.js?name=DownloadKB)]

---

## <a name="publish-a-knowledge-base"></a>Veröffentlichen einer Wissensdatenbank

Veröffentlichen Sie die Wissensdatenbank mit der [publish](/javascript/api/@azure/cognitiveservices-qnamaker/knowledgebase#publish-string--msrest-requestoptionsbase-)-Methode. Diese übernimmt das aktuell gespeicherte und trainierte Modell, auf das von der Knowledge Base-ID verwiesen wird, und veröffentlicht dieses an einem Endpunkt. Überprüfen Sie den HTTP-Antwortcode, um sich zu vergewissern, dass die Veröffentlichung erfolgreich war.

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

[!code-javascript[Publish a knowledge base](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=PublishKB)]

# <a name="qna-maker-managed-preview-release"></a>[Mit QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

[!code-javascript[Publish a knowledge base](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/preview-sdk/quickstart.js?name=PublishKB)]

---

## <a name="query-a-knowledge-base"></a>Abfragen einer Knowledge Base

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

### <a name="get-query-runtime-key"></a>Abrufen des Abfrage-Runtimeschlüssels

Nach dem Veröffentlichen einer Wissensdatenbank benötigen Sie den Abfrage-Runtimeschlüssel, um die Runtime abzufragen. Dabei handelt es sich nicht um den Schlüssel, der zum Erstellen des ursprünglichen Clientobjekts verwendet wurde.

Verwenden Sie die Methode [EndpointKeys.getKeys](/javascript/api/@azure/cognitiveservices-qnamaker/endpointkeys), um die Klasse [EndpointKeysDTO](/javascript/api/@azure/cognitiveservices-qnamaker/endpointkeysdto) abzurufen.

Verwenden Sie eine der im Objekt zurückgegeben Schlüsseleigenschaften, um die Wissensdatenbank abzufragen.

[!code-javascript[Get query runtime key](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=GetQueryEndpointKey)]

### <a name="authenticate-the-runtime-for-generating-an-answer"></a>Authentifizieren der Runtime zum Erstellen einer Antwort

Erstellen Sie ein QnAMakerRuntimeClient-Element, um die Wissensdatenbank abzufragen und eine Antwort zu generieren oder mit aktivem Lernen zu trainieren.

[!code-javascript[Authenticate the runtime](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=AuthorizationQuery)]

Verwenden Sie den QnAMakerRuntimeClient, um eine Antwort aus der Wissensdatenbank abzurufen oder ihr neue Fragenvorschläge für [aktives Lernen](../concepts/active-learning-suggestions.md) zu senden.

### <a name="generate-an-answer-from-the-knowledge-base"></a>Generieren einer Antwort auf der Grundlage der Wissensdatenbank

Generieren Sie mithilfe der Methode „RuntimeClient.runtime.generateAnswer“ eine Antwort aus einer veröffentlichten Wissensdatenbank. Diese Methode akzeptiert die Wissensdatenbank-ID und die [QueryDTO](/javascript/api/@azure/cognitiveservices-qnamaker/querydto)-Klasse. Greifen Sie auf weitere QueryDTO-Eigenschaften zu (etwa „Top“ und „Context“), und verwenden Sie sie in Ihrem Chatbot.

[!code-javascript[Generate an answer from a knowledge base](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=GenerateAnswer)]

# <a name="qna-maker-managed-preview-release"></a>[QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

### <a name="generate-an-answer-from-the-knowledge-base"></a>Generieren einer Antwort auf der Grundlage der Wissensdatenbank

Generieren Sie mithilfe der Methode „QnAMakerClient.knowledgebase.generateAnswer“ eine Antwort auf der Grundlage einer veröffentlichten Wissensdatenbank. Diese Methode akzeptiert die Wissensdatenbank-ID und die [QueryDTO](/javascript/api/@azure/cognitiveservices-qnamaker/querydto)-Klasse. Greifen Sie auf weitere QueryDTO-Eigenschaften zu (etwa „Top“ und „Context“), und verwenden Sie sie in Ihrem Chatbot.

[!code-javascript[Generate an answer from a knowledge base](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/preview-sdk/quickstart.js?name=GenerateAnswer)]

---

Dies ist ein einfaches Beispiel zum Abfragen der Wissensdatenbank. Informationen zu erweiterten Abfrageszenarien finden Sie in [weiteren Abfragebeispielen](../quickstarts/get-answer-from-knowledge-base-using-url-tool.md?pivots=url-test-tool-curl#use-curl-to-query-for-a-chit-chat-answer).

## <a name="delete-a-knowledge-base"></a>Löschen einer Wissensdatenbank

Löschen Sie die Wissensdatenbank mit der [delete](/javascript/api/@azure/cognitiveservices-qnamaker/knowledgebase#deletemethod-string--msrest-requestoptionsbase-)-Methode mit einem Parameter der Wissensdatenbank-ID.

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

[!code-javascript[Delete a knowledge base](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=DeleteKB)]

# <a name="qna-maker-managed-preview-release"></a>[Mit QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

[!code-javascript[Delete a knowledge base](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/preview-sdk/quickstart.js?name=DeleteKB)]

---

## <a name="get-status-of-an-operation"></a>Abrufen des Status eines Vorgangs

Einige Methoden, wie „create“ und „update“, können so viel Zeit in Anspruch nehmen, dass ein [Vorgang](/javascript/api/@azure/cognitiveservices-qnamaker/operations) zurückgegeben wird, anstatt auf den Abschluss des Prozesses zu warten. Verwenden Sie die [Vorgangs-ID](/javascript/api/@azure/cognitiveservices-qnamaker/operation#operationid) des Vorgangs, um den Status der ursprünglichen Methode mittels Abrufen (mit Wiederholungslogik) zu bestimmen.

Der _delayTimer_-Aufruf im folgenden Codeblock wird verwendet, um die Wiederholungslogik zu simulieren. Ersetzen Sie ihn durch Ihre eigene Wiederholungslogik.

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

[!code-javascript[Monitor an operation](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/qnamaker_quickstart.js?name=MonitorOperation)]

# <a name="qna-maker-managed-preview-release"></a>[Mit QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

[!code-javascript[Monitor an operation](~/cognitive-services-quickstart-code/javascript/QnAMaker/sdk/preview-sdk/quickstart.js?name=MonitorOperation)]

---

## <a name="run-the-application"></a>Ausführen der Anwendung

Führen Sie die Anwendung mit dem Befehl `node index.js` über das Anwendungsverzeichnis aus.

```console
node index.js
```

# <a name="qna-maker-ga-stable-release"></a>[QnA Maker, allgemeine Verfügbarkeit (stabile Version)](#tab/version-1)

Den Quellcode für dieses Beispiel finden Sie auf [GitHub](https://github.com/Azure-Samples/cognitive-services-quickstart-code/blob/master/javascript/QnAMaker/sdk/qnamaker_quickstart.js).

# <a name="qna-maker-managed-preview-release"></a>[QnA Maker verwaltet (Vorschauversion)](#tab/version-2)

Den Quellcode für dieses Beispiel finden Sie auf [GitHub](https://github.com/Azure-Samples/cognitive-services-quickstart-code/blob/master/javascript/QnAMaker/sdk/preview-sdk/quickstart.js).

---
