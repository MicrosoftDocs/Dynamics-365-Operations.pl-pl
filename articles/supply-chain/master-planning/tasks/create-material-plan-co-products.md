--- 
title: "Tworzenie planu materiałów dla produktów towarzyszących"
description: "Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-material-plan-for-co-products"></a>Tworzenie planu materiałów dla produktów towarzyszących

[!include [task guide banner](../../includes/task-guide-banner.md)]

Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.


## <a name="create-requirement-for-a-co-product"></a>Tworzenie zapotrzebowania na produkt towarzyszący
1. Przejdź do domyślnego pulpitu nawigacyjnego.
2. Kliknij opcję Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania.
3. Kliknij przycisk Nowy.
4. Kliknij opcję zamówienie sprzedaży.
5. W polu Konto odbiorcy wpisz wartość.
    * Przykład: US-001  
6. Kliknij przycisk OK.
7. W polu Numer towaru wpisz wartość.
    * Przykład: P6003  
8. Wprowadź liczbę w polu Ilość.
    * Przykład: 50000  
9. Kliknij przycisk Zapisz.

## <a name="create-a-material-plan-for-co-products"></a>Tworzenie planu materiałów dla produktów towarzyszących
1. Kliknij opcję Planowanie główne.
2. W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście kliknij łącze w wybranym wierszu.
    * Przykład: Plan główny  
4. Kliknij przycisk Uruchom.
5. Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.
6. Kliknij przycisk Filtr.
7. Na liście zaznacz wiersz, gdzie Pole = Numer towaru.
8. W polu Kryteria wpisz wartość.
    * Przykład: P6003  
9. Kliknij przycisk OK.
10. Kliknij przycisk OK.
11. Kliknij opcję Zamówienia planowane.
12. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Numer towaru z wartością „6000”.
    * Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.  
13. Na liście oznacz wybrany wiersz.
    * Wybierz dowolny wiersz zwrócony przez filtr.  
14. Na liście kliknij łącze w wybranym wierszu.
15. Rozwiń lub zwiń sekcję Oznaczanie transakcji.
16. Na liście kliknij łącze w wybranym wierszu.
    * Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.  
17. Zamknij stronę.


