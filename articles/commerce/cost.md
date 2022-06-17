---
title: Konfiguracja kosztów dla funkcji zarządzania zamówieniami rozdzielonymi (DOM)
description: W tym artykule opisano konfigurację kosztów dla funkcji zarządzania zamówieniami rozdzielonymi (DOM) w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9aaff8f627adcd00be174a0b5f7bd398300cfef9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862026"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a>Konfiguracja kosztów dla funkcji zarządzania zamówieniami rozdzielonymi (DOM)

[!include [banner](../includes/banner.md)]

Organizacje używają wielu składników kosztów w celu ustalenia optymalnej lokalizacji, z której ma zostać zrealizowane zamówienie. Niektóre z tych składników kosztów to koszty wysyłki, koszty obsługi i koszty pakowania. Kombinacja tych kosztów jest obliczana w celu ustalenia lokalizacji realizacji.

Gdy w wyniku pierwszej iteracji zarządzania zamówieniami rozdzielonymi (DOM) w rozwiązaniu Dynamics 365 Commerce byłą wykonywana optymalizacja przypisań zamówień do lokalizacji realizacji, była brana pod uwagę tylko odległość. Mimo że odległość może być skorelowana z kosztami, nie jest tym samym, co koszt. Na przykład wysyłka w ciągu jednej nocy kosztuje więcej niż wysyłka w ciągu trzech lub siedmiu dni na tę samą odległość.

Funkcja konfiguracji kosztów umożliwia sprzedawcom detalicznym definiowanie i konfigurowanie dodatkowych składników kosztów, które będą obliczane i uwzględniane w celu ustalenia optymalnej lokalizacji, z której mają być realizowane wiersze zamówienia.

W przypadku skonfigurowania składników kosztów moduł obliczeniowy DOM używa tylko tych definicji kosztów w celu ustalenia optymalnej lokalizacji realizacji zamówienia. Ten moduł nie traktuje składnika odległości jako kosztu. Jeśli jednak składniki kosztów nie zostaną skonfigurowane, moduł obliczeniowy DOM będzie używał składnika odległości jako kosztu w celu ustalenia optymalnej lokalizacji realizacji zamówienia.

## <a name="set-up-cost-components"></a>Konfigurowanie składników kosztów

W systemie można zdefiniować dwa główne typy składników kosztów: **Wysyłka** i **Inne**.

Oba typy składników kosztów obsługują wiele podstaw obliczania, tak jak pokazano w poniższej tabeli.

<table>
<thead>
<tr>
<th>Typ składnika kosztów</th>
<th>Podstawa obliczania</th>
</tr>
</thead>
<tbody>
<tr>
<td>Wysyłka</td>
<td>
<ul>
<li>Proste</li>
<li>Wielopoziomowe</li>
</ul>
</td>
</tr>
<tr>
<td>Inne</td>
<td>
<ul>
<li>Zamówienie sprzedaży</li>
<li>Wiersz sprzedaży</li>
<li>Lokalizacja</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a>Typ składnika kosztów Wysyłka

W tej sekcji opisano sposób konfigurowania poszczególnych kombinacji typu składnika kosztów **Wysyłka** oraz podstawy obliczania kosztów wysyłki. Wyjaśniono również, w jaki sposób moduł obliczeniowy DOM używa każdej kombinacji.

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a>Typ składnika kosztów = Wysyłka; Podstawa obliczania = Proste

Jeśli jest używana kombinacja typu składnika kosztów **Wysyłka** i podstawa obliczania **Proste**, koszt wysyłki dla metody dostawy jest oparty na ustalonym koszcie lub odległości.

Dla tej kombinacji musisz skonfigurować następujące pola:

- **Współczynnik kosztu** — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.
- **Opis** — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.
- **Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat. Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.
- **Aktywny** — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny. Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.
- **Firma** — umożliwia określenie firmy, dla której jest konfigurowany współczynnik kosztu. Wszystkie wiersze kryteriów obliczania muszą dotyczyć tej samej firmy.
- **Metody dostawy** — umożliwia określenie metod dostawy, dla których jest konfigurowany koszt.
- **Typ obliczania** — umożliwia określenie sposobu obliczania kosztu dla określonej metody dostawy. Obsługiwane są dwa typy obliczania:

    - **Stały** — dla metody dostawy jest używany ustalony koszt. W przypadku wybrania tego typu obliczania w polu **Koszt** należy zdefiniować ustalony koszt.
    - **Na jednostkę odległości** — koszt dla metody dostawy jest obliczany jako iloczyn wartość kosztu określonej w polu **Koszt** i odległości między adresem dostawy a lokalizacjami.

- **Koszt** — umożliwia określenie wartości kosztu używanej w połączeniu z polem **Typ obliczania** w celu obliczenia kosztu dla metody dostawy.

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a>Typ składnika kosztów = Wysyłka; Podstawa obliczania = Wielopoziomowe

Jeśli jest używana kombinacja typu składnika kosztów **Wysyłka** i podstawa obliczania **Wielopoziomowe**, koszt wysyłki dla metody dostawy jest oparty na ustalonym koszcie lub odległości. Jednak w przypadku tej kombinacji odległość jest oparta na wielopoziomowym zakresie odległości.

Dla tej kombinacji musisz skonfigurować następujące pola:

