---
title: Opcje raportowania
description: W tym temacie wyjaśniono sposób dostosowywania raportów programu Microsoft Dynamics 365 Human Resources lub tworzenia nowych raportów.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4649005d6944c05310fc40f0dfd10519b2739ff0
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693984"
---
# <a name="reporting-options"></a>Opcje raportowania


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



**Szczegóły środowiska**

Ten problem dotyczy wszystkich środowisk.

**Objaw**

Odbiorca chce dostosować raporty Microsoft Dynamics 365 Human Resources lub tworzyć nowe raporty.

**Wystawienie**

Użytkownik nie może dostosować osadzonych raportów programu Microsoft Power BI.

**Rozwiązanie**

- Dane programu Human Resources wysyłane do Dataverse mogą być zgłaszane w za pośrednictwem łącznika Power Apps Dataverse do Power BI Desktop. Należy zauważyć, że usługa Dataverse zawiera podzbiór danych programu Human Resources. Aby uzyskać więcej informacji dotyczących Power BI i pulpitów nawigacyjnych, zobacz [Tworzenie raportów Power BI i pulpitów nawigacyjnych za pomocą Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- Raportowanie elektroniczne (RE) jest dostępne dla niektórych raportach w programie Human Resources. Dostosowania według odbiorcy można wykonać za pomocą opcji konfiguracji ER.
- Dane można eksportować do Microsoft Excel lub Microsoft Word przy użyciu różnych elementów danych, które moduł Human Resources dostarcza dzięki integracji z Microsoft Office.

**Rozwiązanie długoterminowe**

Dodatkowe opcje Power BI będą dostępne i więcej danych i jednostek będzie wchodzić w skład Dataverse.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
