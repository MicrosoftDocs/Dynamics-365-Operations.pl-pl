---
title: "Plany wynagrodzeń"
description: "Menedżerowie ds. wynagrodzeń i świadczeń mogą za pomocą modułu Zarządzanie wynagrodzeniami obsługiwać i przetwarzać plany wynagrodzeń o stałej i zmiennej wysokości dla pracowników organizacji."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: a6db69bcf9a26706174e56136696e970ec54ca8b
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="compensation-plans"></a>Plany wynagrodzeń

[!include[banner](includes/banner.md)]


Menedżerowie ds. wynagrodzeń i świadczeń mogą za pomocą modułu Zarządzanie wynagrodzeniami obsługiwać i przetwarzać plany wynagrodzeń o stałej i zmiennej wysokości dla pracowników organizacji.

### <a name="introduction"></a>Wprowadzenie

Zarządzanie wynagrodzeniami służy do kontrolowania wypłat podstawowego wynagrodzenia i nagród. Stałe podstawowe wynagrodzenie pracownika i podwyżki podstawowego wynagrodzenia są kontrolowane przez plany stałych wynagrodzeń. Płatności motywacyjne, takie jak premie motywacyjne, wypłaty premii, nagrody za wyniki pracy, prawa do nabycia akcji po ustalonej cenie, cesje i nagrody jednorazowe lub okazjonalne są kontrolowane za pomocą systemów wynagrodzeń o zmiennej wysokości. 

Pracownicy mogą być przypisani do jednego lub większej liczby obu typów systemów. Pracownik musi spełnić następujące wymagania, aby kwalifikować się do planu wynagrodzeń:
-   Pracownik musi mieć aktywne przypisanie stanowiska.
-   Pracownik musi spełniać kryteria, które są zdefiniowane przez reguły uprawnienia do systemu wynagrodzeń.

## <a name="compensation-setup"></a>Konfiguracja wynagrodzeń
W poniższej tabeli wymieniono składniki procesu wynagrodzenia, który może być integralną częścią w procesie konfigurowania systemu wynagrodzeń w firmie.

