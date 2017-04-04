---
title: "Konfigurowanie składników zadania"
description: "W tym temacie opisano elementy koncepcyjne, że zadanie może zawierać oraz przykłady wykorzystania tych elementów w danej organizacji."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: d96b1f01a5cb4370436888deae8fd4835a0dbb80
ms.openlocfilehash: b8143db5b133337603a7f2f46028d91bb81cd947
ms.lasthandoff: 03/31/2017


---

# <a name="setting-up-the-components-of-a-job"></a>Konfigurowanie składników zadania

W tym temacie opisano elementy koncepcyjne, że zadanie może zawierać oraz przykłady wykorzystania tych elementów w danej organizacji. 

Przed utworzeniem zadania, należy zdefiniować niektóre informacje. Można utworzyć zadanie, które ma tylko nazwę. Jednak przy tym dodatkowe informacje, takie jak stanowisko, należy podać wartości domyślne dla pozycji, które są przypisane do stanowiska. Dodatkowo niektóre z informacji wprowadzonych może służyć do filtrowania świadczeń pracowniczych do określonych stanowisk. Jeśli chcesz skonfigurować uprawnienia, które można użyć do filtrowania świadczeń pracowniczych do określonego zadania, należy ustawić typy zadań i stanowisk pracy przed skonfigurować zadania. Mając te dostępne wartości domyślne, można zaoszczędzić czas podczas dodawania pozycji do zadania. 

Niektóre szczegóły zadania, takie jak stanowisko, typu i funkcji, są skuteczne daty. Tworzenie zadania na dziś, ale nie należy dodawać te informacje później, a następnie spójrz zadania do daty utworzenia, szczegóły te nie pojawi się. W związku z tym należy utworzyć niektóre informacje referencyjne przed jej wymaga. W ten sposób można dodać informacje do nowych miejsc pracy podczas ich tworzenia.

## <a name="job-titles"></a>Zajmowane stanowiska
Przed utworzeniem zadań, należy utworzyć nazwy dla tych stanowisk. Pozycje dziedziczą nazwy stanowisk od stanowisk, z którymi są skojarzone. 

Obsługa stanowisk przy użyciu **tytuły** strony, które można otworzyć za pomocą funkcji wyszukiwania. Na wytwarzanie tytuły ** strony, wprowadź tytuły, które zamierzasz używać do zadań.

## <a name="job-types"></a>Typy stanowisk
Typy zadań służy do grupowania podobnych zadań w kategorii. Typy zadań nie są wymagane. Jednak jeśli planuje się używanie typów zadań podczas tworzenia reguł uprawnienia do zarządzania wynagrodzeniami, przed utworzeniem zadań należy skonfigurować typy zadań. Niektóre przykłady typów zadań są pełnym i niepełnym wymiarze lub wynagrodzenia i co godzinę płacą. Obsługa typów zadań za pomocą **kategorie pracy** strony. Na **kategorie pracy** strony, wprowadź nazwę i krótki opis typu zadania. W **zwolnienia** wybierz jedną z następujących opcji, aby wskazać zwolnione stan zadania, których tego typu zadania uczciwej pracy Standards Act (FLSA):

-   **Zwolnione** — zadania są zwolnione z nadgodzin w obszarze FLSA.
-   **Niewyłączone** — zadania nie są zwolnione z nadgodzin w obszarze FLSA.
-   **Nie stosuje się** — FLSA zapotrzebowania nie jest stosowana.

## <a name="job-functions"></a>Funkcje stanowisk
Skrzyżowania zadania opisują wysokiego poziomu kategorie funkcjonalne i odnoszą się wysokiego poziomu ceł. Stanowisk pracy nie są wymagane. Do filtrowania świadczeń pracowniczych do określonych stanowisk, można używać funkcji zadania, wraz z typów zadań. Typy zadań i stanowisk pracy można skojarzyć z pracowniczych poprzez ustawienie zasady kwalifikowania wydatków na **zasady kwalifikowania wydatków** strony. Zestaw poziomów można następnie dołączyć do wynagrodzeń, którego dotyczą określona kombinacja typu zadania i stanowiskiem, zdefiniowanego za pomocą reguły uprawnienia. (Funkcje te dotyczą zarówno systemów stałych wynagrodzeń i systemów wynagrodzeń o zmiennej wysokości.) Jednakże jeśli zamierzasz używać funkcji zadań podczas konfigurowania reguł dotyczących uprawnień do zarządzania rekompensaty, należy skonfigurować stanowisk pracy przed zdefiniowaniem zadań. W poniższej tabeli przedstawiono kilka przykładów funkcji zadań.

| Zadanie           | Funkcja stanowiska      |
|---------------|-------------------|
| Menedżer ds. sprzedaży | Menedżer średniego szczebla |
| Księgowy    | Specjalistów     |

Obsługa funkcji stanowiska za pomocą **funkcji zadań** strony. Na **funkcji zadań** strony, wprowadź kod identyfikacyjny i krótki opis funkcji zadania.

## <a name="job-tasks"></a>Zadania zlecenia
Zadania zadanie opisano podstawowe zadania, które należy wykonać pracownik, który jest w stanie pracy. To samo zadanie zadania mogą być dodawane do wielu zadań i stanowisk dla zadania, używające tych zadań zlecenia. W poniższej tabeli przedstawiono kilka przykładów zadań zlecenia.

<table>
<thead>
<tr class="header">
<th>Zadanie</th>
<th>Zadanie zlecenia</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Menedżer ds. sprzedaży</td>
<td><ul>
<li><strong>Przegląd Perf</strong> — Przegląd wydajności pracy każdego sprzedawcy.</li>
<li><strong>ABS Weryfikacja</strong> — zatwierdzanie lub odrzucanie wniosków urlopowych lub rejestracji każdego sprzedawcy.</li>
</ul></td>
</tr>
<tr class="even">
<td>Księgowy</td>
<td><strong>FIN-Report</strong> – przedstawić tygodniowe raporty finansowe Dyrektor finansowy.</td>
</tr>
</tbody>
</table>

Obsługa zadań pracy przy użyciu **zlecenia zadania** strony. Na **zlecenia zadania** strony, wprowadź nazwę i opis dla zadania zlecenia. W **Uwaga** pola, opcjonalnie można wprowadzić dodatkowe informacje. Notatki mogą być aktualizowane dla określonego zadania bez zmiany notatek, które zostały wprowadzone w tym miejscu.

## <a name="areas-of-responsibility"></a>Zakres odpowiedzialności
Zakres odpowiedzialności umożliwia wskazanie ról pracy, procesów i produktów, które jest odpowiedzialne za pracownika, który jest w stanie pracy. Na przykład w przypadku zadania o nazwie "Księgowy" jednego obszaru odpowiedzialności może być "Finansowe zgłoszenie dotyczące produktu A." Obsługa zakresów odpowiedzialności za pomocą **zakres odpowiedzialności** strony, które można znaleźć za pomocą funkcji wyszukiwania. Na **zakres odpowiedzialności** strony, wprowadź nazwę i opis dla odpowiedzialności. W **Uwaga** pola, opcjonalnie można wprowadzić dodatkowe informacje. Notatki mogą być aktualizowane dla określonego zadania bez zmiany notatek, które zostały wprowadzone w tym miejscu.


