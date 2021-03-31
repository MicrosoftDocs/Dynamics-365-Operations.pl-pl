---
title: Dostawy alternatywne
description: Osoby wypełniające zamówienia sprzedaży mogą za pomocą strony Dostawy alternatywne wykrywać alternatywne opcje realizacji zamówień.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 783307ea5cc764f4a04d069dfd7d614a4f63dd2d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229262"
---
# <a name="delivery-alternatives"></a>Dostawy alternatywne

[!include [banner](../includes/banner.md)]

Osoby wypełniające zamówienia sprzedaży mogą za pomocą strony **Dostawy alternatywne** wykrywać alternatywne opcje realizacji zamówień.

Układ strony **Dostawy alternatywne** umożliwia przegląd wszystkich alternatywnych opcji. Umożliwia również osobom wypełniającym zamówienia szukanie możliwości realizacji poza bieżącą firmą. Teraz można wyświetlać możliwości zarówno międzyfirmowe, jak i u zewnętrznych dostawców. Sortując opcje według dat dostawy, osoby wypełniające zamówienia sprzedaży mogą wyświetlić inteligentną listę alternatywnych możliwości realizacji dostawy. Ponadto parametry pozwalają lepiej zarządzać sugerowanymi dostawami. Ponieważ czas transportu może wpływać na daty dostawy, osoby wypełniające zamówienia sprzedaży mogą sprawdzać różne opcje transportu oferowane przez przewoźników. Dla każdej sugestii są wyświetlane szczegółowe informacje, dlatego osoby wypełniające zamówienia mogą podejmować optymalne decyzje bezpośrednio ze strony **Dostawy alternatywne**.

## <a name="open-the-delivery-alternatives-page"></a>Otwieranie strony Dostawy alternatywne

Stronę **Dostawy alternatywne** można otworzyć z wiersza zamówienia sprzedaży.

1. Wybierz kolejno opcje **Produkty i dostawa \> Dostawy alternatywne**.
1. Wybierz kolejno opcje **Szczegóły wiersza \> Dostawa \> Dostawy alternatywne.**

Inny sposób otwarcia strony **Dostawy alternatywne** to otwarcie obszaru roboczego **Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania**, a następnie wybranie kolejno opcji **Zamówienia i ulubione \> Wiersze opóźnionych zamówień \> Dostawy alternatywne**. **Uwaga**: stronę **Dostawy alternatywne** można otworzyć tylko wtedy, gdy są spełnione oba poniższe warunki:

- Wszystkie wymagane informacje wiersza sprzedaży są wypełnione.
- W polu **Kontrola daty dostawy** ustawiono wartość inną niż **Brak**.

## <a name="delivery-date-control-methods"></a>Metody kontroli daty dostawy

