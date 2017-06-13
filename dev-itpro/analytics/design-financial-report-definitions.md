---
title: "Definicje raportów w Projektancie raportów finansowych"
description: "Ten artykuł zawiera informacje o definicjach raportów. Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu. Definicja raportu zawiera również opcje i ustawienia umożliwiające dostosowywanie raportu."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter, Core
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 86b527b72ef0c9af71e70fe280bcdfe3992a36b1
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="report-definitions-in-financial-report-designer"></a>Definicje raportów w Projektancie raportów finansowych

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o definicjach raportów. Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu. Definicja raportu zawiera również opcje i ustawienia umożliwiające dostosowywanie raportu. 

Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu. Definicja raportu zawiera również opcje i ustawienia, które mogą służyć do dostosowywania raportu. Po zdefiniowaniu definicji wierszy i kolumn trzeba połączyć je w definicji raportu. Na tym etapie można też zdefiniować inne aspekty definicji, np. poziom szczegółowości i data raportu. Następnie można zapisać i wygenerować raport. Funkcja sprawozdawczości finansowej oferuje następujące poziomy szczegółowości:

-   Finanse
-   Finanse i Konto
-   Finanse, Konto i Transakcja

Jednak w zależności od tego, w jaki sposób dane są przechowywane w systemie ERP Microsoft Dynamics, szczegóły transakcji mogą nie być dostępne w raportach.

## <a name="create-a-report-definition"></a>Tworzenie definicji raportu
1.  W Projektancie raportów w menu **Plik** kliknij przycisk **Nowy**, a następnie wybierz opcję **Definicja raportu**.
2.  Podaj odpowiednie informacje na kartach **Raport**, **Produkcja i dystrybucja**, **Nagłówki i stopki** i **Ustawienia**.

## <a name="contents-of-a-report-definition"></a>Zawartość definicji raportu
W poniższej tabeli opisano karty w definicji raportu oraz sposób wykorzystania informacji.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabulator</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Raport</td>
<td>Tworzenie raportu, konfigurowanie raportu lub modyfikowanie istniejącego raportu.</td>
</tr>
<tr class="even">
<td>Produkcja i dystrybucja</td>
<td>Zmienianie typu produkcji i dystrybucji raportu.</td>
</tr>
<tr class="odd">
<td>Nagłówek i stopki</td>
<td>Definiowanie i formatowanie nagłówków i stopek raportu. Na przykład można dodać tekst lub obrazy w nagłówku lub stopce. Funkcja sprawozdawczości finansowej obsługuje pliki obrazów w formacie .bmp, .jpg i .png. Można również dodać kody autotekstu do wstawiania innych informacji, takich jak nazwa firmy, nazwa raportu czy numer strony.</td>
</tr>
<tr class="even">
<td>Ustawienia</td>
<td>Określanie ustawień definicji raportu, na przykład następujących ustawień:
<ul>
<li>Formatowanie i zaokrąglanie kwot</li>
<li>Formatowanie raportów szczegółów</li>
<li>Formatowanie drzewek raportowania</li>
<li>Generowanie raportu wyjątków</li>
<li>Określanie konwersja waluty</li>
<li>Szczegóły sumy częściowej i filtrowanie szczegółów</li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Informacje dodatkowe
--------

[Raporty finansowe](financial-reporting-intro.md)




