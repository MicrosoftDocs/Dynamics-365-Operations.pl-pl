---
title: Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów
description: Zachowanie kosztów to sklasyfikowanie kosztów jako stałe lub zmienne.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostBehaviorRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58f888a373af33832c24518fbb5483c3de2d1a58
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208710"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów

[!include [banner](../../includes/banner.md)]

Zachowanie kosztów to sklasyfikowanie kosztów jako stałe lub zmienne. Aby zasada weszła w życie, sama zasada i odpowiednie reguły muszą być przypisane do jednostki kontroli kosztów. Ta procedura służy do tworzenia zasady, a następnie jej przypisywania do jednostki kontroli kosztów.


## <a name="create-a-cost-behavior-hierarchy"></a>Tworzenie hierarchii zachowania kosztów
1. Wybierz kolejno opcje Rachunek kosztów > Wymiary > Hierarchie wymiarów.
2. Kliknij przycisk Nowy.
3. Kliknij przycisk Utwórz.
4. W polu Nazwa hierarchii wymiarów wpisz „Hierarchia zachowania kosztów”.
5. W polu Wymiar wprowadź lub wybierz wartość.
    * Wybierz opcję Składniki kosztów.  
6. Kliknij przycisk Zapisz.
7. Kliknij opcję Wyświetl hierarchię.
8. Kliknij przycisk Nowy.
9. W polu Nazwa węzła wpisz wartość.
    * Wypełnij pole Koszt stały.  
10. W drzewie zaznacz pozycję „Hierarchia zachowania kosztów”.
11. Kliknij przycisk Nowy.
12. W polu Nazwa węzła wpisz wartość.
    * Wypełnij pole Koszt zmienny.  
13. Kliknij przycisk Zapisz.
14. W drzewie zaznacz pozycję „Hierarchia zachowania kosztów\Koszt stały”.
15. Kliknij przycisk Nowy.
16. Na liście oznacz wybrany wiersz.
17. W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.
    * Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.  
18. W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.
    * Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.  
19. W drzewie zaznacz pozycję „Hierarchia zachowania kosztów\Koszt zmienny”.
20. Kliknij przycisk Nowy.
21. Na liście oznacz wybrany wiersz.
22. W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.
    * Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.  
23. W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.
    * Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.  
24. Kliknij przycisk Zapisz.

## <a name="create-the-policy-and-rules"></a>Tworzenie zasady i reguł
1. Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady zachowania kosztów.
2. Kliknij przycisk Nowy.
3. W polu Nazwa zasad wpisz wartość.
4. W polu Hierarchia wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Zaznacz utworzoną właśnie hierarchię zasad.  
5. W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Wybierz opcję Organizacja.  
6. Kliknij przycisk Zapisz.
7. Kliknij przycisk Nowy.
8. Na liście oznacz wybrany wiersz.
9. W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Rozwiń hierarchię i wybierz pozycję Koszt zmienny.  
10. W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Domyślnie zmienny procent wynosi 100 procent.  
11. Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.
12. Kliknij przycisk Nowy.
13. Na liście oznacz wybrany wiersz.
14. W polu Ważne od daty księgowania wpisz datę.
    * Reguły mają daty obowiązywania, tzn. użytkownik lub system mogą wygasić regułę, jeśli zostanie utworzona nowsza wersja.  
15. W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.
16. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]