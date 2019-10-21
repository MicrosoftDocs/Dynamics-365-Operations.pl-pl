---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 4 — Wykonanie raportu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aa5b726a7c400da09381944f3303f7ac4bb796aa
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182423"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4-run-the-report"></a>ER Używanie wymiarów finansowych jako źródła danych (Część 4: Wykonanie raportu)

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER. Kroki można wykonać na danych firmy DEMF.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 3: Projektowanie raportu)”. Należy także skonfigurować domyślne typy dokumentów na stronie Parametry raportowania elektronicznego. Domyślne typy dokumentów również są ustawiane podczas pobierania i importowania każdej konfiguracji raportowania elektronicznego. 


## <a name="run-report"></a>Generowanie raportu
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie rozwiń węzeł „Wymiany finansowe przykładowego modelu”.
3. W drzewie zaznacz element „Wymiany finansowe przykładowego modelu\Raport arkusza księgi”.
4. Kliknij przycisk Uruchom.
5. W polu Nazwa wymiaru wprowadź lub wybierz wartość.
    * Aby zaznaczyć wszystkie wymiary w bieżącej firmie, wprowadź następujące wyrażenie: BusinessUnit;CostCenter;Dział;ItemGroup;MainAccount;Projekt  
6. Rozwiń sekcję Rekordy do uwzględnienia.
7. Kliknij przycisk Filtr.
8. Zaznacz wiersz z tabelą Arkusz księgi i polem Arkusz z numerem partii.
9. W polu Kryteria wpisz wartość „00057”.
10. Kliknij przycisk OK.
11. Kliknij przycisk OK.
    * Przejrzyj wygenerowane dane wyjściowe. Należy zauważyć, że dla każdej transakcji wybranej partii są przedstawiane wymiary finansowe z odpowiedniego zestawu wymiarów. Uruchom ten raport i wybierz inne wymiary, a zobaczysz, że raport nie jest zależny od liczby wybranych wymiarów ani liczby wymiarów skonfigurowanych dla tego wystąpienia .  

