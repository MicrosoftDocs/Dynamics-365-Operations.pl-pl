---
title: Dodaj informacje dotyczące zarządzania kredytem odbiorców
description: W tym temacie opisano sposób dodawania informacji o zarządzaniu kredytami dla odbiorcy.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: a04180a5dbec1e08d0149beeed0495a0d13af76c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971735"
---
# <a name="add-credit-management-information-for-customers"></a>Dodaj informacje dotyczące zarządzania kredytem odbiorców

[!include [banner](../includes/banner.md)]

Po skonfigurowaniu parametrów kontrolujących zarządzanie kredytami można dodać więcej szczegółów dla każdego odbiorcy. Te szczegóły kontrolują procesy zarządzania kredytami i udostępniają także dodatkowe informacje, które ułatwiają członkom zespołu ds. Zarządzanie odbiorcami.

## <a name="customer-information"></a>Informacje o odbiorcy

Można dodać szegóły odbiorcy w formularzu **Kredyty i windykacje** na skróconej karcie na stronie **Wszyscy odbiorcy** (**Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**).

1. Opcję **Nieograniczony limit kredytu** należy wybrać na **tak**, jeśli odbiorca nie powinien być ograniczony żadnym testem limitu kredytu.
2. Ustawienie opcji **Wyklucz z zarządzania kredytem** na wartość **tak** powoduje wykluczenie odbiorcy z wszelkich akcji, które zazwyczaj występują podczas procesów zarządzania kredytami.
3. Wybierz grupę zarządzania kredytem dla danego odbiorcy.
4. Aby obliczyć limit kredytu w walucie odbiorcy, w polu **Limit kredytu w polu walucie odbiorcy** wprowadź limit kredytu odbiorcy. Limit kredytu w walucie firmy zostanie przekonwertowany przy użyciu kursów wymiany określonych przez limit kredytu typ kursu wymiany wybranego w parametrach zarządzania kredytami.
5. W polu **Ostatnia data przeglądu** wprowadź datę ostatniej weryfikacji limitu kredytowego odbiorcy przez menedżera kredytu.
6. W polu **Następna zaplanowana daty przeglądu** wprowadź datę zaplanowanego przeglądu i aktualizacji kredytu dla odbiorcy.
7. W polu **uprawniony limit** kredytu wprowadź najwyższy limit kredytu, który może być przypisany do odbiorcy na podstawie przeglądu historii kredytowej tego odbiorcy. Kwalifikujący się limit kredytu może się różnić od limitu kredytowego wyświetlanego w skróconej karcie **Kredyt i windykacje**.
8. W polu **Kwalifikująca się waluta limitu kredytu** wprowadź walutę kwalifikującego się limitu kredytowego.
9. W polu **Kwalifikująca się data limitu kredytu** wprowadź datę utworzenia spełniającego warunki limitu kredytowego.
10. W polu **Stan konta kredytowego** wprowadź stan konta kredytowego odbiorcy.
11. W polu **Przyczyna stanu** wprowadź przyczynę, która jest skojarzona ze stanem konta.
12. Ustawienie opcji **Z agencją** na wartość **tak** powoduje wskazanie, że odbiorca jest aktualnie przypisany do agencji kredytowej. Ta wartośc jest używana wyłącznie w celach informacyjnych. Nie jest on używany w żadnym procesie zarządzania kredytami.
13. Ustawienie opcji **Wytrzymanie tytułu** na wartość **tak** oznacza, że tytuł ma być przechowywany dla firmy. Ta wartośc jest używana wyłącznie w celach informacyjnych. Nie jest on używany w procesie zarządzania kredytami.
14. W polu **Data rozpoczęcia pracy** wprowadź datę, od której odbiorca po raz pierwszy rozpoczął działalność gospodarczą. Te informacje są używane podczas tworzenia wyników dotyczących ryzyka.
15. W polu **Odbiorca od** wprowadź datę przetwarzania pierwszej transakcji dla odbiorcy. Te informacje są używane podczas tworzenia wyników dotyczących ryzyka.
16. Umożliwia wprowadzenie notatek, które mogą być używane przez zespół kredytów do dalszego oceniania zdolności kredytowej odbiorcy.

Należy zauważyć, że niektóre informacje wyświetlane na stronie **Odbiorcy** są tworzone przez inny proces:

- Pole **Data ważności limitu kredytu** pokazuje datę wygaśnięcia limitu kredytowego. Jeśli to pole nie zostanie ustawione, limit kredytu odbiorcy nie wygaśnie.
- Pole **Data limitu kredytu** pokazuje datę stworzenia limitu kredytu. To pole jest aktualizowane przy każdym korygowaniu limitu kredytu.
- Tymczasowe limity kredytowe zastępują limit kredytu odbiorcy dla okresu. Są one używane zamiast limitu kredytu w celu obliczenia łącznego limitu kredytu. Ta informacja jest wyświetlana tylko wtedy, gdy istnieje aktywny limit kredytu. Można dodawać tymczasowe limity kredytu do korekt limitu kredytu.
- Pole **Ubezpieczenie i gwarancje** zawiera łączną wartość ubezpieczenia i gwarancji, które mogą zwiększyć limit kredytu dla odbiorcy.
- Pole **Łączny limit kredytu** zawiera końcowy limit kredytu dla odbiorcy. Łączny limit kredytu uwzględnia ubezpieczenie i gwarancje oraz tymczasowe limity kredytowe.

