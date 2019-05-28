---
title: Konta księgowania likwidacji środków trwałych
description: W tym temacie wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji likwidacji środków trwałych.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8e00c00b0cb7058858fde3774941911ce20fb6f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567536"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Konta księgowania likwidacji środków trwałych

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji likwidacji środków trwałych.

Na stronie Profile księgowania środków trwałych na skróconej karcie Konta księgowe wybierz Likwidacja — sprzedaż i Likwidacja — odpadki, aby ustawić księgowanie do księgi.

Dla obu typów transakcji na konto księgowe wpływa wartość likwidacji środka trwałego. Księgowanie po stronie debetowej obciąży konto przeciwstawne, którym może być na przykład konto bankowe. Jeśli środek trwały zostanie sprzedany odbiorcy, zamiast konta przeciwstawnego użyte zostanie konto odbiorcy.

Kliknij Likwidacja, następnie kliknij Sprzedaż lub Odpadki, a następnie skonfiguruj szczegóły kont, aby wycofać wartość księgową netto środka trwałego. Można również wprowadzić informacje w polach Księguj wartość i Typ wartości sprzedaży na stronie Parametry likwidacji. 

Transakcja likwidacji środka trwałego w puli środków trwałych o niskiej wartości zmniejsza wartość księgową netto tej puli tylko o kwotę danej likwidacji. Jeśli jednak wartość sprzedaży takiego środka trwałego przekracza wartość księgową netto wspomnianej puli, wartość księgowa netto zostanie zmniejszona do zera.





