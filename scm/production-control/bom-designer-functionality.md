---
title: Funkcje konstruktora BOM
description: "W tym artykule opisano, jak za pomocą strony projektanta BOM zaprojektować struktury drzewa dla list składowych (BOM) oraz ich używać. Można kliknąć przycisk Ustawienia i wybierać różne konfiguracje oraz określić rodzaj informacji wyświetlanych w wierszach drzewa."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesigner
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 20981
ms.assetid: 2b92eec1-d28c-4965-9086-939c77b3c62b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c871cf4e5ee7f359010aac1fa0fef81e0e0df564
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="bom-designer-functionality"></a>Funkcje konstruktora BOM

[!include[banner](../includes/banner.md)]


W tym artykule opisano, jak za pomocą strony projektanta BOM zaprojektować struktury drzewa dla list składowych (BOM) oraz ich używać. Można kliknąć przycisk Ustawienia i wybierać różne konfiguracje oraz określić rodzaj informacji wyświetlanych w wierszach drzewa.

Po otwarciu strony **Konstruktor BOM** ze strony **Zwolnione produkty** widać na niej hierarchię list składowych (BOM), które były aktywne i zatwierdzone dla wybranego towaru, domyślny oddział zamówienia towaru oraz rzeczywistą datę.  

Kliknij **Filtr**, aby zmienić początkowy wybór w widoku. Ustawiając regułę wyświetlania na **Wybrane/aktywne lub Wybrane**, można wybrać poszczególne wersje BOM lub marszruty, które mają być używane w widoku. Można wybrać niezatwierdzone i nieaktywne wersje BOM, które mają być wyświetlane lub zachowane w konstruktorze BOM.  

**Uwaga:** po otwarciu konstruktora BOM ze strony **Lista składowa (BOM)** informacje o marszrucie nie są wyświetlane. Obecnie wybór wersji BOM lub marszruty jest właściwością wersji BOM i marszruty i ma zastosowanie do wszystkich instancji konstruktora BOM.  

W poniższych sekcjach opisano funkcje dostępne na poszczególnych kartach w konstruktorze BOM.

## <a name="analyzing-a-bom-structure-by-using-the-bom-designer"></a>Analiza struktury BOM przy użyciu konstruktora BOM
Konstruktor BOM ma dwie sekcje:

-   Widok drzewa struktury BOM.
-   Widok szczegółów dla wybranych danych. Po wybraniu węzła w widoku drzewa skrócone karty w sekcji szczegółów są aktualizowane według tego węzła:
    -   **Szczegóły wiersza BOM** — pokazuje szczegóły wiersza BOM, który jest wybrany w widoku drzewa.
    -   **Pozycja danych** — pokazuje szczegóły głównego towaru lub towaru, który jest używany w wybranym węźle. Opcja **Edytuj zwolniony produkt** umożliwia obsługę wybranego towaru.
    -   **BOM** — pokazuje nagłówek BOM, który jest powiązany z wybranego węzła.
    -   **Marszruta** — pokazuje nagłówek marszruty, który jest powiązany z wybranego węzła.
    -   **Operacje marszruty** — pokazuje podgląd operacji dla marszruty. Po wybraniu wiersza BOM, który jest przypisany do konkretnej operacji, operacja ta jest oznaczana jako **Składnik wymagany w operacji**.

## <a name="selecting-a-bom-and-route"></a>Wybranie BOM i marszruty
Filtr stosowany dla BOM i marszruty jest wyświetlany w nagłówku konstruktora BOM. Można zmienić filtr za pomocą okna dialogowego **Filtr**. W poniższej tabeli opisano pola w tym oknie dialogowym.

<table>
<thead>
<tr class="header">
<th>Pole</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Wymiary produktu</td>
<td>Jeśli wybrany gotowy produkt jest produktem głównym, można zdefiniować aktywne wymiary produktu dla zaznaczenia głównego. <strong>Uwaga:</strong> po otwarciu konstruktora BOM dla produktu, który nie jest produktem głównym, w oknie dialogowym <strong>Filtr</strong> nie można wybrać żadnych wymiarów.</td>
</tr>
<tr class="even">
<td>Oddział</td>
<td>Zmienianie oddziału, dla którego wyświetlane jest drzewo BOM. Domyślnie jest to oddział zapasów dla gotowego towaru.</td>
</tr>
<tr class="odd">
<td>Reguła wyświetlania</td>
<td>Wybierz zasadę wyświetlania wersji obowiązującą dla bieżącej struktury BOM i dla bieżącej marszruty.
<ul>
<li>Jeśli ustawiono zasadę <strong> Aktywne lub Wybrane/aktywne</strong>, to zostanie wyszukana wersja BOM i wersja marszruty ważna dla tej daty.</li>
<li>Jeśli ustawiono zasadę <strong>Wybrane/aktywne lub Wybrane</strong>, można wybrać wersję BOM i wersji marszruty, klikając kolejno opcje <strong>BOM</strong> &gt; <strong>Wersje BOM</strong> or <strong>Marszruta</strong> &gt; <strong>Wersje marszruty</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Data wersji</td>
<td>Służy do wprowadzania daty wersji dla BOM i marszruty. Wersja umożliwia wskazanie wersji BOM używanej dla określonego okresu, co wynika z dat wersji w konfiguracji wersji BOM.</td>
</tr>
<tr class="odd">
<td>Ilość od</td>
<td>Filtrowanie wersji przez wybranie określonej ilości „od”. Jeśli zostanie ustawiona wartość, będzie można wybrać różne wersje BOM i marszruty.</td>
</tr>
<tr class="even">
<td>Pokaż tylko ważne</td>
<td>Po zaznaczeniu pola wyboru w strukturze drzewa widać tylko wiersze BOM z prawidłowymi datami. Kliknij prawym przyciskiem myszy wiersz BOM, aby otworzyć stronę <strong>Edytuj wiersz BOM</strong>, gdzie można sprawdzić daty ważności tego wiersza BOM.</td>
</tr>
</tbody>
</table>

