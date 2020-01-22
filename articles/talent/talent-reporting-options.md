---
title: Opcje raportowania w aplikacji Talent
description: W tym temacie opisano, jak rozwiązać ten problem, w którym odbiorca chce dostosować raporty Microsoft Dynamics 365 Talent lub tworzyć nowe raporty.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 05d4a2c4314b40042ae45b4f653554bad09be4fa
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897955"
---
# <a name="reporting-options-in-talent"></a>Opcje raportowania w aplikacji Talent

**Szczegóły środowiska**

Ten problem dotyczy wszystkich środowisk.

**Objaw**

Odbiorca chce dostosować raporty Microsoft Dynamics 365 Talent lub tworzyć nowe raporty.

**Wystawienie**

Użytkownik nie może dostosować osadzonych raportów programu Microsoft Power BI.

**Rozwiązanie**

- Dane Core HR wysyłane do Common Data Service mogą być zgłaszane w za pośrednictwem łącznika Power Apps Common Data Service do Power BI Desktop. Należy zauważyć, że usługa Common Data Service zawiera podzbiór danych Core HR. Aby uzyskać więcej informacji dotyczących Power BI i pulpitów nawigacyjnych, zobacz [Tworzenie raportów Power BI i pulpitów nawigacyjnych za pomocą Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- Raportowanie elektroniczne (RE) jest dostępne dla niektórych raportach w Talent. Dostosowania według odbiorcy można wykonać za pomocą opcji konfiguracji ER.
- Dane można eksportować do Microsoft Excel lub Microsoft Word przy użyciu różnych elementów danych, które Talent dostarcza dzięki integracji z Microsoft Office.

**Rozwiązanie długoterminowe**

Dodatkowe opcje Power BI będą dostępne i więcej danych i jednostek będzie wchodzić w skład Common Data Service.
