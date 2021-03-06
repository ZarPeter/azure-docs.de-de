---
title: Azure Defender für SQL
description: Hier erhalten Sie Informationen zu den Funktionen zur Verwaltung von Datenbankrisiken und die Erkennung ungewöhnlicher Aktivitäten, die eine Bedrohung für Ihre Datenbank in Azure SQL-Datenbank, Azure SQL Managed Instance oder Azure Synapse darstellen können.
services: sql-database
ms.service: sql-db-mi
ms.subservice: security
ms.devlang: ''
ms.custom: sqldbrb=2
ms.topic: conceptual
ms.author: memildin
manager: rkarlin
author: memildin
ms.reviewer: vanto
ms.date: 12/01/2020
ms.openlocfilehash: 4bb7f2fd5823a9d8ebf4234f3bb41d955574b838
ms.sourcegitcommit: 6a350f39e2f04500ecb7235f5d88682eb4910ae8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96451545"
---
# <a name="azure-defender-for-sql"></a>Azure Defender für SQL
[!INCLUDE[appliesto-sqldb-sqlmi-asa](../includes/appliesto-sqldb-sqlmi-asa.md)]


Azure Defender für SQL ist ein einheitliches Paket für erweiterte SQL-Sicherheitsfunktionen. Azure Defender ist für Azure SQL-Datenbank, Azure SQL Managed Instance und Azure Synapse Analytics verfügbar. Dazu zählen die Funktionen zur Ermittlung und Klassifizierung sensibler Daten, Ermittlung und Verringerung potenzieller Datenbankschwachstellen und Erkennung ungewöhnlicher Aktivitäten, die eine Bedrohung für Ihre Datenbank darstellen können. Es bietet einen einzelnen Anlaufpunkt zum Aktivieren und Verwalten dieser Funktionen.

## <a name="overview"></a>Übersicht

Azure Defender stellt eine Reihe erweiterter SQL-Sicherheitsfunktionen bereit, darunter SQL-Risikoanalyse und Advanced Threat Protection.
- Die [Sicherheitsrisikobewertung](sql-vulnerability-assessment.md) ist ein einfach zu konfigurierender Dienst, mit dem potenzielle Schwachstellen in der Datenbank ermittelt, nachverfolgt und behoben werden können. Er bietet Einblicke in Ihren Sicherheitsstatus, enthält umsetzbare Schritte zum Beheben von Sicherheitsproblemen und verbessert Ihre Datenbanksicherheit.
- [Advanced Threat Protection](threat-detection-overview.md) erkennt Anomalien bei Aktivitäten, die auf ungewöhnliche und potenziell schädliche Versuche hinweisen, auf Ihre Datenbank zuzugreifen oder diese zu nutzen. Sie überwacht Ihre Datenbank fortlaufend auf verdächtige Aktivitäten und bietet sofortige Sicherheitswarnungen zu potenziellen Sicherheitsrisiken, Angriffen durch Einschleusung von Azure SQL-Befehlen und ungewöhnlichen Datenbankzugriffsmustern. Die Warnungen von Advanced Threat Protection enthalten Details zu verdächtigen Aktivitäten sowie Empfehlungen, wie die Bedrohung untersucht und abgewendet werden kann.

