---
title: "Tworzenie działów i dołączanie ich do hierarchii działów"
description: "Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji. Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie. Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych. Działy mogą mieć odpowiedzialność zysków i strat."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HierarchyDesigner, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: 14e0acb2ea16641eecb81bcf23c8b7d778b2b208
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="create-departments-and-include-them-in-the-department-hierarchy"></a>Tworzenie działów i dołączanie ich do hierarchii działów

[!include [banner](includes/banner.md)]

Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji. Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie. Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych. Działy mogą mieć odpowiedzialność zysków i strat.

Dział może zawierać grupę centrów kosztów. Stanowiska mogą być przypisywane do działów. Aby utworzyć dział, kliknij kolejno opcje **Zasoby ludzkie** &gt; **Działy** &gt; **Dział**. W poniższej tabeli przedstawiono dostępne pola.

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

1.  Kliknij kolejno opcje **Zasoby ludzkie** &gt; **Działy** &gt; **Hierarchia działów**.
2.  Kliknij **Edycja**, a następnie wybierz organizację, której powinien podlegać dział.
3.  Kliknij **Wstaw** i wybierz **Dział** na liście.
4.  Z listy działów wybierz dział do dodania do hierarchii.
5.  Zapisz zmiany. Pojawi się komunikat, że utworzono wersję roboczą hierarchii.
6.  Po zakończeniu kliknij przycisk **Opublikuj** w projektancie hierarchii. Można wprowadzić datę wejścia w życie, która wskazuje, kiedy hierarchia powinna zostać opublikowana. Na przykład aby dodać nowy dział na początku następnego roku kalendarzowego, ustaw datę wejścia w życie na 1 stycznia w nowym roku kalendarzowym. Zmiany hierarchii zostaną wprowadzone w tym dniu.

## <a name="steps-for-creating-a-department"></a>Etapy tworzenia działu
Zobacz temat [Definiowanie nowych działów](../fin-and-ops/hr/tasks/define-new-departments.md) zawierający procedurę krok po kroku dotyczącą tworzenia nowego działu. 

