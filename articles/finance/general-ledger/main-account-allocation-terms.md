---
title: Warunki alokacji
description: Ten temat zawiera informacje dotyczące używania warunków alokacji na koncie głównym.
author: rachel-profitt
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount, AllocationTerms
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-06-15
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f529852f63c3dd12064c74403a12f6f3041691e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988683"
---
# <a name="allocation-terms"></a>Warunki alokacji

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące używania warunków alokacji na koncie głównym. Postanowienia alokacji służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że wydatki lub przychody obciążają odpowiednie obiekty podczas księgowania.

Każdy warunek alokacji utworzony na koncie głównym definiuje wartość procentową załącznika, który ma zostać przydzielony z jednego źródłowego konta głównego i kombinację wymiarów finansowych. Ponadto należy zdefiniować docelowe konto główne i wymiary finansowe, w których kwota zostanie przydzielona. 

Podczas definiowania źródłowego wymiaru finansowego dla alokacji można określić, czy każdy wymiar jest określony, czy nieokreślony. Określenie określone wskazuje, że wymiar finansowy dla transakcji źródłowej musi być zgodny z wybranym wymiarem. Wybranie opcji niewłaściwe wskazuje, że dowolna wartość wymiaru finansowego może przyczynić się do dopasowania.

Podczas definiowania docelowego konta księgowego dla warunku alokacji należy określić konto główne, do którego ma zostać przydzielone kwota. Można skorzystać z tego samego konta głównego, na którym jest zaksięgowana transakcja źródłowa, lub innego konta głównego. Jeśli używane jest to samo konto główne, podczas zapisywania rekordu zostanie wyświetlone ostrzeżenie. Oprócz określenia konta głównego należy również określić wymiary docelowe. Dla każdego wymiaru można określić, czy chcesz zachować źródło wartość wymiaru finansowego, czy zmienić je. W przypadku wybrania opcji nie należy wybrać nową wartość dla wymiaru finansowego. W przypadku wybrania opcji tak dodatkowe informacje nie zostaną określone, a podczas księgowania system zachowa oryginalne wymiary finansowe.

Nie ma limitu liczby warunków alokacji, które można dodać do konta głównego; jednak suma wartości procentowych alokacji w warunku alokacji nie może przekroczyć 100. Można utworzyć alokacje o wartości mniejszej niż 100 procent, jeśli część oryginalnej kwoty załącznika powinna pozostawać w źródłowym wymiarze finansowym. Warunki alokacji można dodać do konta głównego jako zastąpienia firmy. W przypadku używania współużytkowanej plan kont należy zdefiniować warunki alokacji dla każdej firmy. Aby uzyskać dostęp do przycisku **Warunki alokacji**, należy najpierw zaznaczyć pole wyboru **Alokacja** w zastępowaniu zastępujące firmy.

## <a name="allocation-term-example"></a>Przykład warunku alokacji
Zdefiniowałeś centrum kosztów dla swojej organizacji o nazwie FIRMOWY, które ma numer 000. Podczas księgowania faktur dla wydatków na narzędzia są one kodowane w FIRMOWYM centrum kosztów. Firma określiła regułę, według której wszystkie wydatki na narzędzia powinny być alokowane w procentach do poszczególnych centrów kosztów. Inne wymiary finansowe dla działu i jednostki biznesowej pozostaną takie same.

W tym przykładzie zostanie utworzony nowy termin alokacji dla konta głównego wydatków na narzędzia. Dla każdego miejsca powstawania kosztów zostałby utworzony jeden wiersz z przypisaną wartością procentową. **Kryteria wyboru** dla źródłowych wymiarów finansowych dla każdego wiersza byłyby **Określone** dla **Centrum kosztów**, a wartość będzie równa 000: FIRMOWE. W przypadku działu i jednostki biznesowej **Kryteria wyboru** byłyby **Nieokreślone**.

Na skróconej karcie **Docelowe konto księgowe** będzie to samo konto wydatku, a **Zachowaj źródłowe wymiary finansowe** zostaną ustawione na **Tak** dla **Jednostki biznesowej** i **Działu.** **Zachowaj źródłowe wymiary finansowe** zostaną ustawione jako **Nie** dla **Centrum kosztu**, a wybrana wartość będzie odpowiadać każdemu centrum kosztów, do którego alokujesz. Jeśli istnieją trzy centra kosztów do alokacji, zostaną utworzone trzy rekordy warunków alokacji. Jedyną różnicą między każdym okresem alokacji jest miejsce powstawania kosztów określone na docelowym koncie księgowym.

## <a name="create-an-allocation-term-on-a-main-account"></a>Tworzenie warunku alokacji na koncie głównym

1. W **Okienko nawigacji** wybierz kolejno **Moduły > Księga główna > Plan kont > Konta > Konta główne**.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na skróconej karcie **Firma zastępuje**, wybierz opcję **Dodaj**.
4. Wybierz **Firmę**, a następnie wybierz przycisk **Dodaj**.
5. Zaznacz pole wyboru **Alokacja**.
6. Wybier **Warunki alokacji** .
7. Wybierz opcję **Edytuj**, aby zmodyfikować rekord domyślny, lub wybierz opcję **Nowy**, aby dodać rekord.
8. W polu **Procent** wprowadź wartość procentową transakcji załączników, które mają zostać przydzielone.
9. Na skróconej karcie **Źródłowy wymiar finansowy** w **Kryteriach wyboru** dla każdego wymiaru finansowego wybierz odpowiednią opcję.
    - W przypadku wybrania opcji **Określone** wybierz wartość wymiaru finansowego w polu rozwijanym po prawej stronie.
    - Jeśli wybrano opcję **Nieokreślone**, dla wymiaru finansowego nie są wymagane żadne dodatkowe informacje.
10. Na skróconej karcie oknta **Docelowa księga** w polu **Do konta** wybierz konto główne, w którym chcesz przydzielić wartość procentową transakcji na załączniku.
11. W obszarze **Zachowaj źródłowe wymiary finansowe** dla każdego wymiaru finansowego wybierz opcję.
    - W przypadku wybrania opcji **Nie** wybierz wartość wymiaru finansowego w polu rozwijanym po prawej stronie, do którego ma być alokowana transakcja na załączniku.
    - W przypadku wybrania opcji **Tak** dodatkowe informacje nie są wymagane. System zachowa wartość w oryginalnym załączniku podczas księgowania alokacji.
12. Powtórz kroki od 7 do 11 dla każdej dodatkowej alokacji. Suma wszystkich alokacji jest wskazana w polu **Łączny procent**. Kwota ta nie może być większa niż 100.
13. Zamknij wszystkie strony.

>[!NOTE] 
> Opcjonalnie można skorzystać z przycisku **Kopiuj**, aby zduplikować wybraną alokację.

Po utworzeniu warunku alokacji dla konta głównego system automatycznie zaksięguje nowy załącznik w przypadku zaksięgowania załącznika, który odpowiada źródłowym wymiarom finansowym w warunkach alokacji.
