---
author: normesta
ms.service: storage
ms.topic: include
ms.date: 09/28/2020
ms.author: normesta
ms.openlocfilehash: e3732823be1c8391f2bec9018a094200c7c93a5e
ms.sourcegitcommit: 829d951d5c90442a38012daaf77e86046018e5b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91710985"
---
| Eigenschaft | BESCHREIBUNG |
|:--- |:---|
|**identity / type** | Hierbei handelt es sich um den für die Anforderung verwendeten Authentifizierungstyp, z. B. `OAuth`, `SAS Key`, `Account Key` oder `Anonymous`. |
|**identity / tokenHash**|Dieses Feld ist ausschließlich zur internen Verwendung vorgesehen. |
|**authorization / action** | Hierbei handelt es sich um die der Anforderung zugewiesene Aktion. |
|**authorization / roleAssignmentId** | Hierbei handelt es sich um die Rollenzuweisungs-ID. Beispiel: `4e2521b7-13be-4363-aeda-111111111111`.|
|**authorization / roleDefinitionId** | Hierbei handelt es sich um die Rollendefinitions-ID. Beispiel: `ba92f5b4-2d11-453d-a403-111111111111"`.|
|**principals / id** | Hierbei handelt es sich um die ID des Sicherheitsprinzipals. Beispiel: `a4711f3a-254f-4cfb-8a2d-111111111111`.|
|**principals / type** | Hierbei handelt es sich um den Typ des Sicherheitsprinzipals. Beispiel: `ServicePrincipal`. |
|**requester / appID** | Hierbei handelt es sich um die OAuth-Anwendungs-ID (Open Authorization), die als Anforderer verwendet wird. <br> Beispiel: `d3f7d5fe-e64a-4e4e-871d-333333333333`.|
|**requester / audience** | Hierbei handelt es sich um die OAuth-Zielgruppe der Anforderung. Beispiel: `https://storage.azure.com`. |
|**requester / objectId** | Hierbei handelt es sich um die OAuth-Objekt-ID des Anforderers. Bei Kerberos-Authentifizierung stellt sie den Objektbezeichner des mit Kerberos authentifizierten Benutzers dar. Beispiel: `0e0bf547-55e5-465c-91b7-2873712b249c`. |
|**requester / tenantId** | Hierbei handelt es sich um die OAuth-Mandanten-ID der Identität. Beispiel: `72f988bf-86f1-41af-91ab-222222222222`.|
|**requester / tokenIssuer** | Hierbei handelt es sich um den Aussteller des OAuth-Tokens. Beispiel: `https://sts.windows.net/72f988bf-86f1-41af-91ab-222222222222/`.|
|**requester / upn** | Hierbei handelt es sich um den Benutzerprinzipalnamen (UPN) des Anforderers. Beispiel: `someone@contoso.com`. |
|**requester / userName** | Dieses Feld ist ausschließlich zur internen Verwendung vorgesehen.|