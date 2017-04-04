---
title: "Zarządzanie informacjami o pracownika za pomocą przepływów pracy"
description: "W tym temacie wyjaśniono, jak możliwości przepływu pracy dla zasobów ludzkich można użyć do zarządzania informacji o pracownikach. Można na przykład skojarzyć przepływu pracy z pozycji i konfigurować procedurę zatwierdzania, który jest uruchamiany, gdy pracownicy zmienić ich rekord."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: f286436aa4833babaeb3de875ee393d18e5f8eea
ms.lasthandoff: 03/31/2017


---

# <a name="use-workflows-to-manage-employee-information"></a>Zarządzanie informacjami o pracownika za pomocą przepływów pracy

W tym temacie wyjaśniono, jak możliwości przepływu pracy dla zasobów ludzkich można użyć do zarządzania informacji o pracownikach. Można na przykład skojarzyć przepływu pracy z pozycji i konfigurować procedurę zatwierdzania, który jest uruchamiany, gdy pracownicy zmienić ich rekord.

Możliwości przepływu pracy dla zasobów ludzkich zawiera wiele przepływów pracy zarządzania działania dotyczące zasobów ludzkich. Ponadto liczne opcje są dostępne, tak, że można modyfikować konkretnych przepływów pracy i skojarz je z hierarchii raportowania. Przepływy pracy są dostępne w celu zarządzania zmianami do kilku standardowych typów informacji o pracownikach. Przepływ pracy można skojarzyć ze stanowiskiem. Następnie jeśli pracownicy zmienić ich rekord pracownika, uruchomieniu przepływu pracy wymagającej zatwierdzenia przed zapisaniem nowych informacji. Przepływy pracy są wstępnie zdefiniowane dla następujących typów informacji, aby ułatwić efektywne zarządzanie zmiany i zachować dokładne dane pracowników:

-   Numery identyfikacyjne
-   Kursy
-   Wykształcenie
-   Wizerunek
-   Wypożyczone elementy
-   Doświadczenie zawodowe
-   Doświadczenie w projekcie
-   Umiejętności
-   Stanowiska zaufania
-   Akcje zasobów ludzkich
-   Rejestracja kursu

Kiedy pracownicy są zatrudniony, przeniesiony lub zakończone, przepływ pracy może zawierać proces recenzji. W ten sposób można poddać przeglądowi dokumentu lub warunki działania można zdefiniować w ramach przepływu pracy. Po zakończeniu procesu przeglądu dokumentu lub akcja jest zakończona, a przepływ pracy przenosi do ostatniego etapu zatwierdzania.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Skojarzenie przepływu pracy z Hierarchia stanowisk
Przepływ pracy można skojarzyć z dowolną hierarchię, którą należy skonfigurować. Na przykład jeśli pozycja jest skojarzony z macierzy hierarchii raportowania, może skonfigurować przepływu pracy, który wydatków dla danego projektu do realizacji projektu zamiast Menedżer pracownika, który jest skojarzony z tym stanowiskiem. Aby utworzyć nowy przepływ pracy lub zmodyfikować istniejący przepływ pracy, na **przepływu pracy zasobów ludzkich** kliknij przycisk **nowy**. Wybierz przepływ pracy na liście, aby uruchomić projektanta przepływów pracy. Projektant służy do tworzenia nowego przepływu pracy lub zmieniać kolejności kroków w istniejącego przepływu pracy. Po zmianie istniejącego przepływu pracy, zmiany zostaną zapisane jako nowa wersja. W związku z tym możesz zawsze wrócić do poprzedniej wersji Jeśli trzeba.

## <a name="configure-a-human-resources-workflow"></a>Konfigurowanie przepływu pracy zasobów ludzkich
Aby skonfigurować podstawowy przepływ pracy, który jest uruchamiany, gdy pracownicy żądać wprowadzenia zmian do ich osobistej identyfikacji, wykonaj następujące kroki.

1.  Na **przepływów pracy modułu zasobów ludzkich** kliknij przycisk **nowy**.
2.  Na liście dostępnych przepływów pracy wybierz **numery identyfikacyjne**.
3.  Kliknij **uruchomić** Aby uruchomić projektanta przepływów pracy, a następnie wprowadź swoją nazwę użytkownika i hasło, gdy zostanie wyświetlony monit.
4.  Przeciągnij **zatwierdzić numer identyfikacyjny** element z listy elementów pracy do obszaru roboczego projektanta.
5.  Połączyć element zatwierdzania do **Start** i **Zakończ**.
6.  Kliknij dwukrotnie **Zatwierdź element**, a następnie kliknij prawym przyciskiem myszy, a następnie wybierz **właściwości**.
7.  Wykonaj następujące kroki, aby dodać instrukcje elementu pracy:
    1.  Wybierz **przydziału**, a następnie wybierz **hierarchii** w obszarze Typ przydziału.
    2.  Pod **hierarchii** zaznaczenie, wybierz **hierarchii można konfigurować**.
    3.  Dodaj warunek zatrzymania i zamknij stronę.

8.  Ukończ dodatkowymi instrukcjami (nie dodatkowych ostrzeżeń powinien istnieć).
9.  Kliknij przycisk **Zapisz i zamknij**. Uaktywnij nowy przepływ pracy, gdy okno dialogowe zostanie wyświetlone, a następnie wybierz **uaktywnić**.
10. Przejdź do **zasoby ludzkie**&gt;**pozycji**&gt;**pozycja typów hierarchii**.
11. Wybierz **macierzy**.
12. Dodaj **numer identyfikacyjny pracownika** przepływu pracy do listy.



