--- 
title: "Uruchamianie formatów w celu dynamicznego dodawania kolumn do raportów programu Excel jako poziomo rozszerzalnych zakresów"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może skonfigurować format raportowania elektronicznego (ER) do generowania raportów jako plików arkuszy OPENXML(Excel), w których wymagane kolumny mogą być tworzone dynamicznie jako poziomo rozszerzalne zakresy."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: c7d563da9a02c91cce17cfa1d4a6915dd768ac3d
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="run-formats-to-dynamically-add-columns-to-excel-reports-as-horizontally-expandable-ranges"></a>Uruchamianie formatów w celu dynamicznego dodawania kolumn do raportów programu Excel jako poziomo rozszerzalnych zakresów

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może skonfigurować format raportowania elektronicznego (ER) do generowania raportów jako plików arkuszy OPENXML(Excel), w których wymagane kolumny mogą być tworzone dynamicznie jako poziomo rozszerzalne zakresy. Kroki można wykonać na danych firmy DEMF.

Aby wykonać te kroki, należy najpierw wykonać kroki procedury „ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 1: Projektowanie formatu)”.

Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.


## <a name="find-created-format"></a>Znajdowanie utworzonego formatu
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie rozwiń węzeł „Wymiany finansowe przykładowego modelu”.
3. W drzewie zaznacz element „Wymiany finansowe przykładowego modelu\Przykładowy raport z poziomo rozszerzalnymi zakresami”.

## <a name="execute-format-to-create-excel-output"></a>Wykonanie formatu w celu utworzenia danych wyjściowych programu Excel
1. Kliknij przycisk Uruchom.
2. W polu Nazwa wymiaru wpisz „BusinessUnit;CostCenter;Dział”.
    * Wprowadź lub wybierz wartość w polu Nazwa wymiaru.  Aby zaznaczyć wszystkie wymiary w bieżącej firmie, wprowadź następujące wyrażenie: BusinessUnit;CostCenter;Dział;ItemGroup;MainAccount;Projekt  
3. Rozwiń sekcję Rekordy do uwzględnienia.
4. Kliknij przycisk Filtr.
5. Zaznacz wiersz z tabelą Arkusz księgi i polem Arkusz z numerem partii.
6. W polu Kryteria wpisz wartość „00057..00058”.
    * 00057..00058  
7. Kliknij przycisk OK.
8. Kliknij przycisk OK.
    * Przejrzyj wygenerowane dane wyjściowe. Należy zauważyć, że nowo utworzony plik programu Excel zawiera taką samą liczbę kolumn, jak wybrana dla wymiarów finansowych. Nagłówek raportu w tych kolumnach reprezentuje nazwy wymiarów finansowych. Wiersze transakcji w tych kolumnach reprezentują wymiary finansowe. Uruchom ten raport i wybierz inne wymiary, a zobaczysz, że raport nie jest zależny od liczby wybranych wymiarów ani liczby wymiarów skonfigurowanych dla tego wystąpienia programu Dynamics 365 for Finance and Operations.  


