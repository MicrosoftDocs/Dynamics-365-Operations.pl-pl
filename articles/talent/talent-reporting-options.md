---
title: Opcje raportowania w aplikacji Talent
description: "W tym temacie opisano, jak rozwiązać ten problem, w którym odbiorca chce dostosować raporty Microsoft Dynamics 365 for Talent lub tworzyć nowe raporty."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

---

# <a name="reporting-options-in-talent"></a>Opcje raportowania w aplikacji Talent

[!include [banner](includes/banner.md)]

**Szczegóły środowiska**

Ten problem dotyczy wszystkich środowisk.

**Objaw**

Odbiorca chce dostosować raporty Microsoft Dynamics 365 for Talent lub tworzyć nowe raporty.

**Wydaj**

Użytkownik nie może dostosować osadzonych raportów programu Microsoft Power BI.

**Rozwiązanie**

- Dane Core HR wysyłane do Common Data Service for Apps mogą być zgłaszane w za pośrednictwem łącznika usługi PowerApps CDS do Power BI Desktop. Należy zauważyć, że usługa Common Data Service for Apps zawiera podzbiór danych Core HR. Aby uzyskać więcej informacji dotyczących Power BI i pulpitów nawigacyjnych, zobacz [tworzenie raportów Power BI i pulpitów nawigacyjnych za pomocą PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).
- Raportowanie elektroniczne (RE) jest dostępne dla niektórych raportach w Talent. Dostosowania według odbiorcy można wykonać za pomocą opcji konfiguracji ER.
- Dane można eksportować do Microsoft Excel lub Microsoft Word przy użyciu różnych elementów danych, które Talent dostarcza dzięki integracji z Microsoft Office.

**Rozwiązanie długoterminowe**

Dodatkowe opcje Power BI będą dostępne i więcej danych i jednostek będzie wchodzić w skład Common Data Service for Apps.

