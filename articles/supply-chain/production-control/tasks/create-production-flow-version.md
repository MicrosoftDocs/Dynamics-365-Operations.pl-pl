--- 
title: "Tworzenie nowej wersji przepływu produkcji"
description: "Ta procedura skupia się na tworzeniu nowej wersji przepływu produkcji."
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8903e618a35e66742b5c2ebcb5b6f0da3853fcaf
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---
# <a name="create-a-production-flow-version"></a>Tworzenie nowej wersji przepływu produkcji

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura skupia się na tworzeniu nowej wersji przepływu produkcji. Aby można było wykonać tę procedurę, należy wcześniej zdefiniować parametry produkcji dla produkcji oszczędnej oraz jednostki miary dla czasu klasy. Ponadto należy zdefiniować strumień wartości i grupę produkcji. Aby uzyskać więcej informacji na temat przepływów produkcji i działań w produkcji oszczędnej, zobacz oficjalne dokumenty o produkcji oszczędnej w systemie Microsoft Dynamics AX. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-production-flow"></a>Tworzenie przepływu produkcji
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz jednostkę operacyjnej typu Strumień wartości. Strumień wartości jest jednostką operacyjną, która obejmuje wszystkie działania i przepływy w strumieniu wartości. Na tym etapie jednostkami operacyjnymi są tylko firmy i nie mają one żadnych dodatkowych funkcji.  
7. W polu Grupa produkcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz grupę produkcji dla przepływu produkcji. Grupy produkcji umożliwiają definiowanie materiałów, robocizny i kont PWT dla procesu produkcji. Aby skojarzyć kontekst księgowania z przepływem produkcji, należy wybrać grupę produkcji.  
9. Kliknij przycisk Zapisz.

## <a name="create-a-production-flow-version"></a>Tworzenie nowej wersji przepływu produkcji
1. Kliknij przycisk Dodaj.
2. W polu Data wygaśnięcia wprowadź datę i godzinę.
    * W razie potrzeby określ datę ważności wersji. Można zaktualizować ją w dowolnym momencie, nawet w przypadku wersji aktywnych. Można jej użyć do zaplanowania wycofania wersji.  
3. Kliknij przycisk OK.
4. Na liście oznacz wybrany wiersz.
5. W polu Jednostka wpisz wartość.
6. Rozstrzygnij zmiany w jednostce taktu.
7. W polu Średni czas taktu wpisz liczbę.
    * Określ średni czas taktu wersji. Do celów kontroli taktu wersji przepływu produkcji określ docelowy średni czas taktu. Takt jest definiowany jako ilość w okresie. W opisywanym przykładzie czas taktu wynosi 0,2 godziny na 10 sztuk. Dla czasu pracy 8 godzin odpowiada to dziennej produktywności 400 sztuk.  
8. W polu Ilość na cykl wprowadź liczbę.
    * Zdefiniuj ilości na cykl związaną ze średnim czasem taktu.  
9. Przełącz rozwinięcie sekcji Szczegóły wersji.
10. W polu Minimalny czas taktu wpisz liczbę.
    * Określ minimalny czas taktu. Minimalny czas taktu musi być mniejszy lub równy średniemu czasowi taktu.  
11. W polu Maksymalny czas taktu wpisz liczbę.
    * Maksymalny czas taktu musi być większy lub równy średniemu czasowi taktu.  
12. W polu Okres rzeczywistego czasu cyklu (dni) wpisz liczbę.
    * Wprowadź liczbę dni w polu Okres rzeczywistego czasu cyklu. Okres rzeczywistego czasu cyklu jest liczbą dni agregowania zadań od faktycznej minuty wstecz, aby obliczyć rzeczywisty czas cyklu. Wartość można zmienić w dowolnym momencie i jest ona używana tylko do obliczania rzeczywistych czasów cykli.  
13. Kliknij przycisk Zapisz.


