--- 
title: "Definiowanie grup harmonogramów produkcji oszczędnej"
description: "Grupy harmonogramów produkcji oszczędnej tworzy się w celu grupowania i odróżniania produktów w planowaniu w systemie Kanban."
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3e07fa270b47be3527c572dc53ca30a7bcde5ba6
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---
# <a name="define-lean-schedule-groups"></a>Definiowanie grup harmonogramów produkcji oszczędnej

[!include [task guide banner](../../includes/task-guide-banner.md)]

Grupy harmonogramów produkcji oszczędnej tworzy się w celu grupowania i odróżniania produktów w planowaniu w systemie Kanban. Grupowanie jest możliwe jako ogólne skojarzenie dla każdej firmy lub specyficzne dla komórki roboczej. Każda grupa ma przypisany osobny kolor do wizualnej identyfikacji na stronie z listą planowania w systemie Kanban. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="define-lean-scheduling-group"></a>Definiowanie grupy harmonogramów produkcji oszczędnej
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Grupy harmonogramów produkcji oszczędnej.
2. Kliknij przycisk Nowy.
3. W polu Grupa harmonogramów wpisz wartość.
    * Grupa harmonogramów może być zdefiniowana jako grupa globalna lub specyficzna dla komórki roboczej. W tym prostym przykładzie zdefiniujemy grupę globalną, a komórka robocza pozostaje pusta. Ustawienia tej grupy mają zastosowanie do wszystkich komórek roboczych, którym nie przypisano konkretnych grup harmonogramów.  
4. Wybierz kolor z palety kolorów.
    * Kolory służą do wyróżniania zadań na stronie listy harmonogramu Kanban lub tablicy procesów w systemie Kanban.  
5. Na liście oznacz wybrany wiersz.
6. Na liście kliknij łącze w wybranym wierszu.

## <a name="associate-product"></a>Kojarzenie produktu
1. Skojarz określony produkt.
    * Istnieją dwa sposoby kojarzenia produktów do grupami harmonogramów produkcji oszczędnej: jako określonego produktu (Typ relacji towaru = Towar) lub jako część klucza alokacji towaru (Typ relacji towaru = Grupa).    
2. W polu Typ relacji produktu wybierz opcję Towar.
3. W polu Numer towaru wpisz wartość.
4. W polu Wskaźnik produktywności wpisz liczbę.
    * Domyślny wskaźnik produktywności wynosi 1, co oznacza, że powiązane produkty zużywają dokładnie zdolności produkcyjne określone w działaniach procesów przepływów produkcji. Wskaźnik produktywności > 1 określa wyższe, a wskaźnik produktywności < 1 niższe zużycie zasobów. Współczynnik jest używany w obliczeniach kosztów i w obliczaniu zużycia w ramach zadania w systemie Kanban.  

## <a name="associate-item-allocation-key"></a>Kojarzenie klucza alokacji towaru
1. Powiąż klucz alokacji towaru.
    * Dodaj skojarzenie do klucza alokacji towaru przy użyciu typu relacji towaru Grupa.   Należy zauważyć, że w przypadku tego procesu w danych musi być zdefiniowany klucz alokacji prognozy towaru.  
2. W polu Typ relacji produktu wybierz opcję Grupa.
3. W polu Klucz alokacji towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście kliknij łącze w wybranym wierszu.


