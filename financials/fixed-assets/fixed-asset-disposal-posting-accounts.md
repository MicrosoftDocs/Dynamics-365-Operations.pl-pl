---
title: "Konta księgowania likwidacji środków trwałych"
description: "W tym artykule wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji likwidacji środków trwałych."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 670a67de2287fa5d0be29463f6f456b27fd88000
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-asset-disposal-posting-accounts"></a>Konta księgowania likwidacji środków trwałych

W tym artykule wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji likwidacji środków trwałych.

Na stronie Profile księgowania środków trwałych na skróconej karcie Konta księgowe wybierz Likwidacja — sprzedaż i Likwidacja — odpadki, aby ustawić księgowanie do księgi.

Dla obu typów transakcji na konto księgowe wpływa wartość likwidacji środka trwałego. Księgowanie po stronie debetowej obciąży konto przeciwstawne, którym może być na przykład konto bankowe. Jeśli środek trwały zostanie sprzedany odbiorcy, zamiast konta przeciwstawnego użyte zostanie konto odbiorcy.

Kliknij Likwidacja, następnie kliknij Sprzedaż lub Odpadki, a następnie skonfiguruj szczegóły kont, aby wycofać wartość księgową netto środka trwałego. Można również wprowadzić informacje w polach Księguj wartość i Typ wartości sprzedaży na stronie Parametry likwidacji. 

Transakcja likwidacji środka trwałego w puli środków trwałych o niskiej wartości zmniejsza wartość księgową netto tej puli tylko o kwotę danej likwidacji. Jeśli jednak wartość sprzedaży takiego środka trwałego przekracza wartość księgową netto wspomnianej puli, wartość księgowa netto zostanie zmniejszona do zera.




