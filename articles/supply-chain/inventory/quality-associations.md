---
title: Powiązania jakości
description: W tym artykule opisano sposób używania skojarzeń jakości w systemie Microsoft Dynamics 365 Supply Chain Management do automatycznego generowania zleceń kontroli jakości związanych z procesami sprzedaży, zakupu i produkcji.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e96f301d8dec255e57f0f0fbfa9c8e1a5922ae9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887523"
---
# <a name="quality-associations"></a>Powiązania jakości

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób używania skojarzeń jakości w systemie Microsoft Dynamics 365 Supply Chain Management do automatycznego generowania zleceń kontroli jakości związanych z procesami sprzedaży, zakupu i produkcji.

Powiązanie jakości określa wszystkie poniższe informacje dla generowanego zlecenia kontroli jakości:

- Zdarzenie transakcji
- Zestaw testów, które należy wykonać na towarach
- Akceptowalny poziom jakości (AQL)
- Plan pobierania próbek

Należy określić skojarzenie jakości dla każdego odchylenia w procesie biznesowym, które wymaga automatycznego generowania zlecenia kontroli jakości. Na przykład: zlecenie kontroli jakości może być generowane w procesie biznesowym związanym z zamówieniami zakupu, zleceniami kwarantanny, zamówieniami sprzedaży i zleceniami produkcyjnymi.

## <a name="working-with-quality-associations"></a>Korzystanie ze skojarzeń jakości

Proces biznesowy, który używa skojarzeń jakości może być powiązany z różnymi dokumentami źródłowymi, takimi jak zamówienia zakupu, zamówienia sprzedaży lub zlecenia produkcyjne.

Poszczególne rekordy skojarzenia jakości określają serie testów, akceptowany poziom jakości i plan próbkowania dotyczące generowanych zleceń kontroli jakości. Należy określić rekord skojarzenia jakości dla każdego odchylenia w procesie biznesowym. Na przykład można skonfigurować skojarzenia jakości, które generuje zlecenia kontroli jakości podczas aktualizowania dokumentu przyjęcia produktów. W zależności od konfiguracji planu wykonania, w przypadku otwartego zlecenia kontroli jakości może zostać zablokowany sam proces wyzwalający. Mogą również zostać zablokowane kolejne procesy, takie jak fakturowanie zamówień zakupu.

> [!NOTE]
> Jeśli są otwarte zlecenia kontroli jakości, ilości zapasów są automatycznie blokowane przed wydaniem. W zależności od ustawienia pola **Pełne blokowanie** na stronie **Kontrola wyrywkowa towarów** ilość jest ilością w zleceniu kontroli jakości lub ilością w wierszu dokumentu źródłowego. Aby uzyskać więcej informacji, zobacz temat [Kontrola wyrywkowa towaru zarządzania jakością](quality-item-sampling.md).

W danym procesie biznesowym rekord skojarzenia jakości identyfikuje zdarzenie i warunki, dla których wygenerowano zlecenie kontroli jakości. Warunki mogą być właściwe dla oddziału lub firmy. Zlecenia kontroli jakości, uwzględniające testy destrukcyjne mogą być generowane tylko wtedy, gdy istnieją dostępne zapasy dla zdarzenia.

Aby pracować ze skojarzeniami jakości, przejdź do menu **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Skojarzenia jakości**. Poniższe przykłady pokazują możliwe sposoby określania rekordu skojarzenia jakości dla odchyleń w poszczególnych procesach biznesowych. Dla każdego przykładu poniższa tabela podsumowuje zdarzenia i warunki zdefiniowane przez rekord skojarzenia jakości.

