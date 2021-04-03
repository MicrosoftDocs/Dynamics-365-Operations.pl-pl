---
title: ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 2 — Inicjowanie formatu)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego w celu generowania raportów jako plików arkuszy OPENXML (Excel). (część 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee0b8c997549bca2cae5500c926ccba916a473b5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569540"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a>ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 2 — Inicjowanie formatu)

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może skonfigurować format raportowania elektronicznego (ER) do generowania raportów jako plików arkuszy OPENXML(Excel), w których wymagane kolumny mogą być tworzone dynamicznie jako poziomo rozszerzalne zakresy. Kroki można wykonać na danych firmy DEMF.

Aby wykonać te kroki, należy najpierw wykonać kroki procedury „ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 1: Projektowanie formatu)”.

Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


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
    * Przejrzyj wygenerowane dane wyjściowe. Należy zauważyć, że nowo utworzony plik programu Excel zawiera taką samą liczbę kolumn, jak wybrana dla wymiarów finansowych. Nagłówek raportu w tych kolumnach reprezentuje nazwy wymiarów finansowych. Wiersze transakcji w tych kolumnach reprezentują wymiary finansowe. Uruchom ten raport i wybierz inne wymiary, a zobaczysz, że raport nie jest zależny od liczby wybranych wymiarów ani liczby wymiarów skonfigurowanych dla tego wystąpienia .  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]