---
title: Definicje raportów w Projektancie raportów finansowych
description: Ten artykuł zawiera informacje o definicjach raportów.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fed19d541af1ef6a55f09127f08d73b1301eefb6369f6d76314463e18fb273c8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747648"
---
# <a name="report-definitions-in-financial-report-designer"></a>Definicje raportów w Projektancie raportów finansowych

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o definicjach raportów. Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu. Definicja raportu zawiera również opcje i ustawienia umożliwiające dostosowywanie raportu. 

Definicja raportu to składnik (blok konstrukcyjny) raportu, który używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu. Definicja raportu zawiera także opcje i ustawienia umożliwiające dostosowanie raportu. Po zdefiniowaniu definicji wierszy i kolumn trzeba połączyć je w definicji raportu. Na tym etapie można też zdefiniować inne aspekty definicji, np. poziom szczegółowości i data raportu. Następnie można zapisać i wygenerować raport. Funkcja sprawozdawczości finansowej oferuje następujące poziomy szczegółowości:

- Finanse
- Finanse i Konto
- Finanse, Konto i Transakcja

Jednak w zależności od sposobu przechowywania danych w systemie Microsoft Dynamics ERP, szczegóły transakcji mogą być niedostępne w raportach.

## <a name="create-a-report-definition"></a>Tworzenie definicji raportu
1. W Projektancie raportów w menu **Plik** kliknij przycisk **Nowy**, a następnie wybierz opcję **Definicja raportu**.
2. Podaj odpowiednie informacje na kartach **Raport**, **Produkcja i dystrybucja**, **Nagłówki i stopki** i **Ustawienia**.

## <a name="contents-of-a-report-definition"></a>Zawartość definicji raportu
W poniższej tabeli opisano karty w definicji raportu oraz sposób wykorzystania informacji.

<table>
<thead>
<tr>
<th>Tabulator</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr>
<td>Raport</td>
<td>Tworzenie raportu, konfigurowanie raportu lub modyfikowanie istniejącego raportu.</td>
</tr>
<tr>
<td>Produkcja i dystrybucja</td>
<td>Zmienianie typu produkcji i dystrybucji raportu.</td>
</tr>
<tr>
<td>Nagłówek i stopki</td>
<td>Definiowanie i formatowanie nagłówków i stopek raportu. Na przykład można dodać tekst lub obrazy w nagłówku lub stopce. Funkcja sprawozdawczości finansowej obsługuje pliki obrazów w formacie .bmp, .jpg i .png. Można również dodać kody autotekstu do wstawiania innych informacji, takich jak nazwa firmy, nazwa raportu czy numer strony.</td>
</tr>
<tr>
<td>Ustawienia</td>
<td>Określanie ustawień definicji raportu, na przykład następujących ustawień:
<ul>
<li>Formatowanie i zaokrąglanie kwot</li>
<li>Formatowanie raportów szczegółów</li>
<li>Formatowanie drzewek raportowania</li>
<li>Generowanie raportu wyjątków</li>
<li>Określanie konwersja waluty</li>
<li>Szczegóły sumy częściowej i filtrowanie szczegółów</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raporty finansowe](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]