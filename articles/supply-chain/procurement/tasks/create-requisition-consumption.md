---
title: Tworzenie zapotrzebowania na zużycie
description: W tym temacie opisano proces tworzenia wniosku.
author: mkirknel
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2948282d8b40f7d34ffbae072a195cf954ab6e2
ms.sourcegitcommit: 81e6eaa2178fda7f7d086ad978f4c891bc4ec10a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/10/2019
ms.locfileid: "1738911"
---
# <a name="create-a-requisition-for-consumption"></a>Tworzenie zapotrzebowania na zużycie

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym temacie opisano proces tworzenia wniosku. Pokazuje różne sposoby wyszukiwania produktów w katalogu zaopatrzenia oraz sposoby dodawania produktu, którego nie ma w katalogu. Przed rozpoczęciem tej procedury musisz mieć skonfigurowaną zasadę zakupów z domyślnym typem zapotrzebowania Zużycie. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Procedurę można wykonać tylko przy użyciu profilu użytkownika skonfigurowanego jako pracownik. To zadanie normalnie wykonuje pracownik. Rola zabezpieczeń **Pracownik** pozwoli wykonać te zadania. Jeśli używasz firmy USMF, możesz się zalogować jako **Alicia**.


## <a name="create-a-new-requisition"></a>Tworzenie nowego zapotrzebowania
1. Wybierz kolejno **okienko nawigacji > Moduły > Zaopatrzenie i sourcing > Zapotrzebowania na zakup > Zapotrzebowania na zakup przygotowane przeze mnie**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa** nadaj zapotrzebowaniu nazwę.
4. W polu **Data wymagalności** wpisz datę. Domyślnie data wymagalności i data księgowania są kopiowane do wierszy zapotrzebowania na zakup. Można je zmienić na poziomie wierszy. Data wymagalności jest wnioskowaną datą dostawy.  
5. W polu **Data księgowania** wpisz datę. Data księgowania jest używana do rejestrowania wpisu księgowania w księdze głównej i do sprawdzania dostępności środków budżetowych.  
6. Kliknij przycisk **OK**.
7. W polu **Przyczyna** wybierz opcję z menu rozwijanego. Wybrana przyczyna uzasadnienia biznesowego pojawia się domyślnie dla wierszy zapotrzebowania na zakup, ale można ją zmienić na poziomie wierszy.  
8. Wybierz przyczynę.
9. W polu **Szczegóły** wprowadź bardziej opisowe uzasadnienie dla zapotrzebowania.

## <a name="add-a-line-to-the-requisition"></a>Dodawanie wiersza do zapotrzebowania
1. Wybierz **Dodaj wiersz**. Istnieją dwa sposoby dodawania wierszy do zapotrzebowania na zakup. Jeśli znasz już numer produktu lub wiesz, że prosić o produkt, który nie znajduje się w katalogu produktów, można dodać wiersz bezpośrednio za pomocą opcji **Dodaj wiersz**. Drugi sposób to użycie opcji **Dodaj produkty**, gdzie można użyć funkcji wyszukiwania i filtrowania w celu znalezienia towarów w katalogu produktów.    
2. Wybierz utworzony właśnie wiersz.
    - Zleceniodawcą jest pracownik, który zgłosił zapotrzebowanie.   
    - Domyślnie osobą przygotowującą zapotrzebowanie jest pracownik, który je złożył. Musisz otrzymać pozwolenie na przygotowanie wiersza zapotrzebowania w imieniu innego pracownika. Jeśli masz takie pozwolenie, drugi pracownik będzie widoczny w tym wyszukiwaniu.  
3. W polu **Numer towaru** wpisz wartość. Towary dostępne do wyboru są ograniczone przez zasady dostępu do kategorii oraz przez katalog zaopatrzenia ustawiony dla firmy dokonującej zakupu.   
4. W polu **Ilość** wpisz liczbę.

