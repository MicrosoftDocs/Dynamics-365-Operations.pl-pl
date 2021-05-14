---
title: Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej
description: W tym temacie opisano sposób, w jaki firma może wykorzystać Microsoft Dynamics 365 Commerce do wyświetlania szacowanej dostępności produktów do dyspozycji w kanałach online i w sklepach.
author: hhainesms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: fdf6df7e393bcc401e770bd1b8afcaedcadc2660
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937441"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej

[!include [banner](../includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano sposób, w jaki firma może wykorzystać Microsoft Dynamics 365 Commerce do wyświetlania szacowanej dostępności produktów do dyspozycji w kanałach online i w sklepach.

## <a name="accuracy-of-inventory-availability"></a>Dokładność dostępności zapasów

Commerce używa wielu serwerów i baz danych w celu zapewnienia skalowalności i wydajności. Dlatego ważne jest, aby rozumieć, że dostępne wartości zapasów dostarczane za pośrednictwem aplikacji punktu sprzedaży (POS), interfejsów programowania aplikacji w handlu elektronicznym (API) i dostępne zapasy w module Commerce Headquarters nie mogą być wykonywane w czasie rzeczywistym ze 100 procentową dokładnością. Jeśli transakcje utworzone dla produktów w kanale online lub sklepu nie zostały jeszcze zsynchronizowane z centralą, strony dostępne w centrali mogą nie wyświetlać dokładnej wartości zapasów w czasie rzeczywistym dla tych produktów. Podobnie, jeśli skonfigurowano firmę, dzięki czemu użytkownicy w centrali lub w innych zintegrowanych aplikacjach mogą sprzedawać, przyjmować, zwracać lub w inny sposób korygować zapasy ze sklepu lub magazynu online, to punkt sprzedaży lub kanał online może nie mieć wszystkich informacji wymaganych do wyświetlenia dokładnej wartości w czasie rzeczywistym dla pozycji.

Istotne jest, aby rozumieć, że wszystkie dane dostępnych zapasów, które są dostarczane w danym dniu roboczym, są uznawane za szacowaną wartość. Dlatego w przypadku próby porównania informacji o dostępnych zapasach, które aplikacja dostarcza z rzeczywistym zapasem fizycznym na półkach lub w przypadku próby porównania wartości dostępnych zapasów w punkcie sprzedaży z danymi dotyczącymi dostępnych zapasów, które znajdują się dla tego samego magazynu w centrali, wartości mogą być różne. Oczekiwana jest różnica w dniu eksploatacyjnym i nie należy jej traktować jako usterki. Jeśli chcesz poddać inspekcji dane i upewnić się, że wartości podane w punkcie sprzedaży, interfejsach API i centrali są zgodne z rzeczywistymi jednostkami fizycznymi, które znajdują się w magazynie lub na półkach magazynowych, to najlepszy czas na wykonanie operacji w ramach kanału zatrzymana na dzień i wszystkie transakcje zostały poprawnie zsynchronizowane między centralą a kanałami.

## <a name="channel-side-inventory-calculation"></a>Obliczanie zapasów po stronie kanału

Obliczanie zapasów po stronie kanału to mechanizm, który przyjmuje jako podstawowe dane magazynu ostatniego znanego kanału w centrali rozwiązania Commerce, a następnie współczynniki dodatkowych zmian zapasów, które wystąpiły po stronie kanału, które nie są uwzględnione w tej podstawie do obliczania przybliżonych dostępnych zapasów w czasie zbliżonym do rzeczywistego. 

W logice obliczania zapasów po stronie kanału są obecnie uznawane następujące zmiany zapasów:

- Zapasy sprzedawane w sklepie na podstawie zamówień rozliczenia gotówkowo-towarowego
- Zapasy sprzedawane przez zamówienia odbiorców w sklepie lub kanale online
- Zapasy zwrócone do sklepu
- Magazyn zrealizowany (pobranie, spakowanie, wysyłka) z magazynu sklepu

Aby można było korzystać z obliczania zapasów po stronie kanału, jako warunek wstępny musi być wysyłana okresowa migawka danych magazynowych z centrali utworzonych za pomocą zadania **Dostępność produktu** do baz danych kanału. Migawka przedstawia informacje o dostępności zapasów posiadane przez centralę w odniesieniu do konkretnej kombinacji produktu lub wariantu produktu oraz magazynu. Obejmuje ona tylko transakcje magazynowe, który były przetwarzane i zaksięgowane w centrali w momencie wykonania migawki i może być nierówna 100-procentowej precyzji w czasie rzeczywistym z powodu stałego przetwarzania sprzedaży wykonywanego między serwerami rozproszonymi.

- Jeśli zapasy zostały sprzedane dla produktu w magazynie sklepu dzięki rozliczeniu gotówkowo-towarowemu lub asynchronicznej sprzedaży zamówienia odbiorcy w aplikacji punktu sprzedaży, w centrali nie będą natychmiast przechowywane informacje o transakcji związanej z zapasami dla sprzedaży. Centrala otrzyma informacje o zapasach sprzedanych dla tych typów sprzedaży w sklepie dopiero po przekazaniu przez zadanie P transakcji z bazy danych kanału magazynu do centrali, a powiązane zamówienia sprzedaży są tworzone poprzez księgowanie zestawień lub cząstkowe procesy księgowania. Proces tworzenia zamówień w centrali powoduje utworzenie powiązanych transakcji magazynowych. 
- W przypadku zamówień w module handlu elektronicznego centrala otrzymuje informacje o transakcjach magazynowych dopiero po wysłaniu transakcji do centrali za pośrednictwem zadania P i procesu synchronizacji zamówienia.

Aby wykonać migawkę zapasów w centrali Commerce, należy wykonać następujące kroki.

1. Umożliwia przejście do modułu **Retail i Commerce \> Retail i Commerce — składniki IT \> Produkty i zapasy \> Dostępność produktu**.
1. Wybierz przycisk **OK**, aby uruchomić zadanie **dostępności produktu**. Można również zaplanować to zadanie, aby było wykonywane w partii.

Po zakończeniu pracy zadania **dostępności produktu** przechwycone dane muszą zostać przekazane do baz danych kanału handlu elektronicznego, dzięki czemu najnowsza migawka zapasów w centrali może zostać uwzględniona w obliczeniach szacowanego stanu dostępnych zapasów po stronie kanału.

Aby synchronizować dane migawki z centrali z bazami danych kanału, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
1. Uruchom zadanie **1130** (**dostępność produktu**), aby zsynchronizować dane migawki, które utworzono w ramach zadania **dostępności produktu**, z centrali do baz danych kanału.

## <a name="inventory-availability-apis-for-e-commerce"></a>Interfejsy API dostępności zapasów dla handlu elektronicznego

W Commerce dostępne są następujące interfejsy API scenariuszy handlu elektronicznego służące do wykonywania zapytań o dostępność zapasów produktu:

- **GetEstimatedAvailability** — ten interfejs API umożliwia wykonywanie zapytań magazynowych o produkt lub wariant produktu w magazynie lub magazynach kanału online połączonych z grupą realizacji kanału online.
- **GetEstimatedProductWarehouseAvailability** — ten interfejs API służy do wykonywania zapytań o zapasy produktu lub wariantu produktu z określonego magazynu.

> [!NOTE]
> Te interfejsy API zastępują interfejsy API **GetProductAvailabilities** i **GetAvailableInventoryNearby** używane w Commerce w wersji 10.0.7 i wcześniejszej.

Oba interfejsy API wewnętrznie korzystają z logiki obliczania po stronie kanału, a także zwracają szacowaną ilość **fizycznie dostępną**, **ilość** łączną dostępną ilość, **jednostkę miary (UoM)** i **poziom zapasów** żądanego produktu i magazynu. Zwrócone wartości mogą być wyświetlane w witrynie handlu elektronicznego w razie potrzeby lub mogą być używane do wyzwalania innych reguł biznesowych w witrynie handlu elektronicznego. Można na przykład uniemożliwić zakup produktów na poziomie zapasów „poza magazynem”.

Mimo że inne interfejsy API dostępne na serwerze Commerce mogą przejść bezpośrednio do centrali, aby pobierać dostępne ilości produktów, nie zaleca się używania ich w środowisku handlu elektronicznego z powodu potencjalnych problemów z wydajnością oraz ten sam wpływ może być związany z tymi częstymi żądaniami na serwerach centrali. Ponadto w przypadku obliczeń strony kanału dwa wymienione powyżej interfejsy API mogą dokładniej oszacować dostępność produktu, biorąc pod uwagę transakcje utworzone w kanałach, które nie są jeszcze znane centralom.

Przed użyciem dwóch wymienionych wcześniej interfejsów API należy włączyć funkcję **obliczania zoptymalizowanej dostępności produktów** za pośrednictwem obszaru roboczego **Zarządzanie funkcjami** w centrali. Jeśli kanały sprzedaży online i sklepu korzystają z tych samych magazynów realizacji, należy również włączyć funkcję **rozszerzonej logiki obliczania zapasów po stronie kanału e-commerce**, tak aby logika obliczeń po stronie kanału w obrębie tych dwóch interfejsów API zawierała współczynnik niezaksięgowanych transakcji (rozliczenie gotówkowo-towarowe, zamówienia odbiorcy, zwroty) w kanale sklepu. Po włączeniu tych funkcji konieczne będzie uruchomienie zadania **1070** (**Konfiguracja kanału**).

Aby określić sposób zwracania ilości produktu w wynikowym interfejsie API, wykonaj następujące kroki.

1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry handlowe**.
1. Wybierz kartę **Zapasy**, a następnie na skróconej karcie **Interfejsy API dostępności zapasów w handlu elektronicznym** skonfiguruj wartość ustawienia **Ilość w danych wyjściowych interfejsu API**.
1. Uruchom zadanie **1070** (**Konfiguracja kanałów**), aby zsynchronizować najnowsze ustawienie z kanałami.

Ustawienie **Ilość w danych wyjściowych interfejsu API** zawiera trzy opcje:

- **Zwracana ilość zapasów** — fizycznie dostępna i łączna dostępna ilość żądanego produktu są zwracane w danych wyjściowych interfejsu API.
- **Zwracana ilość zapasów odejmując bufor zapasów** — ilość zwrócona w wyniku interfejsu API jest korygowana przez odjęcie wartości buforu zapasów. Aby uzyskać więcej informacji o buforze zapasów, zobacz temat [Konfigurowanie buforów zapasów i poziomów zapasów](inventory-buffers-levels.md).
- **Nie zwracaj ilości zapasów** — w wyniku interfejsu API jest zwracany tylko poziom zapasów. Aby uzyskać więcej informacji o poziomach zapasów, zobacz temat [Konfigurowanie buforów zapasów i poziomów zapasów](inventory-buffers-levels.md).

Parametr interfejsu API `QuantityUnitTypeValue` umożliwia określenie typu jednostki, w jakiej interfejsy API mają zwracać ilość. Ten parametr obsługuje opcje **jednostki magazynowej** (domyślna), **jednostki zakupu** i **jednostki sprzedaży**. Zwracana ilość jest zaokrąglana do określonej dokładności odpowiadającej jednostce miary (UOM) w centrali.

Interfejs API **GetEstimatedAvailability** oferuje następujące parametry wejściowe do obsługi różnych scenariuszy zapytań:

- `DefaultWarehouseOnly`— ten parametr służy do wykonywania zapytania o zapasy produktu w domyślnym magazynie kanału online. 
- `FilterByChannelFulfillmentGroup` i `SearchArea` — te dwa parametry służą do wykonywania zapytania o zapasy produktu ze wszystkich lokalizacji pobrania w określonym obszarze wyszukiwania, na podstawie wartości `longitude`, `latitude` i `radius`. 
- `FilterByChannelFulfillmentGroup` i `DeliveryModeTypeFilterValue`— te dwa parametry umożliwiają wykonywanie zapytania o zapasy produktu z określonych magazynów, które są połączone z grupą realizacji kanału online i są skonfigurowane do obsługi pewnych trybów dostawy. Parametr `DeliveryModeTypeFilterValue` obsługuje opcje **wszystkie** (domyślne), **wysyłka** i **pobranie**. Na przykład w scenariuszu, w którym zamówienie online może zostać zrealizowane w wielu magazynach wysyłkowych, można użyć tych dwóch parametrów do zapytania o dostępność zapasów produktu we wszystkich tych magazynach wysyłkowych. Interfejs API w tym przypadku zwraca ilość dostępnych zapasów i poziom zapasów produktu w każdym z magazynów wysyłkowych, a także zagregowaną ilość i zagregowany poziom zapasów ze wszystkich magazynach wysyłkowych w zakresie zapytania.
 
Moduły pola zakupu, selektora sklepu, listy życzeń, koszyka i ikony koszyka Commerce używają wymienionych powyżej interfejsów API i parametrów w celu wyświetlania komunikatów o poziomie zapasów w witrynie handlu elektronicznego. Konstruktor witryn Commerce oferuje różne ustawienia zapasów, aby kontrolować zachowania dotyczące merchandisingu i zakupu. Aby uzyskać więcej informacji, zobacz [Zastosuj ustawienia zapasów](inventory-settings.md).

## <a name="pos-inventory-lookup-with-channel-side-calculation"></a>Wyszukiwanie w magazynie punktu sprzedaży z obliczaniem po stronie kanału

W Commerce w wersji 10.0.9 i starszych operacja **wyszukiwania zapasów** w punkcie sprzedaży używała wywołania usługi w czasie rzeczywistym w centrali, aby uzyskać informacje o zapasach wybranego produktu, zarówno dla bieżącego sklepu użytkownika, jak i wszystkich innych sklepów skonfigurowanych dla grupy realizacji jako część konfiguracji kanału dla sklepu. W Commerce w wersji 10.0.10 i nowszych można wyłączyć wywołania usługi w czasie rzeczywistym w centrali, aby zamiast nich korzystać z obliczania po stronie kanału na serwerze Commerce w celu ustalania dostępnych zapasów, które są fizycznie dostępne dla sklepu i innych lokalizacji zdefiniowanych w grupie realizacji. Ta konfiguracja zapasów obliczona w kanale jest również przydatna w lokalizacjach, w których łączność z Internetem jest zawodna, ponieważ nie trzeba być w trybie online, aby uzyskać wyszukiwanie w magazynie z centrali.

Gdy obliczenie po stronie kanału jest poprawnie skonfigurowane i zarządzane, może zapewnić bardziej niezawodne oszacowanie bieżącego magazynu sklepu, ponieważ korzysta on z danych transakcyjnych w bazie danych w bazie danych kanału Commerce, których centrala jeszcze nie zna. Na przykład w przypadku korzystania z istniejącego zgłoszenia usługi w czasie rzeczywistym do wyszukiwania zapasów w punkcie sprzedaży prawdopodobnie centrala nie będzie jeszcze wiedziała o sprzedaży, która właśnie wystąpiła dla danego produktu. Z tego względu wartość dostępnych zapasów, którą centrala zwraca dla tego produktu, prawdopodobnie przekroczy ilość dostępnych zapasów w magazynie o jedną jednostkę. Jeśli jednak używane jest obliczenie po stronie kanału, sprzedaż środków pieniężnych i towarów do sprzedaży może zostać zaliczona do obliczeń i odjęta od podanej wartości dostępnych zapasów. Chociaż wartości obliczane zarówno po stronie kanału, jak i w wywołaniu usługi w czasie rzeczywistym, są tylko szacunkami dostępnych zapasów, wartość obliczona przez stronę kanału sprzedaży znacznie bardziej prawdopodobna na potrzeby bieżącego sklepu.

Aby skonfigurować operację **wyszukiwania w magazynie** punktu sprzedaży w centrali z logiką obliczania po stronie kanału i wyłączyć wywołanie usługi w czasie rzeczywistym, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**.
1. Wybierz profil funkcji.
1. W karcie skróconej **Funkcje** w sekcji **Obliczanie dostępności magazynowej** zmień wartość pola **Tryb obliczania dostępności zapasów** z **Usługa w czasie rzeczywistym** na **Kanał**. Domyślnie wszystkie profile funkcji korzystają z wywołań usługi w czasie rzeczywistym. Musisz zmienić wartość tego pola, jeśli ma być używana logika obliczania po stronie kanału. Ta zmiana będzie miała wpływ na każdy sklep detaliczny połączony z wybranym profilem funkcji.

Następnie należy zsynchronizować zmiany w kanałach za pomocą procesu planowania dystrybucji w centrali, wykonując następujące kroki.

1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
1. Uruchom zadanie **1070** (**konfiguracja kanału**).

Po zakończeniu konfiguracji informacje dotyczące magazynu fizycznie dostępnego nie korzystają już z wywołania usługi w czasie rzeczywistym, gdy użytkownik w aplikacji punktu sprzedaży używa operacji **wyszukiwania zapasów** (widoki standardowe i macierzowe). Zamiast tego dane o fizycznie dostępnych zapasach dla bieżącego sklepu i wszystkich sklepów w grupie realizacja są obliczane na podstawie ostatniej znanej migawki, która została dostarczona do bazy danych kanału z modułu Commerce Headquarters. Wartość migawki jest dokładniejsza za pomocą obliczeń po stronie kanału w celu skorygowania dostępnej fizycznie wartości na podstawie dodatkowych transakcji sprzedaży lub zwrotów istniejących dla wybranego produktu w bazie danych kanału, które nie zostały uwzględnione w ostatnim zsynchronizowana migawka z zadania 1130. Jeśli baza danych kanału nie zawiera danych transakcyjnych dla żadnego z magazynów lub sklepów w grupie realizacji, nie zawiera żadnych dodatkowych transakcji, które mogą być uwzględniane w ponownym obliczaniu wartości. Dlatego najlepszym oszacowaniem dostępnych zapasów, które mogą być wyświetlane dla tych magazynów lub sklepów, są dane z ostatniej znanej migawki modułu Commerce Headquarters.

Na ekranach **realizacji zamówienia** w punkcie sprzedaży są również używane obliczenia po stronie kanału do wyświetlania dostępnych zapasów towarów, gdy jest wybrany wiersz realizacji zamówienia, a użytkownik wyświetla panel **szczegóły** dla dostępnych zapasów dla wybranego towaru.

## <a name="optimize-your-inventory-data"></a>Optymalizowanie danych magazynowych

Aby zapewnić możliwie najlepszy szacunek stanu zapasów, należy używać następujących zadań wsadowych modułu Commerce i często je wykonywać:

- **Zadanie P** — zadanie p znajduje się na stronie **harmonogramy dystrybucji** i powinno być często uruchamiane. To zadanie powoduje wykonanie zamówień w handlu elektronicznym, asynchronicznych zamówień odbiorców, które zostały utworzone w punkcie sprzedaży oraz zamówień gotówkowych i transprodukcyjnych, które zostały utworzone z baz danych kanałów w programie Commerce Headquarters, dzięki czemu mogą być dalej przetwarzane. Dopóki dane nie zostaną zsynchronizowane z kanału do modułu Commerce Headquarters, moduł Commerce Headquarters nie będzie miał żadnych informacji na temat korekt zapasów do produktów w magazynach powstałych w wyniku tych transakcji.
- **Synchronizuj zamówienia** — to zadanie przetwarza surowe dane transakcyjne w programie Commerce Headquarters, które zadanie P umożliwia i przekształca handel elektroniczny oraz transakcje asynchroniczne zamówienia odbiorcy w zamówienia sprzedaży w programie Commerce Headquarters. Do momentu przetwarzania tego zadania i tworzenia zamówień sprzedaży nie są tworzone żadne transakcje magazynowe. Z tego względu dostępne zapasy w module Commerce Headquarters nie będą rozważać transakcji.
- **Obliczanie zestawień transakcyjnych w partii** — dla transakcji kasowych tworzonych w sklepie proces księgowania cząstkowego zapewnia, że zapasy związane ze sprzedażą są skutecznie aktualizowane. Aby uzyskać najbardziej wydajne przetwarzanie transakcji magazynowych dla zamówień gotówkowych, należy skonfigurować system w taki sposób, aby korzystał [z funkcji księgowania cząstkowego](./trickle-feed.md).
- **Księgowanie wyciągów transakcyjnych w partii** — to zadanie jest również wymagane w przypadku księgowania cząstkowego. Następuje po zadaniu **obliczenia zestawień transakcyjnych w partii**. To zadanie systematycznie księguje obliczone zestawienia, tak aby zamówienia sprzedaży dla sprzedaży gotówkowej i towarowej były tworzone w module Commerce Headquarters i by moduł Commerce Headquarters lepiej odzwierciedlał zapasy sklepu.
- **Dostępność produktu** — to zadanie tworzy migawkę zapasów z modułu Commerce Headquarters.
- **1130 (dostępność produktu)** — to zadanie znajduje się na stronie **harmonogramy dystrybucji** i powinno być uruchamiane natychmiast po zadaniu **dostępności produktu**. To zadanie transportuje dane migawki magazynowej z modułu Commerce Headquarters do baz danych kanału.

> [!NOTE]
> - Dobrą praktyką jest uruchamianie zadań **dostępności produktów** i **1130** co godzinę oraz planowanie zadań P, synchronizowanie zamówień i przesyłanie zadań związanych z przesyłaniem strumieniowym z taką samą lub wyższą częstotliwością.
> - Ze względu na wydajność, gdy obliczenia dostępności zapasów w ramach kanału są używane do realizacji żądania dostępności zapasów przy użyciu logiki magazynowej obsługi handlu elektronicznego lub kanału punktu sprzedaży, w obliczeniu jest używana pamięć podręczna do określenia, czy minęła wystarczająca liczba godzin do ponownego uruchomienia logiki obliczeń. Domyślna pamięć podręczna została ustawiona na 60 sekund. Na przykład po stronie kanału można włączyć obliczanie dla sklepu i wyświetlić dostępne zapasy produktu na stronie **wyszukiwania zapasów**. Jeśli zostanie sprzedana jedna jednostka produktu, strona **wyszukiwania zapasów** nie będzie pokazywała zmniejszonych zapasów, dopóki pamięć podręczna nie zostanie wyczyszczona. Po zaksięgowaniu transakcji przez użytkowników w punkcie sprzedaży należy poczekać 60 sekund przed sprawdzeniem, czy stan dostępnych zapasów został zmniejszony.

Jeśli scenariusz biznesowy wymaga krótszego czasu pamięci podręcznej, skontaktuj się z przedstawicielem pomocy technicznej, aby uzyskać pomoc.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
