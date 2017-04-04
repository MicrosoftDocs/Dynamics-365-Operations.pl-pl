---
title: "Sprawdź wersję BOM"
description: "Podczas wybuchu popytu Jeśli element ma domyślny typ zamówienia produkcji, aparat planowania znajduje prawidłowej wersji BOM-u, opartej na witrynie."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, InventItemOrderSetup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4e4f5f02dfa986669decbc8854148b5eff928c2a
ms.lasthandoff: 03/31/2017


---

# <a name="determine-the-bom-version"></a>Sprawdź wersję BOM

Podczas wybuchu popytu Jeśli element ma domyślny typ zamówienia produkcji, aparat planowania znajduje prawidłowej wersji BOM-u, opartej na witrynie. 

Wymiar lokalizacji jest zawsze znany i znajduje się w transakcji popytu. Proces określania właściwej wersji BOM przebiega następująco:

-   Jeśli w oddziale popytu jest zdefiniowana wersja BOM dla towaru, program używa tego BOM związanego z oddziałem.
-   Jeśli w oddziale popytu nie została zdefiniowana wersja BOM dla towaru, program używa ogólnego BOM. W ogólnym BOM nie jest określony oddział i jest on prawidłowy dla wielu oddziałów. Jeśli istnieje ogólny BOM, jest on używany przez program.
-   Jeśli nie istnieje ogólna wersja BOM, której można użyć, rozłożenie popytu jest zatrzymywane w tym momencie.

Prawidłowa wersja BOM, czy to oddziałowa, czy ogólna, musi spełnić wymagane kryteria daty i ilości.




