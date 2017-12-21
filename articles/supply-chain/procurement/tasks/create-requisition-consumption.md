--- 
title: "Tworzenie zapotrzebowania na zużycie"
description: "Ta procedura poprowadzi Cię przez proces tworzenia zapotrzebowania."
author: mkirknel
manager: AnnBe
ms.date: 11/03/2017
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
ms.sourcegitcommit: 7d8ca4e7eedea140f32e264c205b243027a06d03
ms.openlocfilehash: d1ea95d0bc283297fcedaee730e1829850f07998
ms.contentlocale: pl-pl
ms.lasthandoff: 11/20/2017

---
# <a name="create-a-requisition-for-consumption"></a>Tworzenie zapotrzebowania na zużycie

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura poprowadzi Cię przez proces tworzenia zapotrzebowania. Pokazuje różne sposoby wyszukiwania produktów w katalogu zaopatrzenia oraz sposoby dodawania produktu, którego nie ma w katalogu. Przed rozpoczęciem tej procedury musisz mieć skonfigurowaną zasadę zakupów z domyślnym typem zapotrzebowania Zużycie. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Procedurę można wykonać tylko przy użyciu profilu użytkownika skonfigurowanego jako pracownik.  To zadanie normalnie wykonuje pracownik. Rola zabezpieczeń Pracownik pozwoli wykonać te zadania. Jeśli używasz firmy USMF, możesz się zalogować jako Alicia.


## <a name="create-a-new-requisition"></a>Tworzenie nowego zapotrzebowania
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapotrzebowania na zakup > Zapotrzebowania na zakup przygotowane przeze mnie.
2. Kliknij przycisk Nowy.
3. W polu Nazwa nadaj zapotrzebowaniu nazwę.
4. W polu Data wymagalności wpisz datę.
    * Domyślnie data wymagalności i data księgowania są kopiowane do wierszy zapotrzebowania na zakup. Można je zmienić na poziomie wierszy. Data wymagalności jest wnioskowaną datą dostawy.  
5. W polu Data księgowania wpisz datę.
    * Data księgowania jest używana do rejestrowania wpisu księgowania w księdze głównej i do sprawdzania dostępności środków budżetowych.  
6. Kliknij przycisk OK.
7. W polu Przyczyna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wybrana przyczyna uzasadnienia biznesowego pojawia się domyślnie dla wierszy zapotrzebowania na zakup, ale można ją zmienić na poziomie wierszy.    
8. Na liście znajdź i zaznacz odpowiedni rekord.
9. Wybierz przyczynę.
10. W polu Szczegóły wprowadź bardziej opisowe uzasadnienie dla zapotrzebowania.

## <a name="add-a-line-to-the-requisition"></a>Dodawanie wiersza do zapotrzebowania
1. Kliknij przycisk Dodaj wiersz.
    * Istnieją dwa sposoby dodawania wierszy do zapotrzebowania na zakup. Jeśli znasz już numer produktu lub wiesz, że prosić o produkt, który nie znajduje się w katalogu produktów, można dodać wiersz bezpośrednio za pomocą opcji „Dodaj wiersz”. Drugi sposób to użycie opcji „Dodaj produkty”, gdzie można użyć funkcji wyszukiwania i filtrowania w celu znalezienia towarów w katalogu produktów.    
2. Kliknij nowo utworzony wiersz.
    * Zleceniodawcą jest pracownik, który zgłosił zapotrzebowanie.   
    * Domyślnie osobą przygotowującą zapotrzebowanie jest pracownik, który je złożył. Musisz otrzymać pozwolenie na przygotowanie wiersza zapotrzebowania w imieniu innego pracownika. Jeśli masz takie pozwolenie, drugi pracownik będzie widoczny w tym wyszukiwaniu.  
3. W polu Numer towaru wpisz wartość.
    * Towary dostępne do wyboru są ograniczone przez zasady dostępu do kategorii oraz przez katalog zaopatrzenia ustawiony dla firmy dokonującej zakupu.   
