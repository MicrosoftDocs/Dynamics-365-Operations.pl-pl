--- 
title: "Przypisanie podatku i ręcznych zmian podatków"
description: "Ta procedura przedstawia sposób przypisywania grup podatków do kanałów sprzedaży detalicznej."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 816e00e4238cb0d90a2aea9b2bc070d31504c2ce
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="sales-tax-assignment-and-overrides"></a>Przypisanie podatku i ręcznych zmian podatków

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura przedstawia sposób przypisywania grup podatków do kanałów sprzedaży detalicznej. Ponadto prowadzi przez proces tworzenia nowej ręcznej zmiany podatku i przypisywania jej do istniejącej grupy ręcznej zmiany podatku. Ta procedura

wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Sklepy sieci sprzedaży > Wszystkie sklepy sieci sprzedaży.
2. Na liście kliknij łącze identyfikatora kanału sprzedaży detalicznej „Houston”.
3. Kliknij przycisk Edytuj.
    * Pole „Grupa podatków” zawiera listę grup podatków dla bieżącej firmy. Aktualnie przypisaną grupą jest standardowa grupa podatków „Texas”. Istnieją również grupy podatków „Washington” i „Washington, King County”. Grupy podatków mogą obejmować odnośne podatki dla wielu jednostek administracyjnych.  
    * W polu „Ręczna zmiana podatku” można mapować grupy ręcznych zmian podatków na kanał. Grupy ręcznych zmian podatków mogą służyć do grupowania ręcznych zmian podatków mających zastosowanie do wielu sklepów. Zamiast ręcznego przydzielania ręcznych zmian podatków jedna po drugiej można utworzyć grupę i przypisać ją bezpośrednio do kanałów, aby zaoszczędzić czas.  
4. Kliknij przycisk Zapisz.
5. Zamknij stronę.
6. Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia kanału > Podatki > Ręczne zmiany podatków.
7. Kliknij przycisk Nowy.
8. W polu Ręczna zmiana podatku nadaj nazwę nowej ręcznej zmianie.
9. W polu Opis wprowadź opis ręcznej zmiany.
10. Ustaw stan na „Włącz”.
11. Rozwiń lub zwiń sekcję Ręczna zmiana.
12. W polu Typ wybierz opcję.
    * Grupy podatków dla towarów mogą służyć do ręcznej zmiany podatków dla określonych towarów należących do tej grupy. Na przykład towary żywnościowe są zazwyczaj opodatkowane inaczej niż dobra trwałe i najczęściej mają własną grupy podatków.     Grupy podatków są grupami podatków stosowanymi w konkretnych kanałach sprzedaży. Na przykład jeśli w kanale jest prowadzona sprzedaż odbiorcom detalicznym i firmom, mogą być używane różne grupy podatków dla towarów. Wszystkie stosowne podatki zostaną zmapowane do grupy podatków.  
    * Teraz można wybrać podatki „Z” i „Do” albo ustawienia „Z grupy podatku” i „Do grupy podatku”, aby utworzyć ręczną zmianę podatku.    Pole „Z” wskazuje podatek lub grupę podatków, która ma zostać ręcznie zmieniona. Ręczna zmiana przy użyciu grupy podatków dla pozycji ma inne opcje niż ręczna zmiana przy użyciu grupy podatków.    Ręczne zmiany podatków można skonfigurować tak, aby zastępowały podatki w całych transakcjach lub tylko w konkretnych wierszach transakcji.  
13. Kliknij przycisk Zapisz.
14. Zamknij stronę.
15. Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia kanału > Podatki > Grupy ręcznej zmiany podatku.
    * W tym kroku przypiszesz nowo utworzoną ręczną zmianę podatku do grupy ręcznej zmiany podatku przypisanej do kanału Houston.  
16. Kliknij przycisk Edytuj.
17. Rozwiń lub zwiń sekcję Ustawienia.
18. Kliknij przycisk Dodaj.
19. W polu Ręczna zmiana podatku kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
20. Na liście zaznacz utworzoną wcześniej ręczną zmianę podatku.
21. Na liście kliknij łącze w wybranym wierszu.
22. Kliknij przycisk Zapisz.


