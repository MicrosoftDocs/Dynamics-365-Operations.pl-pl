---
title: "Organizowanie pracowników za pomocą działów, funkcji i stanowisk"
description: "Działy, zadania i stanowiska to elementy organizacyjne zarządzane w module Zasoby ludzkie. W tym temacie opisano koncepcję tych elementów."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent, Retail
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: b2a79c42b67621272af8107661202ea2ce092193
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a>Organizowanie pracowników za pomocą działów, funkcji i stanowisk

[!include [banner](includes/banner.md)]


Działy, zadania i stanowiska to elementy organizacyjne zarządzane w module Zasoby ludzkie. W tym temacie opisano koncepcję tych elementów. 

Poniższy przykład ilustruje koncepcje opisane w tym temacie.

|**Dział**|**Stanowisko**|**Zadanie**|
|---|---|---|
|**Sprzedaż**|Menedżer ds. sprzedaży (Wschód)|Menedżer ds. sprzedaży|
|**Sprzedaż**|Menedżer ds. sprzedaży (Zachód)|Menedżer ds. sprzedaży|
|**Sprzedaż**|Menedżer ds. sprzedaży (Centrala)|Menedżer ds. sprzedaży|
|**Księgowość**|Kierownik ds. księgowania|Menedżer ds. księgowania|
|**Księgowość**|Księgowanie-A|Księgowy|
|**Kadry**|Menedżer ds. HR (Wschód)|Menedżer ds. HR|
|**Kadry**|Menedżer ds. HR (Zachód)|Menedżer ds. HR|
|**Kadry**|Menedżer ds. HR (Centrala)|Menedżer ds. HR|


 <a name="departments"></a>Działy
------------

Dział jest jednostką operacyjną, która reprezentuje kategorię lub obszar funkcjonalny organizacji, który odpowiada za określony obszar organizacji, np. sprzedaż lub księgowość. Dział jest używany w raportach dla obszarów funkcjonalnych i może mieć obowiązek raportowania zysków i strat. Ponadto dział może zawierać grupę centrów kosztów. Sprzedaż, księgowość i zasoby ludzkie to wybrane przykłady działów w organizacji.

## <a name="jobs-and-positions"></a> Stanowiska i pozycje
Stanowisko to zbiór zadań i odpowiedzialności, które są wymagane od osoby, która wykonuje zadanie. Pozycja jest pojedynczym wystąpieniem zadania. Zakresy odpowiedzialności, obowiązki, funkcje stanowisk, umiejętności, informacje o wykształceniu i certyfikaty, które są wymagane dla stanowisk, które są skojarzone z zadaniem.
### <a name="job-tasks"></a>Zadania zlecenia

Można tworzyć zadania opisujące podstawowe zadania, które pracownik zajmujący stanowisko obejmujące to zadanie musi wykonać. To samo zadanie można dodać do wielu stanowisk, i pozycje dla tego zadania będą je dziedziczyć. Niektóre przykłady znajdują się w poniższej tabeli.

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
<li><span class="input">Perf-review</span> — przeglądanie wydajności poszczególnych sprzedawców.</li>
<li><span class="input">Abs-review</span> — zatwierdzanie lub odrzucanie wniosków urlopowych lub rejestracji nieobecności.</li>
</ul></td>
</tr>
<tr class="even">
<td>Księgowy</td>
<td><span class="input">FIN-Report</span> — przeglądanie tygodniowych raportów finansowych dla dyrektora finansowego.</td>
</tr>
</tbody>
</table>

### <a name="job-functions"></a>Funkcje stanowisk

Funkcje stanowisk są podobne do zadań. Zadanie opisuj jedno lub więcej zadań, obowiązków i zakresów odpowiedzialności które są przypisane do stanowiska. Funkcje stanowisk mogą być przypisywane do zadań i mogą służyć do ustawiania i wdrażania reguł uprawnień w systemach wynagrodzeń. W poniższej tabeli przedstawiono przykłady funkcji stanowisk.

| Zadanie           | Funkcja stanowiska                                                |
|---------------|-------------------------------------------------------------|
| Menedżer ds. sprzedaży | Mng-people — zarządzanie ludźmi, którzy Ci podlegają.               |
| Księgowy    | FIN-Review — obsługa danych finansowych dla zestawu kont. |

### <a name="job-types"></a>Typy stanowisk

Typy zadań umożliwiają klasyfikowanie podobnych zadań wg kategorii. Funkcje stanowisk mogą być przypisywane do zadań i mogą służyć do ustawiania i wdrażania reguł uprawnień w systemie wynagrodzeń. W poniższej tabeli przedstawiono przykłady funkcji stanowisk. Poniższa lista zawiera kilka przykładów typów zadań:
-   Pełny etat
-   Część etatu
-   Wynagrodzenie
-   Stawka godzinowa

### <a name="areas-of-responsibility"></a>Zakres odpowiedzialności

Zakresy odpowiedzialności pozwalają wskazać role pracy, procesy i produkty, za które byłby odpowiedzialny pracownik na danym stanowisku. Przykładem zakresu odpowiedzialności dla stanowiska „Księgowy” może być „Raporty finansowe dla produktu A”.

<a name="positions"></a>Pozycje
----------

