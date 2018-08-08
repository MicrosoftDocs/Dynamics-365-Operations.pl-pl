--- 
title: "Sprawdzanie przepływu i wersji produkcji"
description: "W tej procedurze pokazano sposób tworzenia nowego przepływu produkcji oraz pierwszej wersji dla produkcji oszczędnej."
author: ChristianRytt
manager: AnnBe
ms.date: 02/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7fb52291f15bfe9063b2a9d4a572dcdc44286402
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="validate-a-production-flow-and-version"></a>Sprawdzanie przepływu i wersji produkcji

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia nowego przepływu produkcji oraz pierwszej wersji dla produkcji oszczędnej. Warunki wstępne: Należy wcześniej zdefiniować parametry produkcji dla produkcji oszczędnej oraz jednostki miary dla czasu klasy. Trzeba zdefiniować strumień wartości i grupę produkcji. Przeczytaj oficjalne dokumenty o produkcji oszczędnej, aby zaznajomić się z pojęciami przepływów produkcji i działań. Ta procedura odnosi się do firmy USMF umieszczonej w danych demonstracyjnych. Jednak można też używać innych firm, o ile tylko są skonfigurowane dla produkcji oszczędnej.


## <a name="create-a-production-flow"></a>Tworzenie przepływu produkcji
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście kliknij łącze w wybranym wierszu.
    * Strumień wartości jest jednostką operacyjną, która obejmuje wszystkie działania i przepływy w strumieniu wartości.   Na tym etapie jednostkami operacyjnymi są tylko firmy i nie mają one żadnych dodatkowych funkcji.  
7. W polu Grupa produkcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście kliknij łącze w wybranym wierszu.
    * Grupy produkcji umożliwiają definiowanie materiałów, robocizny i kont PWT dla procesu produkcji. Aby skojarzyć kontekst księgowania z przepływem produkcji, należy wybrać grupę produkcji.  
9. Kliknij przycisk Zapisz.

## <a name="create-a-production-flow-version"></a>Tworzenie nowej wersji przepływu produkcji
1. Kliknij przycisk Dodaj.
2. W polu Data wygaśnięcia wprowadź datę i godzinę.
    * Można zmienić datę ważności wersji w każdym momencie, nawet w przypadku wersji aktywnych. Data ważności może służyć do zaplanowania wycofania wersji.  
3. Kliknij przycisk OK.
4. Na liście oznacz wybrany wiersz.
5. W polu Jednostka wpisz wartość.
6. Wybierz jednostkę taktu.
7. W polu Średni czas taktu wpisz liczbę.
    * Do celów kontroli taktu wersji przepływu produkcji określ docelowy średni czas taktu.   Takt jest definiowany jako ilość w okresie.  W podanym przykładzie czas taktu wynosi 0,2 godziny na 10 sztuk. Dla czasu pracy 8 godzin odpowiada to dziennej produktywności 400 sztuk.  
8. W polu Ilość na cykl wprowadź liczbę.
9. Rozwiń lub zwiń sekcję Szczegóły wersji.
10. W polu Minimalny czas taktu wpisz liczbę.
    * Minimalny czas taktu musi być mniejszy lub równy średniemu czasowi taktu.  
11. W polu Maksymalny czas taktu wpisz liczbę.
    * Maksymalny czas taktu musi być większy lub równy średniemu czasowi taktu.  
12. Wprowadź liczbę dni w polu Okres rzeczywistego czasu cyklu.
    * Okres rzeczywistego czasu cyklu jest liczbą dni agregowania zadań od faktycznej minuty wstecz, aby obliczyć rzeczywisty czas cyklu. Wartość można zmienić w dowolnym momencie i jest ona używana tylko do obliczania rzeczywistych czasów cykli.  
13. Kliknij przycisk Zapisz.


