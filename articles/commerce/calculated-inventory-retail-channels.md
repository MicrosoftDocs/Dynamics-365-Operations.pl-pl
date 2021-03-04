---
title: Oblicz dostępność zapasów dla kanałów sprzedaży detalicznej
description: W tym temacie opisano opcje dostępne dla wyświetlania dostępnych zapasów sklepu i kanałów online.
author: hhainesms
manager: annbe
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: de4ee98198f441b8f42a8a55aa5ff1015f485234
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414928"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Oblicz dostępność zapasów dla kanałów sprzedaży detalicznej

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób, w jaki firma może wykorzystać Microsoft Dynamics 365 Commerce do wyświetlania szacowanej dostępności produktów do dyspozycji w kanałach online i w sklepach.

## <a name="accuracy-of-calculation"></a>Dokładność obliczeń

Commerce używa wielu serwerów i baz danych w celu zapewnienia skalowalności i wydajności. Dlatego ważne jest, aby rozumieć, że dostępne wartości zapasów dostarczane za pośrednictwem aplikacji punktu sprzedaży (POS), interfejsów programowania aplikacji w handlu elektronicznym (API) i dostępne zapasy w module Commerce Headquarters nie mogą być wykonywane w czasie rzeczywistym ze 100 procentową dokładnością. Jeśli transakcje utworzone dla produktów w kanale online lub sklepu nie zostały jeszcze zsynchronizowane z serwerem i bazą danych modułu Commerce Headquarters, strony dostępne w module Commerce Headquarter mogą nie wyświetlać dokładnej wartości zapasów w czasie rzeczywistym dla tych produktów. Podobnie, jeśli skonfigurowano firmę, dzięki czemu użytkownicy w Commerce Headquarters lub w innych zintegrowanych aplikacjach mogą sprzedawać, przyjmować, zwracać lub w inny sposób korygować zapasy ze sklepu lub magazynu online, to punkt sprzedaży lub kanał online może nie mieć wszystkich informacji wymaganych do wyświetlenia dokładnej wartości dostępnych zapasów w czasie rzeczywistym dla pozycji.

W tym temacie objaśniono procesy synchronizacji danych, które mogą być często uruchamiane w celu ograniczenia opóźnienia przesyłania danych między aplikacjami lub kanałami. Jednak istotne jest, aby rozumieć, że wszystkie dane dostępnych zapasów, które są dostarczane w danym dniu roboczym, są uznawane za szacowaną wartość. Dlatego w przypadku próby porównania informacji o dostępnych zapasach, które aplikacja dostarcza z rzeczywistym zapasem fizycznym na półkach lub w przypadku próby porównania wartości dostępnych zapasów w punkcie sprzedaży z danymi dotyczącymi dostępnych zapasów, które znajdują się dla tego samego magazynu w module Commerce Headquarters, wartości mogą być różne. Oczekiwana jest różnica w dniu eksploatacyjnym i nie należy jej traktować jako usterki. Jeśli chcesz poddać inspekcji dane i upewnić się, że wartości podane w interfejsach API dostępności zapasów i Commerce Headquarters są zgodne z rzeczywistymi jednostkami fizycznymi, które znajdują się w magazynie lub na półkach magazynowych, to najlepszy czas na wykonanie operacji w ramach kanału zatrzymana na dzień i wszystkie transakcje zostały poprawnie zsynchronizowane między Commerce Headquarters a kanałem.

## <a name="use-inventory-lookup-apis-for-e-commerce-inventory-availability-requests"></a>Korzystaj z interfejsów API wyszukiwania zapasów w przypadku żądań dostępności zapasów w handlu elektronicznego

Poniższe interfejsy API umożliwiają pokazanie dostępności zapasów produktu, gdy odbiorcy dokonują zakupów w witrynie handlu elektronicznego.

- **GetEstimatedAvailability** — ten interfejs API służy do pobierania dostępności zapasów towaru w magazynie kanału handlu elektronicznego lub w ramach wszystkich magazynów połączonych z konfiguracją grupy realizacji dla kanału handlu elektronicznego. Ten interfejs API może być również używany dla magazynów w określonym obszarze wyszukiwania lub promieniu, na podstawie danych o długościach geograficznej i szerokości geograficznej.
- **GetEstimatedProductWarehouseAvailability** — ten interfejs API służy do żądania zapasów towaru z określonego magazynu. Na przykład można go wykorzystać do wyświetlania dostępności zapasów w scenariuszach, które dotyczą pobrania zamówienia.

