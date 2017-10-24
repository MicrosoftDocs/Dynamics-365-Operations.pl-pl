--- 
title: "Konfigurowanie elementu menu urządzenia przenośnego do wykonania pracy w ramach zamówienia zakupu"
description: "W tej procedurze pokazano sposób konfigurowania elementu menu urządzenia przenośnego."
author: BibiSp
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b80c258d6a779a8fc5bb6c846abd3af7e69d5e06
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-in-a-purchase-order"></a>Konfigurowanie elementu menu urządzenia przenośnego do wykonania pracy w ramach zamówienia zakupu

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób konfigurowania elementu menu urządzenia przenośnego. W tym przykładzie element menu służy do wykonywania pracy typu Zamówienie zakupu. Klasa pracy powiązana z elementem menu decyduje o tym, która praca jest prawidłowa. Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF. Ta procedura jest zwykle wykonywana przez kierownika magazynu.


## <a name="create-a-mobile-device-menu-item"></a>Tworzenie elementu menu urządzenia przenośnego
1. Przejdź do okna Elementy menu urządzenia przenośnego.
2. Kliknij przycisk Nowy.
3. W polu Nazwa elementu menu wpisz wartość.
    * Wprowadź unikatową wartość. Na przykład można wpisać „PrzeniesienieZZ”. Zapamiętaj tę wartość, będzie potrzebna później.  
4. W polu Tytuł wpisz wartość.
    * Jest to tytuł, który będzie wyświetlany w urządzeniu przenośnym. Na przykład można wpisać Przeniesienie ZZ.  
5. W polu Tryb wybierz opcję „Praca”.
6. W polu Użyj istniejącej pracy zaznacz opcję Tak.
    * Ten element menu urządzenia przenośnego jest używany do wykonywania istniejącej pracy. W związku z tym należy ustawić wartość Tak.  
    * Pole Wyświetl stan zapasów określa, czy stan dostępnych zapasów będzie wyświetlany pracownikowi magazynu na urządzeniu przenośnym.  
7. W polu Sterowane przez wybierz opcję „Grupowanie systemowe”.
    * Po wybraniu wartości w polu Sterowane przez zostaną wyświetlone dodatkowe pola w sekcji Ogólne na tej stronie. Wyświetlane pola zależą od wybranej wartości. Po wybraniu opcji Grupowanie systemowe są dodawane dwa nowe pola. Omówiono je poniżej.  
8. W polu Grupowanie systemowe zaznacz wartość „WorkPoolId”.
    * Gdy pracownik magazynu otwiera ten element menu, zobaczy monit o zeskanowanie identyfikatora puli pracy. Wszystkie zlecenia o tym identyfikatorze puli pracy oraz otwarte wiersze zlecenia, które mają jedną z klas pracy dodanych do tego elementu menu, zostaną wysłane do użytkownika.  
9. W polu Etykieta grup systemowych wpisz wartość.
    * Jest to tekst wyświetlany użytkownikowi na urządzeniu przenośnym. Na przykład można wpisać Pula pracy.  
10. W polu Zastąp numer identyfikacyjny podczas odłożenia zaznacz opcję Tak.
    * Ta opcja umożliwia pracownikom magazynu zastępowanie docelowego numeru identyfikacyjnego, gdy towary są odkładane do lokalizacji kontrolowanej przez numer identyfikacyjny.  
11. W polu Grupuj odłożone wybierz opcję Tak.
    * Jeśli wszystkie wiersze odłożenia w zleceniu mają tę samą lokalizację, użytkownik otrzyma jedną zbiorczą instrukcję odłożenia dla wszystkich wierszy.  
    * Identyfikator szablonu inspekcji: Szablon inspekcji pracy pozwala określić, że proces pracy dla elementu menu ma zostać przerwany, aby można było wykonać inną operację. Na przykład jeśli element menu dotyczy pracy przychodzącej, szablon inspekcji może wymagać, by pracownik sprawdził temperaturę. Punkt, w którym proces zostanie przerwany, jest określony w szablonie inspekcji i może być np. momentem rozpoczęcia lub ukończenia pracy albo zmiany stanu.  
12. Rozwiń sekcję Klasy robocze.
13. Kliknij przycisk Nowy.
14. W polu Identyfikator klasy roboczej wpisz „Zakup”.
    * Pula pracy ogranicza pracę, dla której można używać elementu menu. W tym przypadku będzie ona używana dla otwartych wierszy zlecenia, które mają identyfikator klasy pracy Zakup.  
15. Kliknij przycisk Zapisz.

## <a name="set-up-work-confirmation"></a>Konfigurowanie potwierdzenia pracy
1. Kliknij opcję Konfiguracja potwierdzenia pracy.
2. W polu Typ pracy zaznacz opcję „Pobranie”.
3. Zaznacz pole wyboru Automatyczne potwierdzenie.
    * Instrukcja pracy o typie pracy Pobranie zostanie potwierdzona automatycznie. Ta instrukcja nie będzie przedstawiana użytkownikowi.  
4. Kliknij przycisk Nowy.
5. W polu Typ pracy zaznacz opcję „Odłożenie”.
6. Zaznacz pole wyboru Potwierdzenie lokalizacji.
    * Pracownik magazynu zostanie poproszony o wykonanie skanowania potwierdzającego w lokalizacji po odłożeniu towaru.  
7. Kliknij przycisk Zapisz.
8. Zamknij stronę.
9. Zamknij stronę.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Dodawanie element menu do menu urządzenia przenośnego
1. Przejdź do okna Menu urządzeń przenośnych.
2. Kliknij przycisk Edytuj.
3. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Nazwa z wartością „przychodzące”.
    * Chcesz znaleźć menu używane dla towarów przychodzących. W firmie USMF nosi ono nazwę Przychodzące.  
4. W drzewie zaznacz wartość.
5. Kliknij strzałkę wskazującą w prawo.
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.


