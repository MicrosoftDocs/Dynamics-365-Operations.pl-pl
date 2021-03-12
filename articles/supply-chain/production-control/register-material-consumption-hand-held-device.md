---
title: Rejestracja na urządzeniu przenośnym zużycia materiałów
description: W tym temacie opisano przepływ pracy umożliwiający rejestrowanie zużycia surowców w produkcji przy użyciu urządzenia przenośnego (podręcznego).
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 40779d1f8bc14072928767ae1c83fdda47476871
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998885"
---
# <a name="register-material-consumption-using-a-mobile-device"></a>Rejestracja na urządzeniu przenośnym zużycia materiałów

[!include [banner](../includes/banner.md)]

W tym temacie opisano przepływ pracy umożliwiający rejestrowanie zużycia surowców w produkcji przy użyciu urządzenia przenośnego (podręcznego).

<a name="introduction"></a>Wprowadzenie
------------

Ten przepływ pracy ma zastosowanie, jeśli istnieje ścisły wymóg identyfikowalności materiałów. W tych przypadkach w celu utrzymania identyfikowalności materiałów należy raportować dokładny czas i ilość zużycia. Ten proces może być traktowany jako przeciwieństwo operacji rozliczania wstępnego i wstecznego, gdzie występuje przesunięcie między czasem rejestracji a momentem, gdy dochodzi do faktycznego zużycia. To wyjaśnia, dlaczego strategii automatycznego zużycia nie można używać do niektórych materiałów z wymogiem identyfikowalności. Spójrzmy na prosty scenariusz, który wyjaśnia, jak skonfigurować przepływ pracy, aby włączyć rejestrowanie zużycia surowców w produkcji za pomocą urządzenia podręcznego. [![Konfigurowanie przepływu pracy w celu włączenie rejestracji zużycia surowców za pomocą urządzenia podręcznego](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a>Szczegóły scenariusza

W procesie produkcji ciągłej (5) jest zużywany surowiec RM-100 wchodzący w skład partii. Materiał jest dostępny w lokalizacji Bulk-001 (1) pod numerem identyfikacyjnym PL-1 w dwóch partiach B1 i B2, obu z ilością 100 kg. Dla surowca RM-100 jest zwalniana i przetwarzana praca magazynowa (2), a materiał zostaje pobrany z lokalizacji Bulk-001 do lokalizacji wejściowej produkcji PIL-01 (3), która jest zdefiniowana jako niekontrolowana przez numer identyfikacyjny. Operator maszyny waży materiał z lokalizacji wejściowej produkcji (3) i rejestruje masę oraz numer partii jako zużyte (4). Z lokalizacji wejściowej produkcji część materiału jest ręcznie dodawana do procesu produkcji w zdefiniowanych odstępach czasu. Gdy operator maszyny dodaje materiał, waży go na wadze i rejestruje numer partii.

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a>Konfigurowanie przepływu pracy rejestrowania zużycia przy użyciu urządzenia podręcznego
Utwórz wyrób gotowy FG-100 z listą składową zawierającą surowiec RM-100 wchodzący w skład partii. Doda dwie partie B1 i B2 surowca RM-100 w ilości 100 do lokalizacji Bulk-001 pod numerem identyfikacyjnym PL-1. Reguła rozliczania w wierszu listy składowej dla surowca RM-100 ma wartość **Ręcznie**. Jako lokalizację wejściową produkcji ustaw PIL-01. Można to zrobić przez zaznaczenie tej lokalizacji jako domyślnej lokalizacji wejściowej produkcji w magazynie 51.

1.  Utwórz nowy element menu w urządzeniu komórkowym: 

-    **Nazwa elementu menu** — Zarejestruj zużycie materiałów. 
-    **Tytuł** — Zarejestruj zużycie materiałów. 
-    **Tryb** — Pośrednie. 
-    **Kod działania** — Zarejestruj zużycie materiałów.

2.  Dodaj element menu do menu urządzenia komórkowego **Produkcja**.
3.  Utwórz zlecenie produkcyjne na wyrób gotowy: 

-    **Numer towaru** — FG-100 
-    **Oddział** — 5 
-    **Magazyn** — 51 
-    **Ilość** - 150

Zlecenie produkcyjne otrzymuje wartości atrybutów **Oszacowane** i **Zwolnione** oraz jest tworzona praca magazynu.

4.  Dokończ pracę przy użyciu przepływu pracy pobrania surowca na urządzeniu przenośnym.

To spowoduje przeniesienie materiału z lokalizacji zbiorczej do lokalizacji wejściowej produkcji PIL-01. Po zakończeniu pracy materiał otrzymuje stan **Pobrane w lokalizacji wejściowej produkcji**. Stan po przetworzeniu pracy może mieć wartość **Pobrane** lub **Fizycznie zarezerwowane**. To się konfiguruje przy użyciu parametru **Stan wydania po zapisaniu w formularzu magazynu**.

5.  Rozpocznij zlecenie produkcyjne z klienta lub z urządzenia przenośnego przy użyciu elementu menu **Rozpoczęcia produkcji**.

Po uruchomieniu zlecenia produkcyjnego można rejestrować zużycie materiału za pomocą przepływu pracy na urządzeniu podręcznym. Zacznijmy od zarejestrowania zużycia 25 kg z partii B1.

6.  Wybierz element menu **Zarejestruj zużycie** **materiałów** w menu na urządzeniu przenośnym i wprowadź następujące informacje: 

-    Numer zlecenia produkcyjnego. 
-    Lokalizacja, w której materiał będzie zużywany, w tym przypadku PIL-01. 
-    Numer towaru RM-100. 
-    Numer partii B1. 
-    Ilość 25.

7.  Kliknij przycisk **OK**.

Zwróć uwagę, że na ekranie pojawił się komunikat „Wiersz arkusza został utworzony”. W zleceniu produkcyjnym istnieje otwarty arkusz typu **Lista pobrania produkcji** dla towaru o numerze RM-100 i partii o numerze B1. 

Teraz możesz wybrać opcję kontynuowania rejestracji, na przykład partii o numerze B2. Po każdym kliknięciu przycisku **OK** zostanie dodany nowy wiersz arkusza do otwartego arkusza. 

Po zakończeniu rejestrowania kliknij przycisk **Gotowe**, aby zaksięgować arkusz i zakończyć przepływ pracy.

### <a name="additional-comments"></a>Dodatkowe uwagi 

-   Jeśli użytkownik anuluje przepływ pracy po utworzeniu wiersza arkusza, arkusz jest w stanie niezaksięgowania, ale jeśli użytkownik później użyje przepływu pracy do tego samego zlecenia produkcyjnego, wiersze zostaną dodane do otwartego arkusza, a nie do nowego arkusza.
-   Nowy przepływ pracy umożliwia również rejestrowanie numerów seryjnych.
-   Można zarejestrować tylko kod towaru zdefiniowany na liście składowej lub w formule dla wybranego zlecenia produkcyjnego lub szarży produkcyjnej.
-   Materiał może być zużywany ponad miarę. Na przykład jeśli szacuje się, że materiał zostanie zużyty w ilości 100 kg, można go zużyć ponad miarę, na przykład w ilości 105 kg.


