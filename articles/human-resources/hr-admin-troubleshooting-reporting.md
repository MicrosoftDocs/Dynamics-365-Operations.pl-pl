---
title: Opcje raportowania
description: W tym artykule wyjaśniono sposób dostosowywania raportów programu Microsoft Dynamics 365 Human Resources lub tworzenia nowych raportów.
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
ms.openlocfilehash: 421883d314fb27b4592e9be0455946ab3730fb1a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856346"
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
