---
title: Ustalanie wersji BOM
description: Jeśli jako domyślny typ zamówienia towar ma ustawioną wartość Produkcja, podczas rozłożenia popytu aparat planowania znajduje prawidłową wersję BOM na podstawie oddziału.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efc980e3a3dfff6d163812396613a1493f4428a4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213798"
---
# <a name="determine-the-bom-version"></a>Ustalanie wersji BOM

[!include [banner](../includes/banner.md)]

Jeśli jako domyślny typ zamówienia towar ma ustawioną wartość Produkcja, podczas rozłożenia popytu aparat planowania znajduje prawidłową wersję BOM na podstawie oddziału. 

Wymiar lokalizacji jest zawsze znany i znajduje się w transakcji popytu. Proces określania właściwej wersji BOM przebiega następująco:

-   Jeśli w oddziale popytu jest zdefiniowana wersja BOM dla towaru, program używa tego BOM związanego z oddziałem.
-   Jeśli w oddziale popytu nie została zdefiniowana wersja BOM dla towaru, program używa ogólnego BOM. W ogólnym BOM nie jest określony oddział i jest on prawidłowy dla wielu oddziałów. Jeśli istnieje ogólny BOM, jest on używany przez program.
-   Jeśli nie istnieje ogólna wersja BOM, której można użyć, rozłożenie popytu jest zatrzymywane w tym momencie.

Prawidłowa wersja BOM, czy to oddziałowa, czy ogólna, musi spełnić wymagane kryteria daty i ilości.





