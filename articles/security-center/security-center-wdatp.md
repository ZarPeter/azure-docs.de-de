---
title: Verwenden der in Azure Security Center enthaltenen Lizenz für Microsoft Defender für den Endpunkt
description: Hier erfahren Sie mehr über Microsoft Defender für den Endpunkt und dessen Bereitstellung aus Azure Security Center.
services: security-center
documentationcenter: na
author: memildin
manager: rkarlin
ms.service: security-center
ms.devlang: na
ms.topic: how-to
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/20/2020
ms.author: memildin
ms.openlocfilehash: 519285f2bad352aa16bdc8d9a1db7a63c2eb04e5
ms.sourcegitcommit: aaa65bd769eb2e234e42cfb07d7d459a2cc273ab
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98876392"
---
# <a name="protect-your-endpoints-with-security-centers-integrated-edr-solution-microsoft-defender-for-endpoint"></a>Schützen Sie Ihre Endpunkte mit der in Security Center integrierten EDR-Lösung: Microsoft Defender für den Endpunkt

Microsoft Defender für den Endpunkt ist eine ganzheitliche, cloudbasierte Lösung für die Endpunktsicherheit. Wichtigste Features:

- Risikobasierte Verwaltung und Bewertung von Sicherheitsrisiken 
- Verringerung der Angriffsfläche
- Verhaltensbasierter und cloudgestützter Schutz
- Endpoint Detection and Response (EDR, Endpunkterkennung und Reaktion)
- Automatisierte Untersuchung und Wiederherstellung
- Verwaltete Bedrohungssuchdienste

> [!TIP]
> Endpoint Detection and Response (EDR) wurde ursprünglich als **Windows Defender ATP** veröffentlicht und 2019 in **Microsoft Defender ATP** umbenannt.
>
> Auf der Ignite 2020 wurde die [Microsoft Defender XDR-Suite](https://www.microsoft.com/security/business/threat-protection) vorgestellt, und diese EDR-Komponente wurde in **Microsoft Defender für den Endpunkt** umbenannt.


## <a name="availability"></a>Verfügbarkeit

| Aspekt                          | Details                                                                                                                                                                                                                                                                                                       |
|---------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Status des Release:                  | Allgemein verfügbar (Generally Available, GA)                                                                                                                                                                                                                                                                                      |
| Preise:                        | Erfordert [Azure Defender für Server](security-center-pricing.md)                                                                                                                                                                                                                                             |
| Unterstützte Plattformen:            | Azure-Computer unter Windows<br>Azure Arc-Computer unter Windows|
| Unterstützte Windows-Versionen:  |  • Security Center unterstützt die Erkennung unter Windows Server 2016, 2012 R2 und 2008 R2 SP1.<br> • Die Serverendpunktüberwachung, die diese Integration verwendet, wurde für Office 365-GCC-Kunden deaktiviert.|
| Nicht unterstützte Betriebssysteme:  |  • Windows Server 2019<br> • Windows 10<br> • Linux|
| Erforderliche Rollen und Berechtigungen: | So aktivieren/deaktivieren Sie die Integration: **Sicherheitsadministrator** oder **Besitzer**<br>So zeigen Sie MDATP-Warnungen in Security Center an: **Sicherheitsleseberechtigter**, **Leser**, **Ressourcengruppenmitwirkender**, **Ressourcengruppenbesitzer**, **Sicherheitsadministrator**, **Abonnementbesitzer** oder **Abonnementmitwirkender**|
| Clouds:                         | ![Ja](./media/icons/yes-icon.png) Kommerzielle Clouds<br>![Ja](./media/icons/yes-icon.png) US Gov<br>![Nein](./media/icons/no-icon.png) China Gov/andere Gov-Clouds<br>![Nein](./media/icons/no-icon.png) GCC-Kunden, die Workloads in globalen Azure-Clouds ausführen                                                        |
|                                 |                                                                                                                                                                                                                                                                                                               |


## <a name="microsoft-defender-for-endpoint-features-in-security-center"></a>Features von Microsoft Defender für den Endpunkt in Security Center

Microsoft Defender für den Endpunkt bietet folgende Features:

- **Erweiterte Erkennungssensoren für Sicherheitsverletzungen**. Sensoren von Defender für den Endpunkt für Windows-Computer sammeln eine Vielzahl von verhaltensbezogenen Signalen.

- **Auf Analysen basierende, cloudgestützte Erkennung von Sicherheitsverletzungen**. Defender für den Endpunkt nimmt eine schnelle Anpassung an sich ändernde Bedrohungen vor. Das Produkt verwendet fortschrittliche Analysen und Big Data. Es wird durch die Leistungsfähigkeit von Intelligent Security Graph mit Signalen aus Windows, Azure und Office verstärkt, um unbekannte Bedrohungen zu erkennen. Das Produkt stellt aussagekräftige Warnmeldungen zur Verfügung und ermöglicht eine schnelle Reaktion.

- **Informationen zu Bedrohungen:** Defender für den Endpunkt generiert Warnungen, wenn es Angriffstools, -techniken und -verfahren erkennt. Das Produkt verwendet Daten, die von Microsoft-Bedrohungsspezialisten und Sicherheitsteams generiert werden, ergänzt durch Informationen von Partnern.

Durch die Integration von Defender für den Endpunkt in Security Center können Sie von den folgenden zusätzlichen Funktionen profitieren:

- **Automatisiertes Onboarding**. Security Center aktiviert automatisch den Sensor von Microsoft Defender für Endpunkte für alle Windows-Server, die von Security Center überwacht werden. Dies gilt nicht für Server, auf denen Windows Server 2019 ausgeführt wird. Für diese muss über ein lokales Skript, ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) oder [Microsoft Endpoint Configuration Manager](/mem/configmgr/) (früher SCCM) ein Onboarding durchgeführt werden.

