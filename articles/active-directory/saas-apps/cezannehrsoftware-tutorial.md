---
title: 'Tutorial: Azure Active Directory-Integration mit Cezanne HR Software | Microsoft Docs'
description: Erfahren Sie, wie Sie das einmalige Anmelden zwischen Azure Active Directory und Cezanne HR Software konfigurieren.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 02/12/2019
ms.author: jeedes
ms.openlocfilehash: faecba93fbbc9e25ea85b644e0254f07747611dc
ms.sourcegitcommit: 32ee8da1440a2d81c49ff25c5922f786e85109b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "109786031"
---
# <a name="tutorial-azure-active-directory-integration-with-cezanne-hr-software"></a>Tutorial: Azure Active Directory-Integration mit Cezanne HR Software

In diesem Tutorial erfahren Sie, wie Sie Cezanne HR Software in Azure Active Directory (Azure AD) integrieren.
Die Integration von Cezanne HR Software in Azure AD bietet die folgenden Vorteile:

* Sie können in Azure AD steuern, wer auf Cezanne HR Software Zugriff hat.
* Sie können es Benutzern ermöglichen, sich mit ihren Azure AD-Konten automatisch bei Cezanne HR Software anzumelden (einmaliges Anmelden; Single Sign-On, SSO).
* Sie können Ihre Konten über das Azure-Portal an einem zentralen Ort verwalten.

