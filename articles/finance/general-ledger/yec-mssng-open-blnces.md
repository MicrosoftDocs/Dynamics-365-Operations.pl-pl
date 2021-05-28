---
title: Brakujące salda otwarcia dla zamknięcia na koniec roku
description: W tym temacie wyjaśniono, dlaczego podczas zamykania roku może brakować sald otwarcia, a także opisano sposób ich odtworzenia w przypadku ich braku.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 045d0bf11b11c9a353858ce3ca82c698dbceea7c
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028581"
---
# <a name="year-end-close-missing-opening-balances"></a>Brakujące salda otwarcia dla zamknięcia na koniec roku

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, dlaczego podczas zamykania roku może brakować sald otwarcia, a także opisano sposób ich odtworzenia w przypadku ich braku.

### <a name="symptom"></a>Objaw

Dlaczego po uruchomieniu zamknięcia na koniec roku księgi głównej nie są dostępne salda początkowe? 

### <a name="resolution"></a>Rozwiązanie

Oto kilka czynności do sprawdzenia w przypadku, gdy zamknięto rok w księdze głównej, a następnie wygenerowano bilans próbny, który nie wyświetlił sald otwarcia dla następnego roku obrachunkowego.

Jeśli dla pola **Cofnij poprzednie zamknięcie** wybrano opcję **Tak**, poprzednie zamknięcie na koniec roku dla tego samego roku obrachunkowego zostanie cofnięte. W przypadku uruchomienia procesu cofnięcia zamknięcia roku wszystkie wpisy zarówno salda zamknięcia, jak i salda otwarcia zostaną usunięte, tak jakby zamknięcie na koniec roku nigdy nie zostało przeprowadzone. Załączniki także zostaną usunięte. Proces zamknięcia na koniec roku nie zostanie ponownie uruchomiony automatycznie. Konieczne będzie ponowne rozpoczęcie procesu, przy czym tym razem należy dla opcji **Cofnij poprzednie zamknięcie** zmienić ustawienie na **Nie**.

Ten scenariusz został opisany w zawierającym często zadawane pytania temacie poświęconym kwestii zamknięcia na koniec roku. Aby uzyskać więcej informacji, zobacz [Działania na koniec roku — często zadawane pytania](faq-year-end-activities.md).

### <a name="symptom"></a>Objaw

Uruchomiono zamknięcie na koniec roku z opcją **Cofnij poprzednie zamknięcie** ustawioną na **Nie**, a mimo to nie są dostępne salda otwarcia dla danego roku obrachunkowego.

### <a name="resolution"></a>Rozwiązanie

Najpierw sprawdź stan zadania wsadowego. Zamknięcie roku obejmuje wiele oddzielnych zadań, ale najważniejszym krokiem jest zadanie wsadowe z opisem **Krok 5.0.0**. W tym kroku ma miejsce zaksięgowanie w księdze głównej transakcji otwarcia oraz, opcjonalnie, transakcji zamknięcia. 

[![Lista historii zadań przetwarzania wsadowego](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)

Jeśli ten krok zakończył się pomyślnie, ale salda otwarcia nie są widoczne na stronie **Zapytanie o bilans próbny** (**Księga główna > Zapytania i raporty > Bilans próbny**), przejrzyj wyniki zadania wsadowego zamknięcia na koniec roku, aby sprawdzić, czy krok Odbuduj salda został pomyślnie ukończony.

[![Wyniki zadania wsadowego zamknięcia na koniec roku](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)

Jeśli ten krok nie powiódł się z dowolnej przyczyny, transakcje otwarcia (i opcjonalnie zamknięcia) prawdopodobnie zostały pomyślnie zaksięgowane. Za pomocą strony **Zapytanie o transakcje na załączniku** można sprawdzić, czy transakcje księgi głównej zostały pomyślnie zaksięgowane. W tym celu należy określić numer załącznika i datę z okna dialogowego zamknięcia na koniec roku przeprowadzonego przez użytkownika (**Księga główna > Zapytania i raporty > Transakcje na załączniku**).

[![Zapytanie o transakcje na załączniku](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)

Jeśli załączniki otwarcia (i opcjonalne zamknięcia) są obecne, nie musisz ponownie uruchamiać zamknięcia na koniec roku. Zamiast tego zapoznaj się z następną sekcją, aby uzyskać informacje o właściwym sposobie dalszego postępowania.

### <a name="symptom"></a>Objaw

Krok „Odbuduj salda” w trakcie zamknięcia na koniec roku nie powiódł się. Czy należy ponownie uruchomić cały proces zamknięcia na koniec roku?

### <a name="resolution"></a>Rozwiązanie

W ramach kroku Odbuduj salda następuje aktualizacja sald księgi głównej, które są używane podczas generowania zapytania o bilans próbny.  Jest to ostatni etap procesu zamknięcia na koniec roku.  Jeśli tylko ten krok zakończy się niepowodzeniem, transakcje księgi głównej zostały pomyślnie zaksięgowane.  Ponowne uruchomienie zamknięcia na koniec roku nie jest konieczne. Proces odbudowy sald można uruchomić ręcznie za pomocą strony **Zestawy wymiarów finansowych** (**Księga główna > Plan kont > Wymiary > Zestawy wymiarów finansowych**).

[![Przycisk Odbuduj salda na stronie Zestawy wymiarów finansowych](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)

Jeśli przetworzenie tego kroku zajmuje dużo czasu, zalecane jest przejrzenie najlepszych rozwiązań w odniesieniu do zestawów wymiarów finansowych zgodnie z opisem w temacie [Najlepsze rozwiązania dotyczące aktualizowania zestawów wymiarów finansowych](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets). 

