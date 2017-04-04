---
title: "Tworzenie działu i przypisywanie go do hierarchii działów"
description: "Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji. Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie. Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych. Działy mogą mieć odpowiedzialność zysków i strat."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HierarchyDesigner, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ee51abe108b3bc0aabc764b991222db6d185e532
ms.lasthandoff: 03/31/2017


---

# <a name="create-a-department-and-associate-it-with-the-department-hierarchy"></a>Tworzenie działu i przypisywanie go do hierarchii działów

Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji. Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie. Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych. Działy mogą mieć odpowiedzialność zysków i strat.

Dział może zawierać grupę centrów kosztów. Stanowiska mogą być przypisywane do działów. Aby utworzyć dział, kliknij **zasoby ludzkie**&gt;**departamenty**&gt;**działu**. Poniższa tabela zawiera opis pola, które są dostępne.

| Pole               | Opis                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Imię i nazwisko                | Wprowadź nazwę działu.                                                                                                                                                                                  |
| Numer działu   | Domyślna wartość może być generowana automatycznie, jeśli kod sekwencji identyfikatorów jest przypisany do odwołania **Numer organizacji** na stronie **Sekwencje identyfikatorów**.                                                 |
| Alias         | Wprowadź krótką nazwę lub akronim, aby ułatwić szybkie wyszukiwanie działów.                                                                                                                                            |
| Nota                | Tutaj możesz wprowadzić dodatkowe informacje.                                                                                                                                                                            |
| W hierarchii        | Jeśli pole wyboru jest zaznaczone, to znaczy, że ten dział jest uwzględniony w hierarchii działów. Aby uzyskać informacje o tym, jak dodawać działy do hierarchii działów, zobacz informacje w dalszej części tego artykułu. |
| Kod DUNS         | DUNS to skrót od Data Universal Number System (uniwersalny system numerowania danych). Jest o 9-cyfrowy numer wydawany przez firmę Dun & Bradstreet.                                                                                                     |
| Menedżer             | Wpisz osobę zarządzającą działem.                                                                                                                                                                    |
| Adresy           | Dodaj informacje adresowe dla działu. Na przykład, dodaj adres korespondencyjny budynku, w którym mieści się dział.                                                                          |
| Informacje kontaktowe | Dodaj informacje kontaktowe dla działu. Na przykład, dodaj numer telefonu do stanowiska obsługi w dziale.                                                                                           |

Aby dodać dział do hierarchii działu, wykonaj następujące kroki:

1.  Kliknij **zasoby ludzkie**&gt;**departamenty**&gt;**Hierarchia działów**.
2.  Kliknij **Edycja**, a następnie wybierz organizację, której powinien podlegać dział.
3.  Kliknij **Wstaw** i wybierz **Dział** na liście.
4.  Z listy działów wybierz dział do dodania do hierarchii.
5.  Zapisz zmiany. Pojawi się komunikat, że została utworzona wersja robocza hierarchii.
6.  Gdy będziesz gotowy, kliknij przycisk **Opublikuj** w projektancie hierarchii. Można wprowadzić datę wejścia, która wskazuje, kiedy należy opublikować hierarchii. Na przykład aby dodać nowy dział na początku następnego roku kalendarzowego, ustaw datę wejścia w życie na 1 stycznia w nowym roku kalendarzowym. Zmiany hierarchii zostaną wprowadzone w tym dniu.



