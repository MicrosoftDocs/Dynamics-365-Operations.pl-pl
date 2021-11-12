---
title: Zbilansowane arkusze dla księgowania międzyjednostkowego
description: W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga.
author: kweekley
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f6ffccb2ee504f182250dbf6d316823efafddf5
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2021
ms.locfileid: "7726901"
---
# <a name="balanced-journals-for-interunit-accounting"></a>Zbilansowane arkusze dla księgowania międzyjednostkowego

[!include [banner](../includes/banner.md)]

W tym artykule przedstawiono sposób automatycznego bilansowania arkusza po wybraniu wymiaru finansowego na stronie Księga. 

Jeśli zapisy na koncie nie bilansują się na poziomie wartości wymiaru finansowego, zapisy dodatkowe konta są tworzone automatycznie do zrównoważenia arkusza. Te zapisy na kontach używają typów księgowania **Międzyjednostkowe — debet** i **Międzyjednostkowe — kredyt** na stronie **kont dla transakcji automatycznych** w celu określenia konta głównego. Na przykład: jednostka biznesowa, czyli drugi segment konta księgowego, jest wybrany jako wymiar finansowy bilansowania i trzeba utworzyć następujące wpisy księgowe.

| &nbsp;               | &nbsp;    |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100,00 DR |
| 6100 – NY – OU\_249  | 100,00 DR |
| 2100 – MSP – OU\_256 | 200,00 CR |

W tym przypadku określane są następujące salda:

-   Dla jednostki biznesowej MSP = 100,00 CR
-   Dla jednostki biznesowej NY = 100,00 DR

Dlatego następujące wpisy księgowe są tworzone automatycznie w celu zbilansowania arkusza na poziomie wartości wymiaru finansowego.

| &nbsp;                            | &nbsp;    |
|-----------------------------------|-----------|
| (Międzyjednostkowe — debet) – MSP – OU\_256 | 100,00 DR |
| (Międzyjednostkowe — kredyt) – NY – OU\_249 | 100,00 CR |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
