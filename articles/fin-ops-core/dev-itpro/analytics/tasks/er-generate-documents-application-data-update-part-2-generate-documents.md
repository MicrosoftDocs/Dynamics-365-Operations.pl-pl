---
title: Projektowanie konfiguracji w celu generowania dokumentów zawierających dane aplikacji
description: W tym artykule opisano sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego. (część 1 — importowanie konfiguracji).
author: kfend
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8494f54c6f84e63e75469aa9d80d090c050b0f7f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290553"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a>Projektowanie konfiguracji w celu generowania dokumentów zawierających dane aplikacji

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