<table>
<thead>
<tr class="header">
<th>Składnik</th>
<th>Więcej informacji...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Akcje związane ze stałym wynagrodzeniem</td>
<td>Akcje dotyczące stałego wynagrodzenia mają dwojaki cel:
<ul>
<li>Akcja można określać rodzaj informacji, które muszą być rejestrowane, gdy wynagrodzenie pracownika zmienia się. Na przykład, można wymagać rejestrowania powodu zmiany, np. promocji lub degradacji.</li>
<li>Akcje mogą także zapewnić, że podczas przetwarzania w systemach stałych wynagrodzeń będą stosowane obliczenia.  Na przykład akcje typu Kapitał własny porównają płace pracowników z minimalnym punktem odniesienia dla poziomu pracownika i zapewnią, że pracownik otrzymuje co najmniej wynagrodzenie minimalne.</li>
</ul></td>
</tr>
<tr class="even">
<td>Poziomy</td>
<td>Poziomy są powiązane z zadaniami i stanowiskami, które są związane z odniesieniami stanowiska. Można utworzyć odrębne poziomy dla następujących trzech typów systemów wynagrodzeń: Kategoria, Pasmo i Krok.</td>
</tr>
<tr class="odd">
<td>Macierz zakresów wykorzystania</td>
<td>Macierz zakresu wykorzystania pomaga przejść pracownikom do punktu kontrolnego ich zadań. Zakresy wykorzystania pozwalają także kontrolować kapitał stawek płacowych w firmie bez uwzględniania wyników osiągniętych przez poszczególnych pracowników bądź całą firmę. Na przykład, gorzej opłacani pracownicy należący do danego zakresu dostają wyższe podwyżki liczone w procentach niż pracownicy z wyższym wynagrodzeniem. W ten sposób można systematycznie kompensować różnice kapitału własnego. Zakres wykorzystania jest obliczany w następujący sposób: (Stała stawka płacy – Wartość minimalna zakresu)/(Wartość maksymalna zakresu – Wartość minimalna zakresu).</td>
</tr>
<tr class="even">
<td>Konfiguracje punktów odniesienia</td>
<td>Konfiguracja punktów odniesienia obejmuje zbiór punktów odniesienia stanowiących zakresy w macierzy. Każdy zakres może być powiązany ze stawką płacy. Na przykład systemy stopniowane często mają punkty odniesienia: minimum, środkowy i maksimum.</td>
</tr>
<tr class="odd">
<td>Macierz wynagrodzeń</td>
<td>Macierz wynagrodzeń jest zbiorem punktów odniesienia i poziomów, które służą do tworzenia struktury wynagrodzeń.</td>
</tr>
<tr class="even">
<td>Struktura wynagrodzeń</td>
<td>Struktura wynagrodzeń jest macierzą, która ma stawki płac skojarzone z punktami odniesienia dla każdego poziomu.</td>
</tr>
<tr class="odd">
<td>Reguły uprawnienia</td>
<td>Reguły uprawnienia służą do identyfikowania pracowników w określonych zadaniach, ich funkcji, typów, działów, związków zawodowych lub lokalizacji objętych określonym systemem wynagrodzeń. Należy utworzyć reguły uprawnienia dla obu systemów wynagrodzeń: zmiennych i stałych, aby zarejestrować pracowników w systemie. Po określeniu reguł uprawnienia dla systemu wynagrodzeń użytkownik może określić zestaw poziomów tego systemu, które powinny być stosowane do zadań objętych systemem.</td>
</tr>
<tr class="even">
<td>Częstotliwości wypłat</td>
<td>Częstotliwości wypłat umożliwiają zdefiniowanie okresu, dla którego określono wynagrodzenie.  Na przykład częstotliwość płac pomoże określić, czy kwota wynagrodzenia została zdefiniowana jako płaca roczna, czy stawka godzinowa. Częstotliwości wypłat są również używane do ustawiania współczynników konwersji w celu konwersji kwot wynagrodzenia z miesięcznych, tygodniowych, dwutygodniowych i godzinowych na roczne.</td>
</tr>
<tr class="odd">
<td>Regiony wynagrodzeń</td>
<td>Region wynagrodzenia można zastosować do określenia wynagrodzenia pracownika na podstawie lokalizacji miejsca pracy.</td>
</tr>
<tr class="even">
<td>Punkt kontrolny</td>
<td>Punkt kontrolny wskazuje idealną stawkę płacową dla wszystkich pracowników, którym przypisano dany poziom wynagrodzeń. W przypadku struktur z kategoriami wynagrodzeń punktami kontrolnymi są zazwyczaj punkty centralne zakresu. Punkty kontrolne są rzadko używane odnośnie do struktur pasmowych systemów wynagrodzeń. Punkt kontrolny stałych wynagrodzeń można określić w formularzu systemów stałych wynagrodzeń.</td>
</tr>
<tr class="odd">
<td>Funkcje stanowisk</td>
<td>Funkcje stanowisk są używane do klasyfikowania i filtrowania systemów wynagrodzeń dla określonych zadań.</td>
</tr>
<tr class="even">
<td>Typy stanowisk</td>
<td>Typy stanowisk są używane do klasyfikowania i filtrowania systemów wynagrodzeń dla określonych zadań.</td>
</tr>
<tr class="odd">
<td>Typy wynagrodzenia o zmiennej wysokości</td>
<td>Typy zmiennych wynagrodzeń, takie jak nagroda w postaci akcji lub premia gotówkowa, są stosowane w zmiennych systemach wynagrodzeń.</td>
</tr>
<tr class="even">
<td>Siatki wynagrodzeń</td>
<td>Siatki wynagrodzeń zawierają strukturę wynagrodzeń.  Siatka wynagrodzeń może być używana w jednym lub kilku systemach wynagrodzeń.</td>
</tr>
<tr class="odd">
<td>Plany wydajności</td>
<td>Plany wydajności można przypisać do macierzy alokacji (w przypadku realizacji strategii związanej z wypłatą wynagrodzeń za wyniki).</td>
</tr>
<tr class="even">
<td>Oceny wydajności</td>
<td>Oceny wydajności są wykorzystywane w planach wydajności do ustalania kwot podwyżek lub wysokości nagród za wydajność.</td>
</tr>
</tbody>
</table>

## <a name="process-events"></a>Zdarzenia procesowe
Zdarzenie procesowe oblicza wysokość wynagrodzenia w danym okresie dla wszystkich pracowników objętych co najmniej jednym stałym lub zmiennym planem wynagrodzeń. Zdarzenie procesu można uruchamiać wielokrotnie, aby na przykład testować lub aktualizować obliczone wyniki wynagrodzeń.

<a name="compensation-events"></a>Wynagrodzenie — zdarzenia
-------------------

Po każdym uruchomieniu procesu jest tworzone zdarzenie dotyczące wynagrodzenia.  Zdarzenie dotyczące wynagrodzenia zawiera wyniki procesu wynagrodzenia dla każdego pracownika uwzględnionego w zdarzeniu tego procesu.  Jeśli obliczenia są poprawne, można załadować zdarzenie związane z wynagrodzeniem w celu aktualizacji rekordów wynagrodzeń dla pracowników, których dotyczą zdarzenia procesu.

## <a name="recommendations"></a> Zalecenia
Po uruchomieniu zdarzenia procesowego może zalecić korekty podwyżki uznaniowej lub kwoty premii pracownika, zgodnie z obliczonymi wytycznymi zdarzenia procesowego. Aby przygotować zalecenia dla pracowników, trzeba włączyć zalecenia podczas konfigurowania systemu wynagrodzeń lub podczas ustawiania zdarzenia procesowego.




