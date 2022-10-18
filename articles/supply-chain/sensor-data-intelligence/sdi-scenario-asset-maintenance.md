---
title: Scenariusz konserwacji składnika majątku
description: W tym artykule opisano scenariusz konserwacji składnika majątku, który umożliwia używanie danych czujnika w celu tworzenia rekordów liczników, które śledzą użycie zasobu maszyny.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: fcd16d09b4293046c457b602857ef8950e8259c6
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644065"
---
# <a name="the-asset-maintenance-scenario"></a>Scenariusz konserwacji składnika majątku

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Scenariusz *konserwacji składnika majątku* umożliwia tworzenie rekordów liczników przy użyciu danych czujnika. Rekordy liczników śledzą użycie zasobu maszyny i są używane jako dane wejściowe do generowania harmonogramu konserwacji składnika majątku.

## <a name="video-instructions"></a>Instrukcje wideo

Poniższy film pokazuje, jak konfigurować i wypróbować scenariusz konserwowanego składnika majątku, używając standardowych [danych demonstracyjnych](../../fin-ops-core/fin-ops/get-started/demo-data.md). Pozostałe sekcje tego artykułu zawierają te same instrukcje w formacie tekstowym.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE58aRW]

## <a name="prepare-demo-data-for-the-asset-maintenance-scenario"></a>Przygotuj dane demonstracyjne do scenariuszy konserwacji składnika majątku

Jeśli chcesz użyć systemu demonstracyjnego do przetestowania scenariusza *konserwacji składnika majątku*, użyj systemu, w którym zainstalowano [dane demonstracyjne](../../fin-ops-core/fin-ops/get-started/demo-data.md), wybierz osobę prawną *USMF* (firma) i przygotuj dodatkowe dane demonstracyjne zgodnie z opisem w tej sekcji. Jeśli korzystasz z własnych czujników i danych, możesz pominąć tę sekcję.

W tej sekcji zostanie przykładowo ustawiony w danych demonstracyjnych składnik majątku *AK-101, nóż powietrzny*. Pozwoli to zobaczyć, jak można przewidzieć nadchodzące prace konserwacyjne na podstawie sygnałów czujników, które mierzą liczbę godzin pracy noża powietrznego. Zostanie również ustawiony plan konserwacji, w którym nóż powietrzny będzie konserwowany co 10 000 godzin.

### <a name="set-up-a-sensor-simulator"></a>Ustawianie symulatora czujnika

Aby spróbować tego scenariusza bez używania fizycznego czujnika, można skonfigurować symulator, aby generował wymagane sygnały. Aby zapoznać się z dodatkowymi informacjami, zobacz [Konfigurowanie symulowanego czujnika do testowania](sdi-set-up-simulated-sensor.md).

### <a name="create-an-asset-counter-to-track-production-hours"></a>Tworzenie licznika składnika majątku w celu śledzenia godzin produkcji

Postępuj zgodnie z tymi krokami, by utworzyć licznik składnika majątku w celu śledzenia godzin produkcji.

1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Ustawienia \> Typy składników majątku \> Liczniki**.
1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć licznik.
1. W nagłówku ustaw następujące wartości:

    - **Licznik:** *ProductionHr*
    - **Nazwa:** *Godziny produkcji*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Jednostka:** *godz.*
    - **Aktualizacja:** *ręczna*
    - **Agregacja sumy:** *suma*

1. Na skróconej karcie **Typy składnika majątku**, należy wybrać przycisk **Dodaj wiersz**.
1. W nowym wierszu ustaw w polu **Typ składnika majątku** wartość *Nóż powietrzny*.

### <a name="create-a-maintenance-plan-for-the-asset"></a>Tworzenie planu konserwacji składnika majątku

Postępuj zgodnie z krokami, aby utworzyć plan konserwacji dla składnika majątku.

1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Konfiguracja \> Konserwacja zapobiegawcza \> Plan konserwacji**.
1. W okienku akcji wybierz opcję **Nowy**, aby utworzyć nowy plan konserwacji.
1. W nagłówku ustaw następujące wartości:

    - **Plan konserwacji:** *AirKnife*
    - **Nazwa:** *plan dla noży powietrznych*

1. Na skróconej karcie **Szczegóły** ustaw następujące wartości:

    - **Data planu:** wprowadź datę dzisiejszą.
    - **Aktywne:** *Tak*

1. Na skróconej karcie **Wiersze** wybierz **Dodaj wiersz licznika składnika majątku**, aby dodać wiersz do siatki. Następnie określ dla niego następujące wartości:

    - **Opis zlecenia pracy:** *Konserwacja dla noży powietrznych*
    - **Typ zadania konserwacji:** *Prewencyjne*
    - **Typ interwału:** *Powtórzone od ostatniego zlecenia pracy*
    - **Częstotliwość okresu:** *10000*
    - **Licznik:** *ProductionHr*

