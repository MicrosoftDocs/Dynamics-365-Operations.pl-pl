---
title: Wysyłka małych paczek
description: Ten temat zawiera informacje dotyczące funkcji Wysyłka małych paczek (SPS). Ta funkcja umożliwia aplikacji Microsoft Dynamics 365 Supply Chain Management przesyłanie do przewoźnika szczegółów dotyczących spakowanego kontenera, a następnie odbieranie od niego etykiety wysyłkowej, stawki kosztów i numeru śledzenia.
author: Mirzaab
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3e72959d79e9b3b03e061a0f26750e3bd025219e
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910216"
---
# <a name="small-parcel-shipping"></a>Wysyłka małych paczek

[!include [banner](../../includes/banner.md)]

Funkcja wysyłki małych paczek (SPS) umożliwia aplikacji Microsoft Dynamics 365 Supply Chain Management bezpośrednią interakcję z przewoźnikami, zapewniając strukturę komunikacji za pośrednictwem interfejsów API przewoźnika. Ta funkcja jest przydatna w przypadku wysyłki pojedynczych zamówień sprzedaży za pośrednictwem przewoźników komercyjnych, zamiast wysyłki kontenerów lub ładunków częściowych (LTL).

Funkcja SPS współpracuje z przewoźnikiem za pośrednictwem dedykowanego *aparatu stawki*. Twoja organizacja musi opracować ten aparat stawki we współpracy z przewoźnikiem lub usługą centrum przewoźników. Aparat stawki umożliwia aplikacji Microsoft Supply Chain Management przesyłanie do przewoźnika szczegółów dotyczących spakowanego kontenera, a następnie odbieranie od niego etykiety wysyłkowej, stawki kosztów i numeru śledzenia.

Zwrócona stawka kosztów wysyłki jest dodawana do skojarzonego zamówienia sprzedaży jako opłata dodatkowa. Zwróconą etykietę wysyłkową można następnie wydrukować automatycznie za pomocą drukarki ZPL (Zebra Programming Language) i zastosować do wysyłki. Przewoźnik zeskanuje tę etykietę wysyłkową, gdy wybierze paczki w magazynie.

## <a name="prepare-your-system-to-support-sps"></a>Przygotowywanie systemu do obsługi funkcji SPS

Aby można było rozpocząć korzystanie z funkcji SPS, należy włączyć funkcję SPS w zarządzaniu funkcjami, dodać aparat stawki oraz skonfigurować moduły **Zarządzanie transportem** i **Zarządzanie magazynem** do obsługi tej funkcji.

### <a name="turn-on-the-sps-feature"></a>Włączanie funkcji SPS

Aby móc używać funkcji SPS, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł**: *Zarządzanie transportem*
- **Nazwa funkcji:** *Wysyłka małych paczek*

### <a name="deploy-and-set-up-rate-engines"></a>Wdrażanie i konfigurowanie aparatów stawki

Supply Chain Management nie zawiera żadnych aparatów stawki. Musisz uzyskać lub utworzyć wszelkie wymagane aparaty stawki, a następnie dodać je do systemu. Microsoft dostarcza jednak pokazowy aparat stawki, który może służyć do testowania.

#### <a name="download-and-deploy-the-demo-rate-engine"></a>Pobieranie i wdrażanie aparatu stawek demonstracyjnych

Aby pobrać aparat stawek demonstracyjnych, należy wykonać następujące kroki.

1. W witrynie GitHub pobierz [bibliotekę linków dynamicznych (DLL) dla aparatu stawek demonstracyjnych](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).
1. Na serwerze aplikacji Supply Chain Management zapisz bibliotekę DLL w folderze **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.

#### <a name="create-and-deploy-functional-rate-engines"></a>Tworzenie i wdrażanie aparatów stawek funkcjonalnych

Aby uzyskać informacje dotyczące sposobu tworzenia i wdrażania aparatów stawek funkcjonalnych, tak aby można było ich używać w środowisku produkcyjnym lub testowym, zobacz następujące tematy:

