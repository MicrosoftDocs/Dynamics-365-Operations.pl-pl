---
title: "Konta księgowania nabycia środków trwałych"
description: "W tym artykule wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji nabycia środków trwałych."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a1a7da48b45566217399bc1d01a9c6e87ad56ec8
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="fixed-asset-acquisition-posting-accounts"></a>Konta księgowania nabycia środków trwałych

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji nabycia środków trwałych.

Konta używane do księgowani nabycia środków trwałych mogą się od siebie różnić w zależności od metody używanej do pozyskiwania składników aktywów. Na stronie Profile księgowania środków trwałych na karcie Konta księgowe należy wybrać opcje Nabycie i Korekta wartości początkowej, aby skonfigurować księgowanie kont środków trwałych do księgi. 

W arkuszach i w zamówieniach zakupu Konto księgowe jest zwykle kontem bilansowym, na którym wartość nabycia nowego środka trwałego księgowana jest po stronie debetowej. To konto nie jest wyświetlane w arkuszu i nie może zostać zastąpione w transakcjach. 

Konto przeciwstawne jest również kontem bilansowym. W arkuszu finansowym i w arkuszu środków trwałych to konto będzie często kontem bankowym używanym do dokonywania płatności za nabycie środka trwałego. Konto przeciwstawne jest domyślnym kontem, które jest zalecane w arkuszach. Można je zmienić w arkuszu na dowolne inne konto z planu kont lub na konto dostawcy, jeśli od niego został zakupiony środek trwały. 

Jeśli opcje Arkusz faktur lub Zamówienia zakupu w formularzu Rozrachunki z dostawcami są używane do nabywania środków trwałych, konto przeciwstawne dla transakcji środków trwałych zostanie zastąpione kontem dostawcy wybranym dla transakcji.

Dla transakcji nabycia zaksięgowanych przy użyciu arkusza Zapasy do środków trwałych w Księdze głównej środki trwałe nie są kupowane z zewnętrznych źródeł, a przenoszone z własnych zapasów firmy. Dlatego też konto przeciwstawne jest kontem wydań z magazynu dla towarów magazynowych w opcji Zarządzanie zapasami.

Aby uzyskać więcej informacji, zobacz [Nabywanie środków trwałych za pomocą zaopatrzenia](acquire-assets-procurement.md).