- **Zentralisierte Benutzeroberfläche**. Die Security Center-Konsole zeigt Warnungen aus Microsoft Defender für den Endpunkt an. Zur weiteren Untersuchung verwenden Sie die speziellen Portalseiten von Microsoft Defender für den Endpunkt, auf denen Sie zusätzliche Informationen wie die Warnungsprozessstruktur und das Incidentdiagramm finden. Sie können auch eine detaillierte Computerzeitachse verwenden, die jedes Verhalten über einen historischen Zeitraum von bis zu sechs Monaten anzeigt.

    :::image type="content" source="./media/security-center-wdatp/microsoft-defender-security-center.png" alt-text="Security Center von Microsoft Defender für den Endpunkt" lightbox="./media/security-center-wdatp/microsoft-defender-security-center.png":::

## <a name="microsoft-defender-for-endpoint-tenant-location"></a>Mandantenstandort in Microsoft Defender für den Endpunkt

Wenn Sie Azure Security Center zum Überwachen Ihrer Server verwenden, wird automatisch ein Mandant für Microsoft Defender für den Endpunkt erstellt. Die von Defender für den Endpunkt gesammelten Daten werden im Rahmen der Bereitstellung des Mandanten am Standort des Mandanten gespeichert. Kundendaten (in pseudonymisierter Form) können auch in den zentralen Speicher- und Verarbeitungssystemen in den USA gespeichert werden. 

Nachdem Sie den Speicherort konfiguriert haben, kann dieser nicht mehr geändert werden. Wenn Sie Ihre eigene Lizenz für Microsoft Defender für Endpunkt besitzen und Ihre Daten an einen anderen Speicherort verschieben müssen, bitten Sie den Microsoft-Support, den Mandanten zurückzusetzen.


## <a name="enabling-the-microsoft-defender-for-endpoint-integration"></a>Aktivieren der Integration von Microsoft Defender für den Endpunkt