Metoda kontroli daty dostawy określa, jak system ustala daty dostawy, jak są obliczane alternatywne opcje dostawy i które informacje są wyświetlane. Należy zwrócić uwagę, że funkcja kontroli dat dostawy uwzględnia kalendarze. W związku z tym następujące kalendarze mogą mieć wpływ na sugerowaną datę przyjęcia: kalendarz magazynu, kalendarz transportu, kalendarz dostawcy i kalendarz odbiorcy. W poniższej tabeli opisano każdą z metod kontroli daty dostawy.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Metoda</strong></td>
<td><strong>Opis</strong></td>
</tr>
<tr class="even">
<td><strong>None</strong></td>
<td><ul>
<li>Alternatywne opcje dostawy dla wierszy sprzedaży nie są obsługiwane. Ta opcja powoduje wyłączenie funkcji kontroli daty dostawy.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Czas realizacji sprzedaży</strong></td>
<td><ul>
<li>Alternatywne opcje dostawy są obliczane na podstawie wstępnie zdefiniowanego czasu realizacji sprzedaży. Liczba dni transportu jest obliczana na podstawie metody dostawy.</li>
<li>Alternatywne opcje dostawy uwzględniają magazyny, w których istnieją dostępne zapasy, oraz zamówienia popytowe/podażowe.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Dostępność zapasów</strong></td>
<td><ul>
<li>Alternatywne opcje dostawy są obliczane na podstawie logiki dostępności zapasów (ATP). Funkcja bierze pod uwagę bieżącą dostępność i oczekiwaną przyszłą dostępność. Liczba dni transportu jest obliczana na podstawie metody dostawy.</li>
<li>Alternatywne opcje dostawy uwzględniają magazyny, w których istnieją dostępne zapasy, oraz zamówienia popytowe/podażowe.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Dostępność zapasów + Zapas czasu dla rozchodu</strong></td>
<td><ul>
<li>Alternatywne opcje dostawy są obliczane podobnie jak w metodzie ATP, ale dodatkowo jest uwzględniany zapas czasu dla rozchodu.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Możliwe do zrealizowania</strong></td>
<td><ul>
<li>Alternatywne opcje dostawy są obliczane na podstawie logiki ilości możliwej do zrealizowania (CTP). Do określenia dostępności służy rozłożenie MRP. Należy zauważyć, że w metodzie CTP następuje co najmniej kompensowanie dat dostawy o czas realizacji sprzedaży. Liczba dni transportu jest obliczana na podstawie metody dostawy.</li>
<li>Alternatywne opcje dostawy zawierają sugestie dotyczące następujących magazynów:
<ul>
<li>Bieżący magazyn</li>
<li>Magazyn domyślny</li>
<li>Wszystkie magazyny, w których istnieją dostępne zapasy</li>
<li>Wszystkie magazyny, które mają zamówienia podażowe</li>
<li>Wszystkie magazyny, które mają aktywne wersje list składowych (BOM)</li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a>Wyświetlanie informacji o alternatywnych opcjach dostawy

W tej sekcji opisano informacje o alternatywnych opcjach dostawy, które są dostępne na skróconej karcie na stronie **Dostawy alternatywne**.

### <a name="the-product-fasttab"></a>Skrócona karta produktów

Ta skrócona karta zawiera podsumowanie produktu i szczegółów bieżącego wiersza sprzedaży.

### <a name="the-delivery-alternatives-fasttab"></a>Skrócona karta Dostawy alternatywne

Ta skrócona karta zawiera listę alternatywnych opcji dostawy posortowanych według dat przyjęcia. Nad listą można wybrać opcje, na których mają się opierać sugestie. Można również wybrać metodę dostawy, co decyduje o liczbie dni transportu. Dostępne są następujące opcje:

- **Uwzględnij inne warianty produktu** — Ta opcja jest dostępna dla produktów mających warianty produktu. Spowoduje uwzględnienie alternatywnych opcji dostawy dla innych wariantów produktu. Ta opcja jest niedostępna dla metody CTP.
- **Uwzględnij ilość częściową** — Domyślnie są uwzględniane tylko propozycje zaspokajające pełną ilość wiersza sprzedaży. Wybierz tę opcję, aby uwzględniać sugestie, które tylko częściowo zaspokajają wiersz zamówienia. Ta opcja jest przydatna, gdy odbiorca prosi o wcześniejszą datę dostawy i akceptuje dostawę częściową.
- **Uwzględnij późniejsze daty** — Domyślnie są wyświetlane tylko sugestie lepsze (wcześniejsze) niż bieżące daty w wierszu sprzedaży. Wybierz tę opcję, aby uwzględniać późniejsze daty. Ta opcja może być przydatna w sytuacjach, gdy pierwszeństwo mają parametry inne niż data. Na przykład może być preferowany określony dostawca lub magazyn.
- **Metoda dostawy** — Umożliwia wybranie preferowanej metody dostawy w celu optymalizacji czasu i kosztów transportu. Natychmiast zobaczysz wpływ na sugerowane alternatywne opcje dostawy. Dzięki temu można łatwo porównywać alternatywne rozwiązania.
- **Uwzględnij zaopatrzenie** — Po wybraniu kryterium zaopatrzenia sugerowane alternatywne opcje dostawy obejmują opcje pozyskiwania od dostawców zewnętrznych i od innych firm w przedsiębiorstwie (dostawy międzyfirmowe). Opcja **Uwzględnij zaopatrzenie** opcja jest obsługiwana dla metod kontroli dat dostawy Dostępność zapasów i Dostępność zapasów + Zapas czasu dla rozchodu. Propozycje uwzględniają opcje zaopatrzenia od domyślnego i wszystkich zatwierdzonych dostawców wybranego produktu.
- W przypadku dostawców zewnętrznych obliczenie bazuje na czasie realizacji zakupu.
- W zaopatrzeniu międzyfirmowym aparat obliczania bierze pod uwagę ilości dostępne w firmie zaopatrującej, używając funkcji kontrolę daty dostawy w firmie zaopatrującej.
- **Typ dostawy** (odpowiedni dla zaopatrzenia)
  - **Zapasy** — Produkty są wysyłane z magazynu zaopatrującego do oddziału/magazynu określonego w wierszu sprzedaży. Następnie są wysyłane z tego magazynu do odbiorcy.
  - **Dostawa bezpośrednia** — Produkty są wysyłane bezpośrednio z magazynu zaopatrującego do odbiorcy.

