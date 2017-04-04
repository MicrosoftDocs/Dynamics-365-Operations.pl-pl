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
translationtype: Human Translation
ms.sourcegitcommit: 6f4429202efd0506378d681188035c5cc69f56a1
ms.openlocfilehash: 1809a6679685e483694a53b7742d80f02ade2cd5
ms.lasthandoff: 03/31/2017


---

# <a name="compensation-plans"></a>Plany wynagrodzeń

Menedżerowie ds. wynagrodzeń i świadczeń mogą za pomocą modułu Zarządzanie wynagrodzeniami obsługiwać i przetwarzać plany wynagrodzeń o stałej i zmiennej wysokości dla pracowników organizacji.

### <a name="introduction"></a>Wprowadzenie

Zarządzanie wynagrodzeniami służy do kontroli dostaw podstawowego wynagrodzenia i nagrody. Dla pracownika stałe podstawowego wynagrodzenia i podwyżki zasług są kontrolowane za pośrednictwem systemów stałych wynagrodzeń. Płatności motywacyjne, takie jak premie motywacyjne, wypłaty premii, nagrody za wyniki pracy, prawa do nabycia akcji po ustalonej cenie, cesje i nagrody jednorazowe lub okazjonalne są kontrolowane za pomocą systemów wynagrodzeń o zmiennej wysokości. 

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
<li>Akcje można zapewnić, że obliczenie jest stosowane podczas przetwarzania systemów stałych wynagrodzeń.  Na przykład akcje typu kapitałowych porównaj płac pracowników do punktu odniesienia minimalne dla poziomu na pracownika i upewnij się, że pracownik jest płacą co najmniej minimalny.</li>
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
<td>Aby zdefiniować okres, dla którego określono rekompensaty służą częstotliwości wypłat.  Na przykład pomaga częstotliwości płac zrozumieć, jeśli kwota rekompensaty jest określony jako wynagrodzeniu rocznym porównaniu o stawkę godzinową stawka płacy. Częstotliwości wypłat są również używane do ustawiania współczynników konwersji do przeliczania kwot odszkodowania od co miesiąc, co tydzień, co dwa tygodnie i częstotliwości wypłat co godzinę do rocznych częstotliwości wypłat.</td>
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
<td>Siatek wynagrodzeń zawierają strukturze wynagrodzeń.  Siatek wynagrodzeń, można za pomocą jednego lub więcej świadczeń pracowniczych.</td>
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

Każdorazowo, gdy zdarzenie procesu zostanie ponownie uruchomiony, utworzone zdarzenie.  Zdarzeń dotyczących wynagrodzenia zawierają wyniki procesu wynagrodzenia dla każdego pracownika, zawarte w tym zdarzenia procesowego.  Kiedy obliczenia są poprawne, można załadować zdarzenia związanego z wynagrodzeniem na aktualizowanie rekordów wynagrodzenia dla pracowników, których dotyczy zdarzenia procesowego.

## <a name="recommendations"></a> Zalecenia
Po uruchomieniu zdarzenia procesowego może zalecić korekty podwyżki uznaniowej lub kwoty premii pracownika, zgodnie z obliczonymi wytycznymi zdarzenia procesowego. Aby przygotować zalecenia dla pracowników, trzeba włączyć zalecenia podczas konfigurowania systemu wynagrodzeń lub podczas ustawiania zdarzenia procesowego.