Pozycje są ważnym elementem dla niższego poziomu hierarchii organizacji. Pozycja jest pojedynczym wystąpieniem zadania. Na przykład stanowisko „Menedżer ds. sprzedaży (Wschód)” jest tylko jednym ze stanowisk skojarzonych z zadaniem „Menedżer ds. sprzedaży”. Stanowiska istnieją w działach i są przypisane do pracowników.
### <a name="position-creation-and-maintenance"></a>Tworzenie i obsługa pozycji

-   Można wyświetlić historię zmian związanych z systemem na łatwo dostępnej stronie listy.
-   Można tworzyć kody przyczyn, które użytkownicy mogą wybierać podczas tworzenia i modyfikowania stanowisk.
-   Można tworzyć typy akcji dotyczących pracowników i przypisywać sekwencje numerów do tych akcji.
-   Można ustawić przepływ pracy w taki sposób, by dodawanie pozycji i wprowadzanie zmian wymagało zatwierdzenia.

### <a name="position-duration"></a>Okres ważności stanowiska

Każda pozycja ma okres ważności. Ten okres jest określany jako czas trwania. Na przykład letnie stanowiska mogą mieć czas trwania od 1 maja 2015 r. do 31 sierpnia 2015 r.

### <a name="worker-assignments"></a>Przypisania pracownika

Przypisanie pracownika do pozycji oznacza wypełnienie tej pozycji. Pracowników można przypisać do wielu pozycji, ale jednocześnie do pozycji może być przypisany tylko jeden pracownik.

### <a name="reporting-relationships"></a>Relacje raportowania

Pozycje są ważnymi elementami dla niższego poziomu hierarchii organizacji. W formularzu Pozycje można określać pozycje nadrzędne. Podczas przypisywania pracownika do pozycji podrzędnej względem innej pozycji, tworzy się relację raportowania między pracownikami przypisanymi do tych dwóch miejsc. Na przykład pozycja „Księgowy-A” podlega pozycji „Kierownik rachunkowości”. Kim Akers jest przydzielona do pozycji „Kierownika rachunkowości”, a Sanjay Patel jest przypisany do pozycja „Księgowy-A”. To znaczy, że Sanjay Patel podlega Kim Akers. 

Jeśli organizacja korzysta z hierarchii macierzy lub innej hierarchii niestandardowej, można ustawić typy hierarchii pozycji i dodawać relacje raportowania do pozycji dla każdego konfigurowanego typu hierarchii. Na przykład Lori Penor jest kierownikiem głównym w Adventure Works i jest przypisana do pozycji „Kierownik główny”. Zarządza rozwojem produktu służącego do czyszczenia widżetów. Lori chce, aby księgowy pomagał jej przy finansach podczas opracowywania produktu. W związku z tym prosi Sanjaya Patela, by był jej księgowym. Sanjay podlega bezpośrednio Kim Akers i jednocześnie współpracuje z Lori Penor przy finansowaniu programu do czyszczenia widżetów. 

W poprzednim przykładzie wykonaliśmy następujące zadania w celu skonfigurowania relacji roboczej między Sanjay Patel i Lori Penor:
1.  Utworzyliśmy niestandardowy typ pozycji o nazwie „Widżet”, by stworzyć hierarchię obejmującą pozycje dla osób pracujących przy projekcie programu do czyszczenia widżetów.
2.  Przypisaliśmy pozycję Kierownika głównego jako nadrzędne względem pozycji Księgowego-A w hierarchii Widżet.

Hierarchia pozycji służy do wyświetlania struktury relacji służbowych pozycji. Jeśli masz wiele hierarchii pozycji, można wyświetlić hierarchię dla każdego typu hierarchii w hierarchii pozycji. Można też wyszukiwać pozycje według identyfikatora lub nazwy pracownika, który jest przypisany do pozycji. Hierarchia pozycji jest hierarchią organizacyjną.

## <a name="date-effective-records"></a>Rekordy efektywne dat
Dla niektórych rekordów można określić przyszłe zmiany w rekordzie. Następujące informacje są uzależnione od dat obowiązywania.

<table>
<thead>
<tr class="header">
<th>Rekordy</th>
<th>Informacje uzależnione od daty obowiązywania</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zadania</td>
<td><ul>
<li>Wybrane szczegółowe informacje o zadaniu</li>
<li>Informacje o klasyfikacji zadań</li>
<li>Informacje o wynagrodzeniach</li>
</ul></td>
</tr>
<tr class="even">
<td>Pozycje</td>
<td><ul>
<li>Wybrane szczegółowe informacje o pozycji</li>
<li>Przypisania pracownika</li>
<li>Okresy ważności stanowisk</li>
<li>Hierarchie stanowisk</li>
</ul></td>
</tr>
</tbody>
</table>

Można modyfikować informacje wymienione w poprzedniej tabeli dla pozycji lub zadania i określić datę, kiedy modyfikacja pozycji lub zadania ma zacząć obowiązywać. Na przykład pozycja może być przypisana tylko do jednego pracownika, ale Sanjay Patel, który jest przypisany do stanowiska Księgowy-A, odchodzi za dwa tygodnie. Zastąpi go Joe Healy. Mimo że Sanjay jest nadal przypisany do pozycji, Joe Healy może zostać przypisany do tej samej pozycji w taki sposób, by przypisanie zaczęło obowiązywać dopiero po odejściu Sanjaya z firmy.