Jeśli używasz konstruktora BOM do sprawdzania i edycji list BOM , które składają się z jednego lub więcej poziomów fantomów, marszruta skojarzona z pozycją u góry zwykle obejmuje całą hierarchię BOM. Aby uprościć przegląd, możesz zablokować marszrutę górnego poziomu w na ekranie, klikając kolejno opcje **Widok** &gt; **Zablokuj marszrutę**. Aby odblokować marszrutę, kliknij kolejno opcje **Widok** &gt; **Odblokuj marszrutę**.

## <a name="adding-and-editing-boms-and-bom-lines"></a>Dodawanie i edytowanie BOM i wierzy BOM
Aby modyfikować wiersze BOM lub BOM, użyj funkcji **Wiersze BOM** lub **BOM**. Po wybraniu węzła na drzewie, typ węzła określa funkcje, które są dostępne.

| Funkcja                            | opis                                                                                               | Typ węzła i warunki                                                                                                                                                                                                                                                                       |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wiersze BOM &gt; Edytuj                 | Otwórz okno dialogowe, w którym można edytować atrybuty wiersza BOM.                                             | Funkcja ta jest dostępna po wybraniu węzła wiersza BOM.                                                                                                                                                                                                                                   |
| Wiersze BOM &gt; Usuń               | Usuń wiersz BOM z wybranej listy BOM.                                                                  | Ta funkcja jest dostępna, gdy jest wybrany jest węzeł wiersza BOM i lista BOM nie jest zablokowana do edycji.                                                                                                                                                                                             |
| Wiersze BOM &gt; Dodaj przed wierszem      | Otwórz okno dialogowe, w którym można wybrać wariant produktu do uwzględnienia przed wybranym wierszem BOM.         | Funkcja ta jest dostępna po wybraniu węzła wiersza BOM.                                                                                                                                                                                                                                   |
| Wiersze BOM &gt; Dodaj do BOM składnika | Otwórz okno dialogowe, w którym można wybrać wariant produktu do uwzględnienia na końcu wybranego wiersza BOM.       | Funkcja ta jest dostępna, gdy wybrany węzeł ma wybraną listę BOM. Jeśli ta funkcja nie jest dostępna, w wersji BOM może brakować wariantu wybranego towaru. W takim przypadku można kliknąć kolejno opcje **BOM** &gt; **Utwórz wersję**, aby utworzyć brakującą wersję wybranego węzła. |
| Wiersze BOM &gt; Dodaj po wierszu       | Otwórz okno dialogowe, w którym można wybrać wariant produktu do uwzględnienia za wybranym wierszem BOM.          | Funkcja ta jest dostępna po wybraniu węzła wiersza BOM.                                                                                                                                                                                                                                   |
| BOM &gt; Utwórz wersję BOM             | Utwórz nową wersję BOM lub BOM dla wybranego węzła wariantu produktu.                             | Ta funkcja jest dostępna, gdy wybrany węzeł wiersza BOM jest połączony z towarem, który ma typ produkcji **BOM** lub **Formuła**.                                                                                                                                                  |
| BOM &gt; Obliczanie                | Otwórz okno dialogowe, w którym można uruchomić koszty lub obliczanie ceny sprzedaży dla wariantu produktu. | Funkcja ta jest dostępna, gdy wybrany węzeł jest powiązany z wersją BOM.                                                                                                                                                                                                         |
| BOM &gt; Sprawdź                      | Sprawdź poprawność i sprawdź wybrany BOM.                                                                      | Funkcja ta jest dostępna, gdy wybrany węzeł jest powiązany z wersją BOM.                                                                                                                                                                                                         |

## <a name="configuring-the-tree-view"></a>Konfigurowanie widoku drzewa
Kliknij **Ustawienia**, aby dostosować dane wyświetlane w widoku drzewa w Konstruktorze BOM.

| Grupa pola | Opis                                                                                                                                                  |
|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| lista BOM         | Użyj pól wyboru, aby wybrać kryteria pokazane w strukturze drzewa. W Konstruktorze BOM wybrane kryteria są wyświetlane u dołu obydwu kart. |
| Trasa       | Użyj pól wyboru, aby wybrać kryteria pokazane dla marszrut.                                                                                    |






