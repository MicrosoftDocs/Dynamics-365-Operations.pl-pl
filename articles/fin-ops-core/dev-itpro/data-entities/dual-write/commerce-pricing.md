---
title: Używanie aparatu kalkulacji cen Dynamics 365 Commerce z rozwiązaniem Dynamics 365 Sales
description: W tym temacie opisano sposób używania aparatu kalkulacji cen w Microsoft Dynamics 365 Commerce z Dynamics 365 Sales w celu tworzenia ofert sprzedaży.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c3f1527e5f37bebba57661ca86b1a3aae7e62da0
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416762"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>Używanie aparatu kalkulacji cen Dynamics 365 Commerce z rozwiązaniem Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób używania aparatu kalkulacji cen w Microsoft Dynamics 365 Commerce z Dynamics 365 Sales w celu tworzenia ofert sprzedaży.

Aparat kalkulacji cen Dynamics 365 Commerce obsługuje większość scenariuszy kalkulacji cen w relacjach B2C, takich jak ceny na poziomie sklepu, ceny oparte na przynależności i lojalności, rabaty za skład zamówienia, rabaty ilościowe i rabaty progowe. Aparat cenowy używa złożonych reguł w celu określenia najlepszej ceny dla danej oferty lub zamówienia.

W przypadku korzystania z funkcji [podwójnego zapisu ](./dual-write-overview.md) dostępne są trzy opcje na potrzeby kalkulacji cen. Można skorzystać z statycznej ceny, która pochodzi z cennika systemu Dynamics 365 Sales, aparatu kalkulacji cen w Dynamics 365 Supply Chain Management lub aparatu kalkulacji cen w Dynamics 365 Commerce. Wśród tych opcji aparat kalkulacji cen Commerce najlepiej nadaje się do scenariuszy B2C.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>Korzystanie z aparatu kalkulacji cen Commerce w module Sprzedaż

> [!NOTE]
> Obecnie aparat kalkulacji cen Commerce może być używany tylko do tworzenia ofert w module Sprzedaż. Integracja zamówienia sprzedaży z aparatem kalkulacji cen Commerce nie jest jeszcze dostępna.

Gdy użytkownicy inicjują ofertę w module Sprzedaż, struktura podwójnego zapisywania kopiuje szczegóły oferty do modułu Commerce. Wszelkie zmiany w istniejących wierszach oferty lub wszystkie nowo dodane wiersze ofert w module Sprzedaż są kopiowane do modułu Commerce. Jeśli użytkownik chce użyć aparatu kalkulacji cen Commerce w celu uzyskania ceny oferty, może wybrać opcję **Oferta cenowa**, aby zaktualizować ceny oferty w oparciu o aparat kalkulacji cen w module Commerce. Następnie ceny są automatycznie aktualizowane zarówno w module Sprzedaż, jak i w Commerce.

## <a name="prerequisites"></a>Wymagania wstępne

- Zanim będzie można użyć aparatu kalkulacji cen Commerce w module Sprzedaż, należy wykonać kroki podane w sekcji [Prospekt do gotówki w podwójnym zapisie](./dual-write-prospect-to-cash.md).
- Należy wyłączyć ocenę umowy handlowej przy wprowadzaniu ręcznym, wykonując następujące kroki:

    1. W środowisku Commerce wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
    1. Na karcie **Ceny**, na skróconej karcie **Ocena umowy handlowej** wyczyść pole wyboru **Wprowadzanie ręczne**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Od prospekta do kasy w podwójnym zapisie](./dual-write-prospect-to-cash.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]