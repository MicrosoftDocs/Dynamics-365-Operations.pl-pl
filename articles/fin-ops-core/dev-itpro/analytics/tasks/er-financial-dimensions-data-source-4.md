---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 4 — Wykonanie raportu)
description: W tym artykule opisano sposób konfigurowania modelu raportowania elektronicznego w celu używania wymiarów finansowych jako źródła danych dla raportów ER. (część 4)
author: kfend
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERSolutionTable, SysQueryForm
ms.openlocfilehash: d0fca8b1a6139b71782af05531d9494c968ef9f5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290763"
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
![Strona konfiguracji raportowania elektronicznego.](../media/er-financial-dimensions-guides-run1.png)
5. Wprowadź lub wybierz wartość w polu Nazwa wymiaru.
    * Aby zaznaczyć wszystkie wymiary w bieżącej firmie, wprowadź następujące dane: BusinessUnit;CostCenter;Dział;ItemGroup;MainAccount;Projekt  
![Wysunięcie parametrów raportowania elektronicznego, lista rozwijana nazwy wymiaru.](../media/er-financial-dimensions-guides-run2.png)
6. Rozwiń sekcję Rekordy do uwzględnienia.
7. Kliknij przycisk Filtr.
8. Zaznacz wiersz z tabelą Arkusz księgi i polem Arkusz z numerem partii.
9. W polu Kryteria wpisz wartość „00057”.
10. Kliknij przycisk OK.
11. Kliknij przycisk OK.
![Wysunięcie parametrów raportowania elektronicznego, sekcja Raporty do załączenia.](../media/er-financial-dimensions-guides-run3.png)
    * Przejrzyj wygenerowane dane wyjściowe. Dla każdej transakcji wybranej partii są przedstawiane wymiary finansowe z odpowiedniego zestawu wymiarów. Uruchom ten raport i wybierz inne wymiary, a zobaczysz, że raport nie jest zależny od liczby wybranych wymiarów ani liczby wymiarów skonfigurowanych dla tego wystąpienia .  
![Wygenerowano dane wyjściowe konfiguracji raportowania elektronicznego.](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
