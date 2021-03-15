---
title: Konfigurowanie przetwarzania grupy czynności
description: W tym przewodniku opisano sposób konfigurowania kryteriów, które określają, jaka praca jest generowana dla magazynu podczas przetwarzania grupy czynności oraz czy grupy czynności są przetwarzane ręcznie czy automatycznie.
author: ShylaThompson
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e22816b33739141fbcd188d631a07313db415959
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977295"
---
# <a name="configure-wave-processing"></a>Konfigurowanie przetwarzania grupy czynności

[!include [banner](../../includes/banner.md)]

W tym przewodniku opisano sposób konfigurowania kryteriów, które określają, jaka praca jest generowana dla magazynu podczas przetwarzania grupy czynności oraz czy grupy czynności są przetwarzane ręcznie czy automatycznie. Kryteria można określić, definiując szablony grupy czynności i kwerendy, które dopasowują grupy czynności do zwolnionych wierszy w zamówieniach sprzedaży, zleceniach produkcyjnych i zleceniach Kanban. Przetwarzanie grup czynności jest stosowane w magazynach, które używają funkcji modułu Zarządzanie magazynem, a nie tych, które używają funkcji modułu Zarządzanie zapasami. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.

1. Przejdź do **okienka nawigacji > Moduły > zarządzanie magazynem > Ustawienia > Grupy czynności > Szablony grupy czynności**.
2. Kliknij przycisk **Nowy**.
3. W polu **Nazwa szablonu grupy czynności** wpisz wartość. Podczas konfigurowania szablonu grupy czynności określasz kolejność, w jakiej szablony będą dopasowywane do zwolnionych wierszy zamówień sprzedaży, zleceń produkcyjnych lub kart Kanban. Podczas zwalniania wiersza do magazynu lub produkcji używa on pierwszego szablonu grupy czynności, którego kryteria spełnia. Zaleca się umieszczanie szablonów z najdokładniejszymi kryteriami u góry listy. Im szersze kryteria, tym łatwiej wiersz może je spełnić, co mogłoby spowodować, że wiersze będą przypisywane do niewłaściwych grup czynności.  
4. W polu **Opis szablonu grupy czynności** wpisz wartość.
5. W polu **Oddział** wprowadź lub wybierz wartość. Jeśli używasz firmy demonstracyjnej USMF, można wybrać oddział 2.  
6. W polu **Magazyn** wprowadź lub wybierz wartość. Jeśli używasz firmy USMF, można wybrać magazyn 24.  
7. W polu **Automatyczne tworzenie grupy czynności** ustaw wartość **Tak**. Wybierz tę opcję, aby automatycznie utworzyć grupę czynności po zwolnieniu do magazynu zamówienia sprzedaży, zlecenia produkcyjnego lub karty kanban.  
8. W opcji **Przetwarza grupę czynności w czasie uwalniania jej do magazynu** zaznacz wartość **Tak**. Wybierz tę opcję, aby automatycznie przetworzyć grupę czynności i utworzyć pracę po zwolnieniu wiersza do magazynu.  
9. W polu **Automatyczne uwolnienie grupy czynności** ustaw wartość **Tak**. Gdy ta opcja jest wybrana, grupy czynności są uwalniane automatycznie. Praca pobierania jest tworzona i udostępniana na urządzeniach przenośnych.  
10. W opcji **Przypisz do otwartych grup czynności** zaznacz wartość **Tak**. Wiersze są przypisywane do grup czynności w oparciu o filtr kwerendy dla szablonu grupy czynności.  
11. W opcji **Automatycznie przetwórz grupę czynności na progu** zaznacz wartość **Tak**. Wybierz tę opcję, aby automatycznie wykonywać grupy czynności po osiągnięciu przez jego wartości progów dla wagi, wysyłki i wierszy określonych w grupie pól Progi grupy czynności. Ta opcja jest dostępna wyłącznie po wybraniu opcji Wysyłka w polu Typ szablonu grupy czynności.  
12. W polu **Automatyczne zwalnianie pracy uzupełniania zapasów** ustaw wartość **Tak**. Wybierz tę opcję, aby tworzyć pracę uzupełnienia opartą na żądaniu, i zwalniać ją automatycznie. Należy dodać do szablonu grupy czynności metodę grupy czynności uzupełnienia i utworzyć szablon uzupełnienia typu Popyt grupy czynności.  
13. Rozwiń sekcję **Metody**.

    - Metody szablonów grup czynności pozwalają sterować kolejnością działań wykonywanych na każdej grupie podczas jej przetwarzania. Na przykład może istnieć metoda uzupełniania zapasów dla grupy czynności. Po dodaniu metody jest ona automatycznie wyświetlana w odpowiednim miejscu w sekwencji etapów. Jeśli w opcji Automatyczne zwalnianie pracy uzupełniania zapasów zaznaczysz wartość Tak, trzeba dodać tutaj metodę uzupełniania zapasów.  
    - Atrybuty grupy czynności pełnią rolę filtrów ograniczających rodzaj towarów, które mogą używać grupy. Na przykład można określić grupę towarów.  
14. Kliknij przycisk **Zapisz**.
15. Zamknij stronę.
16. Wybierz kolejno opcje **Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem**.
17. Rozwiń sekcję **Przetwarzanie grupy czynności**.
18. W polu **Grupa przetwarzania wsadowego grupy czynności** wpisz lub wprowadź wartość.
19. W opcji **Przetwarzaj grupy czynności partiami** zaznacz wartość **Tak**.
20. W polu **Oczekiwanie na blokadę (ms)** wprowadź liczbę. Wprowadź czas w milisekundach, przez który nastąpi krok alokacji zaczeka na zasób systemowy zablokowany przez inny krok alokacji. Po przekroczeniu tego czasu grupa czynności nie jest przetwarzana i zostanie wyświetlony komunikat o błędzie.  
21. Kliknij przycisk **Zapisz**.
22. Zamknij stronę.
23. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Kontrola produkcji > Ustawienia > Parametry kontroli produkcji**.
24. W polu **Zwolnij do magazynu** wybierz opcję.

W przypadku zamówień sprzedaży i zamówień Kanban zapasy muszą być zarezerwowane przed zwolnieniem zamówienia do magazynu. W przeciwnym razie towary lub wiersze alokacji nie mogą zostać przetworzone w grupie czynności. W przypadku zleceń produkcyjnych można również wybrać opcję Zezwalaj na częściową rezerwację. Na przykład jest to przydatne w przypadku materiałów, których produkcję należy uruchomić, a z zakończeniem procesu można poczekać na dostępność dodatkowych materiałów. Jeśli zostanie wybrana ta opcja, należy ręcznie powtórzyć zwolnienia do procesu magazynowego, gdy dodatkowe materiały stają się dostępne.  
25. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]