---
title: Generowanie dokumentów elektronicznych i aktualizowanie danych aplikacji przy użyciu modułu ER
description: Można projektować formaty raportowania elektronicznego (ER), które będą używane w aplikacji do generowania wychodzących dokumentów elektronicznych.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5f78f3b36a1aebfb263d64ccf2293097eb9af6e6de1ab49de39b18e1c318950
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765815"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Generowanie dokumentów elektronicznych i aktualizowanie danych aplikacji przy użyciu raportowania elektronicznego (ER)

[!include [banner](../includes/banner.md)]

Można projektować formaty raportowania elektronicznego (ER), które będą używane w aplikacji do generowania wychodzących dokumentów elektronicznych. Można także zaprojektować formaty ER, które analizują składnię przychodzących dokumentów elektronicznych i używają zawartości tych dokumentów do aktualizowania danych aplikacji.

Dzięki tej funkcjonalności jeden format ER może służyć do generowania wychodzących dokumentów elektronicznych, a następnie aktualizowania danych aplikacji. Tej funkcji można używać w następujących scenariuszach:

- Aby uniknąć wielokrotnego wykorzystywania danych aplikacji w kolejnych procesach, można oznaczyć dane aplikacje bezpośrednio po ich użyciu do wygenerowania dokumentów elektronicznych. Na przykład można oznaczyć transakcje płatności jako już przetworzone natychmiast po ich umieszczeniu w wygenerowanym komunikacie płatniczym.
- Aby zapisać szczegóły przetwarzania dokumentów elektronicznych, które zostały wygenerowane za pomocą logiki modułu ER. Na przykład unikatowy identyfikator komunikatu płatniczego wygenerowanego za pomocą wyrażenia ER. Wyrażenie bazuje na informacjach wprowadzonych w oknie dialogowym modułu ER po uruchomieniu formatu ER w celu wygenerowania dokumentów.

Aby dowiedzieć się więcej o tej funkcji, odtwórz przewodniki po zadaniach ER Generowanie dokumentów z aktualizacją danych aplikacji (część 7.5.4.3 procesu biznesowego Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)), które prowadzą przez kolejne etapy procesu sprawozdawczości i archiwizacji Intrastat. Następujące pliki są wymagane do wykonania pewnych kroków w tych przewodnikach po zadaniach. Pobierz i zapisz te pliki na swoim lokalnym komputerze.

- [Konfiguracja modelu danych ER: Intrastat (model)](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [Konfiguracja mapowania modelu ER: Intrastat (mapowanie)](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [Konfiguracja formatu ER: Intrastat (format)](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