1. Aktivieren Sie **Azure Defender für Server**. Weitere Informationen finden Sie unter [Preise für Azure Security Center](security-center-pricing.md#enable-azure-defender).

    > [!NOTE]
    > Verwenden Sie zum Schützen Ihrer Computer mit Azure Arc-Unterstützung die Anweisungen unter [Schnellstart: Verbinden eines Hybridcomputers mit Servern mit Azure Arc-Unterstützung](../azure-arc/servers/learn/quick-enable-hybrid-vm.md) aus.

1. Wenn Sie Microsoft Defender für den Endpunkt bereits lizenziert und auf Ihren Servern bereitgestellt haben, entfernen Sie diesen mithilfe des unter [Ausschließen von Windows-Servern](/windows/security/threat-protection/microsoft-defender-atp/configure-server-endpoints#offboard-windows-servers) beschriebenen Verfahrens.
1. Wählen Sie im Menü von Security Center **Preise und Einstellungen** aus.
1. Wählen Sie das Abonnement aus, das Sie ändern möchten.
1. Wählen Sie **Bedrohungserkennung** aus.
1. Wählen Sie **Microsoft Defender für Endpunkt den Zugriff auf meine Daten erlauben** und dann **Speichern** aus.

    :::image type="content" source="./media/security-center-wdatp/enable-integration-with-edr.png" alt-text="Aktivieren der Integration zwischen Azure Security Center und Microsoft Defender für den Endpunkt, der EDR-Lösung von Microsoft":::

    Azure Security Center integriert die Server automatisch in Microsoft Defender für den Endpunkt. Das Onboarding kann bis zu 24 Stunden dauern.


## <a name="access-the-microsoft-defender-for-endpoint-portal"></a>Zugreifen auf das Portal von Microsoft Defender für den Endpunkt

1. Vergewissern Sie sich, dass das Benutzerkonto über die notwendigen Berechtigungen verfügt. [Weitere Informationen](/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access)

1. Überprüfen Sie, ob Sie einen Proxy oder eine Firewall einsetzen, der bzw. die anonymen Datenverkehr blockiert. Der Sensor von Defender für den Endpunkt stellt eine Verbindung aus dem Systemkontext her, daher muss anonymer Datenverkehr zugelassen werden. Um den ungehinderten Zugriff auf das Portal von Defender für den Endpunkt sicherzustellen, befolgen Sie die Anweisungen unter [Aktivieren des Zugriffs auf Dienst-URLs im Proxyserver](/windows/security/threat-protection/microsoft-defender-atp/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).

1. Öffnen Sie das [Microsoft Defender Security Center-Portal](https://securitycenter.windows.com/). Weitere Informationen zu den Features und Symbolen des Portals finden Sie in der [Übersicht über das Microsoft Defender Security Center-Portal](/windows/security/threat-protection/microsoft-defender-atp/portal-overview). 

## <a name="send-a-test-alert"></a>Senden einer Testwarnung

So generieren Sie eine unbedenkliche Testwarnung in Microsoft Defender für den Endpunkt

1. Erstellen Sie einen Ordner „C:\test-MDATP-test“.
1. Verwenden Sie Remotedesktop, um auf Ihren Computer zuzugreifen.
1. Öffnen Sie ein Befehlszeilenfenster.
1. Kopieren Sie an der Eingabeaufforderung den folgenden Befehl, und führen Sie ihn aus. Das Eingabeaufforderungsfenster wird automatisch geschlossen.

    ```powershell
    powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden (New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe'); Start-Process 'C:\\test-MDATP-test\\invoice.exe'
    ```
    :::image type="content" source="./media/security-center-wdatp/generate-edr-alert.png" alt-text="Ein Eingabeaufforderungsfenster mit dem Befehl zum Generieren einer Testwarnung":::

1. Wenn der Befehl erfolgreich ist, wird Ihnen eine neue Warnung im Azure Security Center-Dashboard und im Portal von Microsoft Defender für den Endpunkt angezeigt. Die Anzeige dieser Warnung kann einige Minuten dauern.
1. Um die Warnung in Security Center zu überprüfen, navigieren Sie zu **Sicherheitswarnungen** > **Verdächtige PowerShell-Befehlszeile**.
1. Wählen Sie im Untersuchungsfenster den Link aus, um zum Portal von Microsoft Defender für den Endpunkt zu navigieren.

    > [!TIP]
    > Die Warnung wird mit dem Schweregrad **Info** ausgelöst.

## <a name="faq-for-security-centers-integrated-microsoft-defender-for-endpoint"></a>Häufig gestellte Fragen zum in Security Center integrierten Microsoft Defender für den Endpunkt

- [Welche Lizenzierungsanforderungen gelten für Microsoft Defender für den Endpunkt?](#what-are-the-licensing-requirements-for-microsoft-defender-for-endpoint)
- [Kann ich für Azure Defender einen Rabatt erhalten, wenn ich bereits über eine Lizenz für Microsoft Defender für Endpunkt verfüge?](#if-i-already-have-a-license-for-microsoft-defender-for-endpoint-can-i-get-a-discount-for-azure-defender)
- [Wie steige ich von einem Drittanbieter-EDR-Tool um?](#how-do-i-switch-from-a-third-party-edr-tool)

### <a name="what-are-the-licensing-requirements-for-microsoft-defender-for-endpoint"></a>Welche Lizenzierungsanforderungen gelten für Microsoft Defender für den Endpunkt?
Defender für den Endpunkt ist ohne zusätzliche Kosten in **Azure Defender für Server** enthalten. Alternativ kann er separat für 50 Computer oder mehr erworben werden.

### <a name="if-i-already-have-a-license-for-microsoft-defender-for-endpoint-can-i-get-a-discount-for-azure-defender"></a>Kann ich für Azure Defender einen Rabatt erhalten, wenn ich bereits über eine Lizenz für Microsoft Defender für Endpunkt verfüge?
Wenn Sie bereits eine Lizenz für Microsoft Defender für Endpunkt besitzen, müssen Sie für diesen Teil Ihrer Azure Defender-Lizenz nicht bezahlen.

Wenden Sie sich an das Security Center-Supportteam, um den Rabatt zu bestätigen, und geben Sie für jede relevante Lizenz die entsprechende Arbeitsbereichs-ID, die Region und die Lizenzinformationen an.

### <a name="how-do-i-switch-from-a-third-party-edr-tool"></a>Wie steige ich von einem Drittanbieter-EDR-Tool um?
Vollständige Anweisungen zum Wechseln von einer Nicht-Microsoft-Endpunktlösung finden Sie in der Dokumentation zu Microsoft Defender für den Endpunkt: [Übersicht über die Migration](/windows/security/threat-protection/microsoft-defender-atp/switch-to-microsoft-defender-migration).
  


## <a name="next-steps"></a>Nächste Schritte

- [Von Azure Security Center unterstützte Features und Plattformen](security-center-os-coverage.md)
- [Verwalten von Sicherheitsempfehlungen in Azure Security Center](security-center-recommendations.md): Erfahren Sie, wie Empfehlungen Ihnen beim Schutz Ihrer Azure-Ressourcen helfen.