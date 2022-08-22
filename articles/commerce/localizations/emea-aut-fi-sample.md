---
title: Przykład integracji usługi rejestracji fiskalnej (Austria)
description: W tym artykule znajduje się omówienie przykładu integracji fiskalnej dla Austrii w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 7f4f1d796028330d2d655b1e13d3e36bbef95403
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287573"
---
# <a name="fiscal-registration-service-integration-sample-for-austria"></a>Przykład integracji usługi rejestracji fiskalnej (Austria)

[!include[banner](../includes/banner.md)]

W tym artykule znajduje się omówienie przykładu integracji fiskalnej dla Austrii w rozwiązaniu Microsoft Dynamics 365 Commerce.

Aby spełnić lokalne wymagania fiskalne dotyczące kas w Austrii, funkcjonalność rozwiązania Dynamics 365 Retail dla Austrii obejmuje przykład integracji punktu sprzedaży z zewnętrzną usługą rejestracji fiskalnej. Ten przykład rozszerza [funkcjonalność integracji fiskalnej](fiscal-integration-for-retail-channel.md). Jest on oparty na rozwiązaniu [EFR (Electronic Fiscal Register)](https://www.efsta.eu/at/fiskalloesungen/oesterreich) firmy [EFSTA](https://www.efsta.eu/at/) i umożliwia komunikację z usługą EFR za pośrednictwem protokołu HTTPS. Usługę EFR należy hostować na stacji sprzętowej rozwiązania Retail albo na osobnym komputerze, z którym można nawiązać połączenie z poziomu stacji sprzętowej. Przykładowa integracja ma formę kodu źródłowego i jest częścią zestawu SDK modułu Retail.

Firma Microsoft nie udostępnia żadnego sprzętu, oprogramowania ani dokumentacji firmy EFSTA. Aby uzyskać więcej informacji dotyczących sposobu pobierania i używania rozwiązania EFR, skontaktuj się z [firmą EFSTA](https://www.efsta.eu/at/kontakt).

## <a name="scenarios"></a>Scenariusze

Przykład integracji usługi rejestracji fiskalnej dla Austrii umożliwia wykorzystanie następujących scenariuszy:

- Rejestracja transakcji kasowych w usłudze rejestracji fiskalnej:

    - Wysyłanie szczegółowych danych transakcji do usługi rejestracji fiskalnej. Te dane zawierają informacje wiersza sprzedaży oraz informacje o rabatach, płatnościach i podatkach.
    - Przechwytywanie odpowiedzi z usługi rejestracji fiskalnej. Ta odpowiedź zawiera podpis cyfrowy i link do zarejestrowanej transakcji.
    - Rejestrowanie podatków i mapowanie ich na kody podatków usługi rejestracji fiskalnej.
    - Drukowanie kodu QR dla zarejestrowanej transakcji na paragonie.

- Rejestracja operacji dotyczących kart upominkowych i wpłat odbiorców jako transakcji niekasowych w usłudze rejestracji fiskalnej:

    - Wystawianie karty upominkowej lub dodawanie do niej pieniędzy.
    - Rejestrowanie wpłaty na konto odbiorcy.
    - Rejestrowanie wpłaty za zamówienie odbiorcy.

- Rejestracja niezwiązanych ze sprzedażą transakcji i zdarzeń jako transakcji niekasowych w usłudze rejestracji fiskalnej:

    - Otwieranie i zamykanie zmiany
    - Kwota początkowa, przyjęcie do kasy i pobranie środków płatniczych
    - Ręczna zmiana ceny
    - Zastąpienie podatku
    - Drukuj kopię paragonu
    - Otwarta szuflada
    - Drukuj częściowy raport sprzedaży
    - Drukuj końcowy raport sprzedaży

- Drukowanie zestawień na koniec dnia (częściowych/końcowych raportów sprzedaży) zawierających pola specyficzne dla Austrii:

    - Łączna liczba produktów lub usług, które zostały dostarczone do odbiorców
    - Podział sprzedaży według stawki podatku
    - Podział płatności według kasjera / operatora kasy
    - Rabaty i zwroty zmniejszające dzienną sprzedaż
    - Zerowa sprzedaż (upominki)

- Obsługa błędów, np. następujących opcji:

    - Ponowienie próby rejestracji fiskalnej, o ile ponowienie próby jest możliwe, np. jeśli usługa rejestracji fiskalnej jest niedostępna, nie jest gotowa albo nie odpowiada.
    - Odroczenie rejestracji fiskalnej.
    - Pominięcie rejestracji fiskalnej lub oznaczenie transakcji jako zarejestrowanej i wprowadzenie kodów informacji oznaczających przyczynę błędu oraz dodatkowe informacje.
    - Sprawdzanie dostępności usługi rejestracji fiskalnej przed otwarciem nowej transakcji sprzedaży lub sfinalizowaniem transakcji sprzedaży.

### <a name="gift-cards"></a>Karty upominkowe

Przykład integracji usługi rejestracji fiskalnej implementuje następujące reguły związane z kartami upominkowymi:

- Wyłączenie z transakcji kasowej wierszy sprzedaży, które są związane z operacjami *Wystaw kartę upominkową* i *Dodaj do karty upominkowej*. Zamiast rejestrować te wiersze jako część transakcji kasowej, zarejestruj je jako osobną transakcję niekasową w usłudze rejestracji fiskalnej.
- Jeśli paragon zawiera tylko wiersze dotyczące karty upominkowej, nie drukuj podziału grupy podatków ani kodu QR.
- Wydrukuj na paragonie łączną kwotę dotyczącą kart upominkowych, które zostały wystawione lub doładowane w ramach transakcji osobno od kwoty transakcji kasowej.
- Zapisanie obliczanych korekt wierszy płatności w bazie danych kanału w odniesieniu do odpowiedniej transakcji fiskalnej.
- Płatność kartą upominkową jest traktowana jako zwykła płatność.

### <a name="customer-deposits-and-customer-order-deposits"></a>Obsługa wpłat odbiorcy i wpłat za zamówienie odbiorcy

Przykład integracji usługi rejestracji fiskalnej implementuje następujące reguły, które są związane z wpłatami odbiorców i wpłatami za zamówienia odbiorców:

- Zarejestruj transakcję niekasową, jeśli transakcja jest wpłatą odbiorcy.
- Zarejestruj transakcję niekasową, jeśli transakcja zawiera tylko wpłatę za zamówienie odbiorcy lub zwrot takiej wpłaty.
- Odejmij kwotę wpłaty za zamówienie odbiorcy od wiersza płatności, kiedy tworzone jest zamówienie hybrydowe odbiorcy.
- Zapisz obliczane korekty wierszy płatności w bazie danych kanału w odniesieniu do odpowiedniej transakcji fiskalnej dla hybrydowego zamówienia odbiorcy.

### <a name="limitations-of-the-sample"></a>Ograniczenia przykładowej integracji

Usługa rejestracji fiskalnej obsługuje tylko scenariusze, w których podatek jest uwzględniony w cenie. Z tego względu opcja **Cena zawiera podatek** musi być ustawiona na **Tak** zarówno dla sklepów, jak i odbiorców.

## <a name="set-up-commerce-for-austria"></a>Konfigurowanie rozwiązania Commerce dla Austrii

W tej sekcji opisano ustawienia rozwiązania Commerce, które są specyficzne oraz zalecane dla Austrii. Aby uzyskać więcej informacji dotyczących konfiguracji, zobacz [stronę główną rozwiązania Commerce](../index.md).

Aby móc używać funkcjonalności specyficznej dla Austrii, musisz określić następujące ustawienia:

- W podstawowym adresie osoby prawnej ustaw w polu **Kraj/region** wartość **AUT** (Austria).
- W profilu funkcjonalności punktu sprzedaży każdego sklepu zlokalizowanego w Austrii ustaw w polu **Kod ISO** wartość **AT** (Austria).

Musisz także określić wymienione poniżej ustawienia dla Austrii. Pamiętaj, że po zakończeniu konfigurowania musisz uruchomić odpowiednie zadania dystrybucji.

### <a name="set-up-vat-per-austrian-requirements"></a>Konfigurowanie podatku VAT zgodnie z austriackimi wymaganiami

Musisz utworzyć kody podatków, grupy podatków oraz grupy podatków dla towarów. Musisz także skonfigurować informacje o podatkach dla produktów i usług. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania i używania funkcji podatków, zobacz [Omówienie podatku](../../finance/general-ledger/indirect-taxes-overview.md).

Na paragonach sprzedaży można drukować skrócony kod odpowiadający kodowi podatku (na przykład „A” lub „B”). Aby udostępnić tę funkcjonalność, ustaw wartość pola **Drukuj kod** na stronie **Kody podatków**.

### <a name="set-up-stores"></a>Konfigurowanie sklepów

Na stronie **Wszystkie sklepy** zaktualizuj szczegóły sklepu. W szczególności ustaw następujące parametry:

- W polu **Grupa podatków** określ grupę podatków, która ma być używana w odniesieniu do sprzedaży odbiorcy domyślnemu.
- Ustaw dla opcji **Ceny zawierają podatek** wartość **Tak**.
- W polu **Nazwa** ustaw wartość firmy. Ta zmiana pomaga zagwarantować, że nazwa firmy będzie widoczna na paragonie sprzedaży. Możesz również dodać nazwę firmy do układu paragonu sprzedaży w postaci dowolnego tekstu.
- W polu **Numer identyfikacji podatkowej (NIP)** ustaw numer identyfikacyjny firmy. Ta zmiana pomaga zagwarantować, że numer identyfikacyjny firmy będzie widoczny na paragonie sprzedaży. Możesz również dodać numer identyfikacyjny firmy do układu paragonu sprzedaży w postaci dowolnego tekstu.

### <a name="set-up-functionality-profiles"></a>Konfigurowanie profilów funkcjonalności

Skonfiguruj profile funkcjonalności punktu sprzedaży:

- Na skróconej karcie **Numeracja paragonów** skonfiguruj numerowanie paragonów, tworząc lub aktualizując rekordy dla typów transakcji przyjęcia **Sprzedaż**, **Zamówienie sprzedaży** i **Zwrot**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Konfigurowanie pól niestandardowych, aby można było ich używać w formatach paragonów dla paragonów sprzedaży

Możesz skonfigurować tekst w języku oraz pola niestandardowe używane w formatach paragonów dla punktu sprzedaży. Domyślna firma użytkownika, który tworzy konfigurację paragonu, powinna być tą samą osobowością prawną, w której jest tworzone ustawienie tekstu w języku. Alternatywnie, można również utworzyć ten sam tekst językowy w domyślnej firmie użytkownika i dla tego samego bytu prawnego, dla którego utworzono konfigurację.

Na stronie **Tekst w języku** dodaj wymienione poniżej rekordy dla etykiet pól niestandardowych używanych w układach paragonów. Pamiętaj, że wartości **Identyfikatora języka**, **Identyfikatora tekstu** i **Tekst** przedstawione w poniższej tabeli są tylko przykładami. Możesz je zmienić, tak aby spełniały Twoje wymagania. Jednak używane wartości **Identyfikator tekstu** muszą być unikatowe oraz większe lub równe 900001.

Dodaj z tabeli wymienione poniżej etykiety punktu sprzedaży do obszaru **Punkt sprzedaży** na stronie **Tekst w języku**:

| Identyfikator języka | Identyfikator tekstu | Tekst                      |
|-------------|---------|---------------------------|
| en-US       | 900001  | Kod QR                   |
| en-US       | 900002  | Ciągły numer         |
| en-US       | 900003  | Drukowany kod podatku detalicznego     |
| en-US       | 900004  | Suma (sprzedaż)             |
| en-US       | 900005  | Suma podatku (sprzedaż)         |
| en-US       | 900006  | Suma z podatkiem (sprzedaż) |
| en-US       | 900007  | Kwota podatku (sprzedaż)        |
| en-US       | 900008  | Podstawa podatku (sprzedaż)         |

Na stronie **Pola niestandardowe** dodaj następujące rekordy dla pól niestandardowych używanych w układach paragonów. Pamiętaj, że wartości **Identyfikator tekstu podpisu** muszą być zgodne z wartościami **Identyfikator tekstu** określonymi na stronie **Tekst w języku**:

| Nazwa                 | Typ    | Identyfikator tekstu podpisu |
|----------------------|---------|-----------------|
| QRCODE               | Pokwitowanie | 900001          |
| CONTINUOUSNUMBER     | Pokwitowanie | 900002          |
| RETAILPRINTCODE      | Pokwitowanie | 900003          |
| SALESTOTAL           | Pokwitowanie | 900004          |
| SALESTOTALTAX        | Pokwitowanie | 900005          |
| SALESTOTALINCLUDETAX | Pokwitowanie | 900006          |
| SALESTAXAMOUNT       | Pokwitowanie | 900007          |
| SALESTAXBASIS        | Pokwitowanie | 900008          |

> [!NOTE]
> Ważne jest, aby określić poprawne nazwy pól niestandardowych, tak jak podano w poprzedniej tabeli. Niepoprawna nazwa pola niestandardowego spowoduje brak danych na paragonach.

### <a name="configure-receipt-formats"></a>Konfigurowanie formatów paragonów

Dla każdego wymaganego formatu paragonu zmień wartość pola **Zachowanie drukowania** na **Zawsze drukuj**.

W projektancie formatów paragonów dodaj wymienione poniżej pola niestandardowe do odpowiednich sekcji paragonu. Pamiętaj, że nazwy pól muszą odpowiadać tekstom w języku zdefiniowanym w poprzedniej sekcji.

- **Nagłówek:** Dodaj następujące pola:

    - Pola **Nazwa sklepu** i **Numer identyfikacji podatkowej**, które służą do drukowania nazwy i numeru identyfikacyjnego firmy na paragonach. Możesz również dodać nazwę i numer identyfikacyjny firmy do układu w postaci dowolnego tekstu.
    - Pola **Adres sklepu**, **Data**, **Godzina (format 24h)**, **Numer paragonu** i **Numer rejestru**.
    - Pola **Numer ciągły**, które służą do identyfikowania numeru transakcji kasowej w usłudze rejestracji fiskalnej.

- **Wiersze:** Dodaj następujące pola:

    - **Nazwa towaru**.
    - **Ilość**.
    - **Cena razem (z podatkiem)**.
    - Pole **Drukowany kod podatku detalicznego**, które służy do drukowania skróconego kodu odpowiadającego kodowi podatku stosowanego do towaru.

- **Stopka:** Dodaj następujące pola:

    - Pola płatności, tak aby zostały wydrukowane kwoty płatności dla poszczególnych metod płatności. Na przykład dodaj pola **Nazwa metody płatności** oraz **Kwota metody płatności** do jednego wiersza układu.
    - Grupa pól **Suma sprzedaży**:

        - Pole **Suma (sprzedaż)**, które służy do drukowania łącznej kwoty sprzedaży gotówkowej objętej paragonem. Kwota bez podatku. Przedpłaty i operacje związane z kartami upominkowymi są wykluczane.
        - Pole **Suma z podatkiem (sprzedaż)**, które służy do drukowania łącznej kwoty sprzedaży gotówkowej objętej paragonem. Kwota zawiera podatek. Przedpłaty i operacje związane z kartami upominkowymi są wykluczane.
        - Pole **Suma podatku (sprzedaż)**, które służy do drukowania łącznej kwoty podatku od sprzedaży gotówkowej objętej paragonem. Przedpłaty i operacje związane z kartami upominkowymi są wykluczane.

    - Grupa pól **Podział podatku**. Wszystkie pola w tej grupie pól muszą być drukowane w jednym osobnym wierszu.

        - Pole **Identyfikator podatku**, które jest standardowym polem umożliwiającym wydrukowanie podsumowania podatku dla każdego kodu podatku. To pole musi zostać dodane do nowego wiersza.
        - Pole **Procent podatku**, które jest standardowym polem służącym do drukowania efektywnej stawki podatku dla kodu podatku.
        - Pole **Podstawa podatku (sprzedaż)**, które służy do drukowania łącznej kwoty sprzedaży gotówkowej objętej paragonem dla kodu podatku. Przedpłaty i operacje związane z kartami upominkowymi są wykluczane.
        - Pole **Kwota podatku (sprzedaż)**, które służy do drukowania kwoty podatku od sprzedaży gotówkowej objętej paragonem dla kodu podatku.
        - Pole **Drukowany kod podatku detalicznego**, które służy do drukowania skróconego kodu odpowiadającego kodowi podatku.

    - Pole **Kod QR**, które służy do drukowania odwołania do zarejestrowanej transakcji kasowej w formie kodu QR.

        > [!NOTE]
        > Wartość **Kod QR** jest pobierana z odpowiedzi rejestru fiskalnego. Usługa EFR zwraca kod QR w swojej odpowiedzi, tylko jeśli wartość pola **Atrybuty** w konfiguracji usługi EFR została opisana w dokumentacji firmy EFSTA. Format kodu QR w polu **Atrybuty** w konfiguracji usługi EFR musi mieć wartość **BMP**.

Aby uzyskać więcej informacji o sposobie pracy z formatami paragonów, zobacz [Konfigurowanie i projektowanie formatów paragonów](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-austria"></a>Konfigurowanie integracji fiskalnej dla Austrii

Przykład integracji usługi rejestracji fiskalnej dla Austrii jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu Retail SDK. Przykład znajduje się w folderze **src\\FiscalIntegration\\Efr** repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (na przykład [przykład w folderze release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). Przykład [składa się](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji Commerce Runtime (CRT), oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu Retail SDK, zobacz [Architektura zestawu Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) oraz [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Austrii (starsza wersja)](emea-aut-fi-sample-sdk.md). Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

Wykonaj kroki konfiguracji integracji fiskalnej w sposób opisany w [Konfigurowanie integracji fiskalnej dla kanałów Commerce](setting-up-fiscal-integration-for-retail-channel.md):

1. [Konfigurowanie procesu rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Zwróć też uwagę na ustawienia dla procesu rejestracji fiskalnej [specyficzne dla tego przykładu integracji usługi rejestracji fiskalnej](#set-up-the-registration-process).
1. [Określanie ustawienia ustawień obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Konfiguracja składników kanału](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Konfigurowanie procesu rejestracji

Aby włączyć proces rejestracji, wykonaj następujące kroki w celu skonfigurowania centrali w rozwiązaniu Commerce. Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji fiskalnej dla kanałów rozwiązania Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Pobierz pliki konfiguracji dla dostawcy dokumentów fiskalnych i łącznika fiskalnego:

    1. Otwórz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji (na przykład **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Otwórz folder **src \> FiscalIntegration \> Efr**.
    1. Otwórz folder **Configurations \> DocumentProviders** i pobierz pliki konfiguracji dostawcy dokumentów fiskalnych: **DocumentProviderFiscalEFRSampleAustria.xml** i **DocumentProviderNonFiscalEFRSampleAustria.xml** (na przykład [lokalizacja plików w folderze release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders)).
    1. Pobierz plik konfiguracji łącznika fiskalnego z lokalizacji **Configurations \> Connectors \> ConnectorEFRSample.xml** (na przykład [plik z folderu release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Pliki konfiguracji dla tego przykładu integracji fiskalnej znajdują się w wymienionych poniżej folderach zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS:
    >
    > - **Pliki konfiguracji dostawcy dokumentów fiskalnych:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration
    > - **Plik konfiguracji łącznika fiskalnego:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration
    > 
    > Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Wspólne parametry handlu**. Na karcie **Ogólne** ustaw dla opcji **Włącz integrację fiskalną** wartość **Tak**.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Dostawcy dokumentów fiskalnych** i załaduj pobrane wcześniej pliki konfiguracji dostawcy dokumentów fiskalnych.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Łączniki fiskalne** i załaduj pobrany wcześniej plik konfiguracji łącznika fiskalnego.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile funkcjonalności łącznika**. Utwórz dwa nowe profile funkcjonalne łącznika, po jednym dla każdego załadowanego wcześniej dostawcy dokumentów fiskalnych, a następnie wybierz załadowany wcześniej łącznik fiskalny. Zaktualizuj [ustawienia mapowania danych](#default-data-mapping) zgodnie z wymaganiami.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile techniczne łącznika**. Utwórz nowy profil techniczny łącznika i wybierz załadowany wcześniej łącznik fiskalny. Zaktualizuj [ustawienia łącznika](#fiscal-connector-settings) zgodnie z wymaganiami.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Grupy łączników fiskalnych**. Utwórz dwie nowe grupy łączników fiskalnych (po jednej dla każdego utworzonego wcześniej profilu funkcjonalnego łącznika).
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnej**. Utwórz nowy proces rejestracji fiskalnej oraz dwa kroki procesu rejestracji fiskalnej, a następnie wybierz utworzone wcześniej grupy łączników fiskalnych.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**. Wybierz profil funkcjonalności połączony ze sklepem, w którym należy aktywować proces rejestracji. Na skróconej karcie **Proces rejestracji fiskalnej** wybierz utworzony wcześniej proces rejestracji fiskalnej. Aby włączyć rejestrację zdarzeń niefiskalnych w punkcie sprzedaży, na skróconej karcie **Funkcje** w obszarze **Punkt sprzedaży** ustaw dla opcji **Inspekcja** wartość **Tak**.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile sprzętu**. Wybierz profil sprzętu połączony ze stacją sprzętową, z którą będzie połączona drukarka fiskalna. Na skróconej karcie **Fiskalne urządzenia peryferyjne** wybierz utworzony wcześniej profil techniczny łącznika.
1. Otwórz harmonogram dystrybucji (**Handel detaliczny i inny \> Składniki IT w handlu detalicznym i innym \> Harmonogram dystrybucji**) i wybierz zadania **1070** i **1090** do przesyłania danych do bazy danych kanału.

#### <a name="default-data-mapping"></a>Domyślne mapowanie danych

Następujące domyślne mapowanie danych jest uwzględnione w bieżącej konfiguracji dostawcy dokumentu fiskalnego dostarczanego jako część przykładowej integracji fiskalnej:

- **Mapowanie stawek podatku VAT** — mapowanie wartości procentowych podatku skonfigurowanych dla kodów podatków na wartości atrybutu **TaxG** (grupa podatków) w żądaniach wysyłanych do usługi fiskalnej. Poniżej pokazano mapowanie domyślne:

    ```
    A: 20.00; B: 10.00; C: 13.00; D: 0.00; E: 19.00; F: 7.00
    ```

    Pierwszy składnik każdej pary reprezentuje grupę podatków VAT, która jest obsługiwana przez usługę rejestracji fiskalnej EFR. Drugi składnik reprezentuje odpowiadającą jej stawkę podatku VAT. Aby uzyskać więcej informacji dotyczących grup podatku VAT obsługiwanych przez usługę EFR dla Austrii, zobacz [Informacje referencyjne usługi EFR](https://public.efsta.net/efr/).

#### <a name="fiscal-connector-settings"></a>Ustawienia łącznika fiskalnego

Wymienione poniżej ustawienia wchodzą w skład konfiguracji łącznika fiskalnego dostarczanej jako część przykładu integracji fiskalnej:

- **Adres punktu końcowego** — adres URL usługi rejestracji fiskalnej.
- **Limit czasu urządzenia** — ilość czasu (w milisekundach), przez który łącznik fiskalny będzie czekał na odpowiedź z usługi rejestracji fiskalnej.
- **Pokaż powiadomienia rejestracji fiskalnej** — ta flaga określa, czy powiadomienia zwracane przez usługę rejestracji fiskalnej mają być wyświetlane operatorowi.

### <a name="configure-channel-components"></a>Konfiguracja składników kanału.

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Austrii (starsza wersja)](emea-aut-fi-sample-sdk.md).
>
> Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

#### <a name="set-up-the-development-environment"></a>Konfigurowanie środowiska projektowego

Aby skonfigurować środowisko projektowe w celu testowania i rozszerzania przykładu, wykonaj poniższe kroki.

1. Sklonuj lub pobierz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions). Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji. Aby uzyskać więcej informacji, zobacz [Pobieranie przykładów i pakietów referencyjnych zestawu Retail SDK z witryn GitHub i NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Otwórz rozwiązanie EFR w lokalizacji **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln** i skompiluj je.
1. Zainstaluj rozszerzenia kolekcji CRT:

    1. Znajdź instalatora rozszerzeń kolekcji CRT:

        - **Commerce Scale Unit:** w folderze **Efr\\ScaleUnit\\ScaleUnit.EFR.Installer\\bin\\Debug\\net461** znajdź instalatora **ScaleUnit.EFR.Installer**.
        - **Lokalna kolekcja CRT w aplikacji Modern POS:** w folderze **Efr\\ModernPOS\\ModernPOS.EFR.Installer\\bin\\Debug\\net461** znajdź instalatora **ModernPOS.EFR.Installer**.

    1. Uruchom instalatora rozszerzeń kolekcji CRT z poziomu wiersza polecenia:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EFR.Installer.exe install --verbosity 0
            ```

        - **Lokalna kolekcja CRT w aplikacji Modern POS:**

            ```Console
            ModernPOS.EFR.Installer.exe install --verbosity 0
            ```

1. Zainstaluj rozszerzenia programu Fiscal Connector:

    Rozszerzenia programu Fiscal Connector można zainstalować w stacji [sprzętowej](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) lub kasie [punktu sprzedaży](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

    1. Zainstaluj rozszerzenia stacji sprzętowej:

        1. W folderze **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461** znajdź instalatora **HardwareStation.EFR.Installer**.
        1. Uruchom instalator rozszerzenia z wiersza polecenia, uruchamiając następujące polecenie.

            ```Console
            HardwareStation.EFR.Installer.exe install --verbosity 0
            ```

    1. Zainstaluj rozszerzenia punktu sprzedaży:

        1. Otwórz przykładowe rozwiązanie łącznika fiskalnego punkty sprzedaży **Dynamics365Commerce.Solutions\\FiscalIntegration\\PosFiscalConnectorSample\\Contoso.PosFiscalConnectorSample.sln** i skompiluj go.
        1. Commerce Scale Unit: w folderze **PosFiscalConnectorSample\\StoreCommerce.Installer\\bin\\Debug\\net461** znajdź instalatora **Contoso.PosFiscalConnectorSample.StoreCommerce.Installer**.
        1. Uruchom instalator rozszerzenia z wiersza polecenia, uruchamiając następujące polecenie.

            ```Console
            Contoso.PosFiscalConnectorSample.StoreCommerce.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Środowisko produkcyjne

Wykonaj kroki opisane w artykule [Konfigurowanie potoku kompilacji dla przykładu integracji fiskalnej](fiscal-integration-sample-build-pipeline.md), aby wygenerować i wydać rozwiązanie Cloud Scale Unit oraz samoobsługowe wdrażalne pakiety dla przykładu integracji fiskalnej. Plik YAML szablonu **EFR build-pipeline.yml** można znaleźć w folderze **Pipeline\\YAML_Files** w repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Projekt rozszerzenia

Przykład integracji usługi rejestracji fiskalnej dla Austrii jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu Retail SDK. Przykład znajduje się w folderze **src\\FiscalIntegration\\Efr** repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (na przykład [przykład w folderze release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). Przykład [składa się](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji CRT, oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu Retail SDK, zobacz [Architektura zestawu Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) oraz [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Austrii (starsza wersja)](emea-aut-fi-sample-sdk.md). Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

### <a name="commerce-runtime-extension-design"></a>Projekt rozszerzenia środowiska uruchomieniowego Commerce 

Rozszerzenie (dostawca dokumentów fiskalnych) służy do generowania dokumentów specyficznych dla usługi oraz obsługi odpowiedzi z usługi rejestracji fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Istnieją dwa programy obsługi żądań dla dostawców dokumentów:

- **DocumentProviderEFRFiscalAUT** — ten program obsługi służy do generowania dokumentów fiskalnych dla usługi rejestracji fiskalnej.
- **DocumentProviderEFRNonFiscalAUT** — ten program obsługi służy do generowania dokumentów niefiskalnych dla usługi rejestracji fiskalnej.

Te programy obsługi są dziedziczone z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla usługi, który ma zostać zarejestrowany w usłudze rejestracji fiskalnej.
- **GetNonFiscalDocumentDocumentProviderRequest** — to żądanie zawiera informacje dotyczące dokumentu niefiskalnego, który ma zostać wygenerowany. Zwraca dokument specyficzny dla usługi, który ma zostać zarejestrowany w usłudze rejestracji fiskalnej.
- **GetSupportedRegistrableEventsDocumentProviderRequest** — to zapytanie zwraca listę zdarzeń do subskrybowania. Aktualnie obsługiwane są następujące zdarzenia: sprzedaż, drukowanie częściowego raportu sprzedaży, drukowanie końcowego raportu sprzedaży, wpłaty na konta odbiorców, wpłaty za zamówienia odbiorców, zdarzenia inspekcji i transakcji niezwiązane ze sprzedażą.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** — to żądanie zwraca odpowiedź z usługi rejestracji fiskalnej. Ta odpowiedź jest serializowana do postaci ciągu, dzięki czemu można ją zapisać.

#### <a name="configuration"></a>Konfiguracja

Pliki konfiguracji dla dostawcy dokumentów fiskalnych znajdują się w folderze **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders** w repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/):

- **DocumentProviderFiscalEFRSampleAustria** — plik konfiguracji dostawcy dokumentów fiskalnych służący do obsługi dokumentów fiskalnych.
- **DocumentProviderNonFiscalEFRSampleAustria** — plik konfiguracji dostawcy dokumentów fiskalnych służący do obsługi dokumentów niefiskalnych.

Te pliki umożliwiają skonfigurowanie ustawień dostawcy dokumentów fiskalnych z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Rozszerzenie złącza fiskalnego służy do komunikacji z usługą rejestracji fiskalnej. Rozszerzenie stacji sprzętowej używa HTTP i protokołów HTTP w celu przesyłania dokumentów generowanych przez rozszerzenie kolekcji CRT do usługi rejestracji fiskalnej. Obsługuje również odpowiedzi odbierane z usługi rejestracji fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **EFRHandler** jest punktem wejściowym obsługi żądań kierowanych do usługi rejestracji fiskalnej.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik fiskalny obsługuje następujące żądania:

- **SubmitDocumentFiscalDeviceRequest** — to żądanie wysyła dokumenty do usługi rejestracji fiskalnej i zwraca odpowiedź z tej usługi.
- **IsReadyFiscalDeviceRequest** — to żądanie służy do sprawdzania kondycji usługi rejestracji fiskalnej.
- **InitializeFiscalDeviceRequest** — to żądanie służy do inicjowania usługi rejestracji fiskalnej.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji dla łącznika fiskalnego znajduje się w lokalizacji **src\\FiscalIntegration\\Efr\\Configurations\\Connectors\\ConnectorEFRSample.xml** w repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ten plik umożliwia skonfigurowanie ustawień łącznika fiskalnego z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

### <a name="pos-fiscal-connector-extension-design"></a>Projekt przedłużenia złącza fiskalnego POS

Rozszerzenie konektor fiskalny POS służy do komunikacji z usługą rejestracji fiskalnej z POS. Używa protokołu HTTPS do komunikacji.

#### <a name="fiscal-connector-factory"></a>Fabryka łącznika fiskalnego

Fabryka łącznika fiskalnego mapuje nazwę łącznika na implementację łącznika fiskalnego i znajduje się w pliku **Pos.Extension\\Connectors\\FiscalConnectorFactory.ts**. Nazwa łącznika powinna być zgodna z nazwą łącznika fiskalnego określoną w centrali handlowej.

#### <a name="efr-fiscal-connector"></a>Łącznik fiskalny EFR

Łącznik obrachunkowy CSV znajduje się w pliku **Pos.Extension\\Connectors\\Efr\\EfrFiscalConnector.ts**. Implementuje on interfejs **IFiscalConnector** obsługujący następujące żądania:

- **FiscalRegisterSubmitDocumentClientRequest** — to żądanie wysyła dokumenty do usługi rejestracji fiskalnej i zwraca odpowiedź z tej usługi.
- **FiscalRegisterIsReadyClientRequest** — to żądanie służy do sprawdzania kondycji usługi rejestracji fiskalnej.
- **FiscalRegisterInitializeClientRequest** — to żądanie służy do inicjowania usługi rejestracji fiskalnej.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **src\\FiscalIntegration\\Efr\\Configurations\\Connectors** w [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) repozytorium. Ten plik umożliwia skonfigurowanie ustawień łącznika fiskalnego z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- **Adres punktu końcowego** — adres URL usługi rejestracji fiskalnej.
- **Limit czasu** — Czas w milisekundach, przez który łącznik będzie czekał na odpowiedź z usługi rejestracji fiskalnej.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