<table>
<thead>
<tr>
<th>Typ odwołania</th>
<th>Typ zdarzenia</th>
<th>Wykonanie</th>
<th>Blokowanie zdarzeń</th>
<th>Odwołanie do dokumentu</th>
</tr>
</thead>
<tbody>
<tr>
<td>Zapasy</td>
<td>Nie dotyczy</td>
<td>Nie dotyczy</td>
<td>Brak</td>
<td>Wszyscy</td>
</tr>
<tr>
<td rowspan="7">Sprzedaż</td>
<td rowspan="4">Proces pobierania został zaplanowany</td>
<td rowspan="4">Przed</td>
<td>Brak</td>
<td rowspan="22">Określony identyfikator, Grupa lub Tylko wszystkie</td>
</tr>
<tr>
<td>Proces pobierania</td>
</tr>
<tr>
<td>Dokument dostawy</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Dokument dostawy</td>
<td rowspan="3">Przed</td>
<td>Brak</td>
</tr>
<tr>
<td>Dokument dostawy</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="15">Zakup</td>
<td rowspan="7">Lista przychodu</td>
<td rowspan="4">Przed</td>
<td>Brak</td>
</tr>
<tr>
<td>Lista przychodu</td>
</tr>
<tr>
<td>Dokument przyjęcia produktów</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Po</td>
<td>Brak</td>
</tr>
<tr>
<td>Dokument przyjęcia produktów</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Rejestracja</td>
<td rowspan="3">Nie dotyczy</td>
<td>Brak</td>
</tr>
<tr>
<td>Dokument przyjęcia produktów</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="5">Dokument przyjęcia produktów</td>
<td rowspan="3">Przed</td>
<td>Brak</td>
</tr>
<tr>
<td>Dokument przyjęcia produktów</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="2">Po</td>
<td>Brak</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="8">Produkcja</td>
<td rowspan="3">Rejestracja</td>
<td rowspan="3">Nie dotyczy</td>
<td>Brak</td>
<td rowspan="12">Wszyscy</td>
</tr>
<tr>
<td>Zgłoszenie wyrobów gotowych</td>
</tr>
<tr>
<td>Zamknij</td>
</tr>
<tr>
<td rowspan="5">Zgłoszenie wyrobów gotowych</td>
<td rowspan="3">Przed</td>
<td>Brak</td>
</tr>
<tr>
<td>Zgłoszenie wyrobów gotowych</td>
</tr>
<tr>
<td>Zamknij</td>
</tr>
<tr>
<td rowspan="2">Po</td>
<td>Brak</td>
</tr>
<tr>
<td>Zamknij</td>
</tr>
<tr>
<td rowspan="4">Kwarantanna</td>
<td rowspan="3">Zgłoszenie wyrobów gotowych</td>
<td rowspan="2">Przed</td>
<td>Zgłoszenie wyrobów gotowych</td>
</tr>
<tr>
<td>Zamknij</td>
</tr>
<tr>
<td>Po</td>
<td>Zamknij</td>
</tr>
<tr>
<td>Zamknij</td>
<td>Przed</td>
<td>Zamknij</td>
</tr>
<tr>
<td rowspan="3">Operacja marszruty</td>
<td rowspan="3">Zgłoszenie wyrobów gotowych</td>
<td rowspan="2">Przed</td>
<td>None</td>
<td rowspan="3">Określony identyfikator, Grupa lub Wszystkie, oraz określony Zasób, Grupa lub Wszystkie</td>
</tr>
<tr>
<td>Zgłoszenie wyrobów gotowych</td>
</tr>
<tr>
<td>Po</td>
<td>None</td>
</tr>
<tr>
<td rowspan="3">Wytwarzanie produktu towarzyszącego</td>
<td>Rejestracja</td>
<td>Nie dotyczy</td>
<td rowspan="3">None</td>
<td rowspan="3">Wszyscy</td>
</tr>
<tr>
<td rowspan="2">Zgłoszenie wyrobów gotowych</td>
<td>Przed</td>
</tr>
<tr>
<td>Po</td>
</tr>
</tbody>
</table>

> [!NOTE]
> Funkcja *Zarządzanie jakością dla procesów magazynowych* dodaje możliwości przetwarzania zlecenia kontroli jakości dla produkcji z polem **Typ zdarzenia** ustawionym jako *Zgłoś jako gotowe*, a polem **Wykonanie** jako *Po* i dla zakupów z polem **Typ zdarzenia** ustawionym jako *Rejestracja*. Aby zapoznać sie ze szczegółami, zobacz [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md).

Poniższa tabela zawiera więcej informacji na temat sposobu generowania zleceń kontroli jakości dla określonych typów procesów.

