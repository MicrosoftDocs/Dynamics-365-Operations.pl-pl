---
title: Przykład integracji usługi rejestracji fiskalnej dla Republiki Czeskiej
description: W tym temacie znajduje się omówienie przykładu integracji fiskalnej dla Republiki Czeskiej w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-4-1
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: cb9679bd02c5400fc015c6807407b01e9bf55343
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388243"
---
# <a name="fiscal-registration-service-integration-sample-for-the-czech-republic"></a>Przykład integracji usługi rejestracji fiskalnej dla Republiki Czeskiej

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

W tym temacie znajduje się omówienie przykładu integracji fiskalnej dla Republiki Czeskiej w rozwiązaniu Microsoft Dynamics 365 Commerce.

Aby spełnić lokalne wymagania fiskalne dotyczące kas w Republice Czeskiej, funkcjonalność rozwiązania Dynamics 365 Commerce dla Republiki Czeskiej obejmuje przykład integracji punktu sprzedaży z zewnętrzną usługą rejestracji fiskalnej. Ten przykład rozszerza [funkcjonalność integracji fiskalnej](fiscal-integration-for-retail-channel.md). Jest on oparty na rozwiązaniu [EFR (Electronic Fiscal Register)](https://efsta.org/sicherheitsloesungen/) firmy [EFSTA](https://efsta.org/) i umożliwia komunikację z usługą EFR za pośrednictwem protokołu HTTPS. Usługa EFR gwarantuje elektroniczną rejestrację sprzedaży (EET, Elektronická evidence tržeb), czyli przekazywanie danych sprzedaży w trybie online do fiskalnej usługi sieci web używanej przez urzędy skarbowe.

Usługę EFR należy hostować na stacji sprzętowej rozwiązania Commerce albo na osobnym komputerze, z którym można nawiązać połączenie z poziomu stacji sprzętowej. Przykładowa integracja ma formę kodu źródłowego i jest częścią zestawu SDK modułu Retail.

Firma Microsoft nie udostępnia żadnego sprzętu, oprogramowania ani dokumentacji firmy EFSTA. Aby uzyskać więcej informacji dotyczących sposobu pobierania i używania rozwiązania EFR, skontaktuj się z [firmą EFSTA](https://efsta.org/kontakt/).

## <a name="scenarios"></a>Scenariusze

Przykład integracji usługi rejestracji fiskalnej dla Republiki Czeskiej umożliwia wykorzystanie następujących scenariuszy:

- Rejestracja transakcji kasowych w usłudze rejestracji fiskalnej.

    - Wysyłanie szczegółowych danych transakcji do usługi rejestracji fiskalnej. Te dane zawierają informacje wiersza sprzedaży oraz informacje o rabatach, płatnościach i podatkach. Usługa rejestracji fiskalnej wysyła dane do usługi sieci web używanej przez urzędy skarbowe i otrzymuje z niej potwierdzenie, które zawiera kod identyfikacji fiskalnej transakcji.
    - Przechwytywanie odpowiedzi z usługi rejestracji fiskalnej. Ta odpowiedź zawiera dane fiskalne, takie jak m.in. kod identyfikacji fiskalnej i kod zabezpieczeń transakcji.
    - Drukowanie danych fiskalnych dla zarejestrowanej transakcji na paragonie.

- Rejestracja operacji dotyczących kart upominkowych i wpłat odbiorców w usłudze rejestracji fiskalnej.

    - Wystawianie karty upominkowej lub dodawanie do niej pieniędzy.
    - Rejestrowanie wpłaty na konto odbiorcy.
    - Tworzenie zamówienia odbiorcy i rejestrowanie wpłaty za zamówienie.
    - Edytowanie zamówienia odbiorcy i zastępowanie wpłaty za zamówienie.
    - Anulowanie zamówienia odbiorcy i zwracanie wpłaty za zamówienie.

- Obsługa błędów, takich jak poniższe opcje.

    - Ponowienie próby rejestracji fiskalnej, o ile ponowienie próby jest możliwe, np. jeśli usługa rejestracji fiskalnej jest niedostępna, nie jest gotowa albo nie odpowiada.
    - Odroczenie rejestracji fiskalnej.
    - Pominięcie rejestracji fiskalnej lub oznaczenie transakcji jako zarejestrowanej i wprowadzenie kodów informacji oznaczających przyczynę błędu oraz dodatkowe informacje.
    - Sprawdzanie dostępności usługi rejestracji fiskalnej przed otwarciem nowej transakcji sprzedaży lub sfinalizowaniem transakcji sprzedaży.

### <a name="gift-cards"></a>Karty upominkowe

Przykład integracji usługi rejestracji fiskalnej implementuje wymienione poniżej reguły związane z kartami upominkowymi.

- Wiersze sprzedaży powiązane z operacją *Wystaw kartę upominkową* lub *Dodaj do karty upominkowej* w transakcji sprzedaży są oznaczane za pomocą specjalnego atrybutu, gdy transakcja jest rejestrowana w usłudze rejestracji fiskalnej.
- Płatność kartą upominkową jest traktowana jak zwykła płatność i oznaczana za pomocą specjalnego atrybutu, gdy transakcja jest rejestrowana w usłudze rejestracji fiskalnej.

### <a name="customer-account-deposits-and-customer-order-deposits"></a>Wpłaty na konta odbiorców i wpłaty za zamówienia odbiorców

Przykład integracji usługi rejestracji fiskalnej implementuje wymienione poniżej reguły, które są związane z wpłatami na konta odbiorców i wpłatami za zamówienia odbiorców.

- Transakcja związana z wpłatą na konto odbiorcy lub wpłatą za zamówienie odbiorcy jest rejestrowana w usłudze rejestracji fiskalnej jako jednowierszowa transakcja i jest oznaczana za pomocą specjalnego atrybutu. W tym wierszu jest określona grupa podatku VAT dla wpłat.
- Gdy jest tworzone zamówienie hybrydowe odbiorcy, czyli zamówienie odbiorcy zawierające produkty, które odbiorca może zabrać ze sklepu, oraz produkty, które zostaną później pobrane lub wysłane, transakcja rejestrowana w usłudze rejestracji fiskalnej zawiera wiersze produktów, które zostały zabrane, oraz wiersz wpłaty za zamówienie.
- Płatność z konta odbiorcy jest traktowana jak zwykła płatność i oznaczana za pomocą specjalnego atrybutu, gdy transakcja jest rejestrowana w usłudze rejestracji fiskalnej.
- Kwota wpłaty za zamówienie odbiorcy stosowana do operacji Pobierz dotyczącej zamówienia odbiorcy jest traktowana jak zwykła płatność i oznaczana za pomocą specjalnego atrybutu, gdy transakcja jest rejestrowana w usłudze rejestracji fiskalnej.

### <a name="offline-registration"></a>Rejestracja w trybie offline

Jeśli usługa rejestracji fiskalnej nie będzie mogła przekazać danych transakcji do fiskalnej usługi sieci web używanej przez urzędy skarbowe (na przykład z powodu przekroczenia limitu czasu odpowiedzi) i nie otrzyma potwierdzenia z usługi sieci web (czyli kodu identyfikacji fiskalnej transakcji), wygeneruje lokalny podpis transakcji i umieści go w odpowiedzi wraz ze specjalnym kodem błędu. Po przywróceniu działania połączenia sieciowego usługa rejestracji fiskalnej ponownie wyśle transakcje w oryginalnej kolejności w tle.

### <a name="limitations-of-the-sample"></a>Ograniczenia przykładowej integracji

Usługa rejestracji fiskalnej obsługuje tylko scenariusze, w których podatek jest uwzględniony w cenie. Z tego względu opcja **Cena zawiera podatek** musi być ustawiona na **Tak** zarówno dla sklepów, jak i odbiorców.

## <a name="set-up-commerce-for-the-czech-republic"></a>Konfigurowanie lokalizacji rozwiązania Commerce dla Republiki Czeskiej

W tej sekcji opisano ustawienia rozwiązania Commerce, które są specyficzne oraz zalecane dla Republiki Czeskiej. Aby uzyskać więcej informacji dotyczących konfiguracji, zobacz [stronę główną rozwiązania Commerce](../index.md).

Aby móc używać funkcjonalności specyficznej dla Republiki Czeskiej, musisz określić wymienione poniżej ustawienia.

- W podstawowym adresie osoby prawnej ustaw w polu **Kraj/region** wartość **CZE** (Republika Czeska).
- W profilu funkcjonalności punktu sprzedaży każdego sklepu zlokalizowanego w Republiki Czeskiej ustaw w polu **Kod ISO** wartość **CZ** (Republika Czeska).

Musisz także określić wymienione poniżej ustawienia dla Republiki Czeskiej. Pamiętaj, że po zakończeniu konfigurowania musisz uruchomić odpowiednie zadania dystrybucji.

### <a name="set-up-vat-per-czech-republic-requirements"></a>Konfigurowanie podatku VAT zgodnie z wymaganiami obowiązującymi w Republice Czeskiej


Musisz utworzyć kody podatków, grupy podatków oraz grupy podatków dla towarów. Musisz także skonfigurować informacje o podatkach dla produktów i usług. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania i używania funkcji podatków, zobacz [Omówienie podatku](../../finance/general-ledger/indirect-taxes-overview.md).

### <a name="set-up-stores"></a>Konfigurowanie sklepów

Na stronie **Wszystkie sklepy** zaktualizuj szczegóły sklepu. W szczególności ustaw wymienione poniżej parametry.

- W polu **Grupa podatków** określ grupę podatków, która ma być używana w odniesieniu do sprzedaży odbiorcy domyślnemu.
- Ustaw dla opcji **Ceny zawierają podatek** wartość **Tak**.
- W polu **Nazwa** ustaw wartość firmy. Ta zmiana pomaga zagwarantować, że nazwa firmy będzie widoczna na paragonie sprzedaży. Możesz również dodać nazwę firmy do układu paragonu sprzedaży w postaci dowolnego tekstu.
- W polu **Numer identyfikacji podatkowej (NIP)** ustaw numer identyfikacyjny firmy. Ta zmiana pomaga zagwarantować, że numer identyfikacyjny firmy będzie widoczny na paragonie sprzedaży. Możesz również dodać numer identyfikacyjny firmy do układu paragonu sprzedaży w postaci dowolnego tekstu.

### <a name="set-up-functionality-profiles"></a>Konfigurowanie profilów funkcjonalności

Skonfiguruj profile funkcjonalności punktu sprzedaży.

- Na skróconej karcie **Numeracja paragonów** skonfiguruj numerowanie paragonów, tworząc lub aktualizując rekordy dla typów transakcji przyjęcia **Sprzedaż**, **Zamówienie sprzedaży** i **Zwrot**.

### <a name="set-up-registration-numbers"></a>Konfigurowanie numerów rejestracji

1. Wybierz kolejno pozycje **Administrowanie organizacją \> Globalna książka adresowa \> Typy rejestracji \> Typy rejestracji**. Utwórz nowy typ rejestracji. W polu **Kraj/region** określ wartość **CZE** (Republika Czeska) i ogranicz jego zakres do organizacji.
2. Wybierz kolejno pozycje **Administrowanie organizacją \> Globalna książka adresowa \> Typy rejestracji \> Kategorie rejestracji**. Utwórz nową kategorię rejestracji. Wybierz typ rejestracji z poprzedniego kroku i ustaw w polu **Kategoria rejestracji** wartość **Identyfikator lokalu firmy**.
3. Wybierz kolejno opcje **Administrowanie organizacją \> Organizacje \> Jednostki operacyjne**. Dla każdego sklepu znajdującego się w Republice Czeskiej wybierz jednostkę powiązaną ze sklepem. Na skróconej karcie **Adres** rozwiń listę rozwijaną **Więcej opcji** i wybierz pozycję **Zaawansowane**. 
4. Na otwartej stronie **Zarządzanie adresami** musisz określić poniższe ustawienie.

    - Na skróconej karcie **Adres** ustaw w polu **Kraj/region** wartość **CZE**.
    - Na skróconej karcie **Identyfikator rejestracji** utwórz nowy rekord. Wybierz utworzony wcześniej typ rejestracji i ustaw numer rejestracji.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Konfigurowanie pól niestandardowych, aby można było ich używać w formatach paragonów dla paragonów sprzedaży

Możesz skonfigurować tekst w języku oraz pola niestandardowe używane w formatach paragonów dla punktu sprzedaży. Domyślna firma użytkownika, który tworzy konfigurację paragonu, powinna być tą samą osobowością prawną, w której jest tworzone ustawienie tekstu w języku. Alternatywnie, można również utworzyć ten sam tekst językowy w domyślnej firmie użytkownika i dla tego samego bytu prawnego, dla którego utworzono konfigurację.

Na stronie **Tekst w języku** dodaj wymienione poniżej rekordy dla etykiet pól niestandardowych używanych w układach paragonów. Pamiętaj, że wartości **Identyfikatora języka**, **Identyfikatora tekstu** i **Tekst** przedstawione w poniższej tabeli są tylko przykładami. Można je zmienić, aby spełniały wymagania użytkownika. Jednak używane wartości **Identyfikator tekstu** muszą być unikatowe oraz większe lub równe 900001.

Dodaj z tabeli wymienione poniżej etykiety punktu sprzedaży do obszaru **Punkt sprzedaży** na stronie **Tekst w języku**:

| Identyfikator języka | Identyfikator tekstu | Tekst                   |
|-------------|---------|------------------------|
| en-US       | 900001  | ID provozovny/pokladny |
| en-US       | 900002  | BKP                    |
| en-US       | 900003  | PKP                    |
| en-US       | 900004  | FIK                    |
| en-US       | 900005  | Informacje                   |
| en-US       | 900006  | Numer sekwencyjny        |

Na stronie **Pola niestandardowe** dodaj następujące rekordy dla pól niestandardowych używanych w układach paragonów. Pamiętaj, że wartości **Identyfikator tekstu podpisu** muszą być zgodne z wartościami **Identyfikator tekstu** określonymi na stronie **Tekst w języku**:

| Nazwa                 | Typ    | Identyfikator tekstu podpisu |
|----------------------|---------|-----------------|
| TLT                  | Pokwitowanie | 900001          |
| SEC                  | Pokwitowanie | 900002          |
| SIGN                 | Pokwitowanie | 900003          |
| FISCAL               | Pokwitowanie | 900004          |
| INFO                 | Pokwitowanie | 900005          |
| CONTINUOUSNUMBER     | Pokwitowanie | 900006          |

> [!NOTE]
> Ważne jest, aby określić poprawne nazwy pól niestandardowych, tak jak podano w poprzedniej tabeli. Niepoprawna nazwa pola niestandardowego spowoduje brak danych na paragonach.

### <a name="configure-receipt-formats"></a>Konfigurowanie formatów paragonów

Dla każdego wymaganego formatu paragonu zmień wartość pola **Zachowanie drukowania** na **Zawsze drukuj**.

W projektancie formatów paragonów dodaj wymienione poniżej pola niestandardowe do odpowiednich sekcji paragonu. Pamiętaj, że nazwy pól muszą odpowiadać tekstom w języku zdefiniowanym w poprzedniej sekcji.

- **Nagłówek:** dodaj wymienione poniżej pola.

    - **Nazwa sklepu** i **Numer identyfikacji podatkowej**: te pola służą do drukowania nazwy i numeru identyfikacyjnego firmy na paragonach. Możesz również dodać nazwę i numer identyfikacyjny firmy do układu w postaci dowolnego tekstu.
    - **Adres sklepu**, **Data**, **Godzina (format 24h)**, **Numer paragonu** i **Numer rejestru**.
    - **Numer sekwencyjny**: to pole identyfikuje numer transakcji kasowej w usłudze rejestracji fiskalnej.

- **Wiersze:** dodaj wymienione poniżej pola.

    - **Nazwa towaru**
    - **Ilość**
    - **Cena razem (z podatkiem)**

- **Stopka:** dodaj wymienione poniżej pola.

    - Pola płatności, tak aby zostały wydrukowane kwoty płatności dla poszczególnych metod płatności. Na przykład dodaj pola **Nazwa metody płatności** oraz **Kwota metody płatności** do jednego wiersza układu.
    - **ID provozovny/pokladny**: to pole umożliwia drukowanie identyfikatorów lokalu firmy i kasy.
    - **BKP**: to pole umożliwia drukowanie kodu zabezpieczeń podatnika przypisanego przez usługę rejestracji fiskalnej.
    - **FIK**: to pole umożliwia drukowanie kodu identyfikacji podatkowej transakcji, który jest przypisywany przez usługę sieci web używaną przez urzędy skarbowe w przypadku pomyślnej rejestracji w trybie online.
    - **PKP**: to pole umożliwia drukowanie kodu podpisu podatnika generowanego przez usługę rejestracji fiskalnej w przypadku rejestracji w trybie offline.
    - **Informacje:** to pole umożliwia drukowanie dodatkowych informacji z usługi rejestracji fiskalnej.

Aby uzyskać więcej informacji o sposobie pracy z formatami paragonów, zobacz [Konfigurowanie i projektowanie formatów paragonów](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-the-czech-republic"></a>Konfigurowanie integracji fiskalnej dla Republiki Czeskiej

Przykład integracji usługi rejestracji fiskalnej dla Republiki Czeskiej jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu Retail SDK. Przykład znajduje się w folderze **src\\FiscalIntegration\\Efr** repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (na przykład [przykład w folderze release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). Przykład [składa się](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji Commerce Runtime (CRT), oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu Retail SDK, zobacz [Architektura zestawu Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) oraz [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Republiki Czeskiej (starsza wersja)](emea-cze-fi-sample-sdk.md).
>
> Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

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
    1. Pobierz plik konfiguracji dostawcy dokumentów fiskalnych z lokalizacji **Configurations \> DocumentProviders \> DocumentProviderFiscalEFRSampleCzech.xml** (na przykład [plik z folderu release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders/DocumentProviderFiscalEFRSampleCzech.xml)).
    1. Pobierz plik konfiguracji łącznika fiskalnego z lokalizacji **Configurations \> Connectors \> ConnectorEFRSample.xml** (na przykład [plik z folderu release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Pliki konfiguracji dla tego przykładu integracji fiskalnej znajdują się w wymienionych poniżej folderach zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS:
    >
    > - **Plik konfiguracji dostawcy dokumentów fiskalnych:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleCzech.xml
    > - **Plik konfiguracji łącznika fiskalnego:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration\\ConnectorEFRSample.xml
    > 
    > Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Wspólne parametry handlu**. Na karcie **Ogólne** ustaw dla opcji **Włącz integrację fiskalną** wartość **Tak**.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Dostawcy dokumentów fiskalnych** i załaduj pobrany wcześniej plik konfiguracji dostawcy dokumentów fiskalnych.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Łączniki fiskalne** i załaduj pobrany wcześniej plik konfiguracji łącznika fiskalnego.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile funkcjonalności łącznika**. Utwórz nowy profil funkcjonalny łącznika. Wybierz dostawcę dokumentów oraz łącznik, które załadowano wcześniej. Zaktualizuj [ustawienia mapowania danych](#default-data-mapping) zgodnie z wymaganiami.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile techniczne łącznika**. Utwórz nowy profil techniczny łącznika i wybierz załadowany wcześniej łącznik fiskalny. Zaktualizuj [ustawienia łącznika](#fiscal-connector-settings) zgodnie z wymaganiami.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Grupy łączników fiskalnych**. Utwórz nową grupę łączników fiskalnych dla utworzonego wcześniej profilu funkcjonalnego łącznika.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnej**. Utwórz nowy proces rejestracji fiskalnej oraz krok procesu rejestracji fiskalnej, a następnie wybierz utworzoną wcześniej grupę łączników fiskalnych.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**. Wybierz profil funkcjonalności połączony ze sklepem, w którym należy aktywować proces rejestracji. Na skróconej karcie **Proces rejestracji fiskalnej** wybierz utworzony wcześniej proces rejestracji fiskalnej.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile sprzętu**. Wybierz profil sprzętu połączony ze stacją sprzętową, z którą będzie połączona drukarka fiskalna. Na skróconej karcie **Fiskalne urządzenia peryferyjne** wybierz utworzony wcześniej profil techniczny łącznika.
1. Otwórz harmonogram dystrybucji (**Handel detaliczny i inny \> Składniki IT w handlu detalicznym i innym \> Harmonogram dystrybucji**) i wybierz zadania **1070** i **1090** do przesyłania danych do bazy danych kanału.

#### <a name="default-data-mapping"></a>Domyślne mapowanie danych

Następujące domyślne mapowanie danych jest uwzględnione w bieżącej konfiguracji dostawcy dokumentu fiskalnego dostarczanego jako część przykładowej integracji fiskalnej:

- **Mapowanie stawek podatku VAT** — mapowanie wartości procentowych podatku skonfigurowanych dla kodów podatków na wartości atrybutu **TaxG** (grupa podatków) w żądaniach wysyłanych do usługi fiskalnej. Poniżej pokazano mapowanie domyślne:

    ```
    A: 21.00; B: 15.00; C: 10.00; Z: 0.00
    ```

    Pierwszy składnik każdej pary reprezentuje grupę podatków VAT, która jest obsługiwana przez usługę rejestracji fiskalnej EFR. Drugi składnik reprezentuje odpowiadającą jej stawkę podatku VAT. Aby uzyskać więcej informacji dotyczących grup podatków VAT obsługiwanych przez usługę EFR dla Republiki Czeskiej, zobacz [Informacje referencyjne usługi EFR](https://public.efsta.net/efr/).

- **Mapowanie domyślnej grupy podatku VAT** — wszystkie kwoty podatku VAT, których nie można zamapować na jedną ze wstępnie zdefiniowanych grup podatku VAT, będą przypisywane do domyślnej (podstawowej) grupy podatku VAT. Poniżej pokazano mapowanie domyślne:

    ```
    A
    ```

- **Mapowanie grupy podatku VAT dla wpłat** — kwoty wpłat na konta odbiorców oraz kwoty wpłat za zamówienia odbiorców będą przypisywane do grupy podatku VAT dla wpłat. Poniżej pokazano mapowanie domyślne:

    ```
    Z
    ```

#### <a name="fiscal-connector-settings"></a>Ustawienia łącznika fiskalnego

Wymienione poniżej ustawienia wchodzą w skład konfiguracji łącznika fiskalnego dostarczanej jako część przykładu integracji fiskalnej:

- **Adres punktu końcowego** — adres URL usługi rejestracji fiskalnej.
- **Limit czasu** — ilość czasu (w milisekundach), przez który łącznik fiskalny będzie czekał na odpowiedź z usługi rejestracji fiskalnej.

### <a name="configure-channel-components"></a>Konfiguracja składników kanału.

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Republiki Czeskiej (starsza wersja)](emea-cze-fi-sample-sdk.md).
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

Przykład integracji usługi rejestracji fiskalnej dla Republiki Czeskiej jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu Retail SDK. Przykład znajduje się w folderze **src\\FiscalIntegration\\Efr** repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (na przykład [przykład w folderze release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). Przykład [składa się](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji CRT, oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu Retail SDK, zobacz [Architektura zestawu Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) oraz [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Republiki Czeskiej (starsza wersja)](emea-cze-fi-sample-sdk.md). Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

### <a name="commerce-runtime-extension-design"></a>Projekt rozszerzenia środowiska uruchomieniowego Commerce

Rozszerzenie (dostawca dokumentów fiskalnych) służy do generowania dokumentów specyficznych dla usługi oraz obsługi odpowiedzi z usługi rejestracji fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Istnieje jeden program obsługi żądań **DocumentProviderEFRFiscalCZE** dla dostawcy dokumentów, który służy do generowania dokumentów fiskalnych dla usługi rejestracji fiskalnej.

Ten program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje wymienione poniżej żądania.

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla usługi, który ma zostać zarejestrowany w usłudze rejestracji fiskalnej.
- **GetSupportedRegistrableEventsDocumentProviderRequest** — to zapytanie zwraca listę zdarzeń do subskrybowania. Obecnie obsługiwane są następujące zdarzenia: sprzedaż, wpłaty na konta odbiorców i wpłaty za zamówienia odbiorców.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** — to żądanie zwraca odpowiedź z usługi rejestracji fiskalnej. Ta odpowiedź jest serializowana do postaci ciągu, dzięki czemu można ją zapisać.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji dla dostawcy dokumentów fiskalnych znajduje się w lokalizacji **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleCzech.xml** w repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ten plik umożliwia skonfigurowanie ustawień dostawcy dokumentów fiskalnych z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Rozszerzenie (łącznik fiskalny) służy do komunikacji z usługą rejestracji fiskalnej. Rozszerzenie stacji sprzętowej używa protokołu HTTP w celu przesyłania dokumentów generowanych przez rozszerzenie kolekcji CRT do usługi rejestracji fiskalnej. Obsługuje również odpowiedzi odbierane z usługi rejestracji fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **EFRHandler** jest punktem wejściowym obsługi żądań kierowanych do usługi rejestracji fiskalnej.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik obsługuje wymienione poniżej żądania.

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
