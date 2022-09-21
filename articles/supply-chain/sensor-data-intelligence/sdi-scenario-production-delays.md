---
title: Scenariusz opóźnień produkcji
description: W tym artykule opisano scenariusz opóźnień produkcji, który generuje powiadomienie, jeśli przepływność produkcji spadnie poniżej określonej wartości progowej.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 073762581d84646ba12b570e57327b7cab8efd3b
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428422"
---
# <a name="the-production-delays-scenario"></a>Scenariusz opóźnień produkcji

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Scenariusz *opóźnień produkcji* generuje powiadomienie, jeśli przepływność produkcji spadnie poniżej określonej wartości progowej. W tym scenariuszu sygnał *uszkodzona część* jest wysyłany do usługi IoT Hub Microsoft Azure dla każdej produkowanej pozycji. W Dynamics 365 Supply Chain Management opóźnienie jest obliczane na podstawie czasu, w jakim ma być uruchomione zlecenia produkcyjne, liczby towarów, które powinny zostać wyprodukowane, ilości czasu, przez jaki zadanie jest wykonywane oraz liczby odebranych sygnałów *uszkodzona część*. Powiadomienie o opóźnieniu jest generowane, jeśli liczba sygnałów *uszkodzona część* dla zadania spadnie poniżej wartości progowej.

## <a name="scenario-dependencies"></a>Zależności scenariusza

Scenariusz *Opóźnienia produktu* obejmuje następujące zależności:

- Alertu na mapowanym urządzeniu może zostać uruchomiony tylko, jeśli uruchomione jest zlecenie produkcyjne na zamapowanej maszynie.
- Sygnał reprezentujący *uszkodzenie części* mapowanego urządzenia musi zostać wysłany do usługi IoT Hub i musi być zastosowana unikatowa nazwa właściwości.
- Sygnatura czasowa UNIX, gdzie wartość jest wyrażona w milisekundach (MS), musi być obecna w komunikacie Azure IoT Hub.

## <a name="prepare-demo-data-for-the-product-delays-scenario"></a>Przygotuj dane demonstracyjne do scenariuszy opóźnienia produktu

Jeśli chcesz użyć systemu demonstracyjnego do przetestowania scenariusza *opóźnień produkcji*,użyj systemu, w którym zainstalowano [dane demonstracyjne](../../fin-ops-core/fin-ops/get-started/demo-data.md), wybierz osobę prawną *USMF* (firma) i przygotuj dodatkowe dane demonstracyjne zgodnie z opisem w tej sekcji. Jeśli korzystasz z własnych czujników i danych, możesz pominąć tę sekcję.

### <a name="set-up-sensor-simulator"></a>Ustawianie symulatora czujnika

Aby spróbować tego scenariusza bez używania fizycznego czujnika, można skonfigurować symulator, aby generował wymagane sygnały. Aby zapoznać się z dodatkowymi informacjami, zobacz [Konfigurowanie symulowanego czujnika do testowania](sdi-set-up-simulated-sensor.md).

### <a name="verify-that-resource-3118-is-used-for-product-p0111"></a>Sprawdź, czy dla produktu P0111 jest używany zasób 3118

Zlecenie produkcyjne zostanie zaplanowane i zwolnione. W związku z tym zadanie produkcyjne jest zwalniane do zasobu *3118* (*Maszyna do cięcia piany*). Wykonaj te kroki, aby sprawdzić, czy w danych demonstracyjnych dla produktu *P0111* jest używany zasób *3118*.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Znajdź i wybierz produkt, dla którego pole **Kod pozycji** ma wartość *P0111*.
1. W okienku akcji na karcie **Konstruuj** w grupie **Widok** wybierz opcję **Marszruta**.
1. Na stronie **Marszruta**, na karcie **Przegląd** u dołu strony wybierz wiersz, w którym pole **Numer oper.** jest ustawione na *30*.
1. Na karcie **Wymagania dotyczące zasobów** u dołu strony upewnij się, że z operacją jest skojarzony zasób *3118* (*Maszyna do cięcia piany*).

### <a name="create-and-release-a-production-order-for-product-p0111"></a>Utwórz i zwolnij zlecenie produkcyjne dla produktu P0111

Aby utworzyć i zwolnić zlecenie produkcyjne dla produktu *P0111*, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne**.
1. Na stronie **Wszystkie zlecenia produkcyjne** w okienku akcji wybierz pozycję **Nowe zamówienie partii**.
1. W oknie dialogowym **Utwórz partię** ustaw następujące wartości:

    - **Numer pozycji:** *P0111*
    - **Ilość:** *10*

1. Wybierz opcję **Utwórz**, aby utworzyć zamówienie i wrócić do strony **Wszystkie zlecenia produkcyjne**.
1. Pole **Filtruj** umożliwia wyszukiwanie zleceń produkcyjnych, dla których pole **Numer towaru** ma wartość *P0111*. Następnie znajdź i zaznacz zlecenie produkcyjne, która właśnie zostało utworzone.
1. W okienku akcji na karcie **Zlecenie produkcyjne** w grupie **Proces** wybierz opcję **Szacowanie**.
1. W wyświetlonym oknie dialogowym **Szacuj** wybierz przycisk **OK**, aby uruchomić szacowanie.
1. W okienku akcji na karcie **Zlecenie produkcyjne** w grupie **Proces** wybierz opcję **Zwolnij**.
1. W oknie dialogowym **Zwolnij** zanotuj numer utworzonego zamówienia partii.
1. Kliknij przycisk **OK**, aby zwolnić zamówienie.

### <a name="configure-the-production-floor-execution-interface"></a>Konfigurowanie interfejsu wykonania hal produkcyjnych