<div class="tableSection">
<table>
<thead>
<tr>
<th>Typ procesu</th>
<th>Kiedy zlecenia kontroli jakości mogą być generowane automatycznie</th>
<th>Kiedy zlecenia kontroli jakości mogą być generowane, jeśli wymagane są testy destrukcyjne</th>
<th>Informacje o warunku</th>
<th>Informacje generowane ręcznie</th>
</tr>
</thead>
<tbody>
<tr>
<td>Zamówienie zakupu</td>
<td>Przed zaksięgowaniem lub po zaksięgowaniu listy przychodu lub dokumentu przyjęcia produktu dla odebranego materiału</td>
<td>Po odebraniu i zaksięgowaniu dokumentu przyjęcia produktów dla materiału, ponieważ materiał musi być dostępny do testów destrukcyjnych</td>
<td>Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub dostawcą, lub kombinacją tych warunków.</td>
<td>Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zamówienia zakupu, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</td>
</tr>
<tr>
<td>Zlecenie kwarantanny</td>
<td>Przed lub po zgłoszeniu zlecenia kwarantanny jako zakończonego lub gotowego</td>
<td>Nie można generować zleceń kontroli jakości wymagających testów destrukcyjnych. Zakłada się, że funkcja zlecenia kwarantanny obsługuje dyspozycje niszczonego materiału.</td>
<td>Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub dostawcą, lub kombinacją tych warunków.</td>
<td>Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zlecenia kwarantanny, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</td>
</tr>
<tr>
<td>Zamówienie sprzedaży</td>
<td>Przed zaplanowanym procesem pobrania lub aktualizacją dokumentu dostawy dla wysłanych pozycji</td>
<td>Na dowolnym z etapów</td>
<td>Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub odbiorcą, lub kombinacją tych warunków.</td>
<td>Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zamówienia sprzedaży, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</td>
</tr>
<tr>
<td>Zlecenie produkcyjne</td>
<td>Przed zgłoszeniem lub po zgłoszeniu ilości wyrobów gotowych dla zlecenia produkcyjnego</td>
<td>Po zgłoszeniu ilości wyrobów gotowych dla zlecenia produkcyjnego</td>
<td>Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem lub towarem albo kombinacją tych warunków.</td>
<td>Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zlecenia produkcyjnego, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</td>
</tr>
<tr>
<td>Zlecenie produkcyjne, które ma operację marszruty</td>
<td>Przed zakończeniem lub po zakończeniu raportu dla operacji</td>
<td>Po zakończeniu zgłaszania produkcji dla ostatniej operacji</td>
<td>Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub zasobem operacyjnym, lub kombinacją tych warunków.</td>
<td>Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy operacji marszruty, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</td>
</tr>
<tr>
<td>Zapasy</td>
<td>Zlecenie kontroli jakości nie może być generowane automatycznie dla transakcji w arkuszu magazynowym lub dla transakcji zamówienia przeniesienia.</td>
<td></td>
<td></td>
<td>Zlecenie kontroli jakości musi być tworzone ręcznie dla ilości zapasów towaru. Fizyczne dostępne zapasy są wymagane.</td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Przykłady automatycznego generowania zleceń kontroli jakości

### <a name="purchasing"></a>Zakup

Jeśli w obszarze zakupów w polu **Typ zdarzenia** zostanie ustawiona wartość *Przyjęcie produktów*, a w polu **Wykonanie** wartość *Po* na stronie **Powiązania jakości**, otrzymasz następujące wyniki :

- Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na *Tak*, zlecenie kontroli jakości jest generowane dla każdego przyjęcia względem zamówienia zakupu na podstawie przyjętej ilości i ustawień w ramach kontroli wyrywkowej pozycji. Za każdym razem, gdy ilość jest przyjmowana względem zamówienia zakupu, nowe zlecenia kontroli jakości są generowane na podstawie nowo przyjętej ilości.
- Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na *Nie*, zlecenie kontroli jakości jest generowane dla pierwszego przyjęcia względem zamówienia zakupu na podstawie przyjętej ilości. Ponadto co najmniej jedno zlecenie kontroli jakości jest tworzone na podstawie pozostałej ilości, w zależności od wymiarów śledzenia. Zlecenia kontroli jakości nie są generowane dla kolejnych przyjęć względem zamówienia zakupu.

### <a name="production"></a>Produkcyjne

Jeśli w obszarze produkcji w polu **Typ zdarzenia** zostanie ustawiona wartość *Zgłoszenie wyrobów gotowych*, a w polu **Wykonanie** wartość *Po* na stronie **Powiązania jakości**, otrzymasz następujące wyniki :

- Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na *Tak*, zlecenie kontroli jakości jest generowane dla każdej ilości wyrobów gotowych i ustawień w ramach kontroli wyrywkowej pozycji. Za każdym razem, gdy ilość jest zgłaszana jako gotowa względem zlecenia produkcyjnego, nowe zlecenia kontroli jakości są generowane na podstawie nowej ilości zgłoszonej jako gotowa. Ta logika generowania jest spójna z procesem zakupów.
- Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na *Nie*, zlecenie kontroli jakości jest generowane po pierwszym zgłoszeniu ilości jako gotowej na podstawie gotowej ilości. Ponadto co najmniej jedno zlecenie kontroli jakości jest tworzone na podstawie pozostałej ilości, w zależności od wymiarów śledzenia kontroli wyrywkowej pozycji. Zlecenia kontroli jakości nie są generowane dla kolejnych gotowych ilości.

