---
title: Bereitstellen von Inhalt mithilfe von FTP/S
description: Erfahren Sie, wie Sie Ihre App mithilfe von FTP oder FTPS in Azure App Service bereitstellen. Verbessern Sie die Websitesicherheit, indem Sie das unverschlüsselte Dateiübertragungsprotokoll deaktivieren.
ms.assetid: ae78b410-1bc0-4d72-8fc4-ac69801247ae
ms.topic: article
ms.date: 09/18/2019
ms.reviewer: dariac
ms.custom: seodec18
ms.openlocfilehash: cfec5ec5f14afc8c4eba5c21c5904687c9b187cc
ms.sourcegitcommit: f5b8410738bee1381407786fcb9d3d3ab838d813
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98209252"
---
# <a name="deploy-your-app-to-azure-app-service-using-ftps"></a>Bereitstellen der App in Azure App Service mithilfe von FTP/S

In diesem Artikel erfahren Sie, wie Sie eine Web-App, das mobile App-Back-End oder eine API-App mithilfe von FTP oder FTPS in [Azure App Service](./overview.md) bereitstellen.

Der FTP/S-Endpunkt für Ihre App ist bereits aktiv. Zum Aktivieren der FTP/S-Bereitstellung ist keine Konfiguration erforderlich.

## <a name="open-ftp-dashboard"></a>Öffnen des FTP-Dashboards