Jeśli jeszcze tego nie zrobiono, należy skonfigurować interfejs hali produkcyjnej, aby pokazać zadania przypisane do zasobu *3118* (*Maszyna do cięcia piany*). Instrukcje znajdziesz w następnych sekcjach:

- [Konfigurowanie interfejsu wykonania hal produkcyjnych](sdi-scenario-equipment-downtime.md#config-pfe)
- [Włącz opcję wyszukiwania dla interfejsu wykonania hal produkcyjnych](sdi-scenario-equipment-downtime.md#enable-pfe-search)

### <a name="start-the-first-job-in-the-batch-order"></a>Rozpoczęcie pierwszego zadania w zamówieniu partii

Aby rozpocząć pierwsze zadanie w zamówieniu partii, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Kontrola produkcji \> Wykonywanie produkcji \> Tworzenie hal produkcyjnych**.
1. W polu **Identyfikator karty identyfikacyjnej** wpisz *123*. Następnie kliknij przycisk **Zaloguj**.
1. Jeśli zostanie wyświetlony monit z powodu nieobecności, wybierz jedną z kart nieobecności, a następnie wybierz przycisk **OK**.
1. W polu **Wyszukiwanie** wprowadź numer zamówienia partii, dla który wcześniej zanotowano. Następnie wybierz klucz **Zwrot**.
1. Wybierz zamówienie sprzedaży, a następnie wybierz **Rozpocznij zadanie**.
1. W oknie dialogowym **Rozpocznij zadanie** wybierz pozycję **Rozpocznij**.

## <a name="set-up-the-production-delays-scenario"></a>Ustaw scenariusz opóźnień produkcji

Wykonaj następujące kroki, aby skonfigurować scenariusz *opóźnień produkcji* w rozwiązaniu Supply Chain Management.

1. Przejdź do **Kontrola produkcji \> Konfiguracja \> Sensor Data Intelligence \> Scenariusze**.
1. W polu **Scenariusz opóźnień** produkcji wybierz opcję **Konfiguruj**, aby otworzyć kreatora ustawień tego scenariusza.
1. Na stronie **Czujniki**, w okienku akcji wybierz opcję **Nowy**, aby dodać nowy czujnik do siatki. Następnie ustaw dla niego następujące pola:

    - **Identyfikator czujnika** — służy do wprowadzania identyfikatora używanego czujnika. (Jeśli używasz symulatora online Raspberry Pi z Azure IoT i jest on skonfigurowany jako opisano w [Konfigurowanie symulowanego czujnika do testowania](sdi-set-up-simulated-sensor.md), wprowadź *ProductionDelay*).
    - **Opis czujnika** – wprowadź szczegółowy opis czujnika.

1. Powtórz poprzedni krok dla każdego dodatkowego czujnika, który chcesz teraz dodać. W każdej chwili możesz wrócić i dodać więcej czujników.
1. Wybierz pozycję **Następny**.
1. Na stronie **Mapowanie rekordu biznesowego**, w sekcji **Czujniki** zaznacz rekord dla jednego z dodanych czujników.
1. W sekcji **Mapowanie rekordów biznesowych** wybierz pozycję **Nowy**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw **Rekord biznesowy** na zasób, który jest monitorowany przez czujnik. (Jeśli używasz danych demonstracyjnych utworzonych wcześniej w tym artykule, ustaw dla niego wartość *3118, Maszyna do cięcia piany*).
1. Wybierz pozycję **Następny**.
1. Na stronie **Próg odchylenia opóźnienia produkcji**, jeśli używasz danych demonstracyjnych utworzonych wcześniej w tym artykule, wykonaj następujące kroki:

    1. Wybierz nagłówek kolumny **Relacja produktu**, aby otworzyć okno dialogowe z filtrami wyszukiwania dla kolumny. Wprowadź wartość *P0111* w polu wyszukiwania, a następnie wybierz pozycję **Zastosuj**.
    2. Znajdź wiersz, w którym pole o nazwie **Operacja** ma wartość *Przytnij/utnij*. Ustaw **Próg powiadamiania dla opóźnienia (%)** na próg (w procentach), do którego powinno zostać wysłane powiadomienie.

1. Wybierz pozycję **Następny**.
1. Na stronie **Aktywuj czujniki** w siatce zaznacz dodany czujnik, a następnie wybierz opcję **Aktywuj**. Dla każdego aktywowanego czujnika w siatce w kolumnie **Aktywne** jest wyświetlany znacznik wyboru.
1. Wybierz **Zakończ**.

## <a name="work-with-the-production-delays-scenario"></a>Praca ze scenariuszem opóźnień produkcji

### <a name="view-production-delay-data-on-the-resource-status-page"></a>Wyświetlanie danych o opóźnieniu produkcji na stronie Stan zasobu

Na stronie **Stan zasobu** przełożeni mogą monitorować oś czasu sygnałów odebranych z czujników zamapowanych na poszczególne zasoby maszynowe. Wykonaj poniższe czynności, aby skonfigurować oś czasu.

1. Wybierz kolejno opcje **Kontrola produkcji \> Wykonanie produkcji \> Stan zasobu**.
1. W oknie dialogowym **Konfiguruj** ustaw następujące pola:

    - **Zasób** — wybierz zasoby, które chcesz monitorować. (Jeśli używasz danych demonstracyjnych, wybierz opcję *3118*).
    - **Szereg czasowy 1** — wybierz rekord (klucz metryczny), który ma następujący format dla swojej nazwy: *ProductionJobDelayed:ActualQuantity:&lt;JobId&gt;*
    - **Nazwa wyświetlana** — należy wprowadzić *Sygnał uszkodzonych części*.