## <a name="temporary-credit-limits"></a>Limity kredytu tymczasowego

Tymczasowe limity kredytowe zastępują limity kredytu odbiorcy dla zdefiniowanego okresu. Można dodawać tymczasowe limity kredytu za pomocą korekt limitu kredytu. Korekty limitu kredytu umożliwiają menedżerom kredytów aktualizowanie limitów kredytu i dat wygaśnięcia jednego odbiorcy, grupy odbiorców lub wszystkich odbiorców w procesie księgowania.

Istnieje możliwość tworzenia wpisów korekt limitu kredytu na stronie **Korekty limitu kredytu** (**Zarządzanie kredytem \> Korekta limitu kredytu \> Korekty limitu kredytu**).

## <a name="create-insurance-policies-and-guarantees"></a>Tworzenie polis ubezpieczeniowych i gwarancji

Można utworzyć jedną lub więcej polis ubezpieczeniowych i gwarancji dla każdego odbiorcy. Następnie możesz użyć ich do obliczenia ekspozycji, jaką ma firma, gdy oferuje kredyt klientowi. Polisy ubezpieczeniowe i gwarancje mogą być również uwzględnione w limicie kredytu dla odbiorcy.

Można utworzyć polisę ubezpieczeniową i gwarancje na stronie **Wszyscy odbiorcy** (**Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**). Wybierz odbiorcę, a następnie w okienku akcji na karcie **Zarządzanie kredytem** wybierz opcję **Ubezpieczenie i gwarancje**.

> [!NOTE]
> W poniższej procedurze użytkownik wybiera ubezpieczyciela lub gwaranta z globalnej książki adresowej. Dlatego przed rozpoczęciem tej procedury należy upewnić się, że ubezpieczyciele i gwaranci zostali dodani do globalnej książki adresowej.

1. W polu **Identyfikator** wprowadź **Gwarancja** lub **Ubezpieczenie**.
2. W polu **Typ gwarancji/ubezpieczenia** wybierz jeden z poprzednio zdefiniowanych typów gwarancji lub ubezpieczenia.
3. W polu **Ubezpieczyciel/Gwarant** wybierz ubezpieczyciela lub gwaranta z globalnej książki adresowej. 
4. Jeśli wybrano wartość **Ubezpieczenie** w polu **Identyfikator**, w polu **Typ pokrycia polisy** wybierz jeden z poprzednio zdefiniowanych typów pokrycia. Nie można wybrać typu pokrycia polisy dla gwarancji.
5. W polu **Identyfikator** wprowadź identyfikator polisy. Ten identyfikator jest zazwyczaj numerem polisy.
6. W polu **Weszła w życie** wprowadź datę początkową polisy ubezpieczeniowej lub gwarancji.
7. W polu **Data ważności** wprowadź datę początkową polisy ubezpieczeniowej lub gwarancji. wygasa.
8. W polu **Wartość** wprowadź wartość polisy ubezpieczeniowej lub gwarancji. Ta wartość jest pełną wartością polisy.
9. W polu **Waluta** wybierz walutę skojarzoną z wartością polisy. 
10. W polu **Aktualizuj limit kredytu** określ wartość procentową z przedziału od **0** do **100**. Ta wartość procentowa zostanie zastosowana do wartości polisy, a wynikowa kwota zostanie użyta do zwiększenia limitu kredytu używanego w obliczeniach limitu kredytu. Obliczona wartość jest wyświetlana w **Łączny limit kredytu, ubezpieczenie i gwarancje** na skróconej karcie **Kredyt i windykacje** na stronie **Odbiorcy**.

    Oto przykład:

    - Limit kredytu (A) to 100 000.
    - Wartość polisy (B) wynosi 50 000.
    - Wartość procentowa **aktualizacji limitu kredytu** (C) wynosi 50,00.
    
    W tym przypadku efektywny limit kredytu to 125 000 (= A + \[B × C\]).

11. Zaznacz pole wyboru **Uwzględnij w ekspozycji**, aby zmniejszyć limit kredytu używany w obliczeniach limitu kredytu na podstawie pełnej wartości polisy. Jeśli to pole wyboru jest zaznaczone, wartość obliczona w przypadku określenia procentu **Aktualizacja limitu kredytu** nie będzie używana w obliczeniach limitu kredytu.

    Oto przykład:

    - Limit kredytu (A) to 100 000.
    - Wartość polisy (B) wynosi 50 000.
    - Wartość procentowa **aktualizacji limitu kredytu** (C) wynosi 50,00.

    W tym przypadku efektywny limit kredytu to 125 000 (= A + \[B × C\]).
    
    Jeśli jednak zostanie zaznaczone pole wyboru **Uwzględnij w ekspozycji**, **Aktualizuj limit kredytu** będzie wynosić 50 000 (= 50,00 procent z 100 000), a wartość ekspozycji wynosi 75 000 (= A + \[B × C\] – B).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]