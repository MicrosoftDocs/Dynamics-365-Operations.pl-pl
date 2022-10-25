---
title: Scenariusz jakości produktu
description: Ten artykuł zawiera informacje dotyczące scenariusza jakości produktu. Ten scenariusz używa czujnika do mierzenia jakości partii produktów i generuje alert w przypadku, gdy miara przekroczy zdefiniowany próg.
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
ms.openlocfilehash: c0f1c57251234921779f67faf61d47cdde119e64
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690056"
---
# <a name="the-product-quality-scenario"></a>Scenariusz jakości produktu

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

W scenariuszu *jakości produktu* ustawiono czujnik do mierzenia jakości partii produktów na hali sklepowej. Jeśli miara przekracza zdefiniowany próg dla produktu, na pulpicie nawigacyjnym kierownika jest wyświetlane powiadomienie. Na przykład czujnik miedzy wilgotność produktu żywnościowego wychodzącego z taśmy produkcyjnej. Jeśli miara jest poza dozwoloną wartością minimalną lub maksymalną dla wilgotności produktu, generowane jest powiadomienie.

## <a name="scenario-dependencies"></a>Zależności scenariusza

Scenariusz *jakości produktu* obejmuje następujące zależności:

- Aby alert został wyzwolony, na mapowanym urządzeniu musi być uruchomione zlecenie produkcyjne i czy maszyna powoduje tworzenie produktu z mapowanym atrybutem partii.
- Sygnał reprezentujący atrybut partii musi zostać wysłany do centrum IoT Hub i musi zawierać unikatową nazwę właściwości.

## <a name="prepare-demo-data-for-the-product-quality-scenario"></a>Przygotuj dane demonstracyjne do scenariuszy jakości produktu

Jeśli chcesz użyć systemu demonstracyjnego do przetestowania scenariusza *jakości produktu*,użyj systemu, w którym zainstalowano [dane demonstracyjne](../../fin-ops-core/fin-ops/get-started/demo-data.md), wybierz osobę prawną *USMF* (firma) i przygotuj dodatkowe dane demonstracyjne zgodnie z opisem w tej sekcji. Jeśli korzystasz z własnych czujników i danych, możesz pominąć tę sekcję.

W tej sekcji skonfiguruje się dane demonstracyjne, aby można było używać zwolnionego produktu *P0111* (*Przypadek złożony*) ze scenariuszem *jakości produktu*. W tym scenariuszu system śledzi, czy wartość atrybutu partii mierzona za pomocą czujnika nie przekracza zdefiniowanego progu dla atrybutu partii skojarzonego z produktem.

### <a name="set-up-a-sensor-simulator"></a>Ustawianie symulatora czujnika

Aby spróbować tego scenariusza bez używania fizycznego czujnika, można skonfigurować symulator, aby generował wymagane sygnały. Aby zapoznać się z dodatkowymi informacjami, zobacz [Konfigurowanie symulowanego czujnika do testowania](sdi-set-up-simulated-sensor.md).

### <a name="associate-a-batch-attribute-and-resource-with-product-p0111"></a>Skojarz atrybut partii i zasób z produktem P0111

Aby skojarzyć atrybut partii z produktem *P0111* (*Przypadek złożony*) i sprawdzić, czy jest dla niego używany zasób *3118* (*Maszyna do cięcia piany*).

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Znajdź i wybierz produkt, dla którego pole **Kod pozycji** ma wartość *P0111*.
1. W okienku akcji na karcie **Zarządzaj zapasami**, w grupie **Atrybuty partii**, kliknij przycisk **Specyficzne dla produktu**.
1. Na stronie **Specyficzne dla produktu** wybierz przycisk **Nowy**, aby utworzyć atrybut partii specyficzny dla produktu.
1. W nagłówku ustaw następujące pola:

    - **Kod atrybutu** — umożliwia wybór zakresu atrybutów, które będą monitorowane (*Tabela*, *Grupa* lub *Wszystko*). W tym scenariuszu wybierz pozycję *Tabela*, ponieważ zawsze będziesz monitorować jeden atrybut.
    - **Relacja atrybutu** — umożliwia wybór atrybutu w celu monitorowania wartości tego scenariusza *jakości produktu*. W tym przykładzie należy wybrać *Koncentrację*, która jest atrybutem uwzględnionym w standardowych danych demonstracyjnych.

1. Na skróconej karcie **Wartości** w polach **Minimum** i **Maksimum** zdefiniuj zakres akceptowalnych wartości, które atrybut musi zgłosić, aby przejść pomyślnie sprawdzenie jakości. Jeśli czujnik poda wartość spoza tego zakresu, system zidentyfikuje ją jako naruszenie jakości. Inne pola na tej skróconej karcie nie są związane ze scenariuszem *jakości produktu*. Wartości domyślne, które są obecnie dostępne, pochodzą z danych demonstracyjnych. Dlatego pozostaw je bez zmian i zamknij stronę **Specyficzne dla produktu**, aby powrócić do strony **Szczegółów zwolnionego produktu** dla pozycji *P0111*.
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

## <a name="set-up-the-product-quality-scenario"></a>Ustawianie scenariusza jakości produktu

Wykonaj następujące kroki, aby skonfigurować scenariusz *jakości produktu* w rozwiązaniu Supply Chain Management.

