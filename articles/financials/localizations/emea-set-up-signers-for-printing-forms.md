---
title: Konfigurowanie osób podpisujących drukowane formularze
description: Dla firm w Czechach, Estonii, na Węgrzech, Litwie, Łotwie, w Polsce i Rosji można skonfigurować osoby podpisujące oraz tytuły dla odbiorców i dostawców, którzy drukują dokumenty, takie jak faktury i zamówienia gotówkowe.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 263464
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b26ec55f8ee5fe43e7f6cd6d42c78f0c0a49114f
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852378"
---
# <a name="set-up-signers-for-print-forms"></a>Konfigurowanie osób podpisujących drukowane formularze

[!include [banner](../includes/banner.md)]

Dla firm w Czechach, Estonii, na Węgrzech, Litwie, Łotwie, w Polsce i Rosji można skonfigurować osoby podpisujące oraz tytuły dla odbiorców i dostawców, którzy drukują dokumenty, takie jak faktury i zamówienia gotówkowe.

<a name="set-up-default-values"></a>Konfigurowanie wartości domyślnych
---------------------

Aby skonfigurować osoby podpisujące dokumenty drukowane przez firmę, należy użyć strony **Dane urzędowe**. Można skonfigurować osoby podpisujące i ich tytuły zarówno dla firmy, jak i dla odbiorców lub dostawców, w zależności od typu dokumentu. W poniższej tabeli opisano karty znajdujące się na stronie **Dane urzędowe**.

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
<td>Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących (dyrektor i główny księgowy), które mogą podpisywać drukowane dokumenty wszystkich typów.</td>
</tr>
<tr class="even">
<td>Księga</td>
<td>Dodawanie stanowiska i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące wewnętrzne dokumenty finansowe związane z przepływem środków pieniężnych:
<ul>
<li>Dokumenty kasowe</li>
<li>Raport zaliczek</li>
<li>Strona księgi kasowej</li>
<li>Wyciąg kasowy zliczania</li>
<li>Odroczenia<em></li>
</ul></td>
</tr>
<tr class="odd">
<td>Zamówienia sprzedaży</td>
<td>Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące główne dokumenty wychodzące związane z odbiorcami:
<ul>
<li>Faktura do zapłaty</em></li>
<li>Faktura VAT</li>
<li>Dokument faktury<em></li>
<li>Faktura — faktura korygująca</li>
<li>Dokument faktury — faktura korygująca</em></li>
<li>Dokument faktury transakcji podatku (klient)<em></li>
</ul></td>
</tr>
<tr class="even">
<td>Zamówienia zakupu</td>
<td>Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące główne dokumenty przychodzące związane z dostawcami:
<ul>
<li>Faktura VAT</li>
<li>Dokument faktury</em></li>
<li>Faktura — faktura korygująca</li>
<li>Dokument faktury — faktura korygująca<em></li>
<li>Faktura do zapłaty</em></li>
<li>Dokument faktury transakcji podatku (dostawca)<em></li>
</ul></td>
</tr>
<tr class="odd">
<td>Zarządzanie pozycjami magazynowymi</td>
<td>Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące dokumenty magazynowe, gdy materialne środki trwałe są wydawane do odbiorcy lub przyjmowane od dostawcy:
<ul>
<li>Potwierdzenie wystawienia zamówienia sprzedaży (M-15)</em></li>
<li>Dokument KP/Zamówienie przyjęcia</li>
<li>Potwierdzenie wydania towarów dla zamówienia przeniesienia (M-15)*</li>
</ul></td>
</tr>
</tbody>
</table>

\* Ten typ dokumentu jest dostępny tylko w firmach, których adresem podstawowym jest Rosja. W poniższej tabeli opisano pola znajdujące się na stronie **Dane urzędowe**.

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
<td>Wybór tytułu stanowiska osoby podpisującej.</td>
</tr>
<tr class="even">
<td>Nazwisko</td>
<td>Wybór imienia i nazwiska osoby podpisującej. Imiona i nazwiska na liście pochodzą z tabeli Kontakty lub tabeli Pracownicy, w zależności od typu osoby podpisującej (tzn. w zależności od tego, czy jest zaznaczone pole wyboru <strong>Nasz</strong>). Jeśli imienia i nazwiska osoby podpisującej nie ma na liście, należy ręcznie wprowadzić tę informację.</td>
</tr>
<tr class="odd">
<td>Nazwa funkcji</td>
<td>Wybór stanowiska osoby podpisującej. Jeśli stanowiska osoby podpisującej nie ma na liście, należy ręcznie wprowadzić tę informację.</td>
</tr>
<tr class="even">
<td>Kod konta</td>
<td>Określanie, czy osoba podpisująca może podpisywać wszystkie dokumenty wybranego typu, czy tylko dokumenty dotyczące określonego odbiorcy lub dostawcy.</td>
</tr>
<tr class="odd">
<td>Relacja konta</td>
<td>Wybór konta odbiorcy lub dostawcy związanego z kodem wybranego konta. To pole to jest dostępne tylko w przypadku, gdy w polu <strong>Kod konta</strong> zaznaczysz wartość <strong>Rekord</strong>.</td>
</tr>
<tr class="even">
<td>Nasz</td>
<td>Zaznaczone pole wyboru wskazuje, że stanowisko jest wewnętrzne.</td>
</tr>
<tr class="odd">
<td>Powiązanie z magazynem</td>
<td>Określanie, czy osoba podpisująca jest przypisana do wszystkich magazynów, czy tylko do określonego magazynu. Dostępne są następujące opcje:
<ul>
<li><strong>Wszystko</strong> — osoba podpisująca jest przypisana do wszystkich magazynów.</li>
<li><strong>Rekord</strong> — osoba podpisująca jest przypisana do określonego magazynu.</li>
</ul></td>
</tr>
<tr class="even">
<td>Magazyn</td>
<td>Wybór kodu magazynu odpowiadającego magazynowi, do którego jest przypisana osoba podpisująca. To pole to jest dostępne tylko w przypadku, gdy w polu <strong>Powiązanie z magazynem</strong> zaznaczysz wartość <strong>Rekord</strong>.</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-number-sequence-code-for-officials"></a>Konfigurowanie kodu numeracji danych urzędowych
Danym urzędowym można przypisać kod numeracji. Służy do tego sekcja **Sekwencje identyfikatorów** na stronie **Firmy**. Wybierz kod numeracji dla odwołania **Dane urzędowe — identyfikator sesji**.

## <a name="modify-signers-in-primary-documents"></a>Modyfikowanie osób podpisujących w głównych dokumentach
Funkcjonalność danych urzędowych pokazuje domyślne predefiniowane osoby podpisujące z tabeli Dane urzędowe. Na stronie **Księgowanie faktury** na karcie **Dane urzędowe** można modyfikować imiona i nazwiska oraz tytuły osób podpisujących główne dokumenty następujących typów:

-   Faktura dla odbiorcy
-   Faktura dostawcy
-   Wyślij zamówienie przeniesienia
-   Zamówienie gotówkowe

**Uwaga:** Po zaksięgowaniu dokumentu danych urzędowych nie można edytować.



