---
title: Konfigurowanie przetwarzania grupy czynności — przykład
description: W tym temacie opisano sposób konfigurowania kryteriów, które określają, jaka praca jest generowana dla magazynu podczas przetwarzania grupy czynności oraz czy grupy czynności są przetwarzane ręcznie czy automatycznie.
author: Mirzaab
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10277c22f5988797dd55a33ef5151d2bc7a4b0be
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831057"
---
# <a name="configure-wave-processing-example"></a>Konfigurowanie przetwarzania grupy czynności — przykład

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób konfigurowania kryteriów, które określają, jaka praca jest generowana dla magazynu podczas przetwarzania grupy czynności oraz czy grupy czynności są przetwarzane ręcznie czy automatycznie. Kryteria można określić, definiując szablony grupy czynności i kwerendy, które dopasowują grupy czynności do zwolnionych wierszy w zamówieniach sprzedaży, zleceniach produkcyjnych i zleceniach Kanban.

## <a name="enable-sample-data"></a>Włącz dane przykładowe

Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe dane demonstracyjne. Należy również wybrać firmę **USMF** przed rozpoczęciem.

## <a name="example-scenario-configure-wave-processing"></a>Przykładowy scenariusz: skonfiguruj przetwarzanie fal

W tym przykładowym scenariuszu przedstawiono wiele różnych ustawień, które wpływają na sposób tworzenia, wypełniania, przetwarzania i zwalniania grup czynności.

1. Przejdź do **okienka nawigacji > Moduły > zarządzanie magazynem > Ustawienia > Grupy czynności > Szablony grupy czynności**.
1. Wybierz pozycję **Nowy**.
1. W polu **Nazwa szablonu grupy czynności** wpisz wartość. Podczas konfigurowania szablonu grupy czynności określasz kolejność, w jakiej szablony będą dopasowywane do zwolnionych wierszy zamówień sprzedaży, zleceń produkcyjnych lub kart Kanban. Podczas zwalniania wiersza do magazynu lub produkcji używa on pierwszego szablonu grupy czynności, którego kryteria spełnia. Zaleca się umieszczanie szablonów z najdokładniejszymi kryteriami u góry listy. Im szersze kryteria, tym łatwiej wiersz może je spełnić, co mogłoby spowodować, że wiersze będą przypisywane do niewłaściwych grup czynności.  
1. W polu **Opis szablonu grupy czynności** wpisz wartość.
1. W polu **Oddział** wprowadź lub wybierz wartość. Jeśli używasz firmy demonstracyjnej USMF, można wybrać oddział 2.  
1. W polu **Magazyn** wprowadź lub wybierz wartość. Jeśli używasz firmy USMF, można wybrać magazyn 24.  
1. W polu **Automatyczne tworzenie grupy czynności** ustaw wartość **Tak**. Wybierz tę opcję, aby automatycznie utworzyć grupę czynności po zwolnieniu do magazynu zamówienia sprzedaży, zlecenia produkcyjnego lub karty kanban.  
1. W opcji **Przetwarza grupę czynności w czasie uwalniania jej do magazynu** zaznacz wartość **Tak**. Wybierz tę opcję, aby automatycznie przetworzyć grupę czynności i utworzyć pracę po zwolnieniu wiersza do magazynu.  
1. W polu **Automatyczne uwolnienie grupy czynności** ustaw wartość **Tak**. Gdy ta opcja jest wybrana, grupy czynności są uwalniane automatycznie. Praca pobierania jest tworzona i udostępniana na urządzeniach przenośnych.  
1. W opcji **Przypisz do otwartych grup czynności** zaznacz wartość **Tak**. Wiersze są przypisywane do grup czynności w oparciu o filtr kwerendy dla szablonu grupy czynności.  
1. W opcji **Automatycznie przetwórz grupę czynności na progu** zaznacz wartość **Tak**. Wybierz tę opcję, aby automatycznie wykonywać grupy czynności po osiągnięciu przez jego wartości progów dla wagi, wysyłki i wierszy określonych w grupie pól **Progi grupy czynności**. Ta opcja jest dostępna wyłącznie po wybraniu opcji **Wysyłka** w polu **Typ szablonu grupy czynności**.  
1. W polu **Automatyczne zwalnianie pracy uzupełniania zapasów** ustaw wartość **Tak**. Wybierz tę opcję, aby tworzyć pracę uzupełnienia opartą na żądaniu, i zwalniać ją automatycznie. Należy dodać do szablonu grupy czynności metodę grupy czynności uzupełnienia i utworzyć szablon uzupełnienia typu **Popyt grupy czynności**.  
1. Przypisz atrybuty grupy czynności za pomocą ustawień w grupie **Wartości domyślne**. Atrybuty grupy czynności pełnią rolę filtrów ograniczających rodzaj towarów, które mogą używać grupy. Na przykład można określić grupę towarów.  
1. Rozwiń sekcję **Metody** i ustaw akcje podejmowane przez szablon grupy czynności. Metody szablonów grup czynności pozwalają sterować kolejnością działań wykonywanych na każdej grupie podczas jej przetwarzania. Na przykład może istnieć metoda uzupełniania zapasów dla grupy czynności. Po dodaniu metody jest ona automatycznie wyświetlana w odpowiednim miejscu w sekwencji etapów. Jeśli w opcji **Automatyczne zwalnianie pracy uzupełniania zapasów** zaznaczysz wartość **Tak**, trzeba dodać tutaj metodę uzupełniania zapasów.  
1. Wybierz opcję **Zapisz**.
1. Zamknij stronę.
1. Wybierz kolejno opcje **Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem**.
1. Rozwiń sekcję **Przetwarzanie grupy czynności**.
1. W polu **Grupa przetwarzania wsadowego grupy czynności** wpisz lub wprowadź wartość.
1. W opcji **Przetwarzaj grupy czynności partiami** zaznacz wartość **Tak**.
1. W polu **Oczekiwanie na blokadę (ms)** wprowadź liczbę. Wprowadź czas w milisekundach, przez który nastąpi krok alokacji zaczeka na zasób systemowy zablokowany przez inny krok alokacji. Po przekroczeniu tego czasu grupa czynności nie jest przetwarzana i zostanie wyświetlony komunikat o błędzie.  
1. Wybierz opcję **Zapisz**.
1. Zamknij stronę.
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Kontrola produkcji > Ustawienia > Parametry kontroli produkcji**.
1. W polu **Zwolnij do magazynu** wybierz opcję.

    W przypadku zamówień sprzedaży i zamówień Kanban zapasy muszą być zarezerwowane przed zwolnieniem zamówienia do magazynu. W przeciwnym razie towary lub wiersze alokacji nie mogą zostać przetworzone w grupie czynności. W przypadku zleceń produkcyjnych można również wybrać opcję **Zezwalaj na częściową rezerwację**. Na przykład jest to przydatne w przypadku materiałów, których produkcję należy uruchomić, a z zakończeniem procesu można poczekać na dostępność dodatkowych materiałów. Jeśli zostanie wybrana ta opcja, należy ręcznie powtórzyć zwolnienia do procesu magazynowego, gdy dodatkowe materiały stają się dostępne.
1. Zamknij stronę.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Tworzenie i przetwarzanie grupy czynności](../wave-processing.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
