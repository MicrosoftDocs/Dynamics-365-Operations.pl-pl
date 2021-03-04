---
title: Definiowanie grup harmonogramów produkcji oszczędnej
description: Grupy harmonogramów produkcji oszczędnej tworzy się w celu grupowania i odróżniania produktów w planowaniu w systemie Kanban.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9ad470d81d94a0af1c4c4dc6c5072354cfd96d2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434925"
---
# <a name="define-lean-schedule-groups"></a>Definiowanie grup harmonogramów produkcji oszczędnej

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]