> [!NOTE]
> Te interfejsy API zastępują interfejsy API **GetProductAvailabilities** i **GetAvailableInventoryNearby** w Dynamics 365 Retail w wersji 10.0.7 i wcześniejszej.

Oba serwery API pobierają dane z serwera Commerce i zapewniają prognozę dostępnych zapasów dla konkretnej kombinacji produktu lub wariantu produktu oraz magazynu. Mimo że inne interfejsy API dostępne na serwerze Commerce mogą przejść bezpośrednio do modułu Commerce Headquarters, aby pobierać dostępne ilości produktów, nie zaleca się używania ich w środowisku handlu elektronicznego z powodu potencjalnych problemów z wydajnością oraz ten sam wpływ może być związany z tymi częstymi żądaniami na serwerach modułu Commerce Headquarter. Ponadto, jeśli stan dostępnych zapasów jest obliczany za pośrednictwem serwera Commerce, obliczenie ma większe prawdopodobieństwo uwzględnienia zapasów sprzedanych w ostatnich transakcjach handlu elektronicznego, które nie zostały jeszcze zsynchronizowane z modułem Commerce Headquarters. Chociaż program Commerce Headquarters może nie mieć informacji o tych transakcjach, serwer Commerce i baza danych kanału zawierają dane. Dlatego dane będą brane pod uwagę i mogą ułatwić dokładniejsze oszacowanie dostępnych zapasów produktu.

### <a name="get-started-with-e-commerce-calculated-inventory-availability"></a>Wprowadzenie do obliczeniowej dostępności zapasów w handlu elektronicznego

Przed użyciem dwóch wymienionych wcześniej interfejsów API należy włączyć funkcję **obliczania zoptymalizowanej dostępności produktów** za pośrednictwem obszaru roboczego **Zarządzanie funkcjami** w module Commerce Headquarters.

Zanim interfejsy API będą mogły obliczyć najlepsze oszacowanie dostępności towaru, okresowa migawka dostępności zapasów z modułu Commerce Headquarters musi zostać przetworzona i wysłana do bazy danych kanału, która jest używana przez jednostkę Commerce Scale Unit handlu elektronicznego. Migawka przedstawia informacje o dostępności zapasów przez program Commerce Headquarters w odniesieniu do konkretnej kombinacji produktu lub wariantu produktu oraz magazynu. Może to być korekta lub przesunięcia zapasów spowodowane przez przyjęcia magazynowe lub przez wysyłki lub inne procesy, które są wykonywane w programie Commerce Headquarters oraz czy kanał handlu elektronicznego zawiera informacje tylko z powodu synchronizacji procesu.

Migawka bazy danych, która jest tworzona przez zadanie **dostępności produktu**, oblicza tylko transakcje magazynowe, które zostały przetworzone i zaksięgowane w module Commerce Headquarters w czasie, gdy migawka została wykonana. Jeśli zapasy zostały sprzedane dla produktu w magazynie sklepu dzięki rozliczeniu gotówkowo-towarowemu lub asynchronicznej sprzedaży zamówienia odbiorcy w aplikacji punktu sprzedaży, w module Commerce Headquarters nie będą natychmiast przechowywane informacje o transakcji związanej z zapasami dla sprzedaży. Informacje o zapasach sprzedanych dla tych typów sprzedaży w sklepie będą zawierać dopiero po przekazanie przez zadanie P transakcji z bazy danych kanału magazynu do modułu Commerce Headquarters, a powiązane zamówienie sprzedaży jest tworzone w zestawieniu Księgowanie lub cząstkowych procesów księgowania. Proces tworzenia zamówienia w module Commerce Headquarters powoduje utworzenie powiązanych transakcji magazynowych. W przypadku zamówień w module handlu elektronicznego w module Commerce Headquarters istnieją informacje o transakcjach magazynowych tylko po wysłaniu transakcji do modułu Commerce Headquarters za pośrednictwem zadania P i procesu synchronizacji zamówienia. Dlatego ważne jest, aby rozumieć, że wartość migawki zapasów podana w zadaniu **dostępność produktu** może być nierówna 100-procentowej precyzji w czasie rzeczywistym z powodu stałego przetwarzania sprzedaży wykonywanego między serwerami rozproszonymi.

Aby wykonać migawkę zapasów w programie Commerce Headquarters, należy wykonać następujące kroki.

1. Umożliwia przejście do modułu **Retail i Commerce \> Retail i Commerce — składniki IT \> Produkty i zapasy \> Dostępność produktu**.
1. Wybierz przycisk **OK**, aby uruchomić zadanie **dostępności produktu**. Można również zaplanować to zadanie, aby było wykonywane w partii.

