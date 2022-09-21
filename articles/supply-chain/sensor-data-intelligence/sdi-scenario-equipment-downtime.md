---
title: Scenariusz stanu maszyny
description: W tym artykule opisano scenariusz stanu maszyny, który umożliwia używanie danych czujnika w celu monitorowania dostępności sprzętu.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreNotification, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 1f2b424dccf1963a7917059d412b5df7937496ee
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428411"
---
# <a name="the-machine-status-scenario"></a>Scenariusz stanu maszyny

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Scenariusz *stanu maszyny* umożliwia używanie danych czujnika w celu monitorowania dostępności sprzętu. Jeśli zostanie ustawiony czujnik, który wysyła sygnał, gdy zadanie produkcyjne zasobu maszynowego powoduje produkcję wyjściową, ale w określonym czasie nie odebrano żadnego sygnału czujnika, na pulpicie nawigacyjnym kierownika jest wyświetlane powiadomienie.

## <a name="scenario-dependencies"></a>Zależności scenariusza

Scenariusz *stanu maszyny* obejmuje następujące zależności:

- Powiadomienie na mapowanej maszynie może zostać uruchomione tylko, jeśli uruchomione jest zadanie produkcyjne na zamapowanej maszynie.
- Do centrum IoT Hub musi zostać wysłany sygnał reprezentujący *uszkodzoną część*.

## <a name="prepare-demo-data-for-the-machine-status-scenario"></a>Przygotuj dane demonstracyjne do scenariuszy stanu maszyny

Jeśli chcesz użyć systemu demonstracyjnego do przetestowania scenariusza *stanu maszyny*, użyj systemu, w którym zainstalowano [dane demonstracyjne](../../fin-ops-core/fin-ops/get-started/demo-data.md), wybierz osobę prawną *USMF* (firma) i przygotuj dodatkowe dane demonstracyjne zgodnie z opisem w tej sekcji. Jeśli korzystasz z własnych czujników i danych, możesz pominąć tę sekcję.

### <a name="set-up-a-sensor-simulator"></a>Ustawianie symulatora czujnika

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

### <a name="configure-the-production-floor-execution-interface"></a><a name="config-pfe"></a>Konfigurowanie interfejsu wykonania hal produkcyjnych

Za pomocą interfejsu wykonania hali produkcyjnej można rozpocząć zadanie, które zostało zaplanowane i zwolnione dla towaru o numerze *P0111* w poprzedniej sekcji. Postępuj zgodnie z tymi krokami, by skonfigurować interfejs wykonania hal produkcyjnych.

1. Wybierz kolejno opcje **Kontrola produkcji \> Wykonywanie produkcji \> Tworzenie hal produkcyjnych**.
1. Jeśli interfejs nie został jeszcze ustawiony, zostanie wyświetlona strona logowania. Wprowadź swoje poświadczenia.
1. Na stronie powitania wybierz pozycję **Konfiguruj**, aby otworzyć kreatora **konfigurowania urządzeń**.
1. Na stronie **Konfiguruj urządzenie — krok 1 — Wybierz konfigurację**, wybierz konfigurację *Domyślną*.
1. Wybierz pozycję **Następny**.
1. Na stronie **Konfiguruj konfigurację — krok 2 — określ obszar hali produkcyjnej** ustaw wartość w polu **Zasób** na *3118*.
1. Kliknij przycisk **OK**.

### <a name="enable-the-search-option-in-the-production-floor-execution-interface"></a><a name="enable-pfe-search"></a>Włącz opcję wyszukiwania w interfejsie wykonania hal produkcyjnych

Aby ułatwić znalezienie zadania produkcyjnego dla zlecenia produkcyjnego wydanego wcześniej, wykonaj poniższe kroki, aby włączyć opcję wyszukiwania w interfejsie wykonania hali produkcyjnej.

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Wykonywanie produkcji \> Konfigurowanie interfejsu wykonania hal produkcyjnych**.
1. Wybierz *Domyślną* konfigurację.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Ogólne** ustaw opcje **Włącz wyszukiwanie** na *Tak*.
1. Zamknij stronę.