1. Przejdź do **Kontrola produkcji \> Konfiguracja \> Sensor Data Intelligence \> Scenariusze**.
1. W polu scenariusza **Jakość produktu** produkcji wybierz opcję **Konfiguruj**, aby otworzyć kreatora ustawień tego scenariusza.
1. Na stronie **Czujniki**, w okienku akcji wybierz opcję **Nowy**, aby dodać nowy czujnik do siatki. Następnie ustaw dla niego następujące pola:

    - **Identyfikator czujnika** — służy do wprowadzania identyfikatora używanego czujnika. (Jeśli używasz symulatora online Raspberry Pi z Azure IoT i jest on skonfigurowany jako opisano w [Konfigurowanie symulowanego czujnika do testowania](sdi-set-up-simulated-sensor.md), wprowadź *Quality*).
    - **Opis czujnika** – wprowadź szczegółowy opis czujnika.

1. Powtórz poprzedni krok dla każdego dodatkowego czujnika, który chcesz teraz dodać. W każdej chwili możesz wrócić i dodać więcej czujników.
1. Wybierz pozycję **Następny**.
1. Na stronie **Mapowanie rekordu biznesowego**, w sekcji **Czujniki** zaznacz rekord dla jednego z dodanych czujników.
1. W sekcji **Mapowanie rekordów biznesowych** wybierz pozycję **Nowy**, aby dodać wiersz do siatki.
1. W nowym wierszu pole **Typ rekordu biznesowego** powinno być automatycznie ustawione na *Zasoby(WrkCtrTable)*. Ustaw pole **Rekord biznesowy** na zasób, który jest monitorowany przez czujnik. (Jeśli używasz danych demonstracyjnych utworzonych wcześniej w tym artykule, ustaw dla niego wartość *3118, Maszyna do cięcia piany*).
1. Bezpośrednio po wybraniu typu rekordu biznesowego dla wiersza dodanego w poprzednim kroku do siatki zostanie automatycznie dodany drugi wiersz. W tym wierszu pole **Typ rekordu biznesowego** powinno mieć wartość *Atrybuty partii(PdsBatchAttrib)*. Ustaw pole **Rekord biznesowy** na atrybut partii, który jest monitorowany przez czujnik. (Jeśli używasz danych demonstracyjnych utworzonych wcześniej w tym artykule, ustaw dla niego wartość *Koncentracja, procent koncentracji*).
1. Wybierz pozycję **Następny**.
1. Na stronie **Aktywuj czujniki** w siatce zaznacz dodany czujnik, a następnie wybierz opcję **Aktywuj**. Dla każdego aktywowanego czujnika w siatce w kolumnie **Aktywne** jest wyświetlany znacznik wyboru.
1. Wybierz **Zakończ**.

## <a name="work-with-the-product-quality-scenario"></a>Praca ze scenariuszem jakości produktu

### <a name="view-product-quality-data-on-the-resource-status-page"></a>Wyświetlanie danych o jakości produktu na stronie Stan zasobu

Na stronie **Stan zasobu** przełożeni mogą monitorować oś czasu sygnału jakości produktu, który jest odbierany z czujników zamapowanych na poszczególne zasoby maszynowe. Wykonaj poniższe czynności, aby skonfigurować oś czasu.

1. Wybierz kolejno opcje **Kontrola produkcji \> Wykonanie produkcji \> Stan zasobu**.
1. W oknie dialogowym **Konfiguruj** ustaw następujące pola:

    - **Zasób** — wybierz zasoby, które chcesz monitorować. (Jeśli używasz danych demonstracyjnych, wybierz opcję *3118*).
    - **Szereg czasowy 1** — wybierz rekord (klucz metryczny), który ma następujący format dla swojej nazwy: *ProductQuality:&lt;JobId&gt;:&lt;AttributeName&gt;*
    - **Nazwa wyświetlana** — wprowadź *wartości atrybutów partii*.

Na poniższej ilustracji pokazano przykład danych jakości produktu na stronie **Stan zasobu**, gdy wartość znajduje się w przedziale akceptowalnych wartości.

![Dane jakości produktu na stronie Stan zasobu, gdy wartość jest w zakresie.](media/sdi-product-quality-in-range.png "Dane jakości produktu na stronie Stan zasobu, gdy wartość jest w zakresie")

Na poniższej ilustracji pokazano przykład danych jakości produktu w przypadku wykrycia wartości poza zakresem.

![Dane jakości produktu na stronie Stan zasobu, gdy wykryte zostaną wartości poza zakresem.](media/sdi-product-quality-out-of-range.png "Dane jakości produktu na stronie Stan zasobu, gdy wykryte zostaną wartości poza zakresem")

### <a name="view-product-quality-data-on-the-notifications-page"></a>Wyświetlanie danych o jakości produktu na stronie Powiadomienia

Na stronie **Powiadomienia** przełożeni mogą wyświetlać powiadomienie wygenerowane, gdy czujnik zmierzy wartość atrybutu partii, która przekracza zdefiniowany próg dla atrybutu partii. Każde powiadomienie umożliwia przegląd zadania produkcyjnego, na które ma wpływ ten przestój i daje możliwość ponownego przypisania tego zadania do innego zasobu.

Aby otworzyć stronę **Powiadomienia**, przejdź do **Kontrola produkcji \> Zapytania i raporty \> Sensor Data Intelligence \> Powiadomienia**.

Poniższa ilustracja przedstawia przykład powiadomienia o jakości produktu.

![Przykład strony z powiadomieniem o jakości produktu.](media/sdi-product-quality-notification.png "Przykład strony z powiadomieniem o jakości produktu")
