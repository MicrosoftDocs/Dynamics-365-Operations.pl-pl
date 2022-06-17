---
title: Ulepszona obsługa pozycji śledzonych w partii
description: W tym artykule opisano ulepszoną obsługę pozycji śledzonych w partii podczas procesu księgowania zestawień w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 736ab8dd21f04d7119cca6d53bfeb5e408b8cbd2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881886"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Ulepszona obsługa pozycji śledzonych w partii

[!include [banner](includes/banner.md)]

W tym artykule opisano ulepszoną obsługę pozycji śledzonych w partii podczas procesu księgowania zestawień w rozwiązaniu Microsoft Dynamics 365 Commerce.

W punkcie sprzedaży (POS) rozwiązania Dynamics 365 Commerce nie można w momencie sprzedaży przechwytywać numerów partii dla pozycji śledzonych w partii. Jednak w przypadku określonych konfiguracji, gdy sprzedaż jest księgowana w centrali rozwiązania Commerce w ramach procesu księgowania zamówień odbiorcy lub zestawień, rozwiązanie Commerce oczekuje, że istnieją prawidłowe numery partii dla pozycji śledzonych w partii oraz że będą one używane w procesie fakturowania.

Jeśli dla produktów są dostępne prawidłowe numery partii, będą one używane zarówno w procesie fakturowania zamówień odbiorcy, jak i procesie fakturowania zamówień sprzedaży na podstawie księgowania zestawienia. Jeśli dla produktów nie są dostępne prawidłowe numery partii, proces fakturowania zamówienia odbiorcy nie może zostać zaksięgowany, a użytkownik punktu sprzedaży otrzyma komunikat o błędzie. Wówczas księgowanie zestawienia przechodzi w stan błędu, nawet jeśli dla produktów włączona jest ujemna ilość zapasów.

Ulepszenia wprowadzone w rozwiązaniu Commerce zapewniają, że w sytuacji, gdy dla pozycji śledzonych w partii włączono ujemny poziom zapasów, fakturowanie zamówień odbiorcy i fakturowanie zamówień sprzedaży za pośrednictwem księgowania zestawienia nie będzie blokowane dla tych pozycji, gdy ilość zapasów będzie równa 0 (zero) lub gdy numer partii będzie niedostępny. Gdy numery partii są niedostępne, ta ulepszona funkcjonalność używa domyślnego identyfikatora partii dla wierszy sprzedaży.

## <a name="define-the-default-batch-id-that-is-used-for-customer-orders"></a>Służy do definiowania domyślnego identyfikatora partii stosowanego w zamówieniach odbiorcy

W celu zdefiniowania domyślnego identyfikatora partii stosowanego w zamówieniach odbiorcy, wykonaj następujące kroki.

1. W centrali rozwiązania Commerce przejdź do opcji **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry rozwiązania Commerce**.
1. Na karcie **Zamówienia odbiorcy**, na skróconej karcie **Zamówienie** wprowadź wartość w polu **Domyślny identyfikator partii**.

## <a name="define-the-default-batch-id-that-is-used-for-sales-order-invoicing-through-statement-posting"></a>Umożliwia zdefiniowanie domyślnego identyfikatora partii używanego do fakturowania zamówień sprzedaży poprzez księgowanie zestawienia

W celu zdefiniowania domyślnego identyfikatora partii używanego do fakturowania zamówień sprzedaży poprzez księgowanie zestawienia, wykonaj następujące kroki.

1. W centrali rozwiązania Commerce przejdź do opcji **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry rozwiązania Commerce**.
1. Na karcie **Księgowanie**, na skróconej karcie **Aktualizacja zapasów** wprowadź wartość w polu **Domyślny identyfikator partii**.

> [!NOTE]
> - Funkcjonalność domyślnej partii jest dostępna tylko wtedy, gdy dla konkretnego magazynu sklepu i towarów jest włączona funkcja zaawansowanego magazynowania. W przyszłym wydaniu funkcjonalność domyślnej partii będzie również obsługiwana w scenariuszach, w których nie jest włączona funkcja zaawansowanego zarządzania magazynem.
> - W wersji 10.0.5 rozwiązania Commerce została wprowadzona pomoc techniczna do ulepszonej obsługi towarów śledzonych w partii podczas księgowania zestawienia dla scenariuszy niezaawansowanego zarządzania magazynem.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