### <a name="start-the-first-job-in-the-batch-order"></a>Rozpoczęcie pierwszego zadania w zamówieniu partii

Aby rozpocząć zadanie zaplanowane na zasobie *3118*, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Kontrola produkcji \> Wykonywanie produkcji \> Tworzenie hal produkcyjnych**.
1. W polu **Identyfikator karty identyfikacyjnej** wpisz *123*. Następnie kliknij przycisk **Zaloguj**.
1. Jeśli zostanie wyświetlony monit z powodu nieobecności, wybierz jedną z kart nieobecności, a następnie wybierz przycisk **OK**.
1. W polu **Wyszukiwanie** wprowadź numer zamówienia partii, dla który wcześniej zanotowano. Następnie wybierz klucz **Zwrot**.
1. Wybierz zamówienie sprzedaży, a następnie wybierz **Rozpocznij zadanie**.
1. W oknie dialogowym **Rozpocznij zadanie** wybierz pozycję **Rozpocznij**.

## <a name="set-up-the-machine-status-scenario"></a>Ustaw scenariusz stanu maszyny

Wykonaj następujące kroki, aby skonfigurować scenariusz *stanu maszyny* w rozwiązaniu Supply Chain Management.

1. Przejdź do **Kontrola produkcji \> Konfiguracja \> Sensor Data Intelligence \> Scenariusze**.
1. W polu **Stan maszyny** produkcji wybierz opcję **Konfiguruj**, aby otworzyć kreatora ustawień tego scenariusza.
1. Na stronie **Czujniki**, w okienku akcji wybierz opcję **Nowy**, aby dodać nowy czujnik do siatki. Następnie ustaw dla niego następujące pola:

    - **Identyfikator czujnika** — służy do wprowadzania identyfikatora używanego czujnika. (Jeśli używasz symulatora online Raspberry Pi z Azure IoT i jest on skonfigurowany jako opisano w [Konfigurowanie symulowanego czujnika do testowania](sdi-set-up-simulated-sensor.md), wprowadź *MachineStatus*).
    - **Opis czujnika** – wprowadź szczegółowy opis czujnika.

1. Powtórz poprzedni krok dla każdego dodatkowego czujnika, który chcesz teraz dodać. W każdej chwili możesz wrócić i dodać więcej czujników.
1. Wybierz pozycję **Następny**.
1. Na stronie **Mapowanie rekordu biznesowego**, w sekcji **Czujniki** zaznacz rekord dla jednego z dodanych czujników.
1. W sekcji **Mapowanie rekordów biznesowych** wybierz pozycję **Nowy**, aby dodać wiersz do siatki.
1. W nowym wierszu ustaw pole **Rekord biznesowy** na zasób, który jest monitorowany przez czujnik. (Jeśli używasz danych demonstracyjnych utworzonych wcześniej w tym artykule, ustaw dla pola wartość *3118, Maszyna do cięcia piany*).
1. Wybierz pozycję **Następny**.
1. Na stronie **Próg stanu maszyny** określ, jak długo po sygnale *uszkodzonej części* system powinien wysłać powiadomienie o stanie maszyny. Istnieją dwa sposoby do określenia progu:

    - **Domyślny próg (w minutach)** — to pole należy ustawić w celu zdefiniowania domyślnego progu. Ta wartość będzie obowiązywać wszystkie zasoby, w których wartość pola **Próg do określenia braku odpowiedzi z maszyny (minuty)** jest ustawiona na dwie minuty lub mniej. Wartość minimalna to *2* (minuty).
    - **Próg określający, czy maszyna nie odpowiada (minuty)** — dla każdego zasobu w siatce, dla którego nie chcesz używać domyślnego progu, wprowadź wartość zastąpienia w tym polu. Zasoby, dla których ustawiono użycie progu co najmniej dwóch minut, użyją zamiast tego ustawienia **Próg domyślny (minuty)**.

    > [!NOTE]
    > Zazwyczaj do monitorowania stanu maszyny jest używany sygnał *uszkodzona część*. Dlatego należy sprawdzić, czy próg dla każdego zasobu maszynowego jest dłuższy niż wymagany do wyprodukowania każdej części.

