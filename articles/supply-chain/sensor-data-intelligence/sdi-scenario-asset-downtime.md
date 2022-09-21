---
title: Scenariusz przestoju składnika majątku
description: W tym artykule opisano scenariusz przestoju maszyny, który umożliwia używanie danych czujnika w celu monitorowania dostępności składnika majątku.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetObjectProductionStop
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 944818557deebed06c02c00fd69de6e8f08bda83
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428453"
---
# <a name="the-asset-downtime-scenario"></a>Scenariusz przestoju składnika majątku

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Scenariusz przestoju składnika majątku generuje rekord przestoju konserwacyjnego, jeśli nie odebrano żadnego sygnału z maszyny w zdefiniowanym czasie progowym od czasu od ostatniego odebranego sygnału. Scenariusz wymaga, aby maszyna została dopasowana do czujnika, który co pewien czas wysyła sygnał do usługi Azure IoT Hub w trakcie działania maszyny, ale nie wysyła sygnału, gdy maszyna nie działa.

## <a name="set-up-the-asset-downtime-scenario"></a>Ustaw scenariusz przestoju składnika majątku

Wykonaj następujące kroki, aby skonfigurować scenariusz *przestoju składnika majątku* w rozwiązaniu Supply Chain Management.

1. Przejdź do **Zarządzanie składnikami majątku \> Konfiguracja \> Sensor Data Intelligence \> Scenariusze**, aby otworzyć stronę **Scenariusze**.
2. W polu **Przestój składnika majątku** produkcji wybierz opcję **Konfiguruj**, aby otworzyć kreatora ustawień tego scenariusza.
3. Na stronie **Czujniki**, w okienku akcji wybierz opcję **Nowy**, aby dodać nowy czujnik do siatki. Następnie ustaw dla niego następujące pola:

    - **Identyfikator czujnika** — służy do wprowadzania identyfikatora używanego czujnika. (Jeśli używasz symulatora online Raspberry Pi z Azure IoT i jest on skonfigurowany jako opisano w [Konfigurowanie symulowanego czujnika do testowania](sdi-set-up-simulated-sensor.md), wprowadź *AssetDownTime*).
    - **Opis czujnika** – wprowadź szczegółowy opis czujnika.

4. Powtórz poprzedni krok dla każdego dodatkowego czujnika, który chcesz teraz dodać. W każdej chwili możesz wrócić i dodać więcej czujników.
5. Wybierz pozycję **Następny**.
6. Na stronie **Mapowanie rekordu biznesowego**, w sekcji **Czujniki** zaznacz rekord dla jednego z dodanych czujników.
7. W sekcji **Mapowanie rekordów biznesowych** wybierz pozycję **Nowy**, aby dodać wiersz do siatki.
8. W nowym wierszu ustaw pole **Rekord biznesowy** na zasób, który jest monitorowany przez czujnik. (Jeśli używasz danych demonstracyjnych, wybierz opcję *AK-101, nóż powietrzny dla wiersza 1*.)
9. Wybierz pozycję **Następny**.
10. Na stronie **progu przestoju składnika majątku** określ, jak długo po zakończeniu ostatniego wysyłania powiadomień o przestój składnika majątku system powinien czekać. Istnieją dwa sposoby do określenia progu:

    - **Domyślny próg (w minutach)** — to pole należy ustawić w celu zdefiniowania domyślnego progu. Ta wartość dotyczy wszystkich zasobów, dla których wartość pola **Próg powiadomienia (minuty)** jest ustawiona na dwie minuty lub mniej. Wartość minimalna to *2* (minuty).
    - **Próg określający, czy maszyna nie odpowiada (minuty)** — dla każdego zasobu w siatce, dla którego nie chcesz używać domyślnego progu, wprowadź wartość zastąpienia w tym polu. Zasoby, dla których ustawiono użycie progu co najmniej dwóch minut, użyją zamiast tego ustawienia **Próg domyślny (minuty)**.
11. Wybierz pozycję **Następny**.
12. Na stronie **Aktywuj czujniki** w siatce zaznacz skonfigurowany czujnik, a następnie wybierz opcję **Aktywuj**. Dla każdego aktywowanego czujnika w siatce w kolumnie **Aktywne** jest wyświetlany znacznik wyboru.
13. Wybierz **Zakończ**.

## <a name="work-with-the-asset-downtime-scenario"></a>Praca ze scenariuszem przestoju składnika majątku

Jeśli nie odebrano żadnego sygnału ze składnika majątku w progu zdefiniowanego w konfiguracji scenariusza, system utworzy rekord przestoju konserwacyjnego dla tego składnika majątku. Menedżerowie powinni okresowo przeglądać rekordy przestojów (na przykład raz na każdej zmianie) i stosować odpowiednie kody przyczyn i godziny zakończenia każdej rejestracji przestoju. Aby wyświetlić rekordy przestoju konserwacyjnego składnika majątku, należy wykonać następujące kroki:

1. Wybierz **Zarządzanie składnikami majątku > Składniki majątku > Wszystkie składniki majątku**.
2. Odszukaj i zaznacz składnik majątku, który chcesz zbadać. (Jeśli używasz danych demonstracyjnych, wybierz opcję *AK-101*).
3. W okienku akcji otwórz kartę **Składnik majątku** i w grupie **Zlecenia pracy** wybierz pozycję **Przestoje konserwacji**,aby otworzyć stronę z rekordami przestoju konserwacji wybranego składnika majątku.
