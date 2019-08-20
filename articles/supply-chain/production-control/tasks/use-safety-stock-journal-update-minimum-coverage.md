---
title: Używanie arkusza zapasu bezpieczeństwa do aktualizowania minimalnego zapotrzebowania
description: W tej procedurze pokazano sposób obliczania propozycji minimalnego zapotrzebowania na podstawie transakcji historycznych, a następnie aktualizowania zapotrzebowania na pozycje według danych z propozycji.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f3b2916d6d2f24579fd9795c0e0bc548b6c2b747
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835793"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>Używanie arkusza zapasu bezpieczeństwa do aktualizowania minimalnego zapotrzebowania

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób obliczania propozycji minimalnego zapotrzebowania na podstawie transakcji historycznych, a następnie aktualizowania zapotrzebowania na pozycje według danych z propozycji. Można to zrobić za pomocą arkusza zapasu bezpieczeństwa. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF. To zadanie jest przeznaczone dla planisty produkcji i ułatwia mu obsługę minimalnego zapotrzebowania.


## <a name="create-a-new-safety-stock-journal-name"></a>Tworzenie nowego arkusza zapasu bezpieczeństwa
1. Przejdź do okna Nazwy arkuszy zapasu bezpieczeństwa.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz „Materiał”.
4. W polu Opis wpisz „Materiał”.
5. Zamknij stronę.

## <a name="create-a-safety-stock-journal"></a>Tworzenie arkusza zapasu bezpieczeństwa
1. Przejdź do okna Obliczanie zapasu bezpieczeństwa.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wprowadź lub wybierz wartość.
    * Zaznacz nazwę utworzonego arkusza zapasu bezpieczeństwa, na przykład Materiał.  
4. Kliknij opcję Utwórz wiersze.
5. W polu Od dnia wprowadź datę.
    * Ustaw datę „2015-01-02”.  
6. Wprowadź datę w polu Do dnia.
    * Ustaw datę „2015-12-30”.  
7. Kliknij przycisk OK.
    * Spowoduje to utworzenie wierszy dla wymiarów, które mają transakcje magazynowe.  

## <a name="calculate-proposal"></a>Obliczanie propozycji
1. Kliknij opcję Obliczanie propozycji.
2. Zaznacz opcję Użyj średnich rozchodów w czasie realizacji.
3. W polu Mnożnik ustaw wartość „10”.
    * Mnożnik służy do korygowania propozycji. Dane demonstracyjne zawierają tylko kilka transakcji, dlatego należy ustawić współczynnik, aby uzyskać realistyczną propozycję.  
4. Kliknij przycisk OK.
    * Przewiń w dół do towarów M0002 i M0003. Wyświetl kolumnę Obliczona minimalna ilość.   

## <a name="update-minimum-quantity"></a>Aktualizacja ilości minimalnej
1. W polu Nowa ilość minimalna wprowadź liczbę.
    * Zaktualizuj wartość Nowa ilość minimalna, aby była zgodna z wartością w polu Obliczona minimalna ilość. Jeśli obliczona minimalna ilość wynosi zero, można wprowadzić żądaną wartość przyszłą. Na przykład w tym polu można wprowadzić obliczoną ilość minimalną towaru M0002 powiązanego z magazynem 12.  
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Na przykład można wybrać towar M0002 powiązany z magazynem 12.  
3. W polu Nowa ilość minimalna wprowadź liczbę.
    * Zaktualizuj wartość Nowa ilość minimalna, aby była zgodna z wartością w polu Obliczona minimalna ilość. Jeśli obliczona minimalna ilość wynosi zero, można wprowadzić żądaną wartość przyszłą.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Księgowanie nowej ilości minimalnej i sprawdzanie poprawności wyniku
1. Kliknij przycisk Księguj.
2. Kliknij przycisk OK.
3. Kliknij, aby otworzyć łącze znajdujące się w polu Numer towaru.
4. Kliknij, aby otworzyć łącze znajdujące się w polu Numer towaru.
5. W okienku akcji kliknij opcję Plan.
6. Kliknij opcję Zapotrzebowanie na towary.
    * Zwróć uwagę, że pole Ilość minimalna zostało zaktualizowane o nową ilość minimalną z arkusza zapasu bezpieczeństwa.  