<table>
<thead>
<tr>
<th>Specyfikacja jakości</th>
<th>Dla zaktualizowanej ilości</th>
<th>Dla wymiaru śledzenia</th>
<th>Wynik</th>
</tr>
</thead>
<tbody>
<tr>
<td>Wartość procentowa: 10%</td>
<td>Tak</td>
<td>
<p>Numer partii: Nie</p>
<p>Numer seryjny: Nie</p>
</td>
<td>
<p>Ilość w zamówieniu: 100</p>
<ol>
<li>Zgłaszanie wyrobów gotowych dla 30
<ul>
<li>Zlecenie kontroli jakości 1 dla 3 (10% z 30)</li>
</ul>
</li>
<li>Zgłaszanie wyrobów gotowych dla 70
<ul>
<li>Zlecenie kontroli jakości 2 dla 7 (10% pozostałej ilości zamówienia, w tym przypadku 70)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Stała ilość: 1</td>
<td>Nie</td>
<td>
<p>Numer partii: Nie</p>
<p>Numer seryjny: Nie</p>
</td>
<td>Ilość w zamówieniu: 100
<ol>
<li>Zgłaszanie wyrobów gotowych dla 30
<ul>
<li>Zlecenie kontroli jakości 1 dla 1 (dla pierwszej ilości zgłoszonej jako gotowa, która ma stałą wartość równą 1)</li>
<li>Zlecenie kontroli jakości 2 dla 1 (dla pozostałej ilości, która nadal ma stałą wartość równą 1)</li>
</ul>
</li>
<li>Zgłaszanie wyrobów gotowych dla 10
<ul>
<li>Zlecenia kontroli jakości nie są tworzone.</li>
</ul>
</li>
<li>Zgłaszanie wyrobów gotowych dla 60
<ul>
<li>Zlecenia kontroli jakości nie są tworzone.</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Stała ilość: 1</td>
<td>Tak</td>
<td>
<p>Numer partii: Tak</p>
<p>Numer seryjny: Tak</p>
</td>
<td>
<p>Ilość w zamówieniu: 10</p>
<ol>
<li>Zgłoś jako gotowe dla 3: 1 dla numeru partii b1, numeru seryjnego s1; 1 dla numeru partii b2, numeru seryjnego s2; i 1 dla numeru partii b3, numeru seryjnego s3
<ul>
<li>Zlecenie kontroli jakości 1 dla 1 z numeru partii b1, numeru seryjnego s1</li>
<li>Zlecenie kontroli jakości 2 dla 1 z numeru partii b2, numeru seryjnego s2</li>
<li>Zlecenie kontroli jakości 3 dla 1 z numeru partii b3, numeru seryjnego s3</li>
</ul>
</li>
<li>Zgłoś jako gotowe dla 2: 1 dla numeru partii b4, numeru seryjnego s4; i 1 dla numeru partii b5, numeru seryjnego s5
<ul>
<li>Zlecenie kontroli jakości 4 dla 1 z numeru partii b4, numeru seryjnego s4</li>
<li>Zlecenie kontroli jakości 5 dla 1 z numeru partii b5, numeru seryjnego s5</li>
</ul>
</li>
</ol>
<p><strong>Uwaga:</strong> partii można użyć ponownie.</p>
</td>
</tr>
<tr>
<td>Stała ilość: 2</td>
<td>Nie</td>
<td>
<p>Numer partii: Tak</p>
<p>Numer seryjny: Tak</p>
</td>
<td>
<p>Ilość w zamówieniu: 10</p>
<ol>
<li>Zgłoś jako gotowe dla 4: 1 dla numeru partii b1, numeru seryjnego s1; 1 dla numeru partii b2, numeru seryjnego s2; 1 dla numeru partii b3, numeru seryjnego s3 i 1 dla numeru partii b4, numery seryjnego s4
<ul>
<li>Zlecenie kontroli jakości 1 dla 1 z numeru partii b1, numeru seryjnego s1</li>
<li>Zlecenie kontroli jakości 2 dla 1 z numeru partii b2, numeru seryjnego s2</li>
<li>Zlecenie kontroli jakości 3 dla 1 z numeru partii b3, numeru seryjnego s3</li>
<li>Zlecenie kontroli jakości 4 dla 1 z numeru partii b4, numeru seryjnego s4</li>
</ul>
<ul>
<li>Zlecenie kontroli jakości 5 dla 2 bez odwołania do numeru partii i numeru seryjnego</li>
</ul>
</li>
<li>Zgłoś jako gotowe dla 6: 1 dla numeru partii b5, numeru seryjnego s5; 1 dla numeru partii b6, numeru seryjnego s6; 1 dla numeru partii b7, numeru seryjnego s7; 1 dla numeru partii b8, numeru seryjnego s8; 1 dla numeru partii b9, numeru seryjnego s9; i 1 dla numeru partii b10, numeru seryjnego s10
<ul>
<li>Zlecenia kontroli jakości nie są tworzone.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Procesy zarządzania jakością](quality-management-processes.md)
- [Włączanie zarządzania kontrolą jakości i niezgodnością](enable-quality-management.md)
- [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
