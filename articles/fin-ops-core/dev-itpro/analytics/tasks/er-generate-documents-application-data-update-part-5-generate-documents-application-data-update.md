---
title: Generowanie dokumentów zawierających dane aplikacji
description: Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 4 — Modyfikowanie formatu)”.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6af7113031fd77a0a7e06ec23a149a3fa7ad0012
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026070"
---
# <a name="generate-documents-that-have-application-data"></a>Generowanie dokumentów zawierających dane aplikacji

[!include [task guide banner](../../includes/task-guide-banner.md)]

Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 4: Modyfikowanie formatu)”.



Etapy w tej procedurze wyjaśniają sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego i aktualizowania danych aplikacji. W tej procedurze uruchomisz konfigurację formatu ER, aby wygenerować raport Intrastat i zaktualizować dane aplikacji w celu zarchiwizowania szczegółów procesu raportowania.



Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego. Kroki można wykonać przy użyciu zestawu danych firmy DEMF. Przed rozpoczęciem upewnij się, że kontekstem kraju firmy DEMF jest BEL (Belgia).


## <a name="set-up-foreign-trade-parameters"></a>Konfigurowanie parametrów handlu zagranicznego
1. Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego.
2. Kliknij kartę Sekwencje numerów.
    * Archiwizując szczegóły procesu raportowania Intrastat, musimy identyfikować rekordy każdego tworzonego archiwum. Do tego celu należy skonfigurować specjalną numerację.  
3. Wybierz odwołanie „Identyfikator archiwum Intrastat”.
4. W polu Kod sekwencji numerów wpisz wartość.
    * W polu „Kod sekwencji numerów” wprowadź lub wybierz wartość „Fore_2”.  
5. Rozstrzygnij zmiany w kodzie numeracji.
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

## <a name="run-modified-er-format"></a>Uruchamianie zmodyfikowanego formatu ER
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie rozwiń węzeł „Intrastat (model)”.
3. W drzewie zaznacz element „Intrastat (model)\Intrastat (format)”.
4. Kliknij przycisk Uruchom.
5. W polu Wprowadź nazwę pliku wpisz „intrastat2.xml”.
    * intrastat2.xml  
6. Kliknij przycisk OK.

## <a name="review-er-format-executions-results"></a>Przejrzenie wyników wykonania formatu ER
Przejrzyj wygenerowany plik XML.  
1. Zamknij stronę.
2. Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.
    * Otwórz ten formularz zawierający transakcje Intrastat, które uwzględniono w wygenerowanym dokumencie elektronicznym.  
3. Kliknij opcję Archiwum Intrastat.
    * Ponieważ wykonany format raportowania elektronicznego zawiera teraz ustawienia aktualizacji danych aplikacji, szczegóły gotowego raportu Intrastat zostały zarchiwizowane. W tym formularzu widać rekord nagłówka utworzonego archiwum.  
4. Kliknij przycisk Szczegóły.
    * W tym formularzu widać szczegóły utworzonego archiwum.  
5. Zamknij stronę.
6. Zamknij stronę.
7. Zamknij stronę.

