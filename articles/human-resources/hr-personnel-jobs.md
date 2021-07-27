---
title: Konfigurowanie składników funkcji
description: W tym artykule opisano elementy koncepcyjne, które może zawierać zadanie, oraz przykłady wykorzystania tych elementów w organizacji.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle, HcmPersonnelManagementWorkspace, HCMJobFamily
audience: Application User
ms.author: anbichse
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d4e24e64f3fece0807df8fbf4fb206c4588c9332
ms.sourcegitcommit: 43962e6fedaf55aab2f28f53bc38a69d2ff58403
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2021
ms.locfileid: "6333100"
---
# <a name="set-up-the-components-of-a-job"></a>Konfigurowanie składników funkcji

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano elementy koncepcyjne, które może zawierać zadanie, oraz przykłady wykorzystania tych elementów w organizacji. 

Zanim będzie można tworzyć zadania, trzeba skonfigurować pewne informacje referencyjne. Można utworzyć zadanie mające tylko nazwę. Jednak umieszczając dodatkowe informacje, takie jak stanowisko (nazwa stanowiska), podajesz wartości domyślne dla stanowisk przypisanych do zadania. Dodatkowo niektóre wprowadzane informacje mogą służyć do filtrowania systemów wynagrodzeń względem określonych zadań. Jeśli chcesz skonfigurować uprawnienia, których można używać do filtrowania systemów wynagrodzeń względem określonego zadania, należy najpierw skonfigurować funkcje stanowisk i typy zadań, a następnie same zadania. Mając dostępne te wartości domyślne, oszczędzisz czas podczas dodawania stanowisk do zadania. 

Niektóre szczegóły zadania, takie jak stanowisko, typ i funkcja, mają daty obowiązywania. Jeśli utworzysz zadanie dzisiaj, ale te szczegóły dodasz dopiero później, to gdy wyświetlisz zadanie według stanu na dzień utworzenia, nie będziesz widzieć tych informacji. W związku z tym niektóre informacje referencyjne należy utworzyć, jeszcze zanim będą potrzebne. W ten sposób będą one dodawane do nowych zadań podczas ich tworzenia.

## <a name="job-titles"></a>Stanowiska
Przed utworzeniem zadań, należy utworzyć nazwy dla tych stanowisk. Pozycje dziedziczą nazwy stanowisk od stanowisk, z którymi są skojarzone. 

Zarządzanie stanowiskami odbywa się na stronie **Stanowiska**, którą można otworzyć za pomocą funkcji wyszukiwania. Na stronie **Stanowiska** wprowadź stanowiska, których zamierzasz używać do zadań.

## <a name="job-types"></a>Typy posad
Typy zadań umożliwiają grupowanie podobnych zadań w kategorie. Typy zadań nie są wymagane. Jednak jeśli planuje się używanie typów zadań podczas tworzenia reguł uprawnienia do zarządzania wynagrodzeniami, przed utworzeniem zadań należy skonfigurować typy zadań. Przykłady typów zadań to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny. Zarządzanie typami zadań odbywa się na stronie **Typy stanowisk**. Na stronie **Typy stanowisk** wprowadź nazwę i krótki opis typu zadania. W polu **Stan zwolnienia** wybierz jedną z następujących opcji, aby wskazać stan zwolnienia zadania wynikający z Ustawy o standardach uczciwej pracy (FLSA):

-   **Zwolnienie** — zadania są zwolnione z nadgodzin na mocy FLSA.
-   **Niezwolniony** — zadania nie są zwolnione z nadgodzin na mocy FLSA.
-   **Nie ma zastosowania** — ustawa FLSA nie jest stosowana.

## <a name="job-family"></a>Rodzina zadania
Rodzina stanowisk to grupa stanowisk, które wymagają podobnej pracy i wymagają podobnego szkolenia, umiejętności, wiedzy i umiejętności. Rodzinę zadań można połączyć z zadaniem na skróconej karcie  **Klasyfikacja zadań** na stronie **Zadania** oraz na skróconej karcie **Ogólne** dotyczącej **wszystkich stanowisk**. Rodziny stanowisk mogą być szerokie lub specyficzne, w zależności od wymagań firmy i wymagań dotyczących raportowania. Niektóre przykłady szerokiego rodzaju rodziny zadań to **Praca wykwalifikowana** i **Praca niewykwalifikowana**. Przykłady konkretnej rodziny zadań to **Księgowanie**, **Wytwarzanie** i **Sprzedaż**.