1. Suchen Sie im [Azure-Portal](https://portal.azure.com) nach **App Services**, und wählen Sie den Eintrag aus.

    ![Suchen Sie nach App Services.](media/app-service-continuous-deployment/search-for-app-services.png)

2. Wählen Sie die Web-App aus, die Sie bereitstellen möchten.

    ![Wählen Sie Ihre App aus.](media/app-service-continuous-deployment/select-your-app.png)

3. Wählen Sie **Bereitstellungscenter** > **FTP** > **Dashboard** aus.

    ![Öffnen des FTP-Dashboards](./media/app-service-deploy-ftp/open-dashboard.png)

## <a name="get-ftp-connection-information"></a>Abrufen der FTP-Verbindungsinformationen

Klicken Sie auf dem FTP-Dashboard auf **Kopieren**, um den FTPS-Endpunkt und die App-Anmeldeinformationen zu kopieren.

![Kopieren von FTP-Informationen](./media/app-service-deploy-ftp/ftp-dashboard.png)

Es wird empfohlen, **App-Anmeldeinformationen** für die Bereitstellung in Ihrer App zu verwenden, da diese für jede App eindeutig sind. Wenn Sie jedoch auf **Benutzeranmeldeinformationen** klicken, können Sie Anmeldeinformationen auf Benutzerebene festlegen, die Sie für die FTP/S-Anmeldung bei allen App Service-Anwendungen in Ihrem Abonnement verwenden können.

> [!NOTE]
> Für die Authentifizierung an einem FTP/FTPS-Endpunkt mit Anmeldeinformationen auf Benutzerebene ist ein Benutzername im folgenden Format erforderlich: 
>
>`<app-name>\<user-name>`
>
> Weil Anmeldeinformationen auf Benutzerebene mit dem Benutzer und nicht einer bestimmten Ressource verknüpft sind, muss der Benutzername dieses Format aufweisen, damit die Anmeldeaktion an den richtigen App-Endpunkt weitergeleitet wird.
>

## <a name="deploy-files-to-azure"></a>Bereitstellen von Dateien in Azure

1. Verwenden Sie in Ihrem FTP-Client (z.B. [Visual Studio](https://www.visualstudio.com/vs/community/), [Cyberduck](https://cyberduck.io/) oder [WinSCP](https://winscp.net/index.php)) die gesammelten Verbindungsinformationen, um eine Verbindung mit Ihrer App herzustellen.
2. Kopieren Sie Ihre Dateien und die entsprechende Verzeichnisstruktur in das Verzeichnis [ **/site/wwwroot**](https://github.com/projectkudu/kudu/wiki/File-structure-on-azure) in Azure (bzw. für WebJobs in das Verzeichnis **/site/wwwroot/App_Data/Jobs/** ).
3. Navigieren Sie zur URL Ihrer App, um sicherzustellen, dass die Anwendung richtig ausgeführt wird. 

> [!NOTE] 
> Im Gegensatz zu [Git-basierten Bereitstellungen](deploy-local-git.md) unterstützt die FTP-Bereitstellung keine der folgenden Bereitstellungsautomatisierungen: 
>
> - Wiederherstellungen der Abhängigkeit (z.B. NuGet-, NPM-, PIP- oder Composer-Automatisierungen)
> - Kompilierung von .NET-Binärdateien
> - Generierung von „web.config“ (hier sehen Sie ein [Node.js-Beispiel](https://github.com/projectkudu/kudu/wiki/Using-a-custom-web.config-for-Node-apps))
> 
> Generieren Sie diese erforderlichen Dateien auf Ihrem lokalen Computer manuell, und stellen Sie sie zusammen mit Ihrer App bereit.
>

## <a name="enforce-ftps"></a>Erzwingen von FTPS

Aus Sicherheitsgründen sollten Sie nur FTP über TLS/SSL zulassen. Sie können auch FTP und FTPS deaktivieren, wenn Sie keine FTP-Bereitstellung verwenden.

Wählen Sie auf der Ressourcenseite Ihrer App im [Azure-Portal](https://portal.azure.com) im linken Navigationsbereich **Konfiguration** > **Allgemeine Einstellungen** aus.

Um unverschlüsselte FTP-Verbindungen zu deaktivieren, aktivieren Sie **Nur FTPS** unter **FTP-Zustand**. Um FTP und FTPS vollständig zu deaktivieren, wählen Sie **Deaktiviert** aus. Klicken Sie abschließend auf **Speichern**. Bei Verwendung von **Nur FTPS** müssen Sie die Verwendung von TLS 1.2 oder höher erzwingen, indem Sie zum Blatt mit den **TLS/SSL-Einstellungen** Ihrer Web-App navigieren. TLS 1.0 und 1.1 werden für **Nur FTPS** nicht unterstützt.

![Deaktivieren von FTP/S](./media/app-service-deploy-ftp/disable-ftp.png)

## <a name="automate-with-scripts"></a>Automatisieren mit Skripts

Informationen zur FTP-Bereitstellung mithilfe der [Azure CLI](/cli/azure) finden Sie unter [Erstellen einer Web-App und Bereitstellen von Dateien über FTP (Azure CLI)](./scripts/cli-deploy-ftp.md).

Informationen zur FTP-Bereitstellung mithilfe von [Azure PowerShell](/cli/azure) finden Sie unter [Hochladen von Dateien in eine Web-App mithilfe von FTP (PowerShell)](./scripts/powershell-deploy-ftp.md).

[!INCLUDE [What happens to my app during deployment?](../../includes/app-service-deploy-atomicity.md)]

## <a name="troubleshoot-ftp-deployment"></a>Problembehandlung bei der FTP-Bereitstellung

- [Bereitstellen der App in Azure App Service mithilfe von FTP/S](#deploy-your-app-to-azure-app-service-using-ftps)
  - [Öffnen des FTP-Dashboards](#open-ftp-dashboard)
  - [Abrufen der FTP-Verbindungsinformationen](#get-ftp-connection-information)
  - [Bereitstellen von Dateien in Azure](#deploy-files-to-azure)
  - [Erzwingen von FTPS](#enforce-ftps)
  - [Automatisieren mit Skripts](#automate-with-scripts)
  - [Problembehandlung bei der FTP-Bereitstellung](#troubleshoot-ftp-deployment)
    - [Wie behebe ich Probleme bei der FTP-Bereitstellung?](#how-can-i-troubleshoot-ftp-deployment)
    - [Ich kann meinen Code nicht mit FTP erreichen und veröffentlichen. Wie kann ich das Problem beheben?](#im-not-able-to-ftp-and-publish-my-code-how-can-i-resolve-the-issue)
    - [Wie kann ich in Azure App Service über den passiven Modus eine Verbindung mit FTP herstellen?](#how-can-i-connect-to-ftp-in-azure-app-service-via-passive-mode)
  - [Nächste Schritte](#next-steps)
  - [Weitere Ressourcen](#more-resources)

### <a name="how-can-i-troubleshoot-ftp-deployment"></a>Wie behebe ich Probleme bei der FTP-Bereitstellung?

Der erste Schritt in der Problembehandlung bei der FTP-Bereitstellung besteht darin, ein Bereitstellungsproblem von einem Laufzeitproblem der Anwendung zu trennen.

Bereitstellungsprobleme führen in der Regel dazu, dass für Ihre Anwendung keine oder die falschen Dateien bereitgestellt werden. Sie können dies durch Untersuchen Ihrer FTP-Bereitstellung oder Auswählen einer alternativen Bereitstellungsmethode (z.B. Quellcodeverwaltung) beheben.

Laufzeitprobleme der Anwendung führen in der Regel dazu, dass die richtigen Dateien für Ihre App bereitgestellt werden, die App jedoch ein falsches Verhalten aufweist. Sie können dies beheben, indem Sie sich auf das Codeverhalten zur Laufzeit konzentrieren und spezifische Fehlerpfade untersuchen.

Weitere Informationen zur Ermittlung, ob es sich um ein Bereitstellungs- oder Laufzeitproblem handelt, finden Sie unter [Probleme mit Bereitstellung oder Laufzeit](https://github.com/projectkudu/kudu/wiki/Deployment-vs-runtime-issues).

### <a name="im-not-able-to-ftp-and-publish-my-code-how-can-i-resolve-the-issue"></a>Ich kann meinen Code nicht mit FTP erreichen und veröffentlichen. Wie kann ich das Problem beheben?
Vergewissern Sie sich, dass Sie den richtigen Hostnamen und die richtigen [Anmeldeinformationen](#open-ftp-dashboard) eingegeben haben. Stellen Sie auch sicher, dass die folgenden FTP-Ports auf dem Computer nicht durch eine Firewall blockiert werden:

- Port für FTP-Kontrollverbindung:
- Port für FTP-Datenverbindung: 989, 10001–10300
 
### <a name="how-can-i-connect-to-ftp-in-azure-app-service-via-passive-mode"></a>Wie kann ich in Azure App Service über den passiven Modus eine Verbindung mit FTP herstellen?
Azure App Service unterstützt das Herstellen einer Verbindung im aktiven und passiven Modus. Der passive Modus wird bevorzugt, da sich Bereitstellungscomputer in der Regel hinter einer Firewall (im Betriebssystem oder als Teil eines Heim- oder Firmennetzwerks) befinden. Weitere Informationen finden Sie in einem [Beispiel in der WinSCP-Dokumentation](https://winscp.net/docs/ui_login_connection). 

## <a name="next-steps"></a>Nächste Schritte

Für komplexere Bereitstellungsszenarien versuchen Sie die [Bereitstellung in Azure mit Git](deploy-local-git.md). Die Git-basierte Bereitstellung in Azure ermöglicht Versionskontrolle, Paketwiederherstellung, MSBuild und mehr.

## <a name="more-resources"></a>Weitere Ressourcen

* [Anmeldeinformationen für die Azure App Service-Bereitstellung](deploy-configure-credentials.md)