---
title: "Konfigurowanie osoby podpisujące dla drukowania formularzy"
description: "Dla osób prawnych w Republice Czeskiej, Estonii, Węgier, Litwy, Łotwy, Polski i Rosji można skonfigurować osoby podpisujące i tytułów dla odbiorców i dostawców, drukowanych dokumentów, takich jak zamówienia faktur i gotówki."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 263464
ms.assetid: 7213914a-ecb6-4711-99fe-4e11867aaf4d
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 45d2facde1e5502f4a5863863554a486916c26cd
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-signers-for-print-forms"></a>Konfigurowanie osoby podpisujące dla drukowania formularzy

Dla osób prawnych w Republice Czeskiej, Estonii, Węgier, Litwy, Łotwy, Polski i Rosji można skonfigurować osoby podpisujące i tytułów dla odbiorców i dostawców, drukowanych dokumentów, takich jak zamówienia faktur i gotówki.

<a name="set-up-default-values"></a>Konfigurowanie wartości domyślnych
---------------------

Aby skonfigurować osoby podpisujące dla dokumentów, które drukuje firmy, należy użyć **urzędników** strony. Można skonfigurować osoby podpisujące i ich tytuły zarówno dla firmy, jak i dla odbiorców lub dostawców, w zależności od typu dokumentu. W poniższej tabeli opisano karty na **urzędników** strony.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Karta</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ogólne</td>
<td>Dodaj pozycje i informacje dotyczące osoby podpisujące (Dyrektor głównego księgowego i) kto może zarejestrować drukowania dokumentów wszystkich typów.</td>
</tr>
<tr class="even">
<td>Księga</td>
<td>Dodaj pozycję i informacje dotyczące osób podpisujących, które można podpisać następujących wewnętrznych dokumentów finansowych, które są związane z przepływem środków pieniężnych:
<ul>
<li>Dokumenty kasowe</li>
<li>Raport zaliczek</li>
<li>Strona księgi kasowej</li>
<li>Wyciąg kasowy zliczania</li>
<li>Odroczeń *</li>
</ul></td>
</tr>
<tr class="odd">
<td>Zamówienia sprzedaży</td>
<td>Dodaj pozycje i informacje dotyczące osoby podpisujące, którzy mogą podpisywać następujące podstawowe dokumenty wychodzące, związanych z klientami:
<ul>
<li>Faktura dla płatności *</li>
<li>Faktura VAT</li>
<li>Dokument faktury *</li>
<li>Faktura — faktura korygująca</li>
<li>Dokument faktury — kredytu — Uwaga *</li>
<li>Dokument faktury transakcji (klient) podatku *</li>
</ul></td>
</tr>
<tr class="even">
<td>Zamówienia zakupu</td>
<td>Dodaj pozycje i informacje dotyczące osoby podpisujące, którzy mogą podpisywać następujące podstawowe dokumentów przychodzących, które odnoszą się do dostawców:
<ul>
<li>Faktura VAT</li>
<li>Dokument faktury *</li>
<li>Faktura — faktura korygująca</li>
<li>Dokument faktury — kredytu — Uwaga *</li>
<li>Faktura dla płatności *</li>
<li>Dokument faktury transakcji (dostawca) podatku *</li>
</ul></td>
</tr>
<tr class="odd">
<td>Zarządzanie pozycjami magazynowymi</td>
<td>Dodaj pozycje i informacje dotyczące osoby podpisujące, którzy mogą podpisywać następujących dokumentów magazynowych, gdy rzeczowych aktywów trwałych są klientowi lub otrzymania od dostawcy:
<ul>
<li>Potwierdzenie wystawienia zamówienia sprzedaży (m-15) *</li>
<li>RMB. Potwierdzenie dostawy zamówienia</li>
<li>Potwierdzenie wystawienia zamówienia przeniesienia (m-15) *</li>
</ul></td>
</tr>
</tbody>
</table>

\*Ten typ dokumentu jest dostępna tylko dla osób prawnych, które mają ich podstawowy adres w Rosji. W poniższej tabeli opisano pola na **urzędników** strony.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pole</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pozycja</td>
<td>Wybierz tytuł wpisu autora podpisu.</td>
</tr>
<tr class="even">
<td>Nazwisko</td>
<td>Wybierz nazwisko osoby podpisującej. Nazwy na liście pochodzą z tabeli Kontakty lub tabeli Pracownicy w zależności od rodzaju osoby podpisującej (to znaczy, w zależności od tego, czy <strong>naszych</strong> pole wyboru jest zaznaczone). Jeśli nazwa autora podpisu nie ma na liście, należy ręcznie wprowadzić pełną nazwę autora podpisu.</td>
</tr>
<tr class="odd">
<td>Stanowisko</td>
<td>Wybierz stanowisko autora podpisu. Jeśli tytuł podpisującego nie ma na liście, należy ręcznie wprowadzić tytuł podpisującego.</td>
</tr>
<tr class="even">
<td>Kod konta</td>
<td>Określ, czy osoba podpisująca można zarejestrować wszystkie dokumenty typu wybranego dokumentu lub dokumentów tylko dla określonego odbiorcy lub dostawcy.</td>
</tr>
<tr class="odd">
<td>Relacja konta</td>
<td>Wybierz konto odbiorcy lub dostawcy, które jest związane z kodem wybranego konta. To pole jest dostępne tylko po wybraniu <strong>rekordu</strong> w <strong>kod konta</strong> pole.</td>
</tr>
<tr class="even">
<td>Nasz</td>
<td>Zaznaczone pole wyboru wskazuje, że pozycja jest wewnętrzny.</td>
</tr>
<tr class="odd">
<td>Powiązanie z magazynem</td>
<td>Określ, czy osoba podpisująca jest przypisany do wszystkich magazynów lub określonego magazynu. Dostępne są następujące opcje:
<ul>
<li><strong>Wszystkie</strong> — osoba podpisująca jest przypisany do wszystkich magazynów.</li>
<li><strong>Rekord</strong> — osoba podpisująca jest przypisany do określonego magazynu.</li>
</ul></td>
</tr>
<tr class="even">
<td>Magazyn</td>
<td>Wybierz kod magazynu, który odpowiada magazyn, w którym osoba podpisująca jest przypisany do. To pole jest dostępne tylko po wybraniu <strong>rekordu</strong> w <strong>skojarzenie z magazynem</strong> pole.</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-number-sequence-code-for-officials"></a>Ustawienia Kod sekwencji numerów dla urzędników
Można przypisać kod sekwencji numerów dla urzędników w **Number sequences** części **osoby prawne** strony. Wybierz kod sekwencji numerów dla **urzędowe — identyfikator sesji** odwołania.

## <a name="modify-signers-in-primary-documents"></a>Modyfikowanie osoby podpisujące w dokumentach podstawowy
Funkcjonalność urzędników Pokazuje osoby podpisujące domyślne predefiniowane z tabeli urzędników. Na **Księgowanie faktury** strona na **urzędników** kartę, można zmodyfikować nazwę autora podpisu i tytuł w dokumencie podstawowym dla następujących typów dokumentów:

-   Faktura dla odbiorcy
-   Faktura dostawcy
-   Wyślij zamówienie przeniesienia
-   Zamówienie gotówkowe

**Uwaga:** po zaksięgowaniu dokumentu urzędników nie może być edytowany.