Weitere Informationen zur Integration von SaaS-Apps in Azure AD finden Sie unter [Was bedeuten Anwendungszugriff und einmaliges Anmelden mit Azure Active Directory?](../manage-apps/what-is-single-sign-on.md).
Wenn Sie kein Azure-Abonnement besitzen, können Sie ein [kostenloses Konto](https://azure.microsoft.com/free/) erstellen, bevor Sie beginnen.

## <a name="prerequisites"></a>Voraussetzungen

Um die Azure AD-Integration mit Cezanne HR Software konfigurieren zu können, benötigen Sie Folgendes:

* Ein Azure AD-Abonnement Wenn Sie keine Azure AD-Umgebung besitzen, können Sie [hier](https://azure.microsoft.com/pricing/free-trial/) eine einmonatige Testversion anfordern.
* Cezanne HR Software-Abonnement, für das einmaliges Anmelden aktiviert ist

## <a name="scenario-description"></a>Beschreibung des Szenarios

In diesem Tutorial konfigurieren und testen Sie das einmalige Anmelden von Azure AD in einer Testumgebung.

* Cezanne HR Software unterstützt **SP-initiiertes** einmaliges Anmelden.

## <a name="adding-cezanne-hr-software-from-the-gallery"></a>Hinzufügen von Cezanne HR Software aus dem Katalog

Zum Konfigurieren der Integration von Cezanne HR Software in Azure AD müssen Sie Cezanne HR Software aus dem Katalog der Liste mit den verwalteten SaaS-Apps hinzufügen.

**Um Cezanne HR Software aus dem Katalog hinzuzufügen, führen Sie die folgenden Schritte aus:**

1. Klicken Sie im linken Navigationsbereich des **[Azure-Portals](https://portal.azure.com)** auf das Symbol für **Azure Active Directory**.

    ![Schaltfläche „Azure Active Directory“](common/select-azuread.png)

2. Navigieren Sie zu **Unternehmensanwendungen**, und wählen Sie die Option **Alle Anwendungen** aus.

    ![Blatt „Unternehmensanwendungen“](common/enterprise-applications.png)

3. Klicken Sie oben im Dialogfeld auf die Schaltfläche **Neue Anwendung**, um eine neue Anwendung hinzuzufügen.

    ![Schaltfläche „Neue Anwendung“](common/add-new-app.png)

4. Geben Sie im Suchfeld **Cezanne HR Software** ein, wählen Sie im Ergebnisbereich **Cezanne HR Software** aus, und klicken Sie dann auf die Schaltfläche **Hinzufügen**, um die Anwendung hinzuzufügen.

    ![Cezanne HR Software in der Ergebnisliste](common/search-new-app.png)

## <a name="configure-and-test-azure-ad-single-sign-on"></a>Konfigurieren und Testen des einmaligen Anmeldens in Azure AD

Dieser Abschnitt veranschaulicht anhand eines Testbenutzers namens **Britta Simon**, wie das einmalige Anmelden von Azure AD mit Cezanne HR Software konfiguriert und getestet wird.
Damit einmaliges Anmelden funktioniert, muss eine Linkbeziehung zwischen einem Azure AD-Benutzer und dem entsprechenden Benutzer in Cezanne HR Software eingerichtet werden.

Zum Konfigurieren und Testen des einmaligen Anmeldens in Azure AD bei Cezanne HR Software müssen Sie die folgenden Bausteine ausführen:

1. **[Konfigurieren des einmaligen Anmeldens von Azure AD](#configure-azure-ad-single-sign-on)** , um Ihren Benutzern das Verwenden dieses Features zu ermöglichen.
2. **[Konfigurieren des einmaligen Anmeldens für Cezanne HR Software](#configure-cezanne-hr-software-single-sign-on)** , um die Einstellungen für einmaliges Anmelden auf der Anwendungsseite zu konfigurieren
3. **[Erstellen eines Azure AD-Testbenutzers](#create-an-azure-ad-test-user)** , um das einmalige Anmelden mit Azure AD mit dem Testbenutzer Britta Simon zu testen.
4. **[Zuweisen des Azure AD-Testbenutzers](#assign-the-azure-ad-test-user)** , um Britta Simon für das einmalige Anmelden von Azure AD zu aktivieren.
5. **[Erstellen eines Cezanne HR Software-Testbenutzers](#create-cezanne-hr-software-test-user)** , um eine Entsprechung von Britta Simon in Cezanne HR Software zu erhalten, die mit ihrer Benutzerdarstellung in Azure AD verknüpft ist
6. **[Testen der einmaligen Anmeldung](#test-single-sign-on)** , um zu überprüfen, ob die Konfiguration funktioniert.

### <a name="configure-azure-ad-single-sign-on"></a>Konfigurieren des einmaligen Anmeldens in Azure AD

In diesem Abschnitt aktivieren Sie das einmalige Anmelden von Azure AD im Azure-Portal.

Führen Sie zum Konfigurieren des einmaligen Anmeldens von Azure AD mit Cezanne HR Software die folgenden Schritte aus:

1. Wählen Sie im [Azure-Portal](https://portal.azure.com/) auf der Anwendungsintegrationsseite für **Cezanne HR Software** die Option **Einmaliges Anmelden**.

    ![Konfigurieren des Links für einmaliges Anmelden](common/select-sso.png)

2. Wählen Sie im Dialogfeld **SSO-Methode auswählen** den Modus **SAML/WS-Fed** aus, um einmaliges Anmelden zu aktivieren.

    ![Auswahlmodus für einmaliges Anmelden](common/select-saml-option.png)

3. Klicken Sie auf der Seite **Einmaliges Anmelden (SSO) mit SAML einrichten** auf das Symbol **Bearbeiten**, um das Dialogfeld **Grundlegende SAML-Konfiguration** zu öffnen.

    ![Bearbeiten der SAML-Basiskonfiguration](common/edit-urls.png)

4. Führen Sie im Abschnitt **Grundlegende SAML-Konfiguration** die folgenden Schritte aus:

    ![SSO-Informationen zur Domäne und zu den URLs für Cezanne HR Software](common/sp-identifier-reply.png)

    a. Geben Sie im Textfeld **Anmelde-URL** eine URL im folgenden Format ein: `https://w3.cezanneondemand.com/CezanneOnDemand/-/<tenantidentifier>`.

    b. Geben Sie im Textfeld **Bezeichner (Entitäts-ID)** die folgende URL ein: `https://w3.cezanneondemand.com/CezanneOnDemand/`.

    c. Geben Sie im Textfeld **Antwort-URL** eine URL nach folgendem Muster ein: `https://w3.cezanneondemand.com:443/cezanneondemand/-/<tenantidentifier>/Saml/samlp`
    
    > [!NOTE]
    > Hierbei handelt es sich um Beispielwerte. Ersetzen Sie diese Werte durch die tatsächliche Anmelde-URL und Antwort-URL. Wenden Sie sich an das [Kundensupportteam von Cezanne HR Software](https://cezannehr.com/services/support/), um diese Werte zu erhalten.

5. Klicken Sie auf der Seite **Einmaliges Anmelden (SSO) mit SAML einrichten** im Abschnitt **SAML-Signaturzertifikat** auf **Herunterladen**, um das Ihrer Anforderung entsprechende **Zertifikat (Base64)** aus den angegebenen Optionen herunterzuladen und auf Ihrem Computer zu speichern.

    ![Downloadlink für das Zertifikat](common/certificatebase64.png)

6. Kopieren Sie im Abschnitt **Cezanne HR Software einrichten** die entsprechenden URLs gemäß Ihren Anforderungen.

    ![Kopieren der Konfiguration-URLs](common/copy-configuration-urls.png)

    a. Anmelde-URL

    b. Azure AD-Bezeichner

    c. Abmelde-URL

### <a name="configure-cezanne-hr-software-single-sign-on"></a>Konfigurieren des einmaligen Anmeldens für Cezanne HR Software

1. Melden Sie sich in einem anderen Webbrowserfenster an Ihrem Cezanne HR Software-Mandanten als Administrator an.

2. Klicken Sie im seitlichen Menü auf **Administration** (Verwaltung). Navigieren Sie dann zu **Security Settings** (Sicherheitseinstellungen), und klicken Sie auf **Single Sign-On** (Einmaliges Anmelden).

    ![Screenshot des Cezanne H R Software-Mandanten, bei dem „Sicherheitseinstellungen“ und „S S O-Konfiguration“ ausgewählt sind](https://user-images.githubusercontent.com/80324891/115692888-4c266900-a357-11eb-867d-7408b0ef16aa.png)

3. Aktivieren Sie im Bereich **Allow users to log in using the following Single Sign-On (SSO) Service** (Benutzeranmeldung per SSO-Dienst zulassen) das Kontrollkästchen **SAML 2.0**, und wählen Sie die Option für die **Erweiterte Konfiguration** aus.

    ![Screenshot des Bereichs „Benutzer zulassen“, in dem „SAML 2.0“ und „Erweiterte Konfiguration“ ausgewählt sind](https://user-images.githubusercontent.com/80324891/115693054-72e49f80-a357-11eb-93c7-9986770ac17e.png)

4. Klicken Sie auf die Schaltfläche **Neu hinzufügen** .

    ![Screenshot der Schaltfläche „Neu hinzufügen“](./media/cezannehrsoftware-tutorial/tutorial_cezannehrsoftware_002.png)

5. Füllen Sie im Abschnitt **SAML 2.0 IDENTITY PROVIDERS** (SAML 2.0-IDENTITÄTSANBIETER) die folgenden Felder aus, und klicken Sie auf **OK**.

    ![Screenshot eines Abschnitts, in dem Sie die in diesem Schritt beschriebenen Werte eingeben können](./media/cezannehrsoftware-tutorial/tutorial_cezannehrsoftware_003.png)

    a. **Display Name** (Anzeigename): Geben Sie den Namen Ihres Identitätsanbieters als Anzeigenamen ein.

    b. **Entity Identifier** (Entitäts-ID): Fügen Sie in das Textfeld „Entity Identifier“ (Entitäts-ID) den Wert für den Azure AD-Bezeichner ein, den Sie aus dem Azure-Portal kopiert haben.

    c. **SAML Binding** (SAML-Bindung): Ändern Sie die SAML-Bindung in „POST“.

    d. **Security Token Service Endpoint** (Sicherheitstoken-Dienstendpunkt): Fügen Sie in das Textfeld „Security Token Service Endpoint“ (Sicherheitstoken-Dienstendpunkt) den Wert der Anmelde-URL ein, den Sie aus dem Azure-Portal kopiert haben.

    e. **User ID Attribute Name** (Benutzer-ID-Attributname): Geben Sie in das Textfeld „User ID Attribute Name“ (Benutzer-ID-Attributname) die Zeichenfolge http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress ein.

    f. **Public Key Certificate** (Öffentliches Schlüsselzertifikat): Klicken Sie auf das Symbol „Hochladen“, um das heruntergeladene Zertifikat aus dem Azure-Portal hochzuladen.

6. Klicken Sie auf OK.

7. Klicken Sie auf die Schaltfläche Save . 


### <a name="create-an-azure-ad-test-user"></a>Erstellen eines Azure AD-Testbenutzers

Das Ziel dieses Abschnitts ist das Erstellen eines Testbenutzers namens Britta Simon im Azure-Portal.

1. Wählen Sie im Azure-Portal im linken Bereich die Option **Azure Active Directory**, **Benutzer** und dann **Alle Benutzer** aus.

    ![Links „Benutzer und Gruppen“ und „Alle Benutzer“](common/users.png)

2. Wählen Sie oben im Bildschirm die Option **Neuer Benutzer** aus.

    ![Schaltfläche „Neuer Benutzer“](common/new-user.png)

3. Führen Sie in den Benutzereigenschaften die folgenden Schritte aus.

    ![Dialogfeld „Benutzer“](common/user-properties.png)

    a. Geben Sie im Feld **Name** den Namen **BrittaSimon** ein.
  
    b. Geben Sie im Feld **Benutzername** Folgendes ein: **brittasimon\@ihreunternehmensdomäne.erweiterung**.  
    Zum Beispiel, BrittaSimon@contoso.com

    c. Aktivieren Sie das Kontrollkästchen **Kennwort anzeigen**, und notieren Sie sich den Wert, der im Feld „Kennwort“ angezeigt wird.

    d. Klicken Sie auf **Erstellen**.

### <a name="assign-the-azure-ad-test-user"></a>Zuweisen des Azure AD-Testbenutzers

In diesem Abschnitt ermöglichen Sie Britta Simon die Verwendung des einmaligen Anmeldens von Azure, indem Sie ihr Zugriff auf Cezanne HR Software gewähren.

1. Wählen Sie im Azure-Portal die Option **Unternehmensanwendungen** aus, und wählen Sie dann **Alle Anwendungen** und **Cezanne HR Software** aus.

    ![Blatt „Unternehmensanwendungen“](common/enterprise-applications.png)

2. Wählen Sie in der Anwendungsliste **Cezanne HR Software** aus.

    ![Der Cezanne HR Software-Link in der Anwendungsliste](common/all-applications.png)

3. Wählen Sie im Menü auf der linken Seite **Benutzer und Gruppen** aus.

    ![Link „Benutzer und Gruppen“](common/users-groups-blade.png)

4. Klicken Sie auf die Schaltfläche **Benutzer hinzufügen**, und wählen Sie dann im Dialogfeld **Zuweisung hinzufügen** die Option **Benutzer und Gruppen** aus.

    ![Bereich „Zuweisung hinzufügen“](common/add-assign-user.png)

5. Wählen Sie im Dialogfeld **Benutzer und Gruppen** in der Liste „Benutzer“ den Eintrag **Britta Simon** aus, und klicken Sie dann unten im Bildschirm auf die Schaltfläche **Auswählen**.

6. Wenn Sie einen beliebigen Rollenwert in der SAML-Assertion erwarten, wählen Sie im Dialogfeld **Rolle auswählen** in der Liste die entsprechende Rolle für den Benutzer aus, und klicken Sie dann unten auf dem Bildschirm auf **Auswählen**.

7. Klicken Sie im Dialogfeld **Zuweisung hinzufügen** auf die Schaltfläche **Zuweisen**.

### <a name="create-cezanne-hr-software-test-user"></a>Erstellen eines Cezanne HR Software-Testbenutzers

Damit sich Azure AD-Benutzer bei Cezanne HR Software anmelden können, müssen sie in Cezanne HR Software bereitgestellt werden. Bei Cezanne HR Software ist die Bereitstellung ein manueller Vorgang.

**Führen Sie zum Bereitstellen eines Benutzerkontos die folgenden Schritte aus:**

1. Melden Sie sich als Administrator auf Ihrer Cezanne HR Software-Unternehmenswebsite an.

2. Klicken Sie im seitlichen Menü auf **Administration** (Verwaltung). Navigieren Sie dann zu **Users** (Benutzer), und klicken Sie auf **Add New User** (Neuen Benutzer hinzufügen).

    ![Screenshot des Cezanne H R Software-Mandanten, bei dem „Benutzer verwalten“ und „Neuen Benutzer hinzufügen“ ausgewählt sind](https://user-images.githubusercontent.com/80324891/115694050-6ad92f80-a358-11eb-81be-148de665e185.png)

3. Führen Sie im Abschnitt **Person Details** (Angaben zur Person) die folgenden Schritte aus:

    ![Screenshot des Abschnitts „Person Details“, in dem Sie die in diesem Schritt beschriebenen Werte eingeben können](https://user-images.githubusercontent.com/80324891/115694321-a70c9000-a358-11eb-8325-de2582d135ec.png)

    a. Legen Sie **Interner Benutzer** auf „AUS“ fest.

    b. Geben Sie den Vornamen ein.   

    c. Geben Sie den Nachnamen ein.

    d. Geben Sie die E-Mail-Adresse ein.

4. Führen Sie unter **Kontoinformationen** die folgenden Schritte aus:

    ![Screenshot der Kontoinformationen, in denen Sie die in diesem Schritt beschriebenen Werte eingeben können](https://user-images.githubusercontent.com/80324891/115694501-d3c0a780-a358-11eb-8873-0fc778b43775.png)

    a. Geben Sie im Textfeld **Benutzername** die E-Mail-Adresse des Benutzers, z.B. Brittasimon@contoso.com, ein.

    b. Geben Sie im Textfeld **Kennwort** das Kennwort des Benutzers ein.

    c. Wählen Sie unter **Sicherheitsrolle** die Option **HR Professional** (HR-Mitarbeiter).

    d. Klicken Sie auf **OK**.
    ![Screenshot: Schaltfläche „OK“](https://user-images.githubusercontent.com/80324891/115694644-f6eb5700-a358-11eb-9b23-a87a24921052.png)

5. Navigieren Sie zur Registerkarte **Einmalige Anmeldung**, und wählen Sie im Bereich **SAML 2.0 Identifiers** (SAML 2.0-Bezeichner) die Option **Neu hinzufügen**.

    ![Screenshot der Registerkarte „Einmaliges Anmelden“, auf der Sie „Neu hinzufügen“ auswählen können](https://user-images.githubusercontent.com/80324891/115694716-0b2f5400-a359-11eb-9192-d31f6c9d3e3e.png)

6. Wählen Sie unter **Identity Provider** (Identitätsanbieter) Ihren Identitätsanbieter aus, und geben Sie in das Textfeld **User Identifier** (Benutzer-ID) die E-Mail-Adresse des Benutzers ein.

    ![Screenshot der SAML 2.0-Bezeichner, bei denen Sie Ihren Identitätsanbieter und die Benutzer-ID auswählen können](https://user-images.githubusercontent.com/80324891/115694865-28fcb900-a359-11eb-9cd3-496a93124cc4.png)

7. Klicken Sie auf die Schaltfläche **Save** .

    ![Screenshot der Schaltfläche „Speichern“ für die Benutzereinstellungen](https://user-images.githubusercontent.com/80324891/115694880-3023c700-a359-11eb-85d4-83d057660cfb.png)

### <a name="test-single-sign-on"></a>Testen des einmaligen Anmeldens

In diesem Abschnitt testen Sie die Azure AD-Konfiguration für einmaliges Anmelden über den Zugriffsbereich.

Wenn Sie im Zugriffsbereich auf die Kachel „Cezanne HR Software“ klicken, sollten Sie automatisch bei der Cezanne HR Software-Instanz angemeldet werden, für die Sie einmaliges Anmelden eingerichtet haben. Weitere Informationen zum Zugriffsbereich finden Sie unter [Einführung in den Zugriffsbereich](../user-help/my-apps-portal-end-user-access.md).

## <a name="additional-resources"></a>Weitere Ressourcen

- [Liste der Tutorials zur Integration von SaaS-Apps in Azure Active Directory](./tutorial-list.md)

- [Was bedeuten Anwendungszugriff und einmaliges Anmelden mit Azure Active Directory?](../manage-apps/what-is-single-sign-on.md)

- [Was ist bedingter Zugriff?](../conditional-access/overview.md)
