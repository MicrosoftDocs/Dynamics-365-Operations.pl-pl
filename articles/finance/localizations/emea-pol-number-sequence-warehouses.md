---
title: Konfigurowanie numeracji według magazynów
description: W tym temacie omówiono konfigurowanie numeracji dokumentów przyjęcia produktów dla zakupu i dokumentów dostawy dla sprzedaży z podziałem na magazyny dla Polski.
author: ShylaThompson
ms.date: 09/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: roschlom
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 31f8e561b03eb85e2fa213b2f404e5a5bfa0c3e4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832686"
---
# <a name="set-up-number-sequences-by-warehouse"></a>Konfigurowanie numeracji według magazynów

[!include[banner](../includes/banner.md)]

W tym temacie omówiono konfigurowanie numeracji dokumentów przyjęcia produktów dla zakupu i dokumentów dostawy dla sprzedaży z podziałem na magazyny dla Polski.

## <a name="set-up-a-number-sequence-for-purchase-product-receipts-by-warehouse"></a>Konfigurowanie sekwencji numerów dla dokumentów przyjęcia produktów zakupionych według magazynu

Istnieje możliwość skonfigurowania sekwencji numerów dla dokumentów przyjęcia produktów zakupionych według magazynu na stronie **Parametry modułu rozrachunków z dostawcami**. Dokumenty dostawy można ponumerować oddzielnie dla każdego magazynu. 

1. Kliknij kolejno opcje **Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z dostawcami**. 
2. Na stronie **Parametry modułu rozrachunków z dostawcami** w lewym okienku kliknij opcję **Numery kolejne**. 
3. W polu **Kod sekwencji numerów** wybierz numerację dla typu odwołania Wewnętrzny dokument przyjęcia produktów. 
4. Kliknij przycisk **Magazyny**. 
5. Na stronie **Zakup — numerowanie dokumentów dostawy** w polu **Magazyn** wybierz magazyn. 
6. W polu **Kod sekwencji numerów** wprowadź kod sekwencji numerów dokumentów przyjęcia produktów dla wybranego magazynu. 
7. Powtórz krok 6 dla każdego magazynu. 

> [!NOTE]
> Można również skonfigurować numerację dokumentów dostawy według magazynu dla zamówienia zakupu. W tym celu należy wybrać określony magazyn na stronie **Księgowanie dokumentu przyjęcia produktów**. Po zaksięgowaniu dokumentu przyjęcia produktów stan wiersza zamówienia zakupu nie zmieni się na **Dostarczone** lub **Otrzymano**, dopóki wszystkie wiersze zakupu dla wszystkich magazynów nie zostaną zaksięgowane dla tego zamówienia zakupu. 

## <a name="set-up-a-number-sequence-for-sales-packing-slips-by-warehouse"></a>Ustaw sekwencję identyfikatorów dokumentów dostawy sprzedaży według magazynu

Istnieje możliwość skonfigurowania sekwencji numerów dla dokumentów dostawy sprzedaży według magazynu na stronie **Parametry modułu rozrachunków z odbiorcami**. Dokumenty dostawy można ponumerować oddzielnie dla każdego magazynu. 

1. Kliknij kolejno opcje **Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z odbiorcami**. 
2. W lewym okienku kliknij opcję **Aktualizacje**. Zaznacz pole wyboru **Oddzielna numeracja dokumentów dostawy**. 
3. W lewym okienku kliknij opcję **Sekwencje identyfikatorów**. Wybierz sekwencję numerów arkuszy dla typu odwołania Dokument dostawy. 
4. Kliknij przycisk **Magazyny**. 
5. Na stronie **Sprzedaż — numerowanie dokumentów dostawy** w polu **Magazyn** wybierz magazyn. 
6. W polu **Kod sekwencji numerów** wprowadź kod numeracji dokumentów dostawy dla wybranego magazynu. 
7. Powtórz krok 6 dla każdego magazynu. 

> [!NOTE]
> Można również skonfigurować numerację dokumentów dostawy według magazynu dla zamówienia sprzedaży. W tym celu należy wybrać określony magazyn na stronie **Dokument dostawy**. Po zaksięgowaniu dokumentu dostawy stan zamówienia nie zmieni się na **Dostarczone** lub **Otrzymano** w zamówieniu sprzedaży, dopóki wszystkie wiersze sprzedaży dla wszystkich magazynów nie zostaną zaksięgowane dla tego zamówienia sprzedaży. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]