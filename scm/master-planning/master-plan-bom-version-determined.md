---
title: Ustalanie wersji BOM
description: "Jeśli jako domyślny typ zamówienia towar ma ustawioną wartość Produkcja, podczas rozłożenia popytu aparat planowania znajduje prawidłową wersję BOM na podstawie oddziału."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, InventItemOrderSetup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ee265d0ab7807cd92c70096111ffb3dbec11ad62
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="determine-the-bom-version"></a>Ustalanie wersji BOM

[!include[banner](../includes/banner.md)]


Jeśli jako domyślny typ zamówienia towar ma ustawioną wartość Produkcja, podczas rozłożenia popytu aparat planowania znajduje prawidłową wersję BOM na podstawie oddziału. 

Wymiar lokalizacji jest zawsze znany i znajduje się w transakcji popytu. Proces określania właściwej wersji BOM przebiega następująco:

-   Jeśli w oddziale popytu jest zdefiniowana wersja BOM dla towaru, program używa tego BOM związanego z oddziałem.
-   Jeśli w oddziale popytu nie została zdefiniowana wersja BOM dla towaru, program używa ogólnego BOM. W ogólnym BOM nie jest określony oddział i jest on prawidłowy dla wielu oddziałów. Jeśli istnieje ogólny BOM, jest on używany przez program.
-   Jeśli nie istnieje ogólna wersja BOM, której można użyć, rozłożenie popytu jest zatrzymywane w tym momencie.

Prawidłowa wersja BOM, czy to oddziałowa, czy ogólna, musi spełnić wymagane kryteria daty i ilości.