- [Tworzenie nowego aparatu zarządzania transportem](../transportation/create-new-transportation-management-engine.md)
- [Ustawianie aparatów zarządzania transportem](/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

Aby uzyskać więcej informacji na temat sposobu tworzenia aparatu stawek SPS, zobacz następujący wpis w blogu: [Small Parcel Shipping: How to leverage small parcel shipping functionality in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5) (Wysyłka małych paczek: jak używać funkcji wysyłki małych paczek w Microsoft Dynamics 365).

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a>Konfigurowanie aparatu stawek w aplikacji Supply Chain Management

Po utworzeniu i wdrożeniu aparatu stawek dla SPS wykonaj poniższe kroki, aby go skonfigurować.

1. Przejdź do obszaru **Zarządzanie transportem \> Konfiguracja \> Aparaty \> Aparat stawki**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.
1. W nowym wierszu ustaw następujące pola:

    - **Aparat oceniania** — umożliwia wprowadzenie unikatowej nazwy aparatu stawki. Jeśli używasz aparatu stawek demonstracyjnych, wprowadź *Aparat stawek demonstracyjnych*.
    - **Nazwa** — umożliwia wprowadzenie krótkiego opisu aparatu stawki. Jeśli używasz aparatu stawek demonstracyjnych, wprowadź *Aparat stawek demonstracyjnych*.
    - **Identyfikator metadanych oceniania** — wybierz podstawę, która ma być używana do obliczenia stawki. Na przykład stawka może zostać obliczona na podstawie odległości. Jeśli używasz aparatu stawek demonstracyjnych, możesz pozostawić to pole puste.
    - **Zestaw aparatu** — umożliwia wprowadzenie nazwę wdrożonego pliku pakietu DLL. Jeśli używasz aparatu stawek demonstracyjnych, wprowadź *TMSSmallParcelShippingEngine.dll*.
    - **Klasa aparatu** — wprowadź nazwę klasy, która została ustalona dla aparatu stawki. Jeśli używasz aparatu stawek demonstracyjnych, wprowadź *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.

## <a name="example-scenario"></a>Przykładowy scenariusz

W tym przykładowym scenariuszu pokazano, jak skonfigurować funkcję SPS i używać jej po przygotowaniu systemu zgodnie z opisem podanym wcześniej w tym temacie. W tym scenariuszu jest używany poprzednio wymieniony aparat stawek demonstracyjnych.

### <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

Aby pracować z tym scenariuszem przy użyciu określonych pokazowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

### <a name="set-up-the-scenario"></a>Konfiguracja scenariusza

W tym przykładowym scenariuszu musisz mieć przewoźnika demonstracyjnego, grupę przewoźników, zasady pakowania i profil pakowania. Poniższe podsekcje wyjaśniają, jak przygotować rekordy wymagane dla tego scenariusza. W scenariuszu produkcyjnym proces konfiguracji zazwyczaj przypomina proces, który jest tutaj opisany. Zostaną jednak określone inne wartości.

#### <a name="set-up-carriers"></a>Konfigurowanie przewoźników

Wykonaj poniższe kroki, aby skonfigurować przewoźnika.

1. Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Firmy przewozowe**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać przewoźnika.
1. W nagłówku ustaw następujące wartości:

    - **Firma przewozowa:** *Przewoźnik pokazowy*
    - **Nazwa:** *Przewoźnik pokazowy*
    - **Tryb:** *Naziemny*

1. Na skróconej karcie **Omówienie** ustaw następujące wartości:

    - **Aktywowanie interfejsów firmy przewozowej:** *Tak*
    - **Aktywowanie oceny przewoźników:** *Tak*

1. Na skróconej karcie **Usługi** wybierz **Nowe**, aby dodać usługę do siatki.
1. Dla nowej usługi ustaw następujące wartości:

    - **Usługa przewozowa:** *Usługa przewoźnika pokazowego*
    - **Nazwa:** *Usługa przewoźnika pokazowego*
    - **Metoda transportu:** *Naziemny*

    W razie potrzeby wprowadź dowolne wartości dla wszystkich pozostałych pól. (Po zapisaniu nowego rekordu firmy przewozowej zostanie utworzony nowy tryb dostawy, a pole **trybu dostawy** zostanie ustawione automatycznie).

1. Na skróconej karcie **Profile stawek** kliknij opcję **Nowy**, aby dodać profil oceny do siatki.
1. Dla nowego profilu ustaw następujące wartości:

    - **Profil oceny:** *Usługa przewoźnika pokazowego*
    - **Nazwa:** *Usługa przewoźnika pokazowego*
    - **Aparat stawki:** *Aparat stawki pokazowej*

    W razie potrzeby wprowadź dowolne wartości dla wszystkich pozostałych pól.

1. Na okienku akcji wybierz opcję **Zapisz**.

Aby uzyskać więcej informacji o ustawianiu przewoźników, zobacz [Konfigurowanie firm przewozowych](../transportation/tasks/set-up-shipping-carriers.md).

#### <a name="set-up-carrier-service-accounts"></a>Konfigurowanie kont usług przewozowych

Wykonaj poniższe kroki, aby skonfigurować konto usługi przewozowej.

1. Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Ocena \> Konto usługi przewozowej**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać konto usługi przewozowej.
1. Dla nowego konta ustaw następujące wartości:

    - **Firma przewozowa:** *Przewoźnik pokazowy*
    - **Usługa przewozowa:** *Usługa przewoźnika pokazowego*
    - **Numer konta klienta przewoźnika:** numer konta klienta dla przewoźnika używany do weryfikacji i uwierzytelnienia połączenia z firmą przewozową. Ta wartość zostanie podana przez przewoźnika. Jeśli używasz usługi pokazowej, możesz wprowadzić dowolną wartość.
    - **Oddział:** *6*
    - **Magazyn:** *62*

    > [!NOTE]
    > Często wartość **numeru konta klienta dla przewoźnika** jest jedyną wartością wymaganą do uwierzytelnienia połączenia. Jeśli jednak przewoźnik wymaga dodatkowych parametrów uwierzytelniania, organizacja powinna dostosować tę stronę, aby w razie potrzeby dodawać dodatkowe pola.

#### <a name="set-up-a-container-packing-policy"></a>Konfigurowanie zasad pakowania kontenerów

Wykonaj poniższe kroki, aby skonfigurować zasady pakowania kontenerów.

1. Jeśli jeszcze nie skonfigurowano definicji drukarki ZPL, skonfiguruj ją za pomocą aplikacji agenta wyboru trasy dokumentów. Aby uzyskać więcej informacji, zobacz [Omówienie drukowania dokumentów](../../fin-ops-core/dev-itpro/analytics/print-documents.md) i pokrewne tematy.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Zasady pakowania kontenera**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać zasady pakowania kontenerów.
1. W nagłówku nowych zasad określ następujące wartości:

    - **Zasady pakowania kontenerów:** *Pokazowe zasady pakowania*
    - **Opis:** opis zasad

1. Na skróconej karcie **Omówienie** ustaw następujące wartości:

    - **Magazyn:** *62*
    - **Domyślna lokalizacja wysyłki końcowej:** *Brama dokowa*
    - **Jednostka wagi:** *KG*
    - **Zasada zamykania kontenera:** *Automatyczne zwalnianie*
    - **Zasady zwalniania kontenerów:** *Udostępnij w końcowej lokalizacji wysyłki*

1. Na skróconej karcie **Manifest kontenera** możesz ustawić następujące wartości:

    - **Automatyczny manifest przy zamknięciu kontenera:** *Tak*
    - **Wymagania dotyczące manifestu dla kontenera:** *Zarządzanie transportem*
    - **Drukuj zawartość kontenera:** *Nie*

1. Na skróconej karcie **Drukowanie etykiety przewoźnika** możesz ustawić następujące wartości:

    - **Drukuj etykietę wysyłkową kontenera:** *Zawsze*
    - **Nazwa drukarki:** nazwa drukarki ZPL, która powinna drukować etykiety wysyłkowe

#### <a name="set-up-a-packing-profile"></a>Konfigurowanie profilu pakowania

Wykonaj poniższe kroki, aby skonfigurować profil pakowania.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Opakowanie \> Profile pakowania**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy profil pakowania do siatki.
1. Dla nowego profilu ustaw następujące wartości:

    - **Identyfikator profilu pakowania:** *Pokazowy profil pakowania*
    - **Opis:** opis profilu
    - **Zasady pakowania kontenerów:** *Pokazowe zasady pakowania*
    - **Tryb identyfikatora kontenera:** *Automatyczny*
    - **Typ kontenera:** *SmallBox*

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a>Konfigurowanie klienta do używania przewoźnika SPS

Wykonaj następujące kroki, aby skonfigurować klienta do używania utworzonego przewoźnika.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Klienci \> Wszyscy klienci**.
1. W siatce znajdź i zaznacz odbiorcę *US-027*.
1. W okienku akcji na karcie **Ogólne** w grupie **Ustawienia** wybierz opcję **Konta klienta dla przewoźnika**.
1. Na stronie **Konta klienta dla przewoźnika** w okienku akcji wybierz pozycję **Nowy**, aby dodać konto do siatki.
1. Dla nowego konta ustaw następujące wartości:

    - **Firma przewozowa:** *Przewoźnik pokazowy*
    - **Numer konta klienta dla przewoźnika:** *12345* (ta wartość nie jest ważna w tym scenariuszu, ale zostanie dodana w następnej sekcji).

### <a name="go-through-the-example-scenario"></a>Przejdź przez przykładowy scenariusz

Po skonfigurowaniu wszystkich przykładowych danych zgodnie z opisem w poprzedniej sekcji można przejść do przykładowego scenariusza.

#### <a name="create-a-sales-order-and-process-the-work"></a>Tworzenie zamówienia sprzedaży i przetwarzanie pracy

Aby utworzyć zamówienie sprzedaży, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.
1. W oknie dialogowym **Utwórz zamówienie sprzedaży** ustaw pole **Konto klienta** na *US-027*.
1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Na skróconej karcie **Nagłówek zamówienia sprzedaży** ustaw w polu **Numer konta klienta dla przewoźnika** wartość wcześniej wybraną dla tego klienta (*12345*).
1. W sekcji **Wiersze zamówienia sprzedaży** dodaj wiersz sprzedaży i ustaw dla niego następujące wartości:

    - **Numer pozycji:** *A0002*
    - **Ilość:** *1*
    - **Oddział:** *6*
    - **Magazyn:** *62*

1. Przełącz do widoku **nagłówka**.
1. Na skróconej karcie **Dostawa** ustaw następujące wartości:

    - **Firma przewozowa:** *Przewoźnik pokazowy*
    - **Usługa przewozowa:** *Usługa przewoźnika pokazowego*

1. Przełącz się z powrotem do widoku **Wiersz**. Jeśli zostanie wyświetlony monit o aktualizację trybu dostawy dla wierszy sprzedaży, wybierz przycisk **Tak**.
1. W sekcji **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia, który został wcześniej ustawiony, a następnie wybierz opcję **Zapasy \> Rezerwacja**.
1. Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.
1. Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Utworzono pracę w celu przeniesienia towarów z lokalizacji pobrania do stacji pakowania.

1. W sekcji **Wiersze zamówienia sprzedaży** wybierz opcję **Magazyn \> Szczegóły wysyłki**.
1. Na stronie **Szczegóły wysyłki** zanotuj identyfikator wysyłki. Będzie on potrzebny przy pakowaniu wysyłki w stacji pakowania.
1. Zamknij stronę **Szczegóły wysyłki**, aby powrócić do zamówienia sprzedaży.
1. Zanotuj numer zamówienia sprzedaży, a następnie przejdź do obszaru **Zarządzanie magazynem \> Praca \> Cała praca**.
1. Użyj numeru zamówienia sprzedaży, aby znaleźć i wybrać pracę utworzoną dla zamówienia.
1. W okienku akcji na karcie **Praca** wybierz opcję **Zakończ pracę**.
1. Na stronie **Zakończenie pracy** w polu **Identyfikator użytkownika** wybierz identyfikator użytkownika. Następnie w okienku akcji wybierz pozycję **Weryfikuj pracę**.
1. Jeśli weryfikacja pracy zakończy się pomyślnie, wybierz pozycję **Zakończ pracę** w okienku akcji.

    Praca jest oznaczona jako zakończona w celu symulowania ruchu towarów do stacji pakowania.

#### <a name="pack-the-shipment"></a>Pakowanie wysyłki

Aby zapakować wysyłkę, wykonaj następujące czynności.

1. Przejdź do obszaru **Zarządzanie magazynem \> Ustawienia \> Pracownik** i upewnij się, że Twoje konto użytkownika jest skojarzone z kontem pracownika na potrzeby zarządzania magazynem.
1. Przejdź do **Zarządzanie magazynem \> Pobieranie i konteneryzacja \> Pakunek**.
1. W oknie dialogowym **Wybieranie stacji pakowania** ustaw następujące wartości:

    - **Oddział:** *6*
    - **Magazyn:** *62*
    - **Lokalizacja:** *Pakiet*
    - **Identyfikator profilu pakowania:** *Pokazowy profil pakowania*

1. Kliknij przycisk **OK**.
1. Zostanie wyświetlona strona **Pakowanie**. W scenariuszu produkcji pracownik zeskanuje numer identyfikacyjny lub identyfikator wysyłki. Jednak w tym scenariuszu otwórz stronę **Wszystkie wysyłki** i wyszukaj numer właśnie utworzonej wysyłki. Następnie wprowadź tę wartość w polu **Numer identyfikacyjny lub wysyłka** na stronie **Pakowanie**. Możesz również wprowadzić identyfikator wysyłki zanotowany wcześniej.
1. W okienku akcji wybierz opcję **Nowy kontener**.
1. Okno dialogowe, które zostanie wyświetlone, zawiera szczegóły dotyczące nowego kontenera. Pozostaw wartości domyślne, a następnie wybierz pozycję **OK**.
1. Na stronie **Pakowanie** na skróconej karcie **Pakowanie towarów** w polu **Identyfikator** wybierz pozycję *A0002*, aby zapakować ten towar. Towar jest dodawany do kontenera.
1. W okienku akcji wybierz pozycję **Kontenery do wysyłki**.

    Strona **Kontenery do wysyłki**, która zostanie wyświetlona, zawiera wiersz utworzonego właśnie kontenera. Jednak pole **Identyfikator manifestu kontenera** w tym wierszu jest obecnie puste, ponieważ nie odebrano jeszcze etykiety wysyłkowej i numeru śledzenia od przewoźnika.

1. W okienku akcji wybierz opcję **Zamknij kontener**.
1. W oknie dialogowym **Zamykanie kontenera** ustaw wartość pola **Waga brutto** na *1 kg*, a następnie wybierz przycisk **OK**.

    Etykieta wysyłkowa powinna zostać wydrukowana na wybranej wcześniej drukarce ZPL. Powinna ona przypominać następujący przykład.

    ![Przykładowa etykieta wysyłkowa](media/sps-label-example.png "Przykładowa etykieta wysyłkowa")

1. Zwróć uwagę, że wartości pól **Identyfikator manifestu kontenera** oraz **Suma frachtu** zostały dodane jako otrzymane od przewoźnika.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]