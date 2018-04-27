--- 
title: "Tworzenie podwykonawczej komórki roboczej w systemie lean manufacturing"
description: "Aby wymodelować pracę podwykonawczą dla produkcji oszczędnej, należy utworzyć komórkę roboczą skojarzoną z dostawcą, który dostarcza pracę."
author: cvocph
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fc8dc0bc29c6bdb662c46808491abf5395f0be5d
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a>Tworzenie podwykonawczej komórki roboczej w systemie lean manufacturing

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Aby wymodelować pracę podwykonawczą dla produkcji oszczędnej, należy utworzyć komórkę roboczą skojarzoną z dostawcą, który dostarcza pracę. Komórka robocza pracy podwykonawczej jest połączona z dostawcą poprzez skojarzenie zasobu typu Dostawca. Jeśli odtworzysz to nagranie w kontekście firmy demonstracyjnej USMF, możesz wybrać identyfikator konta dostawcy 1002 i oddział 1.


## <a name="create-a-vendor-resource"></a>Tworzenie zasobu dostawcy
1. Przejdź do okna Zasoby.
2. Kliknij przycisk Nowy.
3. W polu Zasób wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Typ wybierz opcję „Dostawca”.
6. W polu Dostawca kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.

## <a name="create-the-resource-group"></a>Tworzenie grupy zasobów
1. Przejdź do okna Grupy zasobów.
2. Kliknij przycisk Nowy.
3. W polu Grupa zasobów wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wybierz oddział, do którego powinna zostać przydzielona komórka robocza. Teoretycznie oddział może reprezentować jeden oddział obsługiwany przez dostawcę. Jednak w większości przypadków zasoby podwykonawcze są przydzielone do oddziału, który zlecenia pracę podwykonawczą. Należy zauważyć, że magazyny wejściowy i wyjściowy komórek pracy podwykonawczej muszą się znajdować w tym samym oddziale.  
6. W polu Oddział wpisz wartość.
7. @SysTaskRecorder:_RequestClose
8. Zaznacz lub wyczyść pole wyboru Komórka robocza.
9. W polu Magazyn wejściowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wybierz magazyn i lokalizację używane do przejściowego składowania materiału dla komórki roboczej zarządzanej przez dostawcę. W wielu przypadkach magazyn i lokalizacja są modelowane przy użyciu oddzielnych magazynów dla poszczególnych dostawców i jednej lokalizacji na każdą komórkę roboczą.  
10. W polu Lokalizacja wejściowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. W polu Magazyn wyjściowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Zdefiniuj magazyn i lokalizację, w których będzie księgowany materiał podczas księgowania działań podwykonawczych komórki roboczej. Magazyn i lokalizacja mogą być w oddziale dostawcy, jeśli dostawca raportuje zadania Kanban. Alternatywnie magazyn i lokalizacja mogą być lokalizacją przyjęcia skojarzoną z następnym etapem przepływu produkcji.  
12. W polu Lokalizacja wyjściowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
13. Rozwiń lub zwiń sekcję Kalendarze.
14. Kliknij przycisk Dodaj.
15. W polu Kalendarz kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Skojarz kalendarz czasu pracy komórki roboczej z grupą zasobów. Dla zasobów krytycznych zalecamy zdefiniowanie określonych kalendarzy, które reprezentują dokładne czasy pracy i powiązane zdolności produkcyjne komórki roboczej lub oddziału dostawcy.  
16. Rozwiń lub zwiń sekcję Zasoby.
17. Kliknij przycisk Dodaj.
    * Grupa zasobów podwykonawczych musi mieć skojarzony zasób typu Dostawca, który łączy grupę zasobów z kontem dostawcy.  
18. W polu Zasób kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Zaznacz lub wprowadź zasób dostawcy utworzony w poprzednim podzadaniu.  
19. Rozwiń lub zwiń sekcję Zdolności produkcyjne komórki roboczej.
20. Kliknij przycisk Dodaj.
    * Komórka robocza musi mieć zdefiniowane zdolności produkcyjne. W tym przykładzie tworzymy produktywność 100 sztuk na standardowy dzień roboczy.  
21. W polu Model przepływu produkcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
22. W polu Okres zdolności produkcyjnych wybierz opcję.
23. W polu Średnia produktywność (ilość) wprowadź liczbę.
24. W polu Jednostka kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
25. Rozstrzygnij zmiany w jednostce.