## <a name="add-more-products-to-the-requisition"></a>Dodawanie kolejnych produktów do zapotrzebowania
1. Wybierz pozycję **Dodaj produkty**. Jest to opcja, która umożliwia wyszukiwanie produktów w katalogu produktów.    
2. W polu **Znajdź węzeł kategorii zaopatrzenia** wpisz pierwszą częścią nazwy kategorii, której szukasz, a następnie wybierz przycisk **Wprowadź**. Na przykład wpisz `comput`.  
3. Użyj skrótu **InvokeDefaultButton**.
4. Użyj opcji **Filtr**, aby wyfiltrować listę produktów w wybranej kategorii.
5. Zaznacz kartę produktu, który ma zostać dodany do zapotrzebowania.
6. Wybierz pozycję **Dodaj do wierszy**.
7. W polu **Ilość** wpisz liczbę.
8. W polu **Znajdź węzeł kategorii zaopatrzenia** wpisz pierwszą częścią nazwy kategorii, której szukasz, a następnie wybierz przycisk **Wprowadź**. Na przykład wpisz `High` (wyróżnione).  
9. Użyj skrótu **InvokeDefaultButton**.
10. Wybierz pozycję **Dodaj niewymieniony na liście produkt do wierszy**, aby dodać produkt, który nie znajduje się w katalogu zaopatrzenia.
11. W polu **Nazwa produktu** wpisz wartość.
12. W polu **Jednostka** wpisz wartość.
13. Kliknij przycisk **OK**.
14. W polu **Opis towaru** wprowadź opis produktu.
15. W polu **Ilość** wpisz liczbę.
16. W polu **Cena jednostkowa** wpisz liczbę. Jeśli znasz cenę określonego dostawcy (wybranego w polu Konto dostawcy), można wprowadzić cenę.   
17. W polu **Konto dostawcy** otwórz listę rozwijaną, aby wybrać opcję. Dostępność dostawców w tym polu zależy od zasad zakupów oraz od stanu dostawcy w bieżącej kategorii zaopatrzenia. Zamiast wybierać dostawcę w tym polu, można wybrać **Sugeruj dostawców**.    
18. Na liście zaznacz dostawcę, z którego chcesz skorzystać.
19. W polu **Zewnętrzny kod towaru** wpisz wartość. Jest to numer referencyjny produktu znany przez dostawcę. Na przykład może to być numer produktu z własnego katalogu dostawcy.  
20. Kliknij przycisk **OK**.

## <a name="distribute-amounts"></a>Dystrybuuj kwoty
1. Wybierz pozycję **Finanse**.
2. Wybierz pozycję **Dystrybuuj kwoty**. Ten proces pokazuje sposób rozdziału kosztów dla pierwszego wiersza między 2 konta. Można to również zrobić później, gdy zapotrzebowanie jest w weryfikacji.  
3. Wybierz pozycję **Podziel**, aby utworzyć nowy wiersz dystrybucji.
4. W polu **Konto księgowe** zaznacz pierwsze centrum kosztów, które ma przejąć część kosztu.
5. Zaznacz drugi wiersz dystrybucji.
6. W polu Konto księgowe określ drugie centrum kosztów.
7. Wybierz **Podziel równo**.
8. Zamknij stronę.

## <a name="view-line-details"></a>Wyświetl szczegóły wiersza
1. Przełącz rozwinięcie sekcji **Szczegóły wiersza**.

## <a name="submit-the-requisition"></a>Przesyłanie zapotrzebowania
1. Wybierz opcję **Przepływ pracy**, aby otworzyć rozwijane okno dialogowe.
2. Wybierz opcję **Prześlij**.
3. Zamknij stronę.
4. W polu **Komentarz** wpisz uwagi do osoby zatwierdzającej zapotrzebowanie.
5. Wybierz opcję **Prześlij**.
6. Zamknij stronę.
7. Odśwież stronę.

