---
title: "Zbilansowane arkusze dla księgowania międzyjednostkowego"
description: "W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga."
author: twheeloc
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5b1d788ebd5617a1d3f1c8ca36f5ae3c29b534c5
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="balanced-journals-for-interunit-accounting"></a>Zbilansowane arkusze dla księgowania międzyjednostkowego

[!include [banner](../includes/banner.md)]

W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga. 

Jeśli zapisy na koncie nie bilansują się na poziomie wartości wymiaru finansowego, zapisy dodatkowe konta są tworzone automatycznie do zrównoważenia arkusza. Te zapisy na kontach używają typów księgowania **Międzyjednostkowe — debet** i**Międzyjednostkowe — kredyt** na stronie **kont dla transakcji automatycznych** w celu określenia konta głównego. Na przykład: jednostka biznesowa, czyli drugi segment konta księgowego, jest wybrany jako wymiar finansowy bilansowania i trzeba utworzyć następujące wpisy księgowe.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100,00 DR |
| 6100 – NY – OU\_249  | 100,00 DR |
| 2100 – MSP – OU\_256 | 200,00 CR |

W tym przypadku określane są następujące salda:

-   Dla jednostki biznesowej MSP = 100,00 CR
-   Dla jednostki biznesowej NY = 100,00 DR

Dlatego następujące wpisy księgowe są tworzone automatycznie w celu zbilansowania arkusza na poziomie wartości wymiaru finansowego.

|                                   |           |
|-----------------------------------|-----------|
| (Międzyjednostkowe — debet) – MSP – OU\_256 | 100,00 DR |
| (Międzyjednostkowe — kredyt) – NY – OU\_249 | 100,00 CR |






