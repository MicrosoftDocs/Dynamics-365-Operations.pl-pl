---
title: "Generowanie dokumentów elektronicznych i aktualizowanie danych aplikacji za pomocą narzędzia Raportowanie elektroniczne"
description: "Można projektować formaty raportowania elektronicznego (ER), które będą używane w aplikacji Finance and Operations do generowania wychodzących dokumentów elektronicznych. Można także zaprojektować formaty ER, które analizują składnię przychodzących dokumentów elektronicznych i używają zawartości tych dokumentów do aktualizowania danych aplikacji."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7378c1d205b9a9cd61044dc33fc52ff75c6b94b7
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="generate-electronic-documents-and-update-application-data-using-the-electronic-reporting-tool"></a>Generowanie dokumentów elektronicznych i aktualizowanie danych aplikacji za pomocą narzędzia Raportowanie elektroniczne

Można projektować formaty raportowania elektronicznego (ER), które będą używane w aplikacji Finance and Operations do generowania wychodzących dokumentów elektronicznych. Można także zaprojektować formaty ER, które analizują składnię przychodzących dokumentów elektronicznych i używają zawartości tych dokumentów do aktualizowania danych aplikacji. 

Dzięki tej funkcjonalności jeden format ER może służyć do generowania wychodzących dokumentów elektronicznych, a następnie aktualizowania danych aplikacji. Tej funkcji można używać w następujących scenariuszach:

- Aby uniknąć wielokrotnego wykorzystywania danych aplikacji w kolejnych procesach, można oznaczyć dane aplikacje bezpośrednio po ich użyciu do wygenerowania dokumentów elektronicznych. Na przykład można oznaczyć transakcje płatności jako już przetworzone natychmiast po ich umieszczeniu w wygenerowanym komunikacie płatniczym.
- Aby zapisać szczegóły przetwarzania dokumentów elektronicznych, które zostały wygenerowane za pomocą logiki modułu ER. Na przykład unikatowy identyfikator komunikatu płatniczego wygenerowanego za pomocą wyrażenia ER. Wyrażenie bazuje na informacjach wprowadzonych w oknie dialogowym modułu ER po uruchomieniu formatu ER w celu wygenerowania dokumentów.

Aby dowiedzieć się więcej o tej funkcji, odtwórz przewodniki po zadaniach ER Generowanie dokumentów z aktualizacją danych aplikacji (część 7.5.4.3 procesu biznesowego Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)), które prowadzą przez kolejne etapy procesu sprawozdawczości i archiwizacji Intrastat. Następujące pliki są wymagane do wykonania pewnych kroków w tych przewodnikach po zadaniach. Pobierz i zapisz te pliki na swoim lokalnym komputerze.

- [Konfiguracja modelu danych ER: Intrastat (model)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Konfiguracja mapowania modelu ER: Intrastat (mapowanie)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Konfiguracja formatu ER: Intrastat (format)](https://go.microsoft.com/fwlink/?linkid=849038)