Sie müssen Azure Defender für SQL nur einmal aktivieren, um alle diese enthaltenen Funktionen zu aktivieren. Mit nur einem Klick können Sie Azure Defender für alle Datenbanken auf Ihrem [Server](logical-servers.md) in Azure oder Azure SQL Managed Instance aktivieren. Um Azure Defender-Einstellungen aktivieren oder verwalten zu können, müssen Sie der Rolle [SQL-Sicherheits-Manager](../../role-based-access-control/built-in-roles.md#sql-security-manager) oder einer der Datenbank- oder Serveradministratorrollen angehören.

Weitere Informationen zu den Preisen für Azure Defender für SQL finden Sie auf der Seite [Azure Security Center – Preise](https://azure.microsoft.com/pricing/details/security-center/).

## <a name="getting-started-with-azure-defender"></a>Erste Schritte mit Azure Defender

Die folgenden Schritte bilden den Einstieg in Azure Defender.

## <a name="enable-azure-defender"></a>Aktivieren von Azure Defender

Sie können über das [Azure-Portal](https://portal.azure.com) auf Azure Defender zugreifen. Aktivieren Sie Azure Defender, indem Sie unterhalb der Überschrift **Sicherheit** für Ihren Server oder Ihre verwaltete Instanz zu **Security Center** navigieren.

> [!NOTE]
> Ein Speicherkonto wird automatisch erstellt und konfiguriert, um die Speicherkontoergebnisse der **Sicherheitsrisikobewertung** zu speichern. Wenn Sie Azure Defender bereits für einen anderen Server in derselben Ressourcengruppe und Region aktiviert haben, wird das vorhandene Speicherkonto verwendet.
>
> Die Kosten von Azure Defender orientieren sich am Azure Security Center-Standardtarif pro Knoten, wobei ein Knoten dem gesamten Server oder der verwalteten Instanz entspricht. Sie bezahlen daher nur einmal für den Schutz aller Datenbanken auf dem Server oder in der verwalteten Instanz durch Azure Defender. Sie können Azure Defender anfänglich mit einer kostenlosen Testversion testen.

:::image type="content" source="media/azure-defender-for-sql/enable-azure-defender.png" alt-text="Aktivieren von Azure Defender":::

## <a name="start-tracking-vulnerabilities-and-investigating-threat-alerts"></a>Beginnen mit dem Nachverfolgen von Sicherheitsrisiken und Untersuchen von Bedrohungswarnungen

Klicken Sie auf die Karte **Sicherheitsrisikobewertung**, um Sicherheitsrisikoscans und -berichte anzuzeigen und zu verwalten und Ihren Sicherheitsstatus zu verfolgen. Wenn Sie Sicherheitswarnungen empfangen haben, klicken Sie auf die Karte **Advanced Threat Protection**, um Details zu den Warnungen anzuzeigen und einen konsolidierten Bericht für alle Warnungen in Ihrem Azure-Abonnement über die Seite mit den Sicherheitswarnungen im Azure Security Center abzurufen.

## <a name="manage-azure-defender-settings"></a>Verwalten von Azure Defender-Einstellungen

Um die Azure Defender-Einstellungen anzuzeigen und zu verwalten, navigieren Sie unterhalb der Überschrift **Sicherheit** für Ihren Server oder Ihre verwaltete Instanz zu **Security Center**. Auf dieser Seite können Sie Azure Defender aktivieren oder deaktivieren und die Einstellungen für die Sicherheitsrisikoanalyse und Advanced Threat Protection für Ihren gesamten Server oder Ihre verwaltete Instanz ändern.

:::image type="content" source="media/azure-defender-for-sql/security-server-settings.png" alt-text="Sicherheitseinstellungen für den Server":::

## <a name="manage-azure-defender-settings-for-a-database"></a>Verwalten von Azure Defender-Einstellungen für eine Datenbank

Um die Azure Defender-Einstellungen für eine bestimmte Datenbank außer Kraft zu setzen, aktivieren Sie in den Einstellungen von **Security Center** für Ihre Datenbank das Kontrollkästchen **Enable Azure Defender for SQL at the database level** (Azure Defender für SQL auf Datenbankebene aktivieren). Verwenden Sie diese Option nur, wenn eine besondere Anforderung zum Empfangen von separaten Advanced Threat Protection-Warnungen oder Risikoanalyseergebnissen für diese Datenbank vorliegt, die anstelle der Warnungen für alle Datenbanken auf dem Server oder in der verwalteten Instanz oder zusätzlich zu diesen empfangen werden müssen.

Sobald das Kontrollkästchen aktiviert wurde, können Sie die relevanten Einstellungen für diese Datenbank konfigurieren.

:::image type="content" source="media/azure-defender-for-sql/enable-for-database-level.png" alt-text="Aktivieren von Azure Defender auf Datenbankebene":::

Sie können auch über den Azure Defender-Datenbankbereich auf die Azure Defender für SQL-Einstellungen für Ihren Server oder Ihre verwaltete Instanz zugreifen. Klicken Sie im Hauptbereich von Security Center auf **Einstellungen** und dann auf **View Azure Defender for SQL server settings** (Servereinstellungen für Azure Defender für SQL anzeigen).

## <a name="next-steps"></a>Nächste Schritte

- Weitere Informationen zur [Sicherheitsrisikobewertung](sql-vulnerability-assessment.md)
- Weitere Informationen zu [Advanced Threat Protection](threat-detection-configure.md)
- Weitere Informationen zu [Azure Security Center](../../security-center/security-center-introduction.md)