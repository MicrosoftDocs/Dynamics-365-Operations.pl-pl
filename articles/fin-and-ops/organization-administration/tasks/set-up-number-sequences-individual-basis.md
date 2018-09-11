--- 
title: "Konfigurowanie indywidualnych sekwencji identyfikatorów"
description: "Sekwencje numeracji są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które ich wymagają."
author: sericks007
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4e2808e57dc8d137fac892d48e99d7687ff1bf81
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Konfigurowanie indywidualnych sekwencji identyfikatorów

[!include [task guide banner](../../includes/task-guide-banner.md)]

Sekwencje numeracji są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które ich wymagają. Rekord transakcji lub danych głównych, który wymaga identyfikatora, odnosi się do odwołania. Aby można było tworzyć nowe rekordy dla odwołania, należy ustawić sekwencję numerów i skojarzyć je z odwołaniem. Można skonfigurować wszystkie wymagane sekwencje identyfikatorów w tym samym czasie przy użyciu kreatora Ustawienie sekwencji identyfikatorów albo skonfigurować lub zmodyfikować indywidualne sekwencje identyfikatorów za pomocą strony Sekwencje identyfikatorów.

1. Wybierz kolejno opcje Administrowanie organizacją > Sekwencje numerów > Sekwencje numerów.
2. Kliknij sekwencja identyfikatorów.
3. W polu Kod sekwencji numerów wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. Rozwiń sekcję Parametry zakresu.
    * Na skróconej karcie Parametry zakresu wybierz zakres dla sekwencji identyfikatorów i wybierz zakres wartości.     Zakres definiuje, która organizacje używają sekwencji numerów. Ponadto sekwencje identyfikatorów o zakresie innym niż Udostępniono mogą mieć segmenty odpowiadające ich zakresowi. Na przykład sekwencja identyfikatorów z zakresem Firma może zawierać segment firmy. Aby uzyskać więcej informacji na temat zakresów, zobacz temat pomocy „Omówienie sekwencji numerów”.  
6. Rozwiń sekcję Segmenty.
    * Na skróconej karcie Segmenty zdefiniuj format dla sekwencji identyfikatorów, dodając, usuwając i zmieniając kolejność segmentów.  
    * Sekwencje identyfikatorów wszystkich zakresów mogą zawierać segmenty stałe i alfanumeryczne. Segmenty stałe zawierają zestaw znaków alfanumerycznych, które się nie zmieniają. Tego typu segmentu należy używać, aby dodać łącznik lub inne separatory między segmentami sekwencji identyfikatorów. Segmenty alfanumeryczne zawierają kombinację znaków cyfry (#) oraz handlowego i (&). Te znaki reprezentują litery i cyfry, które zwiększają się za każdym razem, gdy jest używany numer z tej sekwencji. Użyj znaku liczbowego (#), aby wskazać numery rosnąco i znaku handlowego „i”, aby wskazać litery rosnąco. Na przykład format #####_2014 pozwala tworzyć sekwencje 00001_2014, 00002_2014 i tak dalej.     Musi istnieć co najmniej jeden segment alfanumeryczny. Segmenty zakresów, takich jak przedsiębiorstwo lub firma, nie są wymagane. Jednak nawet jeśli nie umieścisz segmentów zakresów w formacie, numery dla wybranego odwołania nadal są generowane dla zakresu.  
7. Rozwiń sekcję Odwołania.
    * Na skróconej karcie Odwołania wybierz typ lub rekord dokumentu, dla którego chcesz przypisać tę sekwencję identyfikatorów.     Ten krok jest opcjonalny dla sekwencji, które są zdefiniowane dla wzorów użycia specjalnych zgłoszeń. W tych scenariuszach nowy numer jest generowany przy użyciu wartości kodu sekwencji numerów lub identyfikatora, bez korzystania z odwołania. Przykład specjalnego wzorca użycia zgłoszenia to seria załączników i jest używany dla określonych nazw arkuszy. Jednak nie zaleca się używanie takich wzorców.  
8. Rozwiń sekcję Ogólne.
    * Na skróconej karcie Ogólne określ, czy sekwencja identyfikatorów jest wprowadzana ręcznie oraz ciągła czy nieciągła. Poza tym umożliwia wprowadzenie największych i najmniejszych numerów, które mogą być używane w sekwencji.     Nie zaleca się zmieniać nieciągłej sekwencji numerów na ciągłą sekwencji numerów. Nie będzie to naprawdę ciągła sekwencja numerów. Zmiana ta może też spowodować zduplikowanie naruszeń kluczy w bazie danych. Ponadto ciągłe sekwencje numerów mają największy wpływ na wydajność.   
9. Kliknij przycisk Zapisz.