## <a name="set-up-the-asset-maintenance-scenario"></a>Ustaw scenariusz konserwacji składnika majątku

Wykonaj następujące kroki, aby skonfigurować scenariusz *konserwacji składnika majątku* w rozwiązaniu Supply Chain Management.

1. Przejdź do **Zarządzanie składnikami majątku \> Konfiguracja \> Sensor Data Intelligence \> Scenariusze**.
1. W polu **Zarządzanie składnikami majątku** produkcji wybierz opcję **Konfiguruj**, aby otworzyć kreatora ustawień tego scenariusza.
1. Na stronie **Czujniki**, w okienku akcji wybierz opcję **Nowy**, aby dodać nowy czujnik do siatki. Następnie ustaw dla niego następujące pola:

    - **Identyfikator czujnika** — służy do wprowadzania identyfikatora używanego czujnika. (Jeśli używasz symulatora online Raspberry Pi z Azure IoT i jest on skonfigurowany jako opisano w [Konfigurowanie symulowanego czujnika do testowania](sdi-set-up-simulated-sensor.md), wprowadź *AssetMaintenance*).
    - **Opis czujnika** – wprowadź szczegółowy opis czujnika.

1. Powtórz poprzedni krok dla każdego dodatkowego czujnika, który chcesz teraz dodać. W każdej chwili możesz wrócić i dodać więcej czujników.
1. Wybierz pozycję **Następny**.
1. Na stronie **Mapowanie rekordu biznesowego**, w sekcji **Czujniki** zaznacz rekord dla jednego z dodanych czujników.
1. W sekcji **Mapowanie rekordów biznesowych** wybierz pozycję **Nowy**, aby dodać wiersz do siatki.
1. W nowym wierszu pole **Typ rekordu biznesowego** powinno być automatycznie ustawione na *Zasoby(EntAssetObjectTable)*. Ustaw pole **Rekord biznesowy** na zasób, który jest monitorowany przez czujnik. (Jeśli używasz danych demonstracyjnych utworzonych wcześniej w tym artykule, ustaw dla niego wartość *AK-101, AK-101 nóż powietrzny dla wiersza 1*).
1. Bezpośrednio po wybraniu typu rekordu biznesowego dla wiersza dodanego w poprzednim kroku do siatki zostanie automatycznie dodany drugi wiersz. W tym wierszu pole **Typ rekordu biznesowego** powinno mieć wartość *Liczniki(EntAssetCounterType)*. Ustaw pole **Rekord biznesowy** na licznik składnika majątku, który jest aktualizowany na podstawie sygnału z wybranego czujnika. (Jeśli używasz danych demonstracyjnych utworzonych wcześniej w tym artykule, ustaw dla niego wartość *ProductionHr, Godziny produkcji*).
1. Wybierz pozycję **Następny**.
1. Na stronie **Aktywuj czujniki** w siatce zaznacz dodany czujnik, a następnie wybierz opcję **Aktywuj**. Dla każdego aktywowanego czujnika w siatce w kolumnie **Aktywne** jest wyświetlany znacznik wyboru.
1. Wybierz **Zakończ**.

## <a name="work-with-the-asset-maintenance-scenario"></a>Praca ze scenariuszem konserwacji składnika majątku

### <a name="view-counter-values"></a>Wyświetl wartości licznika

Po przygotowaniu danych oraz skonfigurowaniu i uaktywnieniu scenariusza *konserwacji składnika majątku* można zobaczyć, jak rekordy liczników składników majątku są wstawiane na podstawie danych czujnika.

1. Wybierz **Zarządzanie składnikami majątku \> Składniki majątku \> Wszystkie składniki majątku**.
1. Odszukaj i zaznacz składnik majątku, który chcesz zbadać. (Jeśli używasz danych demonstracyjnych utworzonych wcześniej w tym artykule, wybierz *AK-101*).
1. W okienku akcji na karcie **Zasób**, w grupie **Prewencyjne**, wybierz **Liczniki**, by otworzyć stronę rekordów liczników dla składnika majątku *AK-101*.

### <a name="generate-maintenance-work-orders"></a>Generuj zlecenia pracy konserwacji

Po włączeniu scenariusza *konserwacji składnika majątku* i skonfigurowaniu planu konserwacji można uruchomić plan konserwacji w celu wygenerowania zleceń pracy konserwacji. Aby uzyskać więcej informacji na temat pracy z prewencyjną konserwacją, zobacz [Omówienie prewencyjnej konserwacji](../asset-management/preventive-and-reactive-maintenance/preventive-maintenance-overview.md).