### <a name="the-availability-information-fasttab"></a>Skrócona karta Informacje o dostępności

Informacje na tej skróconej karcie dotyczą wybranego wiersza alternatywnych opcji dostawy. Wyświetlane są następujące informacje, w zależności od ustawienia kontroli daty dostawy w wierszu sprzedaży:

- **Czas realizacji sprzedaży**
  - **Dostępne dzisiaj** — Pokazuje obecny stan zapasów fizycznie dostępnych na stanie, zarezerwowanych fizycznie i dostępnych fizycznie.
  - **Parametry** — Pokazuje jednostkę magazynową i czas realizacji sprzedaży.

- **Dostępność zapasów i Dostępność zapasów + Zapas czasu dla rozchodu**
  - **Dostępne dzisiaj** — Pokazuje obecny stan zapasów fizycznie dostępnych na stanie, zarezerwowanych fizycznie i dostępnych fizycznie.
  - **Parametry** — Pokazuje jednostkę magazynową i czas realizacji sprzedaży.
  - **Dostępność w przyszłości** — Pokazuje w sposób graficzny bieżącą i przyszłą dostępność w oddziale i magazynie wybranych w obszarze **Dostawy alternatywne**. Możesz wybierać kolumny wykresu, aby zobaczyć więcej szczegółowych informacji o przyszłej dostępności produktu. Suwak umożliwia wyświetlenie listy odnośnych zamówień popytowych i podażowych w granicach horyzontu czasowego dostępności zapasów.

- **Możliwe do zrealizowania**
  - **Dostępne dzisiaj** — Pokazuje obecny stan zapasów fizycznie dostępnych na stanie, zarezerwowanych fizycznie i dostępnych fizycznie.
  - **Parametry** — Pokazuje jednostkę magazynową i czas realizacji sprzedaży.
  - **Rozłożenie** — Pokazuje rozłożenie podaży w wybranej alternatywnej opcji dostawy. Można użyć przycisku **Ustawienia**, aby zmienić pola i wymiary magazynowe wyświetlane w rozłożeniu.

### <a name="the-impact-of-selected-alternative-fasttab"></a>Skrócona karta Wpływ wybranej alternatywy

Na tej skróconej karcie są eksponowane skutki wybranej alternatywnej opcji dostawy. Wybranie przycisku **OK** spowoduje aktualizację wiersza sprzedaży o wyeksponowane wartości w kolumnach WYBRANE. Należy zwrócić uwagę, że jeśli ilość w wybranej alternatywnej opcji dostawy jest mniejsza niż ilość w wierszu sprzedaży, jest utworzony harmonogram dostaw, a wiersz zamówienia jest dzielony na dwa wiersze: jeden wiersz dla wybranej ilości i jeden wiersz na pozostałej ilości. Można także zaktualizować wiersz handlowy, aby pasował do wierszy harmonogramu i miał wpływ na ceny.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zobowiązanie do zamówienia](delivery-dates-available-promise-calculations.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]