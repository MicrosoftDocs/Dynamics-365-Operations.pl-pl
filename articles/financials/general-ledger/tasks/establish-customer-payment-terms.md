--- 
title: "Definiowanie warunków płatności dla odbiorcy"
description: "Ta procedura określa konfigurację rabatu gotówkowego i terminu płatności."
author: aprilolson
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 04b45508047d26ef7c08ede5862be75835783ef5
ms.contentlocale: pl-pl
ms.lasthandoff: 10/26/2017

---
# <a name="establish-customer-payment-terms"></a>Definiowanie warunków płatności dla odbiorcy

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura określa konfigurację rabatu gotówkowego i terminu płatności. W tym przewodniku po zadaniach jest wykorzystywana firma demonstracyjna USMF.

1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Dni płatności.
    * Konfiguracja warunków płatności jest wspólna dla modułów Rozrachunki z odbiorcami i Rozrachunki z dostawcami. Po zdefiniowaniu w jednym module będzie dostępna również w drugim module. W tym przewodniku po zadaniach skonfiguruję wszystkie warunki płatności w module Rozrachunki z odbiorcami.  
2. Kliknij przycisk Nowy.
    * Utwórz dzień płatności, jeśli warunki płatności wymagają określonego dnia tygodnia (poniedziałek, wtorek itd.) lub określonego dnia miesiąca (5., 10. itp).  
3. W polu Dzień płatności wprowadź identyfikator dnia płatności.
4. W polu Opis wprowadź opis dnia płatności.
5. W polu Tydzień/Miesiąc zaznacz opcję Tydzień lub Miesiąc.
    * Aby wprowadzić dzień tygodnia, taki jak poniedziałek, wybierz opcję Tydzień. Aby wprowadzić dzień miesiąca, taki jak 10., wybierz opcję Miesiąc. W tym przykładzie wybierz opcję Miesiąc.  
6. W polu Dzień miesiąca wprowadź datę.
    * Datę należy wprowadzić jako liczbę, na przykład „10”, a nie jako „10.”.  
7. Kliknij przycisk Zapisz.
8. Zamknij stronę.
9. Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Warunki płatności.
10. Kliknij przycisk Nowy.
    * Warunki płatności służą do definiowania sposobu obliczania terminów płatności. Konfigurację daty rabatu gotówkowego wprowadza się na osobnej stronie.  
11. W polu Warunki płatności wprowadź identyfikator warunków płatności.
12. W polu Opis wprowadź opis.
13. Wybierz metodę płatności, taką jak Płatne przy odbiorze, Netto, Bieżący miesiąc itp.
    * Metoda płatności służy do definiowania początku okresu obliczania terminów płatności w określony sposób.  Na przykład opcja Netto jest używana, jeśli termin płatności jest zawsze określoną liczbą miesięcy lub dni po dacie faktury. Opcja Płatne przy odbiorze może być używana, gdy płatność jest wymagana po otrzymaniu faktury, tzn. nie oblicza się terminu płatności. W tym przewodniku po zadaniach wybierz opcję Bieżący miesiąc.  
14. Wybierz opcję Dzień płatności, jeśli w obliczeniach jest brany pod uwagę określony dzień tygodnia lub data.
    * W zależności od warunków płatności można wprowadzić ilość w miesiącach lub dniach. Alternatywnie można użyć opcji Harmonogram płatności lub Dzień płatności, aby „dodać” dni na końcu metody płatności. Jeśli terminem płatności zawsze będzie 10. dzień następnego miesiąca, w opcji Dzień płatności zaznacz wartość 10.  
15. Kliknij przycisk Zapisz.
16. Zamknij stronę.
17. Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Rabaty gotówkowe.
18. Kliknij przycisk Nowy.
    * Ta strona służy do definiowania sposobu obliczania daty rabatu gotówkowego.  
19. W polu Rabat gotówkowy wprowadź identyfikator rabatu gotówkowego.
20. W polu Opis wprowadź opis.
21. Jeśli jest dostępny warstwowy rabat gotówkowy, wybierz następny kod rabatu przewidziany po tym nowym rabacie gotówkowym.
22. Wpisz liczbę dni używanych do obliczania daty rabatu gotówkowego.
    * Jeśli jest wybrana zasada Netto, w celu obliczenia daty rabatu gotówkowego liczba dni zostanie dodana do daty faktury.  
23. Wprowadź wartość procentową rabatu gotówkowego.
24. Wprowadź konto główne, na którym będzie księgowany rabat gotówkowy faktur dla odbiorców.
25. W polu Konta przeciwstawne rabatów zaznacz opcję.
    * W przypadku wybrania opcji „Konta w wierszach faktury” rabat gotówkowy będzie księgowany na tym samym koncie głównym środków trwałych/wydatków z wierszy faktury od dostawcy. Jeśli wybierzesz opcję „Użyj konta głównego dla faktur od dostawcy”, rabat gotówkowy będzie księgowany na koncie głównym zdefiniowanym w ustawieniu „Konto główne dla faktur od dostawcy”. W tym przykładzie wybierz opcję „Użyj konta głównego dla faktur od dostawcy”.  
26. Wprowadź konto główne, na którym będzie księgowany rabat gotówkowy faktur od dostawców.
27. Kliknij przycisk Zapisz.


