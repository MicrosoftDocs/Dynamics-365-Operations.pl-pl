---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 4 — Wykonanie raportu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb7f49310aa25ff7c17ab4bcd50e1842be84fe2d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684746"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a>ER Używanie wymiarów finansowych jako źródła danych (Część 4 — Wykonanie raportu)

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER. Kroki można wykonać na danych firmy DEMF.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 3: Projektowanie raportu)”. Należy także skonfigurować domyślne typy dokumentów na stronie Parametry raportowania elektronicznego. Domyślne typy dokumentów również są ustawiane podczas pobierania i importowania każdej konfiguracji raportowania elektronicznego. 


## <a name="run-report"></a>Generowanie raportu
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie rozwiń węzeł „Wymiany finansowe przykładowego modelu”.
3. W drzewie zaznacz element „Wymiany finansowe przykładowego modelu\Raport arkusza księgi”.
4. Kliknij przycisk Uruchom.
![Strona konfiguracji raportowania elektronicznego](../media/er-financial-dimensions-guides-run1.png)
5. Wprowadź lub wybierz wartość w polu Nazwa wymiaru.
    * Aby zaznaczyć wszystkie wymiary w bieżącej firmie, wprowadź następujące dane: BusinessUnit;CostCenter;Dział;ItemGroup;MainAccount;Projekt  
![Strona konfiguracji raportowania elektronicznego](../media/er-financial-dimensions-guides-run2.png)
6. Rozwiń sekcję Rekordy do uwzględnienia.
7. Kliknij przycisk Filtr.
8. Zaznacz wiersz z tabelą Arkusz księgi i polem Arkusz z numerem partii.
9. W polu Kryteria wpisz wartość „00057”.
10. Kliknij przycisk OK.
11. Kliknij przycisk OK.
![Strona konfiguracji raportowania elektronicznego](../media/er-financial-dimensions-guides-run3.png)
    * Przejrzyj wygenerowane dane wyjściowe. Dla każdej transakcji wybranej partii są przedstawiane wymiary finansowe z odpowiedniego zestawu wymiarów. Uruchom ten raport i wybierz inne wymiary, a zobaczysz, że raport nie jest zależny od liczby wybranych wymiarów ani liczby wymiarów skonfigurowanych dla tego wystąpienia .  
![Strona konfiguracji raportowania elektronicznego](../media/er-financial-dimensions-guides-run4.png)