Po zakończeniu pracy zadania **dostępności produktu** przechwycone dane muszą zostać przekazane do baz danych kanału handlu elektronicznego, dzięki czemu najnowsza migawka zapasów w module Commerce Headquarters może zostać uwzględniona w obliczeniach szacowanego stanu dostępnych zapasów.

1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
1. Uruchom zadanie **1130** (**dostępność produktu**), aby zsynchronizować dane migawki, które utworzono w ramach zadania **dostępności produktu** z poziomu programu Commerce Headquarters do baz danych kanału.

Po zażądaniu dostępności zapasów z interfejsu API **GetEstimatedAvailability** lub **GetEstimatedProductWarehouseAvailability** należy wykonać obliczenia w celu uzyskania optymalnego oszacowania stanu zapasów produktu. Obliczenie odwołuje się do wszystkich zamówień odbiorcy w handlu elektronicznym, które znajdują się w bazie danych kanału, ale nie zostały uwzględnione w danych migawki, które zostały dostarczone przez zadanie 1130. Tę logikę wykonuje się, śledząc ostatnio przetworzoną transakcję magazynową z modułu Commerce Headquarters i porównując ją z transakcjami w bazie danych kanału. Stanowi podstawę dla logiki obliczeniowej po stronie kanału, dzięki czemu dodatkowe przesunięcia magazynowe, które nastąpiły dla transakcji sprzedaży zamówienia odbiorcy w bazie danych kanału handlu elektronicznego, mogą być uwzględniane w szacowanej wartości zapasów, jaką interfejs API zawiera.

Logika obliczania po stronie kanału zwraca szacowaną, fizycznie dostępną wartość i łączną dostępną wartość dla żądanego produktu i magazynu. Wartości mogą być wyświetlane w witrynie handlu elektronicznego w razie potrzeby lub mogą być używane do wyzwalania innych reguł biznesowych w witrynie handlu elektronicznego. Można na przykład wyświetlić komunikat „brak w magazynie”, a nie rzeczywistą ilość zapasów przekazanych przez interfejs API.

Logika obliczeń, za pomocą której interfejsy API handlu elektronicznego w kanale dla szacowanej wartości zapasów mogą oceniać zapasy wyłącznie na podstawie zamówień odbiorcy utworzonych w bazie danych kanału, ale nie zostały jeszcze zsynchronizowane i zaksięgowane w module Commerce Headquarters. Jeśli baza danych kanału zawiera także dane transakcyjne dla magazynów gotówkowych, sprzedaż w magazynie specyficznym dla sklepu nie jest uwzględniana w obliczeniach handlu elektronicznego dla tych magazynów po stronie kanału.

## <a name="configure-the-inventory-lookup-operation-in-the-pos-channel"></a>Skonfiguruj operację wyszukiwania w magazynie w kanale punktu sprzedaży

W wersji detalicznej 10.0.9 i starszej operacja **wyszukiwania zapasów** z punktu sprzedaży użyła wywołania usługi w czasie rzeczywistym w module Commerce Headquarters, aby uzyskać informacje o zapasach wybranego produktu, zarówno dla bieżącego sklepu użytkownika, jak i wszystkich innych sklepów skonfigurowanych dla grupy realizacji jako część konfiguracji kanału dla sklepu. W systemie Commerce w wersji 10.0.10 lub nowszej można wyłączyć wywołania usługi czasu rzeczywistego w module Commerce Headquarters. Zamiast tego można użyć obliczeń po stronie kanału na serwerze Commerce w celu określenia dostępnych zapasów, które są fizycznie dostępne dla sklepu i wszystkich innych lokalizacji zdefiniowanych w grupie realizacja. Ta konfiguracja zapasów obliczona w kanale jest również przydatna w lokalizacjach, w których łączność z Internetem jest zawodna, ponieważ nie trzeba być w trybie online, aby uzyskać wyszukiwanie w magazynie z modułu Commerce Headquarters.