1. Wybierz pozycję **Następny**.
1. Na stronie **Aktywuj czujniki** w siatce zaznacz dodany czujnik, a następnie wybierz opcję **Aktywuj**. Dla każdego aktywowanego czujnika w siatce w kolumnie **Aktywne** jest wyświetlany znacznik wyboru.
1. Wybierz **Zakończ**.

## <a name="work-with-the-machine-status-scenario"></a>Praca ze scenariuszem stanu maszyny

Po zainstalowaniu czujników i skonfigurowaniu scenariusza można wyświetlić zdarzenia stanu maszyny w rozwiązaniu Supply Chain Management. W tej sekcji opisano miejsce i sposób wyświetlania tych informacji.

### <a name="view-machine-status-data-on-the-resource-status-page"></a>Wyświetlanie danych stanu maszyny na stronie Stan zasobu

Na stronie **Stan zasobu** przełożeni mogą monitorować oś czasu sygnału *uszkodzona część*, który jest odbierany z czujników zamapowanych na poszczególne zasoby maszynowe. Wykonaj poniższe czynności, aby skonfigurować oś czasu.

1. Wybierz kolejno opcje **Kontrola produkcji \> Wykonanie produkcji \> Stan zasobu**.
1. W oknie dialogowym **Konfiguruj** ustaw następujące pola:

    - **Zasób** — wybierz zasoby, które chcesz monitorować. (Jeśli używasz danych demonstracyjnych, wybierz opcję *3118*).
    - **Szereg czasowy 1** — wybierz rekord (klucz metryczny), który ma następujący format dla swojej nazwy: *MachineReportingStatus:&lt;Sensor&gt;*
    - **Nazwa wyświetlana** — należy wprowadzić *Sygnał uszkodzonych części*.

Na poniższej ilustracji pokazano przykład danych o stanie maszyny na stronie **Stan zasobu** podczas standardowej operacji.

![Dane stanu maszyny na stronie Stan zasobu podczas standardowej operacji.](media/sdi-resource-status-downtime-up.png "Dane stanu maszyny na stronie Stan zasobu podczas standardowej operacji")

Na poniższej ilustracji pokazano przykład danych o stanie maszyny w przypadku wykrycia przestoju.

![Dane stanu maszyny na stronie Stan zasobu w przypadku wykrycia przestoju.](media/sdi-resource-status-downtime-down.png "Dane stanu maszyny na stronie Stan zasobu w przypadku wykrycia przestoju")

### <a name="view-machine-status-on-the-notifications-page"></a>Wyświetl stan maszyny na stronie Powiadomienia

Na stronie **Powiadomienia** przełożeni mogą wyświetlać powiadomienia wygenerowane w przypadku zbyt dużo czasu upłynęło od czasu ostatniego dostarczenia sygnału *uszkodzona część*. Każde powiadomienie umożliwia przegląd zadania produkcyjnego, na które ma wpływ ten przestój i daje możliwość ponownego przypisania tego zadania do innego zasobu.

Aby otworzyć stronę **Powiadomienia**, przejdź do **Kontrola produkcji \> Zapytania i raporty \> Sensor Data Intelligence \> Powiadomienia**.

Na poniższej ilustracji pokazano przykład powiadomienia o stanie maszyny.

![Przykład powiadomienia o stanie maszyny.](media/sdi-resource-status-downtime-notification.png "Przykład powiadomienia o stanie maszyny")
