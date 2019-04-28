---
title: Konfigurowanie składników funkcji
description: W tym temacie opisano elementy koncepcyjne, które może zawierać zadanie, oraz przykłady wykorzystania tych elementów w organizacji.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.author: anbichse
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent, Retail
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 255a84c59a7041c80eb0a466c038d6f9885c5f63
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2019
ms.locfileid: "858309"
---
# <a name="set-up-the-components-of-a-job"></a>Konfigurowanie składników funkcji

[!include [banner](includes/banner.md)]


W tym temacie opisano elementy koncepcyjne, które może zawierać zadanie, oraz przykłady wykorzystania tych elementów w organizacji. 

Zanim będzie można tworzyć zadania, trzeba skonfigurować pewne informacje referencyjne. Można utworzyć zadanie mające tylko nazwę. Jednak umieszczając dodatkowe informacje, takie jak stanowisko (nazwa stanowiska), podajesz wartości domyślne dla stanowisk przypisanych do zadania. Dodatkowo niektóre wprowadzane informacje mogą służyć do filtrowania systemów wynagrodzeń względem określonych zadań. Jeśli chcesz skonfigurować uprawnienia, których można używać do filtrowania systemów wynagrodzeń względem określonego zadania, należy najpierw skonfigurować funkcje stanowisk i typy zadań, a następnie same zadania. Mając dostępne te wartości domyślne, oszczędzisz czas podczas dodawania stanowisk do zadania. 

Niektóre szczegóły zadania, takie jak stanowisko, typ i funkcja, mają daty obowiązywania. Jeśli utworzysz zadanie dzisiaj, ale te szczegóły dodasz dopiero później, to gdy wyświetlisz zadanie według stanu na dzień utworzenia, nie będziesz widzieć tych informacji. W związku z tym niektóre informacje referencyjne należy utworzyć, jeszcze zanim będą potrzebne. W ten sposób będą one dodawane do nowych zadań podczas ich tworzenia.

## <a name="job-titles"></a>Stanowiska
Przed utworzeniem zadań, należy utworzyć nazwy dla tych stanowisk. Pozycje dziedziczą nazwy stanowisk od stanowisk, z którymi są skojarzone. 

Zarządzanie stanowiskami odbywa się na stronie **Stanowiska**, którą można otworzyć za pomocą funkcji wyszukiwania. Na stronie **Stanowiska** wprowadź stanowiska, których zamierzasz używać do zadań.

## <a name="job-types"></a>Typy stanowisk
Typy zadań umożliwiają grupowanie podobnych zadań w kategorie. Typy zadań nie są wymagane. Jednak jeśli planuje się używanie typów zadań podczas tworzenia reguł uprawnienia do zarządzania wynagrodzeniami, przed utworzeniem zadań należy skonfigurować typy zadań. Przykłady typów zadań to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny. Zarządzanie typami zadań odbywa się na stronie **Typy stanowisk**. Na stronie **Typy stanowisk** wprowadź nazwę i krótki opis typu zadania. W polu **Stan zwolnienia** wybierz jedną z następujących opcji, aby wskazać stan zwolnienia zadania wynikający z Ustawy o standardach uczciwej pracy (FLSA):

-   **Zwolnienie** — zadania są zwolnione z nadgodzin na mocy FLSA.
-   **Niezwolniony** — zadania nie są zwolnione z nadgodzin na mocy FLSA.
-   **Nie ma zastosowania** — ustawa FLSA nie jest stosowana.

## <a name="job-functions"></a>Funkcje stanowisk
Funkcje stanowisk opisują ogólne kategorie funkcjonalne i wiążą z nimi ogólne obowiązki. Funkcje stanowisk nie są wymagane. Funkcje stanowisk mogą być używane razem z typami zadań do filtrowania systemów wynagrodzeń według konkretnych zadań. Funkcje stanowisk i typy zadań można kojarzyć z systemami wynagrodzeń, ustawiając reguły uprawnień na stronie **Reguły uprawnienia**. Następnie do systemu wynagrodzeń można dołączyć zbiór poziomów obowiązujący dla określonej kombinacji typu zadania i funkcji stanowiska określonej w regule uprawnienia. (Te funkcje stosowane są do systemów stałych i zmiennych wynagrodzeń). Jednak jeśli planujesz używać funkcji stanowisk podczas tworzenia reguł uprawnień do zarządzania wynagrodzeniami, przed utworzeniem zadań należy utworzyć funkcje stanowisk. W poniższej tabeli przedstawiono kilka przykładów funkcji stanowisk.

| Zadanie           | Funkcja stanowiska         |
|---------------|----------------------|
| Menedżer ds. sprzedaży | Menedżer średniego szczebla    |
| Księgowy    | Specjaliści        |

Zarządzanie funkcjami stanowisk odbywa się na stronie **Funkcje stanowisk**. Na stronie **Funkcje stanowisk** wprowadź kod identyfikacyjny i krótki opis funkcji stanowiska.

## <a name="job-tasks"></a>Zadania zlecenia
Zadania zlecenia opisują podstawowe zadania, które musi wykonać pracownik zajmujący stanowisko obejmujące to zadanie. To samo zadanie zlecenia można dodać do wielu zadań oraz do stanowisk w zadaniu wykorzystujących to zadanie zlecenia. W poniższej tabeli przedstawiono kilka przykładów zadań zlecenia.

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
<li><strong>Perf-review</strong> — przeglądanie wydajności poszczególnych sprzedawców.</li>
<li><strong>Abs-review</strong> — zatwierdzanie lub odrzucanie wniosków urlopowych lub rejestracji nieobecności.</li>
</ul></td>
</tr>
<tr class="even">
<td>Księgowy</td>
<td><strong>FIN-Report</strong> — przeglądanie tygodniowych raportów finansowych dla dyrektora finansowego.</td>
</tr>
</tbody>
</table>

Zarządzanie zadaniami zlecenia odbywa się na stronie **Zadania zlecenia**. Na stronie **Zadania zlecenia** wprowadź nazwę i opis zadania zlecenia. W polu **Notatka** można opcjonalnie wprowadzić dodatkowe informacje. Notatki mogą być aktualizowane dla określonego zadania bez zmiany notatek wprowadzonych w tym miejscu.

## <a name="areas-of-responsibility"></a>Zakres odpowiedzialności
Zakresy odpowiedzialności pozwalają wskazać pełnione w ramach obowiązków służbowych, procesy i produkty, za które jest odpowiedzialny pracownik zajmujący stanowisko obejmujące to zadanie. Na przykład dla zadania o nazwie „Księgowy” jednym z zakresów odpowiedzialności może być „Raporty finansowe dla produktu A”. Zarządzanie zakresami odpowiedzialności odbywa się na stronie **Zakres odpowiedzialności**, do której można przejść za pomocą funkcji wyszukiwania. Na stronie **Zakres odpowiedzialności** wprowadź nazwę i opis zbioru obowiązków. W polu **Notatka** można opcjonalnie wprowadzić dodatkowe informacje. Notatki mogą być aktualizowane dla określonego zadania bez zmiany notatek wprowadzonych w tym miejscu.

## <a name="steps-for-creating-a-job"></a>Etapy tworzenia zadania
Zobacz temat [Definiowanie nowych zadań](../fin-and-ops/hr/tasks/define-new-jobs.md) zawierający procedurę krok po kroku dotyczącą tworzenia nowego zadania. 
