---
title: Definiowanie warunków płatności dla odbiorcy
description: Ta procedura określa konfigurację rabatu gotówkowego i terminu płatności.
author: aprilolson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PaymDay, PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f4adfd4231a39df6f17e8a131aa14d057eb8447
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809989"
---
# <a name="establish-customer-payment-terms"></a>Definiowanie warunków płatności dla odbiorcy

[!include [banner](../../includes/banner.md)]

Ta procedura określa konfigurację rabatu gotówkowego i terminu płatności. W tym przewodniku po zadaniach jest wykorzystywana firma demonstracyjna USMF.

1. Wybierz kolejno **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia płatności > Dni płatności**. Konfiguracja **warunków płatności** jest wspólna dla modułów **Rozrachunki z odbiorcami** i **Rozrachunki z dostawcami**. Po zdefiniowaniu w jednym module będzie dostępna również w drugim module. W tym przewodniku po zadaniach skonfiguruję wszystkie warunki płatności w module **Rozrachunki z odbiorcami**.
2. Kliknij przycisk **Nowy**. Utwórz dzień płatności, jeśli warunki płatności wymagają określonego dnia tygodnia (poniedziałek, wtorek itd.) lub określonego dnia miesiąca (5., 10. itp). 
3. W polu **Dzień płatności** wprowadź identyfikator.
4. W polu **Opis** wprowadź opis dnia płatności.
5. W polu **Tydzień/Miesiąc** zaznacz opcję Tydzień lub Miesiąc. Aby wprowadzić dzień tygodnia, taki jak poniedziałek, wybierz opcję Tydzień. Aby wprowadzić dzień miesiąca, taki jak 10., wybierz opcję Miesiąc. W tym przykładzie wybierz opcję Miesiąc. 
6. W polu **Dzień miesiąca** wprowadź datę. Datę należy wprowadzić jako liczbę, na przykład „10”, a nie jako „10.”. 
7. Kliknij przycisk **Zapisz**.
8. Zamknij stronę.
9. Wybierz kolejno **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia płatności > Warunki płatności**.
10. Kliknij przycisk **Nowy**. Warunki płatności służą do definiowania sposobu obliczania terminów płatności. Konfigurację daty rabatu gotówkowego wprowadza się na osobnej stronie. 
11. W polu **Warunki płatności** wprowadź identyfikator.
12. W polu **Opis wprowadź** opis.
13. Wybierz **metodę płatności** taką jak COD, netto, bieżącego miesiąca itp. Metoda płatności służy do definiowania początku, w jaki sposób będą obliczane kwoty należne. Na przykład opcja Netto jest używana, jeśli termin płatności jest zawsze określoną liczbą miesięcy lub dni po dacie faktury. Opcja Płatne przy odbiorze może być używana, gdy płatność jest wymagana po otrzymaniu faktury, tzn. nie oblicza się terminu płatności. W tym przewodniku po zadaniach wybierz opcję „Bieżący miesiąc”.  
14. Wybierz opcję **Dzień płatności**, jeśli w obliczeniach jest brany pod uwagę określony dzień tygodnia lub data. W zależności od warunków płatności można wprowadzić ilość w miesiącach lub dniach. Alternatywnie można użyć opcji **Harmonogram płatności** lub **Dzień płatności**, aby „dodać” dni na końcu metody płatności. Jeśli terminem płatności zawsze będzie 10. dzień następnego miesiąca, w opcji **Dzień płatności** zaznacz wartość 10. 
15. Kliknij przycisk **Zapisz**.
16. Zamknij stronę.
17. Wybierz kolejno opcje **Rozrachunki z odbiorcami > Ustawienia płatności > Rabaty gotówkowe**.
18. Kliknij przycisk **Nowy**. Ta strona służy do definiowania sposobu obliczania daty rabatu gotówkowego. 
19. W polu **Rabat gotówkowy** wprowadź identyfikator.
20. W polu **Opis wprowadź** opis.
21. Jeśli jest dostępny warstwowy rabat gotówkowy, wybierz **następny kod rabatu** przewidziany po tym nowym rabacie gotówkowym.
22. W polu **Dni** wpisz liczbę dni używanych do obliczania daty rabatu gotówkowego. Jeśli jest wybrana zasada **Netto**, w celu obliczenia daty rabatu gotówkowego liczba dni zostanie dodana do daty faktury.  
23. W polu **Procent rabatu** wprowadź wartość procentową rabatu gotówkowego.
24. W polu **konto główne rabatów odbiorcy** wprowadź konto główne, na którym będzie księgowany rabat gotówkowy dla faktur odbiorców.
25. W polu **Konta przeciwstawne rabatów** zaznacz opcję. W przypadku wybrania opcji „Konta w wierszach faktury” rabat gotówkowy będzie księgowany na tym samym koncie głównym środków trwałych/wydatków z wierszy faktury od dostawcy. Jeśli wybierzesz opcję „Użyj konta głównego dla faktur od dostawcy”, rabat gotówkowy będzie księgowany na koncie głównym zdefiniowanym w ustawieniu „Konto główne dla faktur od dostawcy”. W tym przykładzie wybierz opcję „Użyj konta głównego dla faktur od dostawcy”. 
26. W polu **konto główne rabatów dostawcy** wprowadź konto główne, na którym będzie księgowany rabat gotówkowy dla faktur dostawcy.
27. Kliknij przycisk **Zapisz**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]