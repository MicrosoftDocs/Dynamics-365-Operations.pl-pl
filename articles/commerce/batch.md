---
title: Ulepszona obsługa towarów śledzonych w partii
description: W tym temacie opisano ulepszenia dotyczące obsługi partii (w zakresie pozycji śledzonych w partii) podczas procesu księgowania zestawień.
author: josaw1
manager: AnnBe
ms.date: 11/04/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: ecff18f0a34d22ef359f473fa6aaaff16c811bb6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459708"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Ulepszona obsługa pozycji śledzonych w partii


[!include [banner](includes/banner.md)]


W punkcie sprzedaży (POS) nie można w momencie sprzedaży przechwytywać identyfikatorów partii dla pozycji śledzonych w partii. Jednak w przypadku określonych konfiguracji, gdy sprzedaż jest księgowana w centrali w ramach procesu księgowania zamówień odbiorcy lub zestawień, system Microsoft Dynamics oczekuje, że istnieją prawidłowe numery partii dla towarów śledzonych w partii oraz że będą one używane w procesie fakturowania.

Jeśli dla produktów są dostępne prawidłowe numery partii, będą one używane w procesie fakturowania zamówień odbiorcy oraz procesie fakturowania zamówień sprzedaży na podstawie księgowania zestawienia. W przeciwnym razie nie będzie można wykonać księgowania w ramach procesu fakturowania zamówień odbiorcy, a użytkownik w punkcie sprzedaży zobaczy komunikat o błędzie. Następnie proces księgowania zestawienia przejdzie do stanu błędu. Ten stan błędu występuje nawet wtedy, gdy dla produktów został włączony ujemny poziom zapasów.

Ulepszenia wprowadzone w rozwiązaniu Retail w wersji 10.0.4 i nowszych umożliwiają zagwarantowanie, że w sytuacji, gdy dla towarów śledzonych w partii włączono ujemny poziom zapasów, fakturowanie zamówień odbiorców i fakturowanie zamówień sprzedaży za pośrednictwem księgowania zestawienia nie będzie blokowane dla tych towarów, gdy ilość zapasów będzie równa 0 (zero) lub gdy numer partii będzie niedostępny. Gdy numery partii są niedostępne, ta nowa funkcjonalność używa dla wierszy sprzedaży domyślnego identyfikatora partii.

Aby zdefiniować domyślny identyfikator partii, który będzie używany dla zamówień odbiorców, na skróconej karcie **Zamówienie** na karcie **Zamówienia odbiorców** na stronie **Parametry handlowe** ustaw wartość pola **Domyślny identyfikator partii**.

Aby zdefiniować domyślny identyfikator partii, który będzie używany podczas fakturowania zamówień sprzedaży za pośrednictwem fakturowania zestawienia, na skróconej karcie **Aktualizacja zapasów** na karcie **Księgowanie** na stronie **Parametry handlowe** ustaw wartość pola **Domyślny identyfikator partii**.

> [!NOTE]
> Ta funkcjonalność jest dostępna tylko wtedy, gdy dla konkretnego magazynu sklepu i towarów jest włączona funkcja zaawansowanego magazynowania. W późniejszym wydaniu ta funkcjonalność będzie również obsługiwana w scenariuszach, w których nie jest używana funkcja zaawansowanego zarządzania magazynem.

> [!NOTE]
> W wersji 10.0.5 rozwiązania Retail została wprowadzona pomoc techniczna do ulepszonej obsługi towarów śledzonych w partii podczas księgowania zestawienia dla scenariuszy niezaawansowanego zarządzania magazynem.
