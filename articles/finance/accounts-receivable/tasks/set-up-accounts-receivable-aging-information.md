---
title: Konfigurowanie i generowanie informacji o wiekowaniu rozrachunków z odbiorcami
description: Ten podręcznik pomoże skonfigurować definicję okresu wiekowania, wiekować salda odbiorców oraz wyświetlać salda na liście Wiekowane saldo i stronie Windykacja.
author: mikefalkner
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 439be64a864056cc19fd156f664a4b90601be040
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446818"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>Konfigurowanie i generowanie informacji o wiekowaniu rozrachunków z odbiorcami

[!include [banner](../../includes/banner.md)]

Ten podręcznik pomoże skonfigurować definicję okresu wiekowania, wiekować salda odbiorców oraz wyświetlać salda na liście Wiekowane saldo i stronie Windykacja. To nagranie wykorzystuje firmę demonstracyjną USMF.


## <a name="create-an-aging-period-definition"></a>Tworzenie definicji okresu wiekowania
1. Otwórz **Okienko nawigacji > Moduły > Kredyty i windykacja > Ustawienia > Definicje okresów wiekowania**.
2. Kliknij przycisk **Nowy**.
3. W polu **Definicja okresu wiekowania** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. Kliknij przycisk **Dodaj poniżej**, aby wstawić nowy okres wiekowania.
6. W polu **Okres** wprowadź opis, który ma być wyświetlany w raportach o wiekowaniu.
7. W polu **Jednostka** wpisz liczbę.
8. W polu **Interwał** wybierz opcję. Okres finansowy odpowiada okresowi w kalendarzu księgi. Dzień, tydzień, miesiąc, kwartał i lata określają wielkość zakresu według typu daty. Opcja Nieograniczony powoduje zaznaczenie wszystkich transakcji przed lub po poprzednim okresie, w zależności od tego, czy jest to pierwszy czy ostatni okres.  
9. W polu **Wskaźnik wiekowania** wybierz opcję.
10. Zaznacz okres w górnej części siatki. Zaktualizuj opis, aby dotyczył najstarszego okresu w definicji okresu wiekowania.
11. W polu **Okres** wprowadź nowy opis okresu wiekowania.
12. Zamknij stronę.

## <a name="age-the-balances"></a>Wiekowanie sald
1. Wybierz kolejno opcje **Kredyty i windykacja > Zadania okresowe > Wiekuj salda odbiorcy**.
2. W polu **Definicja okresu wiekowania** zaznacz utworzoną przez siebie definicję okresu wiekowania.
    + Może istnieć jedna aktywna migawka dla każdej definicji okresu wiekowania.  
    + Domyślnie są przetwarzani wszyscy odbiorcy. Można użyć tej opcji, aby obliczyć jedną pulę windykacji dla wszystkich odbiorców.  
    + Wybierz datę z transakcji, która będzie używana do wiekowania.  
    + Wybierz dla wiekowania datę „na dzień”. Wartością domyślną jest Dzisiaj, ale jeśli wartość pola zostanie zmieniona na Wybrana data, będzie można wybrać żądaną datę. Dla przetwarzania wsadowego użyj opcji Data dzisiejsza.  
3. Rozwiń węzeł **Zakres** firm. Można wybrać firmy, które zostaną uwzględnione w migawce. Bieżąca firma jest zaznaczona domyślnie.
4. Kliknij przycisk **OK**, aby wykonać przetwarzanie migawki. Trochę to potrwa, dlatego poczekaj, aż suwak zniknie, i poszukaj komunikatu w centrum komunikatów.

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>Wyświetlanie sald na liście Wiekowane salda i na stronie Windykacja
1. Wybierz kolejno opcje **Kredyty i windykacja > Windykacja > Wiekowane salda**. Strona listy pokazuje salda odbiorcy. Ikona wiekowania pokazuje okres wiekowania dla najstarszej transakcji.  
2. Wybierz odbiorcę z saldem.
3. Rozwiń pole informacji **Wiekowanie** i obejrzyj wiekowane salda. Definicja okresu wiekowania dla pola informacji jest pobierana z domyślnej definicji okresu wiekowania określonej w parametrach. Można ją zmienić za pomocą menu Zbierz.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]