---
title: Przykładowa integracja drukarki fiskalnej dla Włoch
description: W tym artykule zawarto ogólne informacje o przykładowej integracji fiskalnej dla Włoch w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-11-01
ms.openlocfilehash: 6ad97e87e4114a8f2250d0ba4880b7a466b3689e
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631404"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Przykładowa integracja drukarki fiskalnej dla Włoch

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

W tym artykule zawarto ogólne informacje o przykładowej integracji fiskalnej dla Włoch w rozwiązaniu Microsoft Dynamics 365 Commerce.

Funkcjonalność rozwiązania Commerce dla Włoch obejmuje przykładową integrację punktu sprzedaży (POS) z drukarką fiskalną. Ten przykład rozszerza [funkcjonalność integracji fiskalnej](fiscal-integration-for-retail-channel.md), dzięki czemu działa ona z drukarkami [Epson FP-90III Series](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) firmy Epson i umożliwia komunikację z drukarką fiskalną w trybie serwera sieci web za pośrednictwem usługi siecie web EpsonFPMate używającej interfejsu API Fiscal ePOS-Print. Przykład obsługuje tylko tryb Registratore Telematico (RT). Przykładowa integracja ma formę kodu źródłowego i jest częścią zestawu SDK modułu Commerce.

Firma Microsoft nie udostępnia żadnego sprzętu, oprogramowania ani dokumentacji firmy Epson. Aby dowiedzieć się, jak uzyskać drukarkę fiskalną i jak ją obsługiwać, skontaktuj się z firmą [Epson Italia S.p.A](https://www.epson.it)

## <a name="scenarios"></a>Scenariusze

Przykład integracji drukarki fiskalnej dla Włoch umożliwia realizację następujących scenariuszy:

- Scenariusze sprzedaży:

    - Drukowanie paragonu fiskalnego dla sprzedaży i zwrotów zapłaty przy kasie.
    - Rejestrowanie odpowiedzi z drukarki fiskalnej i zapisywanie jej w bazie danych kanału.
    - Podatki:

        - Mapowanie kodów podatku drukarki fiskalnej (działy).
        - Przesyłanie zamapowanych danych podatku do drukarki fiskalnej.
        - Drukowanie podatków na paragonie fiskalnym.

    - Płatności:

        - Mapowanie metod płatności drukarki fiskalnej.
        - Drukowanie płatności na paragonie fiskalnym.
        - Drukowanie informacji o zmianie.

    - Drukowanie rabatów dla pozycji.
    - Karty upominkowe:

        - Wykluczanie pozycji wydanej/doładowanej karty upominkowej z paragonu fiskalnego dla sprzedaży.
        - Drukowanie płatności używającej karty upominkowej jako zwykłej metody płatności.

    - Drukowanie paragonów fiskalnych dla operacji zamówień odbiorcy:

        - Paragon fiskalny nie jest drukowany dla wypłaty za zamówienie odbiorcy.
        - Drukowanie paragonu fiskalnego z wyszczególnieniem wierszy hybrydowego zamówienia odbiorcy.
        - Drukowanie paragonu fiskalnego dla operacji pobrania zamówienia odbiorcy.
        - Drukowanie paragonu fiskalnego dla zamówienia zwrotu.

    - Drukowanie kodu kreskowego dla numeru paragonu widocznego na paragonie fiskalnym.
    - Umożliwia drukowanie [informacji o odbiorcy](emea-ita-customer-information.md), które zostały określone dla transakcji sprzedaży w paragonie fiskalnym. Przykładem tej informacji jest kod na loterię odbiorcy. 

- Zestawienia na koniec dnia (raporty fiskalne X i końcowy raport sprzedaży).
- Obsługa błędów, np. następujących opcji:

    - Ponowienie próby rejestracji fiskalnej, o ile ponowienie próby jest możliwe, np. jeśli drukarka fiskalna nie jest podłączona, jest niegotowa lub nie odpowiada albo jeśli w drukarce nie ma papieru lub doszło do zakleszczenia papieru.
    - Odrocz rejestrację fiskalną.
    - Pominięcie rejestracji fiskalnej lub oznaczenie transakcji jako zarejestrowanej i wprowadzenie kodów informacji oznaczających przyczynę błędu oraz dodatkowe informacje.
    - Sprawdź dostępność drukarki fiskalnej przed otwarciem nowej transakcji sprzedaży lub zakończeniem transakcji sprzedaży.

### <a name="gift-cards"></a>Karty upominkowe

Przykładowa integracja drukarki fiskalnej implementuje następujące reguły związane z kartami upominkowymi:

- Wyłączenie z paragonu fiskalnego wierszy sprzedaży, które są związane z operacjami *Wystaw kartę upominkową* i *Dodaj do karty upominkowej*.
- Niedrukowanie paragonu fiskalnego, jeśli zawiera on tylko wiersze karty upominkowej.
- Odjęcie łącznej kwoty kart upominkowych, które zostały wystawione lub doładowane w ramach transakcji z wierszy płatności paragonu fiskalnego.
- Zapisanie obliczanych korekt wierszy płatności w bazie danych kanału w odniesieniu do odpowiedniej transakcji fiskalnej.
- Płatność kartą upominkową jest traktowana jako zwykła płatność.

### <a name="customer-deposits-and-customer-order-deposits"></a>Obsługa wpłat odbiorcy i wpłat za zamówienie odbiorcy

Przykładowa integracji drukarki fiskalnej implementuje następujące reguły, które są związane z wpłatami odbiorcy i wpłatami za zamówienie odbiorcy:

- Nie drukuj paragonu fiskalnego, jeśli transakcja jest wpłatą odbiorcy.
- Nie drukuj paragonu fiskalnego, jeśli transakcja zawiera tylko wpłatę za zamówienie klienta lub zwrot takiej wpłaty.
- Drukuj kwotę wcześniej zapłaconej wpłaty na paragonie fiskalnym dla operacji odebrania zamówienia odbiorcy.
- Odejmij kwotę wpłaty za zamówienie odbiorcy od wiersza płatności, kiedy tworzone jest zamówienie hybrydowe odbiorcy.
- Zapisz obliczane korekty wierszy płatności w bazie danych kanału w odniesieniu do odpowiedniej transakcji fiskalnej dla hybrydowego zamówienia odbiorcy.

### <a name="limitations-of-the-sample"></a>Ograniczenia przykładowej integracji

- Drukarka fiskalna obsługuje tylko scenariusze, w których podatek od sprzedaży jest uwzględniony w cenie. Z tego względu opcja **Cena zawiera podatek** musi być ustawiona na **Tak** zarówno dla sklepów, jak i odbiorców.
- Raporty dzienne (fiskalny częściowy i końcowy raport sprzedaży) są drukowane przy użyciu formatu osadzonego w oprogramowaniu układowym drukarki fiskalnej.
- Mieszane transakcje nie są obsługiwane przez drukarkę fiskalną. Opcja **Zabraniaj umieszczania sprzedaży i zwrotów na jednym paragonie** powinna być ustawiona na **Tak** w profilach funkcji POS.
- Przykład obsługuje integrację tylko z drukarką fiskalną pracującą w trybie Registratore Telematico (RT).

## <a name="set-up-fiscal-integration-for-italy"></a>Konfigurowanie integracji fiskalnej dla Włoch

Przykład integracji drukarki fiskalnej dla Włoch jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu SDK do Commerce. Próbka znajduje się w folderze **src\\FiscalIntegration\\EpsonFP90IIISample** w repozytorium [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). [Próbka](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) składa się z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji Commerce Runtime (CRT), oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu SDK do Commerce, zobacz [Pobieranie próbek i pakietów referencyjnych zestawu SDK do Retail z GitHub i NuGet](../dev-itpro/retail-sdk/sdk-github.md) i [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!NOTE]
> Przykład integracji drukarki fiskalnej dla Włoch jest dostępny w zestawie SDK do Commerce w wersji 10.0.29. W wersji Commerce 10.0.28 lub wcześniejszej musisz użyć poprzedniej wersji zestawu SDK do Retail na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Włoch (starsza wersja)](emea-ita-fpi-sample-sdk.md).

