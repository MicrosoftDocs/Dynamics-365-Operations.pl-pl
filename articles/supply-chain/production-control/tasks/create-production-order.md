---
title: Tworzenie zlecenia produkcyjnego
description: W tej procedurze pokazano sposób tworzenia zlecenia produkcyjnego.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdTable, ProdBOM, ProdRoute
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 468465e3e82ff608d7d290b71f058cd790a0f013
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564121"
---
# <a name="create-a-production-order"></a>Tworzenie zlecenia produkcyjnego

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia zlecenia produkcyjnego. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Jest to pierwsza z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.


## <a name="create-a-production-order"></a>Tworzenie zlecenia produkcyjnego
1. Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.
2. Kliknij opcję Nowe zlecenie produkcyjne.
3. W polu Numer pozycji wpisz „D0001”.
4. W polu Dostawa wprowadź datę.
    * Data dostawy wskazuje, kiedy zlecenie produkcyjne powinno się zakończyć, aby dostawa nastąpiła w na czas. Ta data może być wykorzystywana w procesie planowania. Na przykład można zaplanować zlecenie z datą wsteczną względem daty dostawy.  
5. W polu Ilość wpisz wartość 20.
    * Uwaga: W polu Numer BOM jest automatycznie wyświetlana liczba wszystkich aktywnych BOM bieżącego towaru, ale można zmienić BOM zlecenia produkcyjnego, wybierając aktywny BOM z listy zatwierdzonych wersji BOM.    W polu Numer marszruty jest automatycznie wyświetlana liczba wszystkich aktywnych marszrut bieżącego towaru, ale można zmienić marszrutę zlecenia produkcyjnego, wybierając aktywną marszrutę z listy zatwierdzonych wersji marszruty.  
6. Kliknij przycisk Utwórz.

## <a name="validate-the-production-order"></a>Weryfikacja zlecenia produkcyjnego
1. Na liście kliknij łącze w wybranym wierszu.
    * Kliknij łącze do numeru nowo utworzonego zlecenia produkcyjnego. Spowoduje to otwarcie strony szczegółów zlecenia.  
2. Kliknij przycisk Edytuj.
3. W polu Dostawa wprowadź datę.
    * Na przykład można zmienić datę dostawy zlecenia produkcyjnego.  
4. Kliknij przycisk Zapisz.
5. Zamknij stronę.

## <a name="update-the-bom"></a>Aktualizacja BOM
1. W okienku akcji kliknij opcję Zlecenie produkcyjne.
2. Kliknij opcję BOM.
    * Otwórz stronę BOM, aby sprawdzić poprawność danych BOM, które zostały skopiowane z domyślnych danych podczas tworzenia zlecenia produkcyjnego. W tej procedurze należy zaktualizować ilość w BOM.  
3. Kliknij przycisk Edytuj.
4. Wprowadź liczbę w polu Ilość.
    * Zmiana ilości w wierszu BOM ma wpływ na szacowane koszty zużycia materiałów dla zlecenia produkcyjnego.  
5. Kliknij przycisk Zapisz.
6. Zamknij stronę.

## <a name="update-the-production-route"></a>Aktualizacja marszruty produkcji
1. W okienku akcji kliknij opcję Zlecenie produkcyjne.
2. Kliknij opcję Marszruta.
    * Otwórz stronę Marszruta, aby sprawdzić poprawność danych marszruty produkcji, które zostały skopiowane z domyślnych danych podczas tworzenia zlecenia. W tej procedurze należy zaktualizować ilość w jednej operacji w marszrucie produkcji.  
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Kliknij przycisk Edytuj.
5. W polu Ilość z procesu wpisz liczbę.
    * Zmiana czasu procesu wpływa na szacowane zużycie w marszrucie i koszt zlecenia produkcyjnego.  
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

