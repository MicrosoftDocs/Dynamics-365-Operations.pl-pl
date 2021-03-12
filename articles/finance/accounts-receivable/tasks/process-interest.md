---
title: Przetwarzanie odsetek
description: W tej procedurze pokazano sposób tworzenia, drukowania i księgowania not odsetkowych.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad30984f55017ee275af15ddb4f1a46c6a50db69
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992946"
---
# <a name="process-interest"></a>Przetwarzanie odsetek

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób tworzenia, drukowania i księgowania not odsetkowych. W zadaniu wykorzystano firmę demonstracyjną USMF.


## <a name="set-up-interest-on-the-posting-profile"></a>Konfigurowanie odsetek w profilu księgowania
1. W **Okienku nawigacji** przejdź do **Moduły > Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców**.
2. Kliknij przycisk **Edytuj**.
3. W **skróconej karcie Ustawień** w polu **Kod odsetek** wybierz kod odsetek z listy rozwijanej. Jeśli nie chcesz naliczać odsetek dla transakcji przy użyciu tego profilu księgowania, pozostaw to pole puste. Karta skrócona **Restrykcje tabeli** pozwala na zmianę sposobu przetwarzania odsetek. Jeśli to pole ma ustawioną wartość Tak, odsetki będą obliczane dla tego profilu księgowania.  

## <a name="calculate-interest"></a>Nalicz odsetki
1. W **Okienku nawigacji** przejdź do **Moduły > Kredyty i windykacja > Odsetki > Utwórz noty odsetkowe**.
2. Należy wybrać typy transakcji, dla których będą obliczane odsetki. Wszystkie otwarte transakcje dla tych typów zostaną uwzględnione w obliczeniach.  
3. Jeśli opcję **Odsetki** ustawiono na „Tak”, obliczysz odsetki od odsetek. Przed uwzględnieniem tych transakcji warto sprawdzić przepisy dotyczące obliczania odsetek od odsetek.  
4. W polu **Od dnia** wprowadź datę, od kiedy będą naliczane odsetki. Jeśli nie określisz wartości **Od dnia**, wszystkie niezaksięgowane noty odsetkowe zostaną anulowane, a odsetki zostaną obliczone ponownie od daty transakcji.
5. W polu **Do dnia** wprowadź datę, do kiedy będą naliczane odsetki.
6. W polu **Użyj profilu księgowania z** wybierz opcję. Dostępne są trzy opcje profili księgowania:
    - Konto — Dla każdej noty odsetkowej używanie profilu księgowania, który został przypisany do konta odbiorcy. 
    - Wybierz — Zostanie użyty profil księgowania wybrany w polu Profil księgowania.
    - Transakcja — Użycie dla każdej noty odsetkowej indywidualnego profilu księgowania z transakcji, w której obliczano odsetki. Transakcje, które nie mają przypisanego profilu księgowania, będą używać profilu księgowania określonego w formularzu Parametry modułu rozrachunków z odbiorcami w obszarze Księga i podatek.  
7. Rozwiń kartę skróconą **Rekordy do uwzględnienia**.
8. Kliknij przycisk **Filtr**.
9. W polu **Kryteria** wpisz identyfikator odbiorcy. Na przykład wpisz „US-001”.
6. Kliknij przycisk **OK**.
7. Kliknij przycisk **OK**.

## <a name="print-interest-notes"></a>Drukuj noty odsetkowe
1. W **Okienku nawigacji** przejdź do **Moduły > Kredyty i windykacja > Odsetki > Przejrzyj i przetwórz noty odsetkowe**.
2. W polu **Stan** wybierz opcję „Utworzono”.
3. W polu **Wydrukowane** wybierz opcję „Nie wydrukowano”.
4. Kliknij przycisk **Drukuj**.
5. Rozwiń kartę skróconą **Rekordy do uwzględnienia**.
6. Kliknij przycisk **OK**.
7. Zamknij stronę.

## <a name="post-the-interest-note"></a>Księgowanie noty odsetkowej
1. Wybierz notę odsetkową, która jest gotowa do zaksięgowania (ma stan Utworzono).
2. Kliknij przycisk **Księguj**.
3. Wprowadź datę księgowania noty odsetkowej. Zaznacz opcję Tak, aby tworzyć transakcje księgi głównej dla każdej noty odsetkowej. Jeśli nie zaznaczysz opcji Tak, odsetki ze wszystkich not odsetkowych dotyczących danego klienta zostaną skumulowane i zaksięgowane w księdze głównej jako jedna transakcja.  
4. Rozwiń kartę skróconą **Rekordy do uwzględnienia**.
5. Kliknij przycisk **OK**.
6. W polu **Stan** wybierz opcję „Zaksięgowano”.

