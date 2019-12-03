---
title: Edycja i przeprowadzanie inspekcji transakcji sklepu sieci sprzedaży
description: W tym temacie opisano funkcje edycji i przeprowadzania inspekcji transakcji sklepu sieci sprzedaży.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: f53573b8afb2003f6796930f5877185e533a4715
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693073"
---
# <a name="edit-and-audit-retail-store-transactions"></a>Edycja i przeprowadzanie inspekcji transakcji sklepu sieci sprzedaży

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

Klienci korzystający z rozwiązania Dynamics 365 Retail używają naszych i pochodzących od innych firm aplikacji w punkcie sprzedaży (POS). Dzięki naszej aplikacji POS transakcje sklepu sieci sprzedaży są pobierane do rozwiązania Retail Headquarters z kanałów za pomocą procesu wsadowego. W przypadku aplikacji POS innych firm transakcje sklepu sieci sprzedaży są pobierane do rozwiązania Retail Headquarters poprzez integrację. W obu przypadkach po pobraniu transakcji do rozwiązania Retail Headquarters musi być wykonany proces sprawdzania spójności, który przeprowadzi wiele weryfikacji transakcji, by tylko pomyślnie zweryfikowane transakcje zostały pobrane do zestawienia, które zostanie zaksięgowane w Retail Headquarters. 

Transakcje sprzedaży detalicznej nie przechodzą weryfikacji z różnych powodów. Na przykład usterka w kodzie integracyjnym lub usterka w aplikacji POS mogą spowodować niespójność danych bądź błąd użytkownika, np. usunięcie produktu po jego synchronizacji z kanałem lub zamknięciu okresu obrachunkowego bez zaksięgowania transakcji sprzedaży detalicznej za ten okres także mogą spowodować niespójność danych.

Te transakcje są oflagowane i wyłączone z zestawień, ale mogą one zakłócić codzienny proces księgowania sprzedaży detalicznej do działu finansowego klienta.

W rozwiązaniu Retail można edytować konkretne transakcje sprzedaży detalicznej, których weryfikacja się nie powiodła, jednocześnie przeprowadzając inspekcje wszystkich zmian. 

## <a name="edit-and-audit-transactions"></a>Edycja i przeprowadzanie inspekcji transakcji

W wersji 10.0.5 rozwiązania Retail można edytować tylko transakcje kasowe i przeniesienia, jak sprzedaż i zwroty. Edycja zamówień klienta lub zamówień online nie jest obsługiwana. W wersji 10.0.6 lub wyższej rozwiązania Retail edycja transakcji zarządzania gotówką także jest obsługiwana.

1. Instalacja aplikacji dodatkowych Dynamics Excel.

2. Przejdź do obszaru roboczego **Finanse sklepu sieciowego**. Kafelek **Weryfikacje transakcji zakończone niepowodzeniem** oferuje wstępnie filtrowany widok formularza transakcji Retail, który nie spełnił co najmniej jednej reguły weryfikacji.
 
3. Otwórz formularz. Kliknij zapis, którego weryfikacja się nie powiodła. Kliknij **Dodatek pakietu Office**, a następnie kliknij **Edytuj wybraną transakcję**. Otworzy się plik programu Excel ze szczegółami wybranej transakcji zawierający następujące arkusze:

    - Wiersze: ten arkusz zawiera nagłówek i wiersze produktów oraz dane dotyczące transakcji.
    - Płatności: ten arkusz zawiera wiersze szczegółów płatności dla transakcji.
    - Rabaty: ten arkusz zawiera szczegóły dotyczące rabatów dla transakcji.
    - Podatki: ten arkusz zawiera szczegóły dotyczące podatków dla transakcji.
    - Opłaty: ten arkusz zawiera dane dotyczące opłat dla transakcji.

4. W pliku programu Excel możesz zmodyfikować odpowiednie pola, a następnie przekazać dane z powrotem do Retail Headquarters, korzystając z funkcji publikowania aplikacji dodatkowej Dynamics Excel. Po opublikowaniu zmiany zostaną odzwierciedlone w systemie. W trakcie publikacji nie jest przeprowadzana weryfikacja zmian wprowadzonych przez użytkownika.

