---
title: "Generowanie dokumentów elektronicznych i aktualizowanie danych aplikacji za pomocą narzędzia Raportowanie elektroniczne"
description: "Można projektować formaty raportowania elektronicznego (ER), które będą używane w aplikacji Finance and Operations do generowania wychodzących dokumentów elektronicznych. Można także zaprojektować formaty ER, które analizują składnię przychodzących dokumentów elektronicznych i używają zawartości tych dokumentów do aktualizowania danych aplikacji."
author: kfend
manager: AnnBe
ms.date: 05/11/2017
ms.topic: article
ms.prod: 
ms.service: Lifecycle Services
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.2, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d37d20b26d8ae755a6c5a688afd1ad0541d1f693
ms.openlocfilehash: 7e4e0acb374fe091c0e099355204116345c62997
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017

---


Można projektować formaty raportowania elektronicznego (ER), które będą używane w aplikacji Finance and Operations do generowania wychodzących dokumentów elektronicznych. Można także zaprojektować formaty ER, które analizują składnię przychodzących dokumentów elektronicznych i używają zawartości tych dokumentów do aktualizowania danych aplikacji. 

Dzięki tej funkcjonalności jeden format ER może służyć do generowania wychodzących dokumentów elektronicznych, a następnie aktualizowania danych aplikacji. Tej funkcji można używać w następujących scenariuszach:

- Aby uniknąć wielokrotnego wykorzystywania danych aplikacji w kolejnych procesach, można oznaczyć dane aplikacje bezpośrednio po ich użyciu do wygenerowania dokumentów elektronicznych. Na przykład można oznaczyć transakcje płatności jako już przetworzone natychmiast po ich umieszczeniu w wygenerowanym komunikacie płatniczym.
- Aby zapisać szczegóły przetwarzania dokumentów elektronicznych, które zostały wygenerowane za pomocą logiki modułu ER. Na przykład unikatowy identyfikator komunikatu płatniczego wygenerowanego za pomocą wyrażenia ER. Wyrażenie bazuje na informacjach wprowadzonych w oknie dialogowym modułu ER po uruchomieniu formatu ER w celu wygenerowania dokumentów.

Aby dowiedzieć się więcej o tej funkcji, odtwórz przewodniki po zadaniach ER Generowanie dokumentów z aktualizacją danych aplikacji (część 7.5.4.3 procesu biznesowego Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)), które prowadzą przez kolejne etapu procesu sprawozdawczości i archiwizacji Intrastat. Następujące pliki są wymagane do wykonania pewnych kroków w tych przewodnikach po zadaniach. Pobierz i zapisz te pliki na swoim lokalnym komputerze.

- [Konfiguracja modelu danych ER: Intrastat (model)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Konfiguracja mapowania modelu ER: Intrastat (mapowanie)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Konfiguracja formatu ER: Intrastat (format)](https://go.microsoft.com/fwlink/?linkid=849038)