Gdy obliczenie po stronie kanału jest poprawnie skonfigurowane i zarządzane, może zapewnić bardziej niezawodne oszacowanie bieżącego magazynu sklepu, ponieważ korzysta on z danych transakcyjnych w bazie danych w bazie danych kanału Commerce, których moduł Commerce Headquarters jeszcze nie zawiera. Na przykład w przypadku korzystania z istniejącego zgłoszenia usługi w czasie rzeczywistym do wyszukiwania zapasów w punkcie sprzedaży prawdopodobnie system Commerce Headquarters nie będzie jeszcze zawierał informacji o sprzedaży, która właśnie wystąpiła dla danego produktu. Z tego względu wartość dostępnych zapasów, którą program Commerce Headquarter zwraca dla tego produktu, prawdopodobnie przekroczy ilość dostępnych zapasów w magazynie o jedną jednostkę. Jeśli jednak używane jest obliczenie po stronie kanału, sprzedaż środków pieniężnych i towarów do sprzedaży może zostać zaliczona do obliczeń i odjęta od podanej wartości dostępnych zapasów. Chociaż wartości obliczane zarówno po stronie kanału, jak i w wywołaniu usługi w czasie rzeczywistym, są tylko szacunkami dostępnych zapasów, wartość obliczona przez stronę kanału sprzedaży znacznie bardziej prawdopodobna na potrzeby bieżącego sklepu.

### <a name="get-started-with-pos-channel-side-calculated-inventory-availability"></a>Wprowadzenie do obliczeniowej dostępności zapasów po stronie punktu sprzedaży

Aby skorzystać z logiki obliczeniowej po stronie kanału i wyłączyć wywołania usługi w czasie rzeczywistym dla wyszukiwań zapasów z aplikacji punktu sprzedaży, najpierw należy włączyć funkcję **obliczania zoptymalizowanej dostępności produktów** za pośrednictwem obszaru roboczego **Zarządzanie funkcjami** w module Commerce Headquarters. Oprócz włączenia funkcji należy wprowadzić zmiany w **profilu funkcji**.

Aby zmienić **profil funkcji**, wykonaj poniższe kroki:

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**.
1. Wybierz profil funkcji.
1. W karcie skróconej **Funkcje** w sekcji **Obliczanie dostępności magazynowej** zmień wartość pola **Tryb obliczania dostępności zapasów** z **Usługa w czasie rzeczywistym** na **Kanał**. Domyślnie wszystkie profile funkcji korzystają z wywołań usługi w czasie rzeczywistym. Dlatego też należy zmienić wartość tego pola, jeśli ma być używana logika obliczania po stronie kanału. Ta zmiana będzie miała wpływ na każdy sklep detaliczny połączony z wybranym profilem funkcji.

Następnie należy zsynchronizować zmiany w kanale za pomocą procesu planowania dystrybucji, wykonując następujące kroki:

1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
1. Uruchom zadanie **1070** (**konfiguracja kanału**).

Po zakończeniu konfiguracji informacje dotyczące magazynu fizycznie dostępnego nie korzystają już z wywołania usługi w czasie rzeczywistym, gdy użytkownik w aplikacji punktu sprzedaży używa operacji **wyszukiwania zapasów** (widoki standardowe i macierzowe). Zamiast tego dane o fizycznie dostępnych zapasach dla bieżącego sklepu i wszystkich sklepów w grupie realizacja są obliczane na podstawie ostatniej znanej migawki, która została dostarczona do bazy danych kanału z modułu Commerce Headquarters. Wartość migawki jest dokładniejsza za pomocą obliczeń po stronie kanału w celu skorygowania dostępnej fizycznie wartości na podstawie dodatkowych transakcji sprzedaży lub zwrotów istniejących dla wybranego produktu w bazie danych kanału, które nie zostały uwzględnione w ostatnim zsynchronizowana migawka z zadania 1130. Jeśli baza danych kanału nie zawiera danych transakcyjnych dla żadnego z magazynów lub sklepów w grupie realizacji, nie zawiera żadnych dodatkowych transakcji, które mogą być uwzględniane w ponownym obliczaniu wartości. Dlatego najlepszym oszacowaniem dostępnych zapasów, które mogą być wyświetlane dla tych magazynów lub sklepów, są dane z ostatniej znanej migawki modułu Commerce Headquarters.

Na ekranach **realizacji zamówienia** w punkcie sprzedaży są również używane obliczenia po stronie kanału do wyświetlania dostępnych zapasów towarów, gdy jest wybrany wiersz realizacji zamówienia, a użytkownik wyświetla panel **szczegóły** dla dostępnych zapasów dla wybranego towaru.

## <a name="optimize-your-inventory-data"></a>Optymalizowanie danych magazynowych

Aby zapewnić możliwie najlepszy szacunek stanu zapasów, należy używać następujących zadań wsadowych modułu Commerce i często je wykonywać:

