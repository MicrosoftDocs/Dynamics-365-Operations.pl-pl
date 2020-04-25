---
title: Aktualizacje fizyczne i finansowe
description: W tym temacie przedstawiono typy transakcji, które przekładają się na zwiększanie lub zmniejszanie ilości zapasów.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ea79bd9c6561c4e4f6fad2c177f44fe62bdea5b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214649"
---
# <a name="physical-and-financial-updates"></a>Aktualizacje fizyczne i finansowe

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono typy transakcji, które przekładają się na zwiększanie lub zmniejszanie ilości zapasów. 

W Dynamics 365 Supply Chain Management transakcje magazynowe można zaktualizowane fizycznie i finansowo. Niektóre typy transakcji fizycznych i finansowych zwiększają ilości zapasów, podczas gdy inne je zmniejszają.

## <a name="physical-increases"></a>Wzrost fizyczny
Po zaksięgowaniu transakcji fizycznej stan tej transakcji przyjmuje wartość **Otrzymano**. Oto transakcje, które stanowią wzrost fizyczny:

-   zamówienie zakupu — przychód,
-   zwrot dokumentu dostawy zamówienia sprzedaży,
-   Zgłaszanie zlecenia produkcyjnego jako zakończonego
-   według produktów na liście pobrania zlecenia produkcyjnego.

## <a name="financial-increases"></a>Wzrost finansowy
Po zaksięgowaniu finansowej transakcji przychodu stan rekordu tej transakcji powodującej zwiększenie ilości przyjmuje wartość **Zakupiono**. Oto transakcje, które stanowią wzrost finansowy:

-   Faktura dostawcy
-   faktura zamówienia zakupu do zwrotu,
-   wycena zlecenia produkcyjnego,
-   Arkusze magazynowe z ilością dodatnią, takie jak przeniesienie, zyski i straty, zliczanie, BOM i przeniesienie.

## <a name="transactions-that-increase-quantity"></a>Transakcje, które zwiększają ilość
Transakcje zwiększające ilość są księgowane według dynamicznych średnich kosztów własnych. Po zaksięgowaniu transakcji zwiększających ilość obliczone dynamiczne średnie koszty własne na podstawie tych wszystkich transakcji dla każdego wymiaru magazynowego podlegającego śledzeniu finansowemu. Aby uzyskać informacje o uruchamianiu średnich kosztów własnych, zobacz [Dynamiczne średnie koszty własne](running-average-cost-price.md).

## <a name="transactions-that-decrease-quantity"></a>Transakcje, które zmniejszają ilość
Obliczone dynamiczne średne koszty są używane podczas księgowania transakcji, która zmniejsza ilość, niezależnie od tego, który model magazynu jest powiązany z danym magazynem. Wymaga to, aby transakcja, która zmniejsza ilość nie została wcześniej oznaczona dla innej transakcji przed zaksięgowaniem. Jeśli fizyczny stan dostępnych zapasów uzyskuje wartość ujemną, jest używany koszt magazynowy zdefiniowany dla towaru na stronie **Pozycja**. 

> [!NOTE]
> Jeśli włączono funkcję wielooddziałowości, to koszt ten będzie zastępczo używany jako koszt magazynowy, zdefiniowany dla oddziału na stronie **Ustawienia domyślne zamówień**.

## <a name="physical-issues-vs-financial-issues"></a>Rozchody fizyczne a finansowe
Po zaksięgowaniu transakcji fizycznego rozchodu stan rekordu transakcji przyjmuje wartość **Zmniejszono**. Oto transakcje stanowiące fizyczne rozchody:

-   arkusz listy pobrań zlecenia produkcyjnego,
-   dokument dostawy zamówienia sprzedaży,
-   zwrot dokumentu dostawy zamówienia zakupu.

Po zaksięgowaniu transakcji finansowej stan rekordu tej transakcji przyjmuje wartość **Sprzedano**. Oto transakcje stanowiące finansowe rozchody:

-   Kończenie zlecenia produkcyjnego
-   Faktura dla zamówienia sprzedaży
-   Zwrot z faktury od dostawcy
-   Arkusze magazynowe z ilością ujemną, takie jak przeniesienie, zyski i straty, zliczanie, BOM i przeniesienie.

Transakcje zmniejszające ilość są księgowane według dynamicznych średnich kosztów własnych. Z tego powodu proces zamknięcia magazynu jest wymagany w celu rozliczenia transakcji rozchodu z transakcjami przychodu, według modelu magazynu przypisanego dla danego towaru.