5. Pełen dziennik inspekcji zmian można wyświetlić, klikając **Wyświetl dziennik inspekcji** na nagłówku **Transakcja detaliczna** dla zmian na poziomie nagłówka i w odpowiednim obszarze i rekordzie na stosownej stronie transakcji. Na przykład wszystkie zmiany powiązane z wierszami sprzedaży będą widoczne na stronie **Transakcje sprzedaży**, zmiany związane z płatnościami będą widoczne na stronie **Transakcje płatności** itd. Szczegóły inspekcji, które są obsługiwane dla zmian:

   - Data i godzina modyfikacji
   - Pole 
   - Stara wartość
   - Nowa wartość
   - Zmodyfikowane przez

6. Po przeprowadzeniu i opublikowaniu zmian ponownie uruchom opcję **Sprawdź poprawność transakcji w sklepie**, by zweryfikować, że dokonane zmiany są spójne i prawidłowe.

> [!NOTE]
> Edycja jest dozwolona wyłącznie dla transakcji, których weryfikacja się nie powiodła. Jeśli chcesz edytować transakcje, których weryfikacja zakończyła się pomyślnie, zmień stan weryfikacji modyfikowanej transakcji na **Błąd** lub **Brak**. Teraz można ją edytować. 


## <a name="bulk-edit-transactions"></a>Edycja zbiorcza transakcji

W wersji 10.0.6 lub wyższej rozwiązania Retail opcja edycja zbiorczej transakcji sprzedaży detalicznej na poziomie zestawienia jest obsługiwana. 

1. Użyj aplikacji dodatkowej Excel do otwarcia zestawienia zawierającego transakcje, które chcesz modyfikować, wykonując opisane powyżej kroki 1–3.

2. Wybierz jedną z poniższych opcji.

    - **Edytuj transakcje kasowe i przeniesienia**. Ta opcja umożliwia edycję wszystkich transakcji kasowych i przeniesienia zawartych w zestawieniu. Dostępne są następujące arkusze programu Excel.
    
       - **Transakcja**: ten arkusz zawiera wszystkie informacje na poziomie nagłówka dla transakcji sprzedaży.
       - **Transakcja sprzedaży**: ten arkusz zawiera wszystkie informacje na poziomie wiersza dla transakcji sprzedaży.
       - **Transakcje płatności**: ten arkusz zawiera wszystkie informacje wierszy płatności dla transakcji sprzedaży.
       - **Transakcje rabatu**: ten arkusz zawiera wszystkie informacje wierszy rabatów dla transakcji sprzedaży.
       - **Transakcje sprzedaży**: ten arkusz zawiera wszystkie informacje wierszy podatków dla transakcji sprzedaży.
       - **Transakcje opłat**: ten arkusz zawiera wszystkie informacje wierszy opłat dla transakcji sprzedaży.

    - **Edytuj transakcje zarządzania gotówką**. Ta opcja umożliwia edycję wszystkich transakcji zarządzania gotówką zawartych w zestawieniu. Dostępne są następujące arkusze programu Excel.
     
       - **Transakcja**: ten arkusz zawiera wszystkie informacje na poziomie nagłówka dla transakcji zarządzania gotówką.
       - **Transakcje wpłat bankowych**: ten arkusz zawiera wszystkie szczegóły transakcji przekazania pieniędzy do banku.
       - **Transakcje wpływające na kwotę w kasecie kasowej**: ten arkusz zawiera wszystkie szczegóły transakcji wpływających na kwotę w kasecie kasowej.
       - **Deklaracja środków płatniczych**: ten arkusz zawiera wszystkie szczegóły transakcji deklaracji środków płatniczych.
       - **Transakcje przychodów/wydatków**: ten arkusz zawiera wszystkie szczegóły wiersza transakcji przychodów/wydatków.
       - **Transakcje płatności**: ten arkusz zawiera wszystkie informacje dotyczące płatności dla operacji **Zapłać fakturę**, a także transakcję przychodów/wydatków.

3.  Weryfikacje nie są przeprowadzane, jeśli publikowane są transakcje edytowane zbiorczo. Należy upewnić się, że wszystkie zmiany są dokładne i że zachowana jest wierność danych we wszystkich arkuszach. Na przykład jeśli chcesz zmienić datę transakcji, by zarządzać scenariuszami, gdzie okres obrachunkowy lub magazynowy dla otwartych transakcji sprzedaży detalicznej jest zamknięty, musisz zmienić datę we wszystkich arkuszach programu Excel, które zawierają kolumnę **Data biznesowa**. Aby zweryfikować transakcje po ich edycji, możesz użyć opcji **Ponownie sprawdź poprawność transakcji** na stronie **Zestawienia sieci sprzedaży**.
