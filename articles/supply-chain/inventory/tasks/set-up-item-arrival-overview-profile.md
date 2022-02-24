---
title: Konfigurowanie profilu przeglądu przyjęć pozycji
description: Ten temat koncentruje się na konfiguracji profilu przeglądu przyjęć.
author: ShylaThompson
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ecfe132d9b0e096c5fdf015f80a6efb34c9b178
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961443"
---
# <a name="set-up-an-item-arrival-overview-profile"></a>Konfigurowanie profilu przeglądu przyjęć pozycji

[!include [banner](../../includes/banner.md)]]

Ten temat koncentruje się na konfiguracji profilu przeglądu przyjęć. Profil przeglądu przyjęć to zbiór reguł, które zostaną zastosowane po otwarciu strony Przegląd przyjęć przez użytkownika. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF. Tę procedurę zazwyczaj wykonuje pracownik przyjmujący.

1. Otwórz w okienku nawigacji **Moduły > Zarządzanie zapasami > Ustawienia > Dystrybucja > Profile przeglądu przyjęć**.
2. Wybierz pozycję **Nowy**. Ponieważ prawie zawsze pracujesz w tym samym magazynie, rozładowując ciężarówki, należy utworzyć profil przeglądu przyjęć, aby uprościć proces rejestrowania przyjętych towarów.  
3. W polu **Nazwa profilu przeglądu przyjęć** wpisz wartość.
4. W polu **Pokaż wiersze** wybierz opcję. Umożliwia wybór wierszy wyświetlanych dla przyjęć:  

    - **Wszystko** — Wyświetlanie wszystkich wierszy, niezależnie od ich stanu.   
    - **W toku** — Wyświetlane są wiersze przyjęć, w których postęp ma stan Zakończony lub Częściowo. To oznacza, że dla wszystkich wierszy całość lub część ilości została zarejestrowana w arkuszu przyjęć.   
    - **Nieukończone** — Wyświetlane są wiersze przyjęć, w których postęp ma stan Brak lub Częściowo. To oznacza, że dla wszystkich wierszy zarejestrowana w arkuszu przyjęć została część ilości lub nic nie zostało zarejestrowane.  

5. Rozwiń lub zwiń sekcję **Opcje przyjęcia**.
6. W polu **Dni do przodu** wpisz wartość. Ustawia to filtr, który pokazuje wiersze przyjęć oczekiwanych do realizacji w ciągu najbliższych kilku dni (w zależności od ustawionej liczby).  
7. W polu **Dni wstecz** wpisz wartość. Spowoduje to ustawienie filtru wyświetlającego wiersze przyjęć oczekiwanych do realizacji tę liczbę dni przed datą dzisiejszą.  
8. W polu **Magazyny** wpisz wartość. Wyfiltruj jeden lub więcej magazynów.  
9. W polu **Metoda dostawy** wybierz wartość. Spowoduje to ustawienie filtru wyświetlającego tylko wiersze przyjęć z tą metodą dostawy.  
10. W polu **Nazwa** wybierz wartość WHS.
11. W polu **Magazyn** wybierz magazyn 24. Jest to magazyn domyślny, który będzie używany dla zarejestrowanych wierszy przyjęć używających tego profilu.  
12. W polu **Lokalizacja** wybierz wartość **Baydoor**. Jest to lokalizacja domyślna, która będzie używana dla zarejestrowanych wierszy przyjęć używających tego profilu.  
13. Rozwiń lub zwiń sekcję **Szczegóły zapytania dotyczącego przyjęcia**.
14. W polu **Ogranicz do oddziału** wybierz oddział 2. Spowoduje to ustawienie filtru wyświetlającego tylko wiersze przyjęć z tym oddziałem.  
15. W opcji **Zamówienia zakupu** ustaw wartość **Tak**. Wybierz wiersze przyjęć z zamówień zakupu.  
16. W opcji Zamówienia **przeniesienia** ustaw wartość **Tak**. Wybierz wiersze przyjęć z zamówień przeniesienia.  
17. Wybierz opcję **Zapisz**.
18. Zamknij stronę.

