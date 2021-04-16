---
title: Opcje raportowania
description: W tym artykule opisano, jak rozwiązać ten problem, w którym odbiorca chce dostosować raporty Microsoft Dynamics 365 Human Resources lub tworzyć nowe raporty.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2d0fc6b2d4af6ad021943717645bfff7a27797a8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803904"
---
# <a name="reporting-options"></a>Opcje raportowania

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

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