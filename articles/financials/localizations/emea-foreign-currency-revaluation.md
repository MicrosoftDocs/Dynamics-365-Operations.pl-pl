---
title: Przeszacowanie w walucie obcej dla kont bankowych
description: Ten temat zawiera informacje o przeszacowywaniu w walucie obcej dla kont bankowych.
author: ShylaThompson
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 11464
ms.search.region: Czech Republic, Estonia, Latvia, Lithuania, Poland
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7e04c046aac0825a6a9d2b2b439bc2261ed61f16
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="currency-revaluation-for-bank-account-transactions"></a>Przeszacowanie w walucie dla transakcji na kontach bankowych

[!include [banner](../includes/banner.md)]

## <a name="revalue-foreign-currency-amounts-for-bank-account-transactions"></a>Zmiana wartości kwoty w walucie obcej dla transakcji na kontach bankowych

> [!IMPORTANT]
> Ta sekcja dotyczy tylko firm, które mają podstawowy adres w Polsce.

Można zmienić wartości kwoty w walucie obcej dla transakcji bankowych. Następnie można utworzyć raport o transakcjach bankowych z korektami przeszacowań w walucie obcej.

1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Zadania okresowe** &gt; **Bank — różnica kursowa (FIFO/LIFO)**.
2. W polu **W dniu** wprowadź datę końcową dotyczącą przeszacowania. W obliczaniu są uwzględnione tylko transakcje z datami wcześniejszymi od wskazanej daty.
3. Wybierz kolejno opcje **Rekordy do uwzględnienia** &gt; **Filtr** &gt; **Dodaj**, aby dodać konto bankowe. Jeśli nie określisz konta bankowego, zostaną przeszacowane kwoty dla wszystkich kont bankowych.
4. Kliknij przycisk **OK**, aby zamknąć stronę zapytania.
5. Na stronie **Przeszacowanie w walucie obcej** zaznacz pole wyboru **Ponowne obliczanie**, aby przeszacować kwoty w walucie obcej dla wszystkich otwartych okresów.

## <a name="create-a-report-to-view-bank-transactions-that-have-adjustments-for-foreign-currency-revaluations"></a>Tworzenie raportu o transakcjach bankowych z korektami przeszacowań w walucie obcej

> [!IMPORTANT]
> Ta sekcja dotyczy tylko firm, które mają podstawowy adres w Polsce.

1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Zapytania i raporty** &gt; **Bank — raport korekt kursu wymiany**.
2. Wybierz kolejno opcje **Rekordy do uwzględnienia** &gt; **Filtr**, aby znaleźć jedno lub więcej kont bankowych, o których chcesz wyświetlić informacje.
3. Opcjonalnie: W polu **Konto bankowe** wybierz konto bankowe. Jeśli zostawisz to pole puste, raport będzie zawierał szczegóły transakcji bankowej dla wszystkich kont bankowych.
4. Kliknij przycisk **OK**. Raport zostanie wygenerowany. 

## <a name="calculate-exchange-rate-adjustments-for-bank-account-transactions"></a>Obliczanie korekt kursu wymiany dla transakcji konta bankowego

> [!IMPORTANT]
> Ta sekcja dotyczy tylko firm, które mają podstawowy adres w Czechach, Estonii, na Litwie lub na Łotwie.

Musisz przeszacować i dostosować konta bankowe, jeśli istnieje różnica kursów wymiany między walutą rozliczeniową i walutą raportowania. To zadanie ułatwia obliczenie odpowiedniego salda w walucie rozliczeniowej i walucie raportowania dla kont bankowych.

1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie gotówką i bankami**.
2. Na karcie **Sekwencje numerów** w polu **Odwołanie** wybierz numerację dla odwołania **Bank — różnice kursowe**.
3. Zamknij stronę.
4. Wybierz kolejno opcje **Księga główna** &gt; **Ustawienia** &gt; **Waluta** &gt; **Kursy wymiany waluty**. Na stronie **Kursy wymiany waluty** można definiować kurs wymiany między dwiema walutami lub dla pary walut.
5. Po zakończeniu zamknij stronę.
6. Wybierz kolejno opcje **Księga główna** &gt; **Ustawienia** &gt; **Księga**. W polach **Niezrealizowana dodatnia różnica kursowa** i **Niezrealizowana ujemna różnica kursowa** wybierz konto główne, dla którego są księgowane kursy wymiany.
7. Zamknij stronę.
8. Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Zadania okresowe** &gt; **Przeszacowanie w walucie obcej**.
9. W polu **W dniu** wybierz datę przeszacowanie lub korekty.
10. W polu **Z waluty** wybierz kod bieżącej waluty. W polu **Na walutę** wybierz walutę, na którą należy dokonać korekty.
11. Wybierz kolejno opcje **Rekordy do uwzględnienia** &gt; **Filtr**, aby znaleźć konto bankowe, a następnie kliknij przycisk **OK**.
12. Na stronie **Przeszacowanie w walucie obcej** kliknij przycisk **OK**. Zostanie obliczona korekta transakcji kont bankowych dla wybranej daty.

> [!NOTE]
> W księdze głównej są wyświetlane dwie oddzielne transakcje: jedna w walucie rozliczeniowej i jedna w walucie raportowania.

