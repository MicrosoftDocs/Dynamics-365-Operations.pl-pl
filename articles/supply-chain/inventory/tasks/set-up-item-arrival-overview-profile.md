---
title: Konfigurowanie profilu przeglądu przyjęć pozycji
description: To zadanie koncentruje się na konfiguracji profilu przeglądu przyjęć.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20472f76a03a2a7bb1a7a87e2687135bce35dfa1
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845474"
---
# <a name="set-up-an-item-arrival-overview-profile"></a>Konfigurowanie profilu przeglądu przyjęć pozycji

[!include [task guide banner](../../includes/task-guide-banner.md)]

To zadanie koncentruje się na konfiguracji profilu przeglądu przyjęć. Profil przeglądu przyjęć to zbiór reguł, które zostaną zastosowane po otwarciu strony Przegląd przyjęć przez użytkownika. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF. Tę procedurę zazwyczaj wykonuje pracownik przyjmujący.





1. Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Dystrybucja > Profile przeglądu przyjęć.
2. Kliknij przycisk Nowy.
    * Ponieważ prawie zawsze pracujesz w tym samym magazynie, rozładowując ciężarówki, należy utworzyć profil przeglądu przyjęć, aby uprościć proces rejestrowania przyjętych towarów.  
3. W polu Nazwa profilu przeglądu przyjęć wpisz wartość.
4. W polu Pokaż wiersze wybierz opcję.
    * Wybierz, które wiersze mają być wyświetlane dla przyjęć:   Wszystko — Wyświetlanie wszystkich wierszy, niezależnie od ich stanu.   W toku — Wyświetlane są wiersze przyjęć, w których postęp ma stan Zakończony lub Częściowo. To oznacza, że dla wszystkich wierszy całość lub część ilości została zarejestrowana w arkuszu przyjęć.   Nieukończone — Wyświetlane są wiersze przyjęć, w których postęp ma stan Brak lub Częściowo. To oznacza, że dla wszystkich wierszy zarejestrowana w arkuszu przyjęć została część ilości lub nic nie zostało zarejestrowane.  
5. Rozwiń lub zwiń sekcję Opcje przyjęcia.
6. W polu Dni do przodu wpisz wartość.
    * Ustawia to filtr, który pokazuje wiersze przyjęć oczekiwanych do realizacji w ciągu najbliższych kilku dni (w zależności od ustawionej liczby).  
7. W polu Dni wstecz wpisz wartość.
    * Spowoduje to ustawienie filtru wyświetlającego wiersze przyjęć oczekiwanych do realizacji tę liczbę dni przed datą dzisiejszą.  
8. W polu Magazyny wpisz wartość.
    * Wyfiltruj jeden lub więcej magazynów.  
9. W polu Metoda dostawy wybierz wartość.
    * Spowoduje to ustawienie filtru wyświetlającego tylko wiersze przyjęć z tą metodą dostawy.  
10. W polu Nazwa wybierz wartość WHS.
11. W polu Magazyn wybierz magazyn 24.
    * Jest to magazyn domyślny, który będzie używany dla zarejestrowanych wierszy przyjęć używających tego profilu.  
12. W polu Lokalizacja wybierz wartość Baydoor.
    * Jest to lokalizacja domyślna, która będzie używana dla zarejestrowanych wierszy przyjęć używających tego profilu.  
13. Rozwiń lub zwiń sekcję Szczegóły zapytania dotyczącego przyjęcia.
14. W polu Ogranicz do oddziału wybierz oddział 2.
    * Spowoduje to ustawienie filtru wyświetlającego tylko wiersze przyjęć z tym oddziałem.  
15. W opcji Zamówienia zakupu ustaw wartość Tak.
    * Wybierz wiersze przyjęć z zamówień zakupu.  
16. W opcji Zamówienia przeniesienia ustaw wartość Tak.
    * Wybierz wiersze przyjęć z zamówień przeniesienia.  
17. Kliknij przycisk Zapisz.
18. Zamknij stronę.