- **Zadanie P** — zadanie p znajduje się na stronie **harmonogramy dystrybucji** i powinno być często uruchamiane. To zadanie powoduje wykonanie zamówień w handlu elektronicznym, asynchronicznych zamówień odbiorców, które zostały utworzone w punkcie sprzedaży oraz zamówień gotówkowych i transprodukcyjnych, które zostały utworzone z baz danych kanałów w programie Commerce Headquarters, dzięki czemu mogą być dalej przetwarzane. Dopóki dane nie zostaną zsynchronizowane z kanału do modułu Commerce Headquarters, moduł Commerce Headquarters nie będzie miał żadnych informacji na temat korekt zapasów do produktów w magazynach powstałych w wyniku tych transakcji.
- **Synchronizuj zamówienia** — to zadanie przetwarza surowe dane transakcyjne w programie Commerce Headquarters, które zadanie P umożliwia i przekształca handel elektroniczny oraz transakcje asynchroniczne zamówienia odbiorcy w zamówienia sprzedaży w programie Commerce Headquarters. Do momentu przetwarzania tego zadania i tworzenia zamówień sprzedaży nie są tworzone żadne transakcje magazynowe. Z tego względu dostępne zapasy w module Commerce Headquarters nie będą rozważać transakcji.
- **Obliczanie zestawień transakcyjnych w partii** — dla transakcji kasowych tworzonych w sklepie proces księgowania cząstkowego zapewnia, że zapasy związane ze sprzedażą są skutecznie aktualizowane. Aby uzyskać najbardziej wydajne przetwarzanie transakcji magazynowych dla zamówień gotówkowych, należy skonfigurować system w taki sposób, aby korzystał [z funkcji księgowania cząstkowego](https://docs.microsoft.com/dynamics365/commerce/trickle-feed).
- **Księgowanie wyciągów transakcyjnych w partii** — to zadanie jest również wymagane w przypadku księgowania cząstkowego. Następuje po zadaniu **obliczenia zestawień transakcyjnych w partii**. To zadanie systematycznie księguje obliczone zestawienia, tak aby zamówienia sprzedaży dla sprzedaży gotówkowej i towarowej były tworzone w module Commerce Headquarters i by moduł Commerce Headquarters lepiej odzwierciedlał zapasy sklepu.
- **Dostępność produktu** — to zadanie tworzy migawkę zapasów z modułu Commerce Headquarters.
- **1130 (dostępność produktu)** — to zadanie znajduje się na stronie **harmonogramy dystrybucji** i powinno być uruchamiane natychmiast po zadaniu **dostępności produktu**. To zadanie transportuje dane migawki magazynowej z modułu Commerce Headquarters do baz danych kanału.

Zaleca się, aby te zadania wsadowe nie były uruchamiane zbyt często (co kilka minut). Częste uruchomienia będą przeciążać usługi Commerce Headquarter (HQ) i mogą potencjalnie wpłynąć na wydajność. Ogólnie rzecz biorąc, dobrą praktyką jest uruchamianie dostępności produktów i 1130 zadań na podstawie godzinowej oraz planowanie zadań P, synchronizowanie zamówień i przesyłanie zadań związanych z przesyłaniem strumieniowym z taką samą lub wyższą częstotliwością.

> [!NOTE]
> Ze względu na wydajność, gdy obliczenia dostępności zapasów w ramach kanału są używane do realizacji żądania dostępności zapasów przy użyciu logiki magazynowej obsługi handlu elektronicznego lub nowego kanału punktu sprzedaży, w obliczeniu jest używana pamięć podręczna do określenia, czy minęła wystarczająca liczba godzin do ponownego uruchomienia logiki obliczeń. Domyślna pamięć podręczna została ustawiona na 60 sekund. Na przykład po stronie kanału można włączyć obliczanie dla sklepu i wyświetlić dostępne zapasy produktu na stronie **wyszukiwania zapasów**. Jeśli zostanie sprzedana jedna jednostka produktu, strona **wyszukiwania zapasów** nie będzie pokazywała zmniejszonych zapasów, dopóki pamięć podręczna nie zostanie wyczyszczona. Po zaksięgowaniu transakcji przez użytkowników w punkcie sprzedaży należy poczekać 60 sekund przed sprawdzeniem, czy stan dostępnych zapasów został zmniejszony.

Jeśli scenariusz biznesowy wymaga krótszego czasu pamięci podręcznej, skontaktuj się z przedstawicielem pomocy technicznej, aby uzyskać pomoc.


[!INCLUDE[footer-include](../includes/footer-banner.md)]