Wykonaj kroki konfiguracji integracji fiskalnej w sposób opisany w [Konfiguracja integracji fiskalnej dla kanałów Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Konfigurowanie procesu rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Należy zwrócić także uwagę na ustawienia dla procesu rejestracji fiskalnej [specyficzne dla tej drukarki fiskalnej w przykładzie integracji](#set-up-the-registration-process).
1. [Konfigurowanie tekstów fiskalnych dotyczących rabatów](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).
1. [Określanie ustawienia ustawień obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Konfigurowanie raportów fiskalnych X / końcowych raportów sprzedaży z POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).
1. [Konfigurowanie funkcjonalności służącej do zarządzania informacjami klientów w punkcie sprzedaży](emea-ita-customer-information.md#setup).
1. [Konfigurowanie składników kanału](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Konfigurowanie procesu rejestracji

Aby włączyć proces rejestracji, wykonaj następujące kroki w celu skonfigurowania centrali w rozwiązaniu Commerce. Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji fiskalnej dla kanałów rozwiązania Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Pobierz pliki konfiguracji dla dostawcy dokumentów fiskalnych i łącznika fiskalnego:

    1. Otwórz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji.
    1. Otwórz folder **src \> FiscalIntegration \> EpsonFP90IIISample**.
    1. Pobierz plik konfiguracji dostawcy dokumentów fiskalnych z lokalizacji **CommerceRuntime \> DocumentProvider.EpsonFP90IIISample \> Configuration \> DocumentProviderEpsonFP90IIISample.xml**.
    1. Pobierz plik konfiguracji łącznika fiskalnego z lokalizacji **HardwareStation \> EpsonFP90IIIFiscalDeviceSample \> Configuration \> ConnectorEpsonFP90IIISample.xml**.

    > [!NOTE]
    > Dla wersji Commerce 10.0.28 lub wcześniejszej musisz użyć poprzedniej wersji zestawu SDK do Retail na maszynie wirtualnej dewelopera w usłudze LCS. Pliki konfiguracji dla tego przykładu integracji fiskalnej znajdują się w wymienionych poniżej folderach zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS:
    >
    > - **Plik konfiguracji dostawcy dokumentów fiskalnych:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml
    > - **Plik konfiguracji łącznika fiskalnego:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml

1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Wspólne parametry handlu**. Na karcie **Ogólne** ustaw dla opcji **Włącz integrację fiskalną** wartość **Tak**.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Dostawcy dokumentów fiskalnych** i załaduj pobrany wcześniej plik konfiguracji dostawcy dokumentów fiskalnych.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Łączniki fiskalne** i załaduj pobrany wcześniej plik konfiguracji łącznika fiskalnego.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile funkcjonalności łącznika**. Utwórz nowy profil funkcjonalny łącznika. Wybierz dostawcę dokumentów oraz łącznik, które załadowano wcześniej. Zaktualizuj [ustawienia mapowania danych](#default-data-mapping) zgodnie z wymaganiami.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile techniczne łącznika**. Utwórz nowy profil techniczny łącznika i wybierz załadowany wcześniej łącznik fiskalny. Zaktualizuj [ustawienia łącznika](#fiscal-connector-settings) zgodnie z wymaganiami.
6. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Grupy łączników fiskalnych**. Utwórz nową grupę łączników fiskalnych dla utworzonego wcześniej profilu funkcjonalnego łącznika.
7. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnej**. Utwórz nowy proces rejestracji fiskalnej oraz krok procesu rejestracji fiskalnej, a następnie wybierz utworzoną wcześniej grupę łączników fiskalnych.
8. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**. Wybierz profil funkcjonalności połączony ze sklepem, w którym należy aktywować proces rejestracji. Na skróconej karcie **Proces rejestracji fiskalnej** wybierz utworzony wcześniej proces rejestracji fiskalnej.
9. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile sprzętu**. Wybierz profil sprzętu połączony ze stacją sprzętową, z którą będzie połączona drukarka fiskalna. Na skróconej karcie **Fiskalne urządzenia peryferyjne** wybierz utworzony wcześniej profil techniczny łącznika.
10. Otwórz harmonogram dystrybucji (**Handel detaliczny i inny \> Składniki IT w handlu detalicznym i innym \> Harmonogram dystrybucji**) i wybierz zadania **1070** i **1090** do przesyłania danych do bazy danych kanału.

#### <a name="default-data-mapping"></a>Domyślne mapowanie danych

Następujące domyślne mapowanie danych jest uwzględnione w bieżącej konfiguracji dostawcy dokumentu fiskalnego dostarczanego jako część przykładowej integracji fiskalnej:

- **Mapowanie typów metod płatności** — mapowanie metod płatności skonfigurowanych dla sklepu na typy płatności obsługiwane przez drukarkę fiskalną. W poniższym przykładzie pokazano mapowanie domyślne.

    ```JSON
    {"PaymentMethods": [
        {"StorePaymentMethod":"1", "PrinterPaymentType":"0", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"3", "PrinterPaymentType":"2", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"4", "PrinterPaymentType":"2", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"6", "PrinterPaymentType":"0", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"8", "PrinterPaymentType":"6", "PrinterPaymentIndex":"01"}
        ],
        "DepositPaymentMethod": {"PrinterPaymentType":"2", "PrinterPaymentIndex":"00"}}
    ```

    Poniżej znajduje się objaśnienie atrybutów używanych w tym mapowaniu:

    - Atrybut **StorePaymentMethod** to metoda płatności skonfigurowana dla sklepu w lokalizacji **Handel detaliczny i inny \> Ustawienia kanału \> Metody płatności \> Metody płatności**.
    - Atrybuty **PrinterPaymentType** i **PrinterPaymentIndex** to typ i indeks odpowiedniej płatności zdefiniowane w dokumentacji drukarki fiskalnej firmy Epson.
    - Atrybut **DepositPaymentMethod** służy do określania typu płatności drukarki i indeksu części kwoty pobrania zamówienia klienta, która jest rozliczana względem wpłaty za zamówienie odbiorcy.

    W poniższej tabeli pokazano, w jaki sposób przykładowe mapowanie metod płatności odpowiada metodom płatności sklepu, które zostały skonfigurowane w standardowych danych demonstracyjnych.

    | Metoda płatności | Nazwa metody płatności |
    |----------------|---------------------|
    | 1              | Kasa                |
    | 3              | Karta                |
    | 4              | Konto odbiorcy    |
    | 6              | Waluta            |
    | 8              | Karta upominkowa           |

    Z tego powodu należy zmodyfikować przykładowe mapowanie pod kątem metod płatności skonfigurowanych w Twojej aplikacji.

- **Typ kodu kreskowego dla numeru paragonu** — typ kodu kreskowego używanego w celu pokazania numeru paragonu na paragonie fiskalnym. Mapowanie domyślne to **CODE128**.
- **Drukuj dane fiskalne w nagłówku paragonu** — jeśli ten parametr jest włączony, informacje o sklepie będą drukowane na paragonie fiskalnym. Te informacje zawierają nazwę, adres i numer identyfikacji podatkowej sklepu oraz imię i nazwisko kasjera.
- **Mapowanie działu drukarki fiskalnej** — mapowanie działów drukarki fiskalnej na stawki podatku VAT, rodzaje zwolnienia z podatku VAT oraz typy produktów. W poniższym przykładzie pokazano mapowanie domyślne.

    ```JSON
    {"Departments": [
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"01"},
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"02"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"03"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"04"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"05"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"06"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"07"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"08"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"09"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"10"},
        {"VATRate":"0000", "VATExemptNature":"NS", "ProductType":"0", "DepartmentNumber":"99"}]}
    ```

    Poniżej znajduje się objaśnienie atrybutów używanych w tym mapowaniu:

    - Atrybut **VATRate** to obsługiwana stawka podatku VAT skonfigurowana jako kod podatku. Wartość w mapowaniu ma dwa miejsca dziesiętne, ale nie ma separatora dziesiętnego. Na przykład wartość **2200** oznacza 22 procent, a wartość **1000** oznacza 10 procent.
    - Atrybut **VATExemptNature** ma zastosowanie tylko w sytuacjach, gdy stawka podatku VAT wynosi 0 (zero), w tym w sytuacjach, gdy nie jest używany podatek. Aktualnie atrybut **VATExemptNature** jest obsługiwany tylko w przypadku kart upominkowych, a wartość w mapowaniu musi odpowiadać wartości właściwości **VATExemptNatureForGiftCard** w pliku konfiguracji w formacie XML.
    - Atrybut **ProductType** to typ produktu. Wartość **0** oznacza towary, a wartość **1** oznacza usługi.
    - Atrybut **DepartmentNumber** to numer działu, który jest skonfigurowany w drukarce i odpowiada poprzednim trzem atrybutom.

    Musisz zmodyfikować przykładowe mapowanie zgodnie ze stawkami podatku VAT skonfigurowanymi w Twojej aplikacji i odpowiednimi działami, które zostały skonfigurowane w drukarce fiskalnej.

- **Rodzaj zwolnienia z podatku VAT dla karty upominkowej** — rodzaj zwolnienia z podatku VAT, który ma być stosowany w przypadku wystawienia karty upominkowej lub uzupełnienia jej stanu. Ta wartość musi odpowiadać pewnemu wpisowi w mapowaniu działu drukarki fiskalnej. Mapowanie domyślne to **NS**.
- **Włącz bezpłatne elementy** — włączenie tego parametru spowoduje włączenie specjalnego typu korekty rabatów *omaggio* dla elementów, dla których jest włączony 100-procentowy rabat.
- **Kod informacji dla źródła zwrotu** — kod informacji służący do przechwytywania źródła transakcji zwrotu w sytuacji, gdy nie został dostarczony oryginalny paragon sprzedaży. Ten parametr jest używany razem z parametrami **Kod informacji dla daty oryginalnej sprzedaży** i **Mapowanie źródła zwrotu** w celu wygenerowania poprawnego komunikatu na paragonie fiskalnym, który dotyczy źródła transakcji zwrotu w sytuacji, gdy nie istnieje oryginalna transakcja sprzedaży. 

    Ten kod informacji należy skonfigurować, aby umożliwić użytkownikowi wybranie lub wprowadzenie jednego z możliwych źródeł zwrotów w Twoich sklepach. Na przykład można go skonfigurować jako listę kodów podrzędnych (takich jak **Zwrot z oddziału** lub **Zwrot z kiosku**). Parametr **Mapowanie źródła zwrotu** jest następnie używany w celu przetłumaczenia wartości kodu informacji na polecenie kierowane do drukarki fiskalnej.

    Kod informacji wybrany dla parametru **Kod informacji dla źródła zwrotu** musi być skonfigurowany jako obowiązkowy kod informacji, który jest wyzwalany raz na transakcję sprzedaży. Należy go przypisać jako kod informacji **Zwróć produkt** w profilu funkcjonalności punktu sprzedaży, dzięki czemu będzie wyzwalany po uruchomieniu operacji **Zwróć produkt**.

    Dla tego mapowania nie określono wartości domyślnej. Musisz wybrać kod informacji skonfigurowany w Twojej aplikacji.

- **Kod informacji dla daty oryginalnej sprzedaży** — kod informacji służący do przechwytywania daty oryginalnej sprzedaży dla transakcji zwrotu w sytuacji, gdy nie został dostarczony oryginalny paragon sprzedaży. Ten parametr jest używany razem z parametrami **Kod informacji dla źródła zwrotu** i **Mapowanie źródła zwrotu** w celu wygenerowania poprawnego komunikatu na paragonie fiskalnym, który dotyczy źródła transakcji zwrotu w sytuacji, gdy nie istnieje oryginalna transakcja sprzedaży.

    Kod informacji musi być skonfigurowany tak, aby pole **Typ wejściowy** miało wartość **Data**. Należy skonfigurować go jako obowiązkowy kod informacji, który jest wyzwalany raz na transakcję sprzedaży. Należy go również przypisać jako **Połączony kod informacji** dla kodu informacji wybranego jako wartość parametru **Kod informacji dla źródła zwrotu**, dzięki czemu te dwa kody informacji będą wyzwalane jeden po drugim.

    Dla tego mapowania nie określono wartości domyślnej. Musisz wybrać kod informacji skonfigurowany w Twojej aplikacji.

- **Mapowanie źródła zwrotu** — mapowanie źródła zwrotu służące do drukowania źródła transakcji zwrotu w sytuacji, gdy nie został dostarczony oryginalny paragon sprzedaży. Ten parametr jest używany razem z parametrami **Kod informacji dla źródła zwrotu** i **Kod informacji dla daty oryginalnej sprzedaży** w celu wygenerowania poprawnego komunikatu na paragonie fiskalnym, który dotyczy źródła transakcji zwrotu w sytuacji, gdy nie istnieje oryginalna transakcja sprzedaży. W poniższym przykładzie pokazano mapowanie domyślne.

    ```JSON
    {"ReturnOrigins": [
        {"ReturnOrigin":"1", "PrinterReturnOrigin":"POS"},
        {"ReturnOrigin":"2", "PrinterReturnOrigin":"ND"}
        ],
        "PrinterReturnOriginWithoutFiscalData":"POS"}
    ```

    Poniżej znajduje się objaśnienie atrybutów używanych w tym mapowaniu:

    - Wartość atrybutu **ReturnOrigin** to jedno z możliwych źródeł zwrotów w Twoich sklepach. Wartość musi odpowiadać wartości parametru **Kod informacji dla źródła zwrotu**.
    - Wartość argumentu **PrinterReturnOrigin** to jedno ze źródeł zwrotów akceptowanych przez drukarkę fiskalną (**POS**, **VR** lub **ND**).
    - Wartość atrybutu **PrinterReturnOriginWithoutFiscalData** to akceptowane przez drukarkę fiskalną źródło zwrotu odpowiadające transakcji zwrotu połączonej z oryginalną transakcją sprzedaży, która nie ma połączonych danych fiskalnych, ponieważ nie została zarejestrowana za pośrednictwem drukarki fiskalnej. W takim przypadku data oryginalnej sprzedaży jest identyfikowana jako data oryginalnej transakcji sprzedaży.

Wymienione poniżej domyślne mapowania danych są przestarzałe i pozostawiono je wyłącznie w celu zapewnienia zgodności z poprzednimi wersjami:

- Mapowanie kodów podatku VAT
- Typ płatności wpłaty

#### <a name="fiscal-connector-settings"></a>Ustawienia łącznika fiskalnego

Wymienione poniżej ustawienia wchodzą w skład konfiguracji łącznika fiskalnego dostarczanej jako część przykładu integracji fiskalnej:

- **Adres punktu końcowego** — adres URL drukarki.
- **Data i godzina synchronizacji** – wartość określająca, czy należy zsynchronizować datę i godzinę drukarki ze stacją połączoną Hardware Station.

### <a name="configure-channel-components"></a>Konfiguracja składników kanału.

> [!NOTE]
> - Przykład integracji drukarki fiskalnej dla Włoch jest dostępny w zestawie SDK do Commerce w wersji 10.0.29. W wersji Commerce 10.0.28 lub wcześniejszej musisz użyć poprzedniej wersji zestawu SDK do Retail na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Włoch (starsza wersja)](emea-ita-fpi-sample-sdk.md).
> - Przykłady Commerce wdrożone w środowisku nie są automatycznie aktualizowane po zastosowaniu aktualizacji usług lub jakości do składników usług Commerce. Wymagane próbki należy zaktualizować ręcznie.

#### <a name="set-up-the-development-environment"></a>Konfigurowanie środowiska projektowego

Aby skonfigurować środowisko projektowe w celu testowania i rozszerzania przykładu, wykonaj poniższe kroki.

1. Sklonuj lub pobierz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions). Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji. Aby uzyskać więcej informacji, zobacz [Pobieranie przykładów i pakietów referencyjnych zestawu SDK do Commerce z witryn GitHub i NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Otwórz rozwiązanie integracji drukarki fiskalnej w lokalizacji **Dynamics365Commerce.Solutions\\FiscalIntegration\\EpsonFP90IIISample\\EpsonFP90IIISample.sln** i skompiluj je.
1. Zainstaluj rozszerzenia kolekcji CRT:

    1. Znajdź instalatora rozszerzeń kolekcji CRT:

        - **Commerce Scale Unit:** w folderze **EpsonFP90IIISample\\ScaleUnit\\ScaleUnit.EpsonFP90III.Installer\\bin\\Debug\\net461** znajdź instalatora **ScaleUnit.EpsonFP90III.Installer**.
        - **Lokalne wystąpienie kolekcji CRT w aplikacji Modern POS:** w folderze **EpsonFP90IIISample\\ModernPOS\\ModernPOS.EpsonFP90III.Installer\\bin\\Debug\\net461** znajdź instalatora **ModernPOS.EpsonFP90III.Installer**.

    1. Uruchom instalatora rozszerzeń kolekcji CRT z poziomu wiersza polecenia:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EpsonFP90III.Installer.exe install --verbosity 0
            ```

        - **Lokalna kolekcja CRT w aplikacji Modern POS:**

            ```Console
            ModernPOS.EpsonFP90III.Installer.exe install --verbosity 0
            ```

1. Zainstaluj rozszerzenia stacji sprzętowej:

    1. W folderze **EpsonFP90IIISample\\HardwareStation\\HardwareStation.EpsonFP90III.Installer\\bin\\Debug\\net461** znajdź instalatora **HardwareStation.EpsonFP90III.Installer**.
    1. Uruchom instalatora rozszerzeń z poziomu wiersza polecenia:

        ```Console
        HardwareStation.EpsonFP90III.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Środowisko produkcyjne

Wykonaj kroki opisane w artykule [Konfigurowanie potoku kompilacji dla przykładu integracji fiskalnej](fiscal-integration-sample-build-pipeline.md), aby wygenerować i wydać rozwiązanie Cloud Scale Unit oraz samoobsługowe wdrażalne pakiety dla przykładu integracji fiskalnej. Plik YAML szablonu **EpsonFP90III build-pipeline.yml** można znaleźć w folderze **Pipeline\\YAML_Files** w repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Projekt rozszerzenia

Przykład integracji drukarki fiskalnej dla Włoch jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu SDK do Commerce. Próbka znajduje się w folderze **src\\FiscalIntegration\\EpsonFP90IIISample** w repozytorium [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). [Przykład](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) składa się z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji CRT, oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu SDK do Commerce, zobacz [Pobieranie próbek i pakietów referencyjnych zestawu SDK do Retail z GitHub i NuGet](../dev-itpro/retail-sdk/sdk-github.md) i [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!NOTE]
> Przykład integracji drukarki fiskalnej dla Włoch jest dostępny w zestawie SDK do Commerce w wersji 10.0.29. W wersji Commerce 10.0.28 lub wcześniejszej musisz użyć poprzedniej wersji zestawu SDK do Retail na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Włoch (starsza wersja)](emea-ita-fpi-sample-sdk.md).

### <a name="commerce-runtime-extension-design"></a>Projekt rozszerzenia środowiska uruchomieniowego Commerce

Celem rozszerzenia (dostawcy dokumentów fiskalnych) jest generowanie dokumentów specyficznych dla drukarki i obsługa odpowiedzi z drukarki fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **DocumentProviderEpsonFP90III** jest punktem wejścia dla żądania generowania dokumentów z drukarki fiskalnej.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla drukarki, który powinien zostać zarejestrowany w drukarce fiskalnej.
- **GetSupportedRegistrableEventsDocumentProviderRequest** — to zapytanie zwraca listę zdarzeń do subskrybowania. Obecnie są obsługiwane następujące zdarzenia: sprzedaż, drukowanie raportu X i drukowanie końcowego raportu sprzedaży.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji dla dostawcy dokumentów fiskalnych znajduje się w lokalizacji **src\\FiscalIntegration\\EpsonFP90IIISample\\CommerceRuntime\\DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml** w repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ten plik służy do obsługi konfiguracji ustawień dostawcy dokumentu z centrali Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Zastosowaniem rozszerzenia (łącznika fiskalnego) jest do komunikowanie się z drukarką fiskalną. To rozszerzenie używa protokołu HTTP w celu przesyłania dokumentów generowanych przez rozszerzenie kolekcji CRT do drukarki fiskalnej. Obsługuje również odpowiedzi odbierane z drukarki fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **EpsonFP90IIISample** jest punktem wejściowym obsługi żądania kierowanego do fiskalnego urządzenia peryferyjnego.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **SubmitDocumentFiscalDeviceRequest** — to żądanie wysyła dokumenty do drukarek i zwraca odpowiedzi z drukarki fiskalnej.
- **IsReadyFiscalDeviceRequest** — to żądanie służy do sprawdzania stanu urządzenia.
- **InitializeFiscalDeviceRequest** — to żądanie jest używane do inicjowania drukarki.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji dla łącznika fiskalnego znajduje się w lokalizacji **src\\FiscalIntegration\\EpsonFP90IIISample\\HardwareStation\\EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml** w repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ten plik służy do obsługi konfiguracji ustawień łącznika z centrali Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
