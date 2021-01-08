---
title: Konfigurowanie elementu menu urządzenia przenośnego do wykonania pracy typu Zamówienie zakupu
description: W tym temacie pokazano sposób konfigurowania elementu menu urządzenia przenośnego.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFAutoConfirm, WHSRFMenu
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 86ccc39cb243354db337a5747701e9731c5ad775
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435435"
---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-of-type-purchase-order"></a>Konfigurowanie elementu menu urządzenia przenośnego do wykonania pracy typu Zamówienie zakupu

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób konfigurowania elementu menu urządzenia przenośnego. W tym przykładzie element menu służy do wykonywania pracy typu Zamówienie zakupu. Klasa pracy powiązana z elementem menu decyduje o tym, która praca jest prawidłowa. Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF. Ta procedura jest zwykle wykonywana przez kierownika magazynu.


## <a name="create-a-mobile-device-menu-item"></a>Tworzenie elementu menu urządzenia przenośnego
1. Przejdź do **Elementy menu urządzenia przenośnego** wprowadzając je na pasku wyszukiwania.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa elementu menu** wpisz wartość. Wprowadź unikatową wartość. Na przykład można wpisać `POMove`. Zapamiętaj tę wartość, będzie potrzebna później.  
4. W polu **Tytuł** wpisz wartość. Jest to tytuł, który będzie wyświetlany w urządzeniu przenośnym. Na przykład można wpisać `PO Move`.  
5. W polu **Tryb** wybierz opcję **Praca**.
6. W polu **Użyj istniejącej pracy** zaznacz opcję **Tak**.
    - Ten element menu urządzenia przenośnego jest używany do wykonywania istniejącej pracy. W związku z tym należy ustawić wartość **Tak**.  
    - Pole **Wyświetl stan zapasów** określa, czy stan dostępnych zapasów będzie wyświetlany pracownikowi magazynu na urządzeniu przenośnym.  
7. W polu **Sterowane przez** wybierz opcję **Grupowanie systemowe**. Po wybraniu wartości w polu **Sterowane przez** zostaną wyświetlone dodatkowe pola w sekcji **Ogólne** na tej stronie. Wyświetlane pola zależą od wybranej wartości. Po wybraniu opcji **Grupowanie systemowe** są dodawane dwa nowe pola. Omówiono je poniżej.  
8. W polu **Grupowanie systemowe** zaznacz **WorkPoolId**. Gdy pracownik magazynu otwiera ten element menu, zobaczy monit o zeskanowanie Identyfikatora puli pracy. Wszystkie zlecenia o tym identyfikatorze puli pracy oraz otwarte wiersze zlecenia, które mają jedną z klas pracy dodanych do tego elementu menu, zostaną wysłane do użytkownika.  
9. W polu **Etykieta grup systemowych** wpisz wartość. Jest to tekst wyświetlany użytkownikowi na urządzeniu przenośnym. Na przykład można wpisać **Pula pracy**.  
10. W polu **Zastąp numer identyfikacyjny podczas odłożenia** zaznacz opcję **Tak**. Ta opcja umożliwia pracownikom magazynu zastępowanie docelowego numeru identyfikacyjnego, gdy towary są odkładane do lokalizacji kontrolowanej przez numer identyfikacyjny.  
11. W polu **Grupuj odłożone** wybierz opcję **Tak**.
    - Jeśli wszystkie wiersze odłożenia w zleceniu mają tę samą lokalizację, użytkownik otrzyma jedną zbiorczą instrukcję odłożenia dla wszystkich wierszy. 
    - Identyfikator szablonu inspekcji: Szablon inspekcji pracy pozwala określić, że proces pracy dla elementu menu ma zostać przerwany, aby można było wykonać inną operację. Na przykład jeśli element menu dotyczy pracy przychodzącej, szablon inspekcji może wymagać, by pracownik sprawdził temperaturę. Punkt, w którym proces zostanie przerwany, jest określony w szablonie inspekcji i może być np. momentem rozpoczęcia lub ukończenia pracy albo zmiany stanu.  
12. Rozwiń sekcję **Klasy robocze**.
13. Wybierz pozycję **Nowy**.
14. W polu **Identyfikator klasy roboczej** wpisz `Purchase`. Pula pracy ogranicza pracę, dla której można używać elementu menu. W tym przypadku będzie ona używana dla otwartych wierszy zlecenia, które mają identyfikator klasy pracy Zakup.  
15. Wybierz opcję **Zapisz**.

## <a name="set-up-work-confirmation"></a>Konfigurowanie potwierdzenia pracy
1. Wybierz **Konfiguracja potwierdzenia pracy**.
2. W polu **Typ pracy** zaznacz opcję **Pobierz**.
3. Zaznacz pole wyboru **Automatyczne potwierdzenie**. Instrukcja pracy o typie pracy Pobranie zostanie potwierdzona automatycznie. Ta instrukcja nie będzie przedstawiana użytkownikowi.  
4. Wybierz pozycję **Nowy**.
5. W polu **Typ pracy** zaznacz opcję „Odłożenie”.
6. Zaznacz pole wyboru **Potwierdzenie lokalizacji**. Pracownik magazynu zostanie poproszony o wykonanie skanowania potwierdzającego w lokalizacji po odłożeniu towaru.  
7. Wybierz opcję **Zapisz**.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Dodawanie element menu do menu urządzenia przenośnego
1. Przejdź do menu **Elementy menu urządzenia przenośnego** wprowadzając je na pasku wyszukiwania.
2. Wybierz opcję **Edycja**.
3. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola **Nazwa** z wartością **przychodzące**. Chcesz znaleźć menu używane dla towarów przychodzących. W firmie USMF nosi ono nazwę **Przychodzące**.  
4. W drzewie zaznacz **wartość**.
5. Wybierz strzałkę wskazującą w prawo.
6. Wybierz opcję **Zapisz**.
7. Zamknij stronę.