- **Współczynnik kosztu** — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.
- **Opis** — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.
- **Koszt domyślny** — umożliwia określenie kosztu, który ma być używany dla metody dostawy, jeśli odległość między adresem dostawy a lokalizacją nie należy do żadnej wielopoziomowej odległości ustalonej dla metody dostawy.
- **Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat. Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.
- **Aktywny** — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny. Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.
- **Firma** — umożliwia określenie firmy, dla której jest konfigurowany współczynnik kosztu. Wszystkie wiersze kryteriów obliczania muszą dotyczyć tej samej firmy.
- **Metody dostawy** — umożliwia określenie metod dostawy, dla których jest konfigurowany koszt.
- **Typ odległości** — umożliwia określenie, czy definicja odległości wielopoziomowej to odległość lotnicza, czy drogowa.
- **Jednostki odległości** — umożliwia określenie jednostki, w której będzie mierzona odległość wielopoziomowa.
- **Odległość od** — określa zakres początkowy dla odległości wielopoziomowej.
- **Odległość do** — określa zakres końcowy dla odległości wielopoziomowej.
- **Typ obliczania** — umożliwia określenie sposobu obliczania kosztu dla określonej metody dostawy i odległości wielopoziomowej. Obsługiwane są dwa typy obliczania:

    - **Stały** — dla metody dostawy jest używany ustalony koszt. W przypadku wybrania tego typu obliczania w polu **Koszt** należy zdefiniować ustalony koszt.
    - **Na jednostkę odległości** — koszt dla metody dostawy i odległości wielopoziomowej jest obliczany jako iloczyn wartość kosztu określonej w polu **Koszt** i odległości między adresem dostawy a lokalizacjami.

- **Koszt** — umożliwia określenie wartości kosztu używanej w połączeniu z polem **Typ obliczania** w celu obliczenia kosztu dla metody dostawy.

> [!NOTE]
> - Podczas definiowania odległości wielopoziomowych system sprawdza, czy nie brakuje żadnych odległości i czy jakiekolwiek odległości nie nakładają się na siebie.
> - Typ odległości używany dla metody dostawy musi być taki sam dla wszystkich odległości wielopoziomowych.

### <a name="other-cost-component-type"></a>Typ składnika kosztów Inny

W tej sekcji opisano sposób konfigurowania poszczególnych kombinacji typu składnika kosztów **Inny** oraz innego typu koszu dla kosztów niezwiązanych z wysyłką. Wyjaśniono również, w jaki sposób moduł obliczeniowy DOM używa każdej kombinacji.

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a>Typ składnika kosztów = Inny; Inny typ kosztu = Zamówienie sprzedaży

Kombinacja typu składnika kosztów **Inny** oraz innego typu kosztu **Zamówienie sprzedaży** służy do definiowania kosztów niezwiązanych z wysyłką na poziomie zamówienia sprzedaży.

Dla tej kombinacji musisz skonfigurować następujące pola:

- **Współczynnik kosztu** — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.
- **Opis** — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.
- **Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat. Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.
- **Aktywny** — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny. Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.
- **Koszt** — umożliwia określenie wartości kosztu niezwiązanego z wysyłką na poziomie zamówienia sprzedaży.

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a>Typ składnika kosztów = Inny; Inny typ kosztu = Wiersz sprzedaży

Kombinacja typu składnika kosztów **Inny** oraz innego typu kosztu **Wiersz sprzedaży** służy do definiowania kosztów niezwiązanych z wysyłką na poziomie wiersza zamówienia sprzedaży.

Dla tej kombinacji musisz skonfigurować następujące pola:

- **Współczynnik kosztu** — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.
- **Opis** — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.
- **Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat. Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.
- **Aktywny** — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny. Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.
- **Koszt** — umożliwia określenie wartości kosztu niezwiązanego z wysyłką na poziomie wiersza zamówienia sprzedaży.

#### <a name="cost-component-type--other-and-other-cost-type--location"></a>Typ składnika kosztów = Inny; Inny typ kosztu = Lokalizacja

Kombinacja typu składnika kosztów **Inny** oraz innego typu kosztu **Lokalizacja** służy do definiowania kosztów niezwiązanych z wysyłką dla grupy lokalizacji lub pojedynczej lokalizacji.

Dla tej kombinacji musisz skonfigurować następujące pola:

- **Współczynnik kosztu** — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.
- **Opis** — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.
- **Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat. Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.
- **Aktywny** — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny. Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.
- **Grupa realizacji** — umożliwia określenie grupy lokalizacji, dla której jest definiowany koszt niezwiązany z wysyłką.
- **Lokalizacja realizacji** — umożliwia określenie lokalizacji, dla której jest definiowany koszt niezwiązany z wysyłką.

    > [!NOTE]
    > W przypadku kryteriów obliczania opartych na lokalizacji nie możesz określić w tym samym wierszu grupy realizacji i lokalizacji realizacji.

- **Koszt** — umożliwia określenie wartości kosztu dla kosztu niezwiązanego z wysyłką na poziomie grupy realizacji lub lokalizacji realizacji.

> [!IMPORTANT]
> Aby funkcja zarządzania zamówieniami rozdzielonymi mogła uwzględniać te koszty, gdy zostanie uruchomiona, musisz dodać współczynnik kosztu do odpowiedniego profilu realizacji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]