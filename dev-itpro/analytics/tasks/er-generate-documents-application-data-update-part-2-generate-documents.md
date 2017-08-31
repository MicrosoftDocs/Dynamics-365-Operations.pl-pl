--- 
title: "Generowanie dokumentów z aktualizacjami danych aplikacji na potrzeby raportowania elektronicznego (ER)"
description: "Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 1 — Importowanie konfiguracji)”."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f10faaaffeb7df5be0b37a9b8dbfa5db5c24d2a2
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="generate-documents-with-application-data-update-for-electronic-reporting-er"></a>Generowanie dokumentów z aktualizacjami danych aplikacji na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 1: Importowanie konfiguracji)”.



Etapy w tej procedurze wyjaśniają sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego. W tej procedurze uruchomisz zaimportowaną konfigurację formatu ER, którą utworzono dla przykładowej firmy Litware, Inc., w celu wygenerowania dokumentów elektronicznych.



Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego. Kroki można wykonać przy użyciu zestawu danych firmy DEMF. 



Przed rozpoczęciem zmień kontekst kraju firmy DEMF z DEU (Niemcy) na BEL (Belgia). Kliknij kolejno opcje Administrowanie organizacją > Organizacje > Firmy i zaktualizuj kod kraju w podstawowym adresie firmy DEMF. Następnie ponownie uruchom aplikację.


## <a name="run-imported-er-format"></a>Uruchamianie zaimportowanego formatu ER
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie rozwiń węzeł „Intrastat (model)”.
3. W drzewie zaznacz element „Intrastat (model)\Intrastat (format)”.
4. Kliknij przycisk Uruchom.
    * Uruchom wersję roboczą konfiguracji formatu ER, aby wygenerować raport Intrastat.  
5. W polu Wprowadź nazwę pliku wpisz „intrastat.xml”.
    * Nadaj plikowi nazwę.  
6. Kliknij przycisk OK.
    * Przejrzyj wygenerowany plik XML.  
7. Zamknij stronę.
8. Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.
    * Otwórz ten formularz, aby wyświetlić transakcje Intrastat zawarte w wygenerowanym dokumencie elektronicznym.  
9. Kliknij opcję Archiwum Intrastat.
    * Ponieważ wykonany format raportowania elektronicznego nie zawiera żadnych ustawień aktualizacji danych aplikacji, szczegóły gotowego raportu Intrastat nie zostały zarchiwizowane.  
10. Zamknij stronę.
11. Zamknij stronę.


