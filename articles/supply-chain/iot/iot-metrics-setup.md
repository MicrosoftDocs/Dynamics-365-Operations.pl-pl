---
title: Konfigurowanie metryk dla analizy Internetu rzeczy (IoT)
description: W tym artykule wyjaśniono, jak konfigurować metryki analizę Internetu rzeczy (IoT).
author: johanhoffmann
ms.date: 08/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fddfee837761a4f23b42257424582a3c76c3d493
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228336"
---
# <a name="set-up-metrics-for-iot-intelligence"></a>Konfigurowanie metryk dla analizy Internetu rzeczy (IoT)

[!include [banner](../../includes/banner.md)]
[!INCLUDE [iot-sdi-announcement](../../includes/iot-sdi-announcement.md)]

## <a name="configure-metrics"></a>Konfiguracja metryk

Aby wyświetlić wykresy szeregów czasowych komunikatów w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management, musisz skonfigurować metryki, wykonując następujące kroki.

1. Skopiuj parametry połączenia dla pamięci podręcznej Redis Cache:

    1. W portalu Azure, przejdź do pamięci podręcznej Redis Cache.
    2. Przejdź do **Ustawienia** \> **Klucze dostępu**.
    3. Skopiuj wartość w polu **Podstawowe parametry połączenia**.

2. W aplikacji Supply Chain Management przejdź do pozycji **Kontrola produkcji \> Ustawienia \> Analiza Internetu rzeczy (IoT) \> Parametry scenariuszy**.
3. Na stronie **Parametry scenariusza**, na karcie **Szereg czasowy** w polu **Parametry połączenia sklepu metryk Redis** wklej skopiowane wcześniej parametry połączenia. Ten krok umożliwia wizualizowanie metryk z centrum IoT Azure w rozwiązaniu Supply Chain Management. Wartość wklejana do pola jest pokazywana jako **\*\*\*\*\*\***.

    > [!NOTE]
    > Za każdym razem, gdy parametry połączenia pamięci podręcznej Redis Cachesą aktualizowane, musisz również zaktualizować to pole.

4. Przejdź do **Kontrola produkcji \> Zapytania i raporty \> Analiza IoT \> Klucze metryki**.
5. Na stronie **Klucze metryk** wybierz pozycję **Aktualizuj**.
6. W oknie dialogowym **Aktualizuj klucze metryczne** zwróć uwagę, że w tym polu jest wybrana opcja **Uruchom w tle**. Kliknij przycisk **OK**.

Wszystkie klucze metryczne w pamięci podręcznej Redis Cache są pobierane i dodawane do listy **Klucze metryk**. Wartości metryk nie będą wyświetlane, dopóki nie [włączysz scenariuszy](iot-scenario-setup.md).

## <a name="configure-the-resource-status-time-series"></a>Konfigurowanie szeregu czasowego stanu zasobów

Aby skonfigurować szereg czasowy **Stanu zasobów**, wykonaj następujące kroki.

1. W rozwiązaniu Supply Chain Management przejdź do stanu **Kontrola produkcji \> Wykonywanie produkcji \> Stan zasobów**.
2. Na stronie **Stan zasobów** wybierz opcję **Konfiguruj**.
2. W oknie dialogowym **Konfiguruj** na liście **Zasoby** wybierz element do monitorowania.
3. Wybierz przycisk **Edytuj** dla **Szeregu czasowego 1**.
4. W oknie dialogowym **Wybierz szereg czasowy** wybierz metrykę w siatce. (Można również użyć łącza **Aktualizuj klucze metryczne**, aby zaktualizować klucze metryczne z tego okna dialogowego.)
5. Wybierz przycisk **OK**, aby powrócić do okna dialogowego **Konfiguruj**.
6. Należy wprowadzić nazwę wyświetlaną.
7. W polu **Pokaż dane z** wybierz horyzont czasowy.
8. Kliknij przycisk **OK**.

Wykres jest pokazywany.

## <a name="delete-a-metric-key"></a>Usuwanie klucza metryki

1. W rozwiązaniu Supply Chain Management przejdź do **Kontrola produkcji \> Zapytania i raporty \> Analiza IoT \> Klucze metryki**.
2. Na stronie **Klucze metryczne** wybierz klucz metryczny, który chcesz usunąć.
3. Wybierz opcję **Usuń**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]