Zarządzanie stanowiskami odbywa się na stronie **Rodzina zadań**, którą można otworzyć za pomocą funkcji wyszukiwania. Na stronie **Rodzina zadań** wprowadź unikatową nazwę rodziny i wprowadź szczegółowy opis, który ma być następnie używanie jej na stanowiskach.

## <a name="job-functions"></a>Funkcje posad
Funkcje stanowisk opisują ogólne kategorie funkcjonalne i wiążą z nimi ogólne obowiązki. Funkcje stanowisk nie są wymagane. Funkcje stanowisk mogą być używane razem z typami zadań do filtrowania systemów wynagrodzeń według konkretnych zadań. Funkcje stanowisk i typy zadań można kojarzyć z systemami wynagrodzeń, ustawiając reguły uprawnień na stronie **Reguły uprawnienia**. Następnie do systemu wynagrodzeń można dołączyć zbiór poziomów obowiązujący dla określonej kombinacji typu zadania i funkcji stanowiska określonej w regule uprawnienia. (Te funkcje stosowane są do systemów stałych i zmiennych wynagrodzeń). Jednak jeśli planujesz używać funkcji stanowisk podczas tworzenia reguł uprawnień do zarządzania wynagrodzeniami, przed utworzeniem zadań należy utworzyć funkcje stanowisk. W poniższej tabeli przedstawiono kilka przykładów funkcji stanowisk.

| Zadanie           | Funkcja stanowiska         |
|---------------|----------------------|
| Menedżer ds. sprzedaży | Menedżer średniego szczebla    |
| Księgowy    | Specjaliści        |

Zarządzanie funkcjami stanowisk odbywa się na stronie **Funkcje stanowisk**. Na stronie **Funkcje stanowisk** wprowadź kod identyfikacyjny i krótki opis funkcji stanowiska.

## <a name="compensation"></a>Kompensata
Aby przypisać stały plan wynagrodzeń do pracownika, który ma stanowisko w pracy, musisz ustawić poziomy wynagrodzeń na stanowisku. Poziom kompensacji jest używany, gdy w strukturze kompensacji (siatka kompensacji) ustawione są kwoty minimalna, środkowa i maksymalna. Kiedy tworzony jest plan wynagrodzeń stałych, wybierana jest struktura wynagrodzeń. Struktura wynagrodzeń obejmuje również poziom wynagrodzeń. W przypadku wyboru planu wynagrodzeń stałych dla pracownika, poziomy wynagrodzeń, które są dostępne do wyboru, zależą od stanowiska, z którym związany jest dany pracownik. Aby uzyskać więcej informacji o planach wynagrodzeń, zobacz [Plany wynagrodzeń](hr-compensation-overview.md).

## <a name="job-skills"></a>Stanowisko — kwalifikacje
Umiejętności na tym stanowisku opisują umiejętności wymagane do wykonania stanowiska. Poziom umiejętności musi być skojarzony z każdą kwalifikacją stanowiska. Poziomy umiejętności są definiowane przez użytkownika. Wskazują one poziom wiedzy lub biegłości, który jest wymagany dla danej umiejętności. Na przykład, firmy mogą ustawić poziomy numeryczne, takie jak od 1 do 5, gdzie **1** oznacza początkującego, a **5** oznacza specjalistę. Ewentualnie firmy mogą ustawiać poziomy o takich poziomach etykietach **Początkujący**, **Średniozaawansowany** lub **Ekspert**. Po określeniu poziomu umiejętności można również określić jej ważność. Na przykład, jeśli od księgowego wymaga się dobrej znajomości programu Microsoft Excel, można utworzyć umiejętność o nazwie **Znajomość programu Excel**. Poziom umiejętności można następnie ustawić na **Średniozaawansowany**, a ważność może mieć wartość **Najbardziej**.

Umiejętności dostępne na stanowisku mogą być używane w mapowaniu umiejętności. Mapowanie umiejętności umożliwia porównanie zestawu umiejętności wymaganych na danym stanowisku z umiejętnościami, które są powiązane z danym pracownikiem. Następnie może określić procent dopasowania na podstawie pokrywających się umiejętności. Aby dowiedzieć się więcej o mapowaniu umiejętności, zobacz temat [Konfiguruj kwalifikacje](hr-develop-skills.md). 

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
Zobacz artykuł [Definiowanie nowych zadań](./hr-personnel-define-jobs.md) zawierający procedurę krok po kroku dotyczącą tworzenia nowego zadania. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