4. Wprowadź liczbę w polu Ilość.

## <a name="add-more-products-to-the-requisition"></a>Dodawanie kolejnych produktów do zapotrzebowania
1. Kliknij przycisk Dodaj produkty.
    * Jest to opcja, która umożliwia wyszukiwanie produktów w katalogu produktów.    
2. W polu Znajdź węzeł kategorii zaopatrzenia wpisz pierwszą częścią nazwy kategorii, której szukasz, a następnie kliknij przycisk Wprowadź.
    * Na przykład wpisz komput.  
3. Użyj skrótu InvokeDefaultButton.
4. Użyj opcji Filtr, aby wyfiltrować listę produktów w wybranej kategorii.
5. Zaznacz kartę produktu, który ma zostać dodany do zapotrzebowania.
6. Kliknij opcję Dodaj do wierszy.
7. W polu Ilość wprowadź liczbę.
8. W polu Znajdź węzeł kategorii zaopatrzenia wpisz pierwszą częścią nazwy kategorii, której szukasz, a następnie kliknij przycisk Wprowadź.
    * Na przykład wpisz Wysoki (wyróżnione).  
9. Użyj skrótu InvokeDefaultButton.
10. Kliknij przycisk Dodaj niewymieniony na liście produkt do wierszy, aby dodać produkt, który nie znajduje się w katalogu zaopatrzenia.
11. W polu Nazwa produktu wpisz wartość.
12. W polu Jednostka wpisz wartość.
13. Kliknij przycisk OK.
14. W polu Opis towaru wprowadź opis produktu.
15. Wprowadź liczbę w polu Ilość.
16. Wprowadź liczbę w polu Cena jednostkowa.
    * Jeśli znasz cenę określonego dostawcy (wybranego w polu Konto dostawcy), można wprowadzić cenę.   
17. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Dostępność dostawców w tym polu zależy od zasad zakupów oraz od stanu dostawcy w bieżącej kategorii zaopatrzenia. Zamiast wybierać dostawcę w tym polu, można kliknąć przycisk Sugeruj dostawców.    
18. Na liście zaznacz dostawcę, z którego chcesz skorzystać.
19. W polu Zewnętrzny kod towaru wpisz wartość.
    * Jest to numer referencyjny produktu znany przez dostawcę. Na przykład może to być numer produktu z własnego katalogu dostawcy.  
20. Kliknij przycisk OK.

## <a name="distribute-amounts"></a>Dystrybuuj kwoty
1. Kliknij opcję Finanse.
2. Kliknij opcję Rozdziel kwoty.
    * Ten proces pokazuje sposób rozdziału kosztów dla pierwszego wiersza między 2 konta. Można to również zrobić później, gdy zapotrzebowanie jest w weryfikacji.  
3. Kliknij opcję Podziel, aby utworzyć nowy wiersz dystrybucji.
4. W polu Konto księgowe zaznacz pierwsze centrum kosztów, które ma przejąć część kosztu.
5. Zaznacz drugi wiersz dystrybucji.
6. W polu Konto księgowe określ drugie centrum kosztów.
7. Kliknij opcję Podziel równo.
8. Zamknij stronę.

## <a name="view-line-details"></a>Wyświetl szczegóły wiersza
1. Przełącz rozwinięcie sekcji Szczegóły wiersza.

## <a name="submit-the-requisition"></a>Przesyłanie zapotrzebowania
1. Kliknij opcję Przepływ pracy, aby otworzyć rozwijane okno dialogowe.
2. Kliknij przycisk Prześlij.
3. Zamknij stronę.
4. W polu Komentarz wpisz uwagi do osoby zatwierdzającej zapotrzebowanie.
5. Kliknij przycisk Prześlij.
6. Zamknij stronę.
7. Odśwież stronę.


