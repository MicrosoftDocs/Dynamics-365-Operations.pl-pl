---
title: "Projektant formuł"
description: "W tym temacie wyjaśniono, jak używać projektanta formuł do analizowania formuł i zarządzania nimi w widoku drzewa."
author: cvocph
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: d9b61e545067db592545d5fbce7b4315c51a8bf8
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---

# <a name="formula-designer"></a>Projektant formuł

[!include[banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak używać projektanta formuł do analizowania formuł i zarządzania nimi w widoku drzewa.

Po otwarciu strony **Projektant formuł** ze strony **Zwolnione produkty** drzewo w lewym okienku pokazuje listę produktów towarzyszących oraz hierarchię składników zwolnionego produktu. Struktura jest ustalana na podstawie hierarchii formuł, które są aktywne i zatwierdzone dla wybranego towaru i jego składników, domyślnego oddziału zlecenia i faktycznej daty.

Kliknij przycisk **Ustawienia**, aby wybrać różne konfiguracje oraz określić rodzaj informacji wyświetlanych w wierszach drzewa.

Kliknij **Filtr**, aby zmienić początkowy wybór w widoku. Jeśli ustawisz zasadę wyświetlania na **Wybrane/aktywne** lub **Wybrane**, można wybrać poszczególne wersje formuły lub marszruty, które mają być używane w widoku. Można wybrać niezatwierdzone i nieaktywne wersje formuły, które mają być wyświetlane lub zachowane w projektancie formuł.  

> [!NOTE]
> Po otwarciu strony **Projektant formuł** ze strony **Lista składowa (BOM)** informacje o marszrucie nie są wyświetlane. Obecnie wybór wersji formuły lub marszruty ma zastosowanie do wszystkich wystąpień projektanta formuł.  

W poniższych sekcjach opisano funkcje dostępne w projektancie BOM.

## <a name="analyze-a-formula-structure-by-using-the-formula-designer"></a>Analizowanie struktury formuły za pomocą projektanta formuł
Projektant formuł ma dwie sekcje:

-   Widok drzewa struktury formuły.
-   Widok szczegółów dla wybranych danych. Po wybraniu węzła w widoku drzewa skrócone karty w sekcji szczegółów są aktualizowane według tego węzła:
    -   **Szczegóły wiersza formuły** — wyświetlanie szczegółów wiersza formuły wybranego w widoku drzewa.
    -   **Pozycja danych** — wyświetlanie szczegółów głównego towaru lub towaru używanego w wybranym węźle. Opcja **Edytuj zwolniony produkt** umożliwia obsługę wybranego towaru.
    -   **Formuła** — wyświetlanie nagłówka formuły powiązanego z wybranym węzłem.
    -   **Marszruta** — wyświetlanie nagłówka marszruty powiązanego z wybranym węzłem.
    -   **Operacje marszruty** — wyświetlanie podglądu operacji w marszrucie. Po wybraniu wiersza listy składowej (BOM) przypisanego do konkretnej operacji operacja ta jest oznaczana jako **Składnik wymagany w operacji**.

## <a name="select-a-formula-and-route"></a>Wybieranie formuły i marszruty
Filtr stosowany do formuły i marszruty jest wyświetlany w nagłówku projektanta formuł. Można zmienić filtr za pomocą okna dialogowego **Filtr**. W poniższej tabeli opisano pola w tym oknie dialogowym.

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
<td>Jeśli wybrany produkt gotowy jest produktem głównym, można zdefiniować aktywne wymiary produktu dla głównego wyboru. Należy zauważyć, że jeśli otworzysz projektanta formuł dla produktu, który nie jest produktem głównym, nie będzie można wybrać żadnych wymiarów produktu w oknie dialogowym <strong>Filtr</strong>.</p></td>
</tr>
<tr class="even">
<td>Oddział</td>
<td>Zmiana oddziału, dla którego jest wyświetlane drzewo składników. Domyślnie jest to oddział zapasów dla gotowego towaru.</td>
</tr>
<tr class="odd">
<td>Reguła wyświetlania</td>
<td><p>Wybierz zasadę wyświetlania wersji obowiązującą dla bieżącej struktury formuły i dla bieżącej marszruty:</p>
<ul>
<li>Jeśli ustawiono zasadę <strong>Aktywne</strong> lub <strong>Wybrane/aktywne</strong>, to zostanie wyszukana wersja formuły lub wersja marszruty ważna dla tej daty.</li>
<li>Jeśli ustawiono zasadę <strong>Wybrane/aktywne</strong> lub <strong>Wybrane</strong>, można wybrać wersję formuły lub wersji marszruty, klikając kolejno opcje <strong>Formuła</strong> &gt; <strong>Wersje formuły</strong> lub <strong>Marszruta</strong> &gt; <strong>Wersje marszruty</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Data wersji</td>
<td>Służy do wprowadzania daty wersji dla formuły i marszruty. Wersja wskazuje wersję formuły stosowaną w określonym dniu, zgodnie z datami wersji w ustawieniach wersji formuły.</td>
</tr>
<tr class="odd">
<td>Ilość od</td>
<td>Filtrowanie wersji przez wybranie określonej ilości „od”. Jeśli zostanie ustawiona wartość, będzie można wybrać różne wersje formuły i marszruty.</td>
</tr>
<tr class="even">
<td>Pokaż tylko ważne</td>
<td>Po zaznaczeniu pola wyboru w strukturze drzewa widać tylko wiersze formuły z prawidłowymi datami. Kliknij prawym przyciskiem myszy wiersz formuły, aby otworzyć stronę <strong>Edytuj wiersz formuły</strong>, gdzie można sprawdzić daty ważności tego wiersza formuły.</td>
</tr>
</tbody>
</table>

Jeśli używasz projektanta formuł do sprawdzania i edytowania formuł składających się z jednego lub więcej poziomów fantomów, marszruta skojarzona z pozycją u góry zwykle obejmuje całą hierarchię formuły. Aby uprościć przegląd, możesz zablokować marszrutę górnego poziomu w na ekranie, klikając kolejno opcje **Widok** &gt; **Zablokuj marszrutę**. Aby odblokować marszrutę, kliknij kolejno opcje **Widok** &gt; **Odblokuj marszrutę**.

## <a name="add-and-edit-formulas-and-formula-lines"></a>Dodawanie i edytowanie formuł i ich wierszy
Aby zmodyfikować wiersze formuły lub formułę, użyj funkcji **Wiersze BOM** lub **Formuła**. Po wybraniu węzła na drzewie typ węzła określa funkcje, które są dostępne.

| Funkcja                            | opis                                                                                               | Typ węzła i warunki |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------|
| Wiersze BOM &gt; Edytuj                 | Otwórz okno dialogowe, w którym można edytować atrybuty wiersza formuły.                                         | Funkcja ta jest dostępna po wybraniu węzła wiersza formuły. |
| Wiersze BOM &gt; Usuń               | Usuwanie wiersza formuły z wybranej formuły.                                                          | Ta funkcja jest dostępna, gdy jest wybrany jest węzeł wiersza formuły, a lista BOM nie jest zablokowana do edycji. |
| Wiersze BOM &gt; Dodaj przed wierszem      | Otwieranie okna dialogowego, w którym można wybrać wariant produktu do uwzględnienia przed wybranym wierszem formuły.     | Funkcja ta jest dostępna po wybraniu węzła wiersza formuły. |
| Wiersze BOM &gt; Dodaj do BOM składnika | Otwieranie okna dialogowego, w którym można wybrać wariant produktu do uwzględnienia na końcu wybranej formuły.   | Funkcja ta jest dostępna, gdy wybrany węzeł ma wybraną formułę. Jeśli ta funkcja nie jest dostępna, w wersji formuły może brakować wariantu wybranego towaru. W takim przypadku można kliknąć kolejno opcje **Formuła** &gt; **Utwórz wersję**, aby utworzyć brakującą wersję wybranego węzła. |
| Wiersze BOM &gt; Dodaj po wierszu       | Otwieranie okna dialogowego, w którym można wybrać wariant produktu do uwzględnienia za wybranym wierszem formuły.      | Funkcja ta jest dostępna po wybraniu węzła wiersza formuły. |
| Formuła &gt; Utwórz wersję         | Tworzenie nowej wersji formuły lub formuły dla wariantu produktu w wybranym węźle.                     | Ta funkcja jest dostępna, gdy wybrany węzeł wiersza formuły jest połączony z towarem, który ma typ produkcji **BOM** lub **Formuła**. |
| Formuła &gt; Obliczanie            | Otwórz okno dialogowe, w którym można uruchomić koszty lub obliczanie ceny sprzedaży dla wariantu produktu. | Funkcja ta jest dostępna, gdy wybrany węzeł jest powiązany z wersją formuły. |
| Formuła &gt; Sprawdź                  | Weryfikowanie i sprawdzanie wybranej formuły.                                                                  | Funkcja ta jest dostępna, gdy wybrany węzeł jest powiązany z wersją formuły. |

## <a name="configuring-the-tree-view"></a>Konfigurowanie widoku drzewa
Kliknij przycisk **Ustawienia**, aby dostosować informacje wyświetlane w widoku drzewa w projektancie formuł.

| Grupa pola | opis |
|-------------|-------------|
| lista BOM         | Użyj pól wyboru, aby wybrać kryteria pokazane w strukturze drzewa. W projektancie formuł wybrane kryteria są wyświetlane u dołu obydwu kart. |
| Marszruta       | Użyj pól wyboru, aby wybrać kryteria pokazane dla marszrut. |

