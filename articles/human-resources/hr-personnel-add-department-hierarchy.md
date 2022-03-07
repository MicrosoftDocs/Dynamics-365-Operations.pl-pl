---
title: Tworzenie działów i dołączanie ich do hierarchii działów
description: Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji. Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HierarchyDesigner, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 8571b254a3dcdeaf562a97f165b8124f04ae7e6d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068901"
---
# <a name="create-departments-and-include-them-in-the-department-hierarchy"></a>Tworzenie działów i dołączanie ich do hierarchii działów


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji. Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie. Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych. Działy mogą mieć odpowiedzialność zysków i strat.

Dział może zawierać grupę centrów kosztów. Stanowiska mogą być przypisywane do działów. Aby utworzyć dział, kliknij kolejno opcje **Zasoby ludzkie** &gt; **Działy** &gt; **Dział**. W poniższej tabeli przedstawiono dostępne pola.

| Pole               | Opis                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Imię i nazwisko**                | Wprowadź nazwę działu.                                                                                                                                                                                  |
| **Numer działu**   | Domyślna wartość może być generowana automatycznie, jeśli kod sekwencji identyfikatorów jest przypisany do odwołania **Numer organizacji** na stronie **Sekwencje identyfikatorów**.                                                 |
| **Alias**         | Wprowadź krótką nazwę lub akronim, aby ułatwić szybkie wyszukiwanie działów.                                                                                                                                            |
| **Nota**                | Tutaj możesz wprowadzić dodatkowe informacje.                                                                                                                                                                            |
| **W hierarchii**        | Jeśli pole wyboru jest zaznaczone, to znaczy, że ten dział jest uwzględniony w hierarchii działów. Aby uzyskać informacje o tym, jak dodawać działy do hierarchii działów, zobacz informacje w dalszej części tego artykułu. |
| **Numer w bazie Chemical Abstracts Service (DUNS)**         | DUNS to skrót od Data Universal Number System (uniwersalny system numerowania danych). Jest o 9-cyfrowy numer wydawany przez firmę Dun & Bradstreet.                                                                                                     |
| **Menedżer**             | Wpisz osobę zarządzającą działem.                                                                                                                                                                    |
| **Adresy**           | Dodaj informacje adresowe dla działu. Na przykład, dodaj adres korespondencyjny budynku, w którym mieści się dział.                                                                          |
| **Informacje kontaktowe** | Dodaj informacje kontaktowe dla działu. Na przykład, dodaj numer telefonu do stanowiska obsługi w dziale.                                                                                           |

Aby dodać dział do hierarchii działu, wykonaj następujące kroki:

1.  Kliknij kolejno opcje **Zasoby ludzkie** &gt; **Działy** &gt; **Hierarchia działów**.
2.  Kliknij **Edycja**, a następnie wybierz organizację, której powinien podlegać dział.
3.  Kliknij **Wstaw** i wybierz **Dział** na liście.
4.  Z listy działów wybierz dział do dodania do hierarchii.
5.  Zapisz zmiany. Pojawi się komunikat, że utworzono wersję roboczą hierarchii.
6.  Po zakończeniu kliknij przycisk **Opublikuj** w projektancie hierarchii. Można wprowadzić datę wejścia w życie, która wskazuje, kiedy hierarchia powinna zostać opublikowana. Na przykład aby dodać nowy dział na początku następnego roku kalendarzowego, ustaw datę wejścia w życie na 1 stycznia w nowym roku kalendarzowym. Zmiany hierarchii zostaną wprowadzone w tym dniu.

## <a name="steps-for-creating-a-department"></a>Etapy tworzenia działu
Zobacz artykuł [Definiowanie nowych działów](./hr-personnel-define-departments.md) zawierający procedurę krok po kroku dotyczącą tworzenia nowego działu. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
