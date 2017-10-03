--- 
title: Przetwarzanie odsetek
description: "W tej procedurze pokazano sposób tworzenia, drukowania i księgowania not odsetkowych."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8a53c4deb146d336fdd8ca88a081e6a5af71465a
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="process-interest"></a>Przetwarzanie odsetek

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia, drukowania i księgowania not odsetkowych. W zadaniu wykorzystano firmę demonstracyjną USMF.


## <a name="set-up-interest-on-the-posting-profile"></a>Konfigurowanie odsetek w profilu księgowania
1. Wybierz kolejno opcje Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców.
2. Kliknij przycisk Edytuj.
    * Z listy rozwijanej wybierz kod odsetek. Jeśli nie chcesz naliczać odsetek dla transakcji przy użyciu tego profilu księgowania, pozostaw to pole puste.  
    * Karta Restrykcje tabeli pozwala na zmianę sposobu przetwarzania odsetek. Jeśli to pole ma ustawioną wartość Tak, odsetki będą obliczane dla tego profilu księgowania.  

## <a name="calculate-interest"></a>Nalicz odsetki
1. Wybierz kolejno opcje Kredyty i windykacja > Odsetki > Utwórz noty odsetkowe.
    * Należy wybrać typy transakcji, dla których będą obliczane odsetki. Wszystkie otwarte transakcje dla tych typów zostaną uwzględnione w obliczeniach.  
    * Jeśli wybrano opcję Odsetki, będziesz naliczać odsetki od odsetek. Przed uwzględnieniem tych transakcji warto sprawdzić przepisy dotyczące obliczania odsetek od odsetek.  
    * Odsetki będą obliczane od tego dnia do daty „Do dnia”. Jeśli nie określisz wartości „Od dnia”, wszystkie niezaksięgowane noty odsetkowe zostaną anulowane, a odsetki zostaną obliczone ponownie od daty transakcji.  
2. Wprowadź datę noty odsetkowej.
    * Istnieją trzy opcje profili księgowania:   Konto — Dla każdej noty odsetkowej używanie profilu księgowania, który został przypisany do konta odbiorcy.   Wybierz — Zostanie użyty profil księgowania wybrany w polu Profil księgowania.   Transakcja — Użycie dla każdej noty odsetkowej indywidualnego profilu księgowania z transakcji, w której obliczano odsetki. Transakcje, które nie mają przypisanego profilu księgowania, będą używać profilu księgowania określonego w formularzu Parametry modułu rozrachunków z odbiorcami w obszarze Księga i podatek.  
    * Jeśli w polu „Użyj profilu księgowania z” zmieniono wartość na „Wybierz”, w tym miejscu wybierz profil księgowania.  
3. Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.
4. Kliknij przycisk Filtr.
5. W polu Kryteria wpisz identyfikator odbiorcy. Na przykład wpisz „US-001”.
6. Kliknij przycisk OK.
7. Kliknij przycisk OK.

## <a name="print-interest-notes"></a>Drukuj noty odsetkowe
1. Wybierz kolejno opcje Kredyty i windykacja > Odsetki > Przejrzyj i przetwórz noty odsetkowe.
2. W polu Stan wybierz opcję „Utworzono”.
3. W polu Wydrukowane wybierz opcję „Nie wydrukowano”.
4. Kliknij przycisk Drukuj.
5. Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.
6. Kliknij przycisk OK.
7. Zamknij stronę.

## <a name="post-the-interest-note"></a>Księgowanie noty odsetkowej
1. Wybierz notę odsetkową, która jest gotowa do zaksięgowania (ma stan Utworzono).
2. Kliknij przycisk Księguj.
3. Wprowadź datę księgowania noty odsetkowej.
    * Zaznacz opcję Tak, aby tworzyć transakcje księgi głównej dla każdej noty odsetkowej.     Jeśli nie zaznaczysz opcji Tak, odsetki ze wszystkich not odsetkowych dotyczących danego klienta zostaną skumulowane i zaksięgowane w księdze głównej jako jedna transakcja.  
4. Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.
5. Kliknij przycisk OK.
6. W polu Stan wybierz opcję „Zaksięgowano”.


