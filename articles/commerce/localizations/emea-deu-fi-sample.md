---
title: Przykład integracji usługi rejestracji fiskalnej (Niemcy)
description: W tym artykule znajduje się omówienie przykładu integracji fiskalnej dla Niemiec w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-05-29
ms.openlocfilehash: a725badbce498e4e7b35aecb2500e273586c7b77
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631461"
---
# <a name="fiscal-registration-service-integration-sample-for-germany"></a>Przykład integracji usługi rejestracji fiskalnej (Niemcy)

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

W tym artykule znajduje się omówienie przykładu integracji fiskalnej dla Niemiec w rozwiązaniu Microsoft Dynamics 365 Commerce.

Aby spełnić lokalne wymagania fiskalne dotyczące kas w Niemczech, funkcjonalność rozwiązania Dynamics 365 Commerce dla Niemiec obejmuje przykład integracji punktu sprzedaży (POS) z zewnętrzną usługą rejestracji fiskalnej. Ten przykład rozszerza [funkcjonalność integracji fiskalnej](fiscal-integration-for-retail-channel.md). Jest on oparty na rozwiązaniu [EFR (Electronic Fiscal Register)](https://www.efsta.eu/de/fiskalloesungen/deutschland) firmy [EFSTA](https://www.efsta.eu/de/) i umożliwia komunikację z usługą EFR za pośrednictwem protokołu HTTPS. Usługę EFR należy hostować na stacji sprzętowej rozwiązania Retail albo na osobnym komputerze, z którym można nawiązać połączenie z poziomu stacji sprzętowej. Przykładowa integracja ma formę kodu źródłowego i jest częścią zestawu SDK modułu Commerce.

Firma Microsoft nie udostępnia żadnego sprzętu, oprogramowania ani dokumentacji firmy EFSTA. Aby uzyskać więcej informacji dotyczących sposobu pobierania i używania rozwiązania EFR, skontaktuj się z [firmą EFSTA](https://www.efsta.eu/de/kontakt/kontakt).

## <a name="scenarios"></a>Scenariusze

Przykład integracji usługi rejestracji fiskalnej dla Niemiec umożliwia wykorzystanie następujących scenariuszy:

### <a name="sales-operations"></a>Operacje sprzedaży

- **Rejestracja sprzedaży i zwrotów gotówkowych w usłudze rejestracji fiskalnej:**

    Rejestracja operacji sprzedaży obejmuje następujące kroki:

    1. Rejestracja rozpoczęcia transakcji

        Rozpoczęcie każdej transakcji jest rejestrowane w elemencie zabezpieczeń technicznym (TSE) połączonym z usługą EFR. W wyniku rejestracji element TSE przypisuje identyfikator transakcji (TID).

    2. Rejestracja zakończenia transakcji

        Transakcja kończona w punkcie sprzedaży jest rejestrowana przy użyciu tego samego identyfikatora TID, który został przypisany podczas rejestracji rozpoczęcia transakcji. W tym momencie szczegółowe dane transakcji są wysyłane do usługi rejestracji fiskalnej. Te dane zawierają informacje wiersza sprzedaży oraz informacje o rabatach, płatnościach i podatkach.

    3. Przechwytywanie odpowiedzi z usługi rejestracji fiskalnej

        Dane zabezpieczeń są odbierane z elementu TSE jako część odpowiedzi i są zapisywane w transakcji w bazie danych kanału. Dane zabezpieczeń zawierają następujące informacje:

        - Identyfikator TID
        - Data i godzina rozpoczęcia transakcji
        - Data i godzina zakończenia transakcji
        - Licznik podpisów
        - Wartość sprawdzania
        - Numer seryjny elementu TSE

- **Rejestracja zamówień odbiorców w usłudze rejestracji fiskalnej**: proces rejestracji jest taki sam jak proces sprzedaży i zwrotów gotówkowych.
- **Rejestracja operacji obejmujących karty upominkowe i wpłaty**: proces rejestracji jest taki sam jak proces sprzedaży i zwrotów gotówkowych.

#### <a name="notifying-users-about-fiscal-registration-failures"></a>Powiadamianie użytkowników o niepowodzeniach rejestracji fiskalnej

Usługa rejestracji fiskalnej może na dwa sposoby powiadamiać użytkowników o błędach, które wystąpiły podczas rejestracji fiskalnej:

- Drukowanie dodatkowych informacji z odpowiedzi w polu **Komunikat informacyjny** na paragonach.
- Wyświetlanie powiadomień z usługi fiskalnej jako komunikatów użytkownika w punkcie sprzedaży.

    > [!NOTE]
    > Ten mechanizm powiadamiania wymaga włączenia parametru **Pokaż powiadomienia rejestracji fiskalnej** na stronie **Profile techniczne łącznika**.

#### <a name="printing-receipts"></a>Drukowanie paragonów

Drukowanie paragonów jest w Niemczech obowiązkowe. Wszystkie paragony muszą zawierać co najmniej następujące informacje:

- Nazwa i adres firmy
- Informacje o towarach, w tym o ich cenach i ilościach
- Informacje o otrzymanych płatnościach
- Informacje o podatkach, w tym łączne kwoty dla poszczególnych stawek podatku
- Dane zabezpieczeń:

    - Identyfikator TID
    - Data i godzina rozpoczęcia transakcji
    - Data i godzina zakończenia transakcji
    - Licznik podpisów
    - Wartość sprawdzania
    - Numer seryjny elementu TSE

- Komunikat informacyjny

> [!NOTE]
> Na paragonach można również drukować kody QR. Kod QR jest opcjonalny, ale jego używanie jest zdecydowanie zalecane. Aby uzyskać więcej informacji na temat sposobu pobierania kodu QR jako części odpowiedzi z usługi rejestracji fiskalnej, zobacz dokument „EFR Guide \[DE\]” opublikowany w witrynie internetowej z [dokumentacją firmy EFSTA](https://public.efsta.net/efr/).
>
> Pole **Komunikat informacyjny** na paragonach zawiera powiadomienie z usługi rejestracji fiskalnej. Na przykład jeśli urządzenie do podpisywania jest uszkodzone, na paragonie można wydrukować specjalny tekst.

#### <a name="voided-suspended-and-recalled-transactions"></a>Unieważnione, wstrzymane i wznowione transakcje

- Unieważniona transakcja jest rejestrowana jako żądanie przerwania transakcji w usłudze rejestracji fiskalnej.
- Wstrzymana transakcja jest rejestrowana jako żądanie przerwania transakcji w usłudze rejestracji fiskalnej.
- Wznowienie wstrzymanej transakcji jest rejestrowane jako rozpoczęcie nowej transakcji w usłudze rejestracji fiskalnej.

### <a name="non-sales-transactions-and-shift-closing"></a>Transakcje niezwiązane ze sprzedażą i zamknięcie zmiany

Wymienione poniżej transakcje niezwiązane ze sprzedażą są rejestrowane jako operacje niefiskalne w usłudze rejestracji fiskalnej przy użyciu tagu **NFS**:

- Zadeklaruj kwotę początkową
- Przyjęcie do kasy
- Pobranie środków płatniczych
- Przekazanie pieniędzy do sejfu
- Przekazanie pieniędzy do banku
- Konta przychodów
- Konta wydatków

Operacja **Zamknij zmianę** także jest rejestrowana jako operacja niefiskalna w usłudze rejestracji fiskalnej przy użyciu tagu **NFS**.

### <a name="data-export-and-audit"></a>Eksport i inspekcja danych

Wszystkie transakcje muszą być podpisane przez element TSE, co ma na celu zagwarantowanie ich integralności, autentyczności i kompletności oraz zapobieżenie manipulowaniu zarejestrowanymi danymi.

> [!WARNING]
> Można używać tylko certyfikowanego elementu TSE. Aby uzyskać informacje dotyczące typów i modeli elementów TSE obsługiwanych w rozwiązaniu EFR, zobacz dokument „EFR Guide \[DE\]” opublikowany w witrynie internetowej z [dokumentacją firmy EFSTA](https://public.efsta.net/efr/). Aby uzyskać informacje dotyczące sposobu wybierania i uzyskiwania elementu TSE, skontaktuj się z [firmą EFSTA](https://www.efsta.eu/at/kontakt).

Przepisy w Niemczech wymagają obsługi eksportu w formacie DSFinV-K. Eksport w formacie DSFinV-K można wyzwolić w rozwiązaniu EFR. Aby uzyskać więcej informacji dotyczących eksportu w formacie DSFinV-K, zobacz dokument „EFR Guide \[DE\]” opublikowany w witrynie internetowej z [dokumentacją firmy EFSTA](https://public.efsta.net/efr/).

### <a name="limitations-of-the-sample"></a>Ograniczenia przykładowej integracji

Usługa rejestracji fiskalnej obsługuje tylko scenariusze, w których podatek jest uwzględniony w cenach. Z tego względu opcja **Ceny zawierają podatek** musi mieć wartość **Tak** zarówno dla sklepów, jak i odbiorców.

Usługa fiskalna nie obsługuje sytuacji, w których do jednego wiersza transakcji zastosowano więcej niż jeden kod podatku.

Struktura integracji fiskalnej nie obsługuje ofert sprzedaży. Z tego powodu te operacje nie są rejestrowane w usłudze fiskalnej.

## <a name="set-up-commerce-for-germany"></a>Konfigurowanie rozwiązania Commerce dla Niemiec

W tej sekcji opisano ustawienia rozwiązania Commerce, które są specyficzne oraz zalecane dla Niemiec. Aby uzyskać więcej informacji dotyczących konfiguracji, zobacz [stronę główną rozwiązania Commerce](../index.md).

Aby móc używać funkcjonalności specyficznej dla Niemiec, musisz określić następujące ustawienia.

- W podstawowym adresie osoby prawnej ustaw w polu **Kraj/region** wartość **DEU** (Niemcy).
- W profilu funkcjonalności punktu sprzedaży każdego sklepu zlokalizowanego w Niemczech ustaw w polu **Kod ISO** wartość **DE** (Niemcy).

Musisz także określić wymienione poniżej ustawienia dla Niemiec. Pamiętaj, aby po zakończeniu konfigurowania uruchomić odpowiednie zadania dystrybucji.

### <a name="set-up-vat-per-german-requirements"></a>Konfigurowanie podatku VAT zgodnie z niemieckimi wymaganiami

Musisz utworzyć kody podatków, grupy podatków oraz grupy podatków dla towarów. Musisz także skonfigurować informacje o podatkach dla produktów i usług. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania i używania funkcji podatków, zobacz [Omówienie podatku](../../finance/general-ledger/indirect-taxes-overview.md).

Na paragonach sprzedaży można drukować skrócony kod odpowiadający kodowi podatku (na przykład „A” lub „B”). Aby udostępnić tę funkcjonalność, ustaw wartość pola **Kod do drukowania** na stronie **Kody podatków**.

### <a name="set-up-stores"></a>Konfigurowanie sklepów

Na stronie **Wszystkie sklepy** zaktualizuj szczegóły sklepu. W szczególności ustaw następujące parametry:

- W polu **Grupa podatków** określ grupę podatków, która ma być używana w odniesieniu do sprzedaży odbiorcy domyślnemu.
- Ustaw dla opcji **Ceny zawierają podatek** wartość **Tak**.
- W polu **Nazwa** ustaw wartość firmy. Ta zmiana pomaga zagwarantować, że nazwa firmy będzie widoczna na paragonie sprzedaży. Możesz również dodać nazwę firmy do układu paragonu sprzedaży w postaci dowolnego tekstu.
- W polu **Numer identyfikacji podatkowej (NIP)** ustaw numer identyfikacyjny firmy. Ta zmiana pomaga zagwarantować, że numer identyfikacyjny firmy będzie widoczny na paragonie sprzedaży. Możesz również dodać numer identyfikacyjny firmy do układu paragonu sprzedaży w postaci dowolnego tekstu.

### <a name="set-up-functionality-profiles"></a>Konfigurowanie profilów funkcjonalności

Skonfiguruj profile funkcjonalności punktu sprzedaży. Na skróconej karcie **Numeracja paragonów** skonfiguruj numerowanie paragonów, tworząc lub aktualizując rekordy dla typów transakcji przyjęcia **Sprzedaż**, **Zamówienie sprzedaży** i **Zwrot**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Konfigurowanie pól niestandardowych, aby można było ich używać w formatach paragonów dla paragonów sprzedaży

Możesz skonfigurować tekst w języku oraz pola niestandardowe używane w formatach paragonów dla punktu sprzedaży. Domyślna firma użytkownika, który tworzy konfigurację paragonu, powinna być tą samą osobowością prawną, w której jest tworzone ustawienie tekstu w języku. Alternatywnie, można również utworzyć ten sam tekst językowy w domyślnej firmie użytkownika i dla tego samego bytu prawnego, dla którego utworzono konfigurację.

Na stronie **Tekst w języku** dodaj wymienione poniżej rekordy dla etykiet pól niestandardowych używanych w układach paragonów. Pamiętaj, że wartości **Identyfikatora języka**, **Identyfikatora tekstu** i **Tekst** przedstawione w poniższej tabeli są tylko przykładami. Można je zmienić, aby spełniały wymagania użytkownika. Jednak używane wartości **Identyfikator tekstu** muszą być unikatowe oraz większe lub równe 900001.

Dodaj wymienione poniżej etykiety punktu sprzedaży do obszaru **Punkt sprzedaży** na stronie **Tekst w języku**.

| Identyfikator języka | Identyfikator tekstu | Tekst                                  |
|-------------|---------|---------------------------------------|
| en-US       | 900001  | Kod QR                               |
| en-US       | 900002  | Identyfikator transakcji                        |
| en-US       | 900003  | Drukowany kod podatku detalicznego                 |
| en-US       | 900004  | Kwota podatku (sprzedaż)                    |
| en-US       | 900005  | Podstawa podatku (sprzedaż)                     |
| en-US       | 900006  | Data i godzina rozpoczęcia transakcji           |
| en-US       | 900007  | Data i godzina zakończenia transakcji             |
| en-US       | 900008  | Numer seryjny elementu zabezpieczeń |
| en-US       | 900009  | Licznik podpisów                     |
| en-US       | 900010  | Wartość sprawdzania                           |
| en-US       | 900011  | Komunikat informacyjny                          |

Na stronie **Pola niestandardowe** dodaj następujące rekordy dla pól niestandardowych używanych w układach paragonów. Pamiętaj, że wartości **Identyfikator tekstu podpisu** muszą być zgodne z wartościami **Identyfikator tekstu** określonymi na stronie **Tekst w języku**.

| Nazwa                            | Typ    | Identyfikator tekstu podpisu |
|---------------------------------|---------|-----------------|
| QRCODE\_DE                      | Pokwitowanie | 900001          |
| TRANSACTIONID\_DE               | Pokwitowanie | 900002          |
| RETAILPRINTCODE\_DE             | Pokwitowanie | 900003          |
| SALESTAXAMOUNT\_DE              | Pokwitowanie | 900004          |
| SALESTAXBASIS\_DE               | Pokwitowanie | 900005          |
| TRANSACTIONSTARTDATETIME\_DE    | Pokwitowanie | 900006          |
| TRANSACTIONENDDATETIME\_DE      | Pokwitowanie | 900007          |
| SECURITYELEMENTSERIALNUMBER\_DE | Pokwitowanie | 900008          |
| SIGNCOUNTER\_DE                 | Pokwitowanie | 900009          |
| SIGN\_DE                        | Pokwitowanie | 900010          |
| INFOMESSAGE\_DE                 | Pokwitowanie | 900011          |

> [!NOTE]
> Ważne jest, aby określić poprawne nazwy pól niestandardowych, tak jak podano w poprzedniej tabeli. Niepoprawna nazwa pola niestandardowego spowoduje brak danych na paragonach.

### <a name="configure-receipt-formats"></a>Konfiguracja formatów paragonów

Dla każdego wymaganego formatu paragonu zmień wartość pola **Zachowanie drukowania** na **Zawsze drukuj**.

W projektancie formatów paragonów dodaj wymienione poniżej pola niestandardowe do odpowiednich sekcji paragonu. Pamiętaj, że nazwy pól muszą odpowiadać tekstom w języku zdefiniowanym w poprzedniej sekcji.

- **Nagłówek:** Dodaj następujące pola:

    - Pola **Nazwa sklepu** i **Numer identyfikacji podatkowej**, które służą do drukowania nazwy i numeru identyfikacyjnego firmy na paragonach. Możesz również dodać nazwę i numer identyfikacyjny firmy do układu w postaci dowolnego tekstu.
    - Pola **Adres sklepu**, **Data**, **Godzina (format 24h)**, **Numer paragonu** i **Numer rejestru**.

- **Wiersze:** Dodaj następujące pola:

    - Pole **Nazwa towaru**
    - Pole **Ilość**
    - Pole **Cena razem (z podatkiem)**
    - Pole **Drukowany kod podatku detalicznego**, które służy do drukowania skróconego kodu odpowiadającego kodowi podatku stosowanego do towaru

- **Stopka:** Dodaj następujące pola:

    - Pola płatności, tak aby zostały wydrukowane kwoty płatności dla poszczególnych metod płatności. Na przykład dodaj pola **Nazwa metody płatności** oraz **Kwota metody płatności** do jednego wiersza układu.
    - Pola w grupie pól **Podział podatku**. Wszystkie pola w tej grupie pól muszą być drukowane w jednym osobnym wierszu.

        - Pole **Identyfikator podatku**, które jest standardowym polem umożliwiającym wydrukowanie podsumowania podatku dla każdego kodu podatku. To pole musi zostać dodane do nowego wiersza.
        - Pole **Procent podatku**, które jest standardowym polem służącym do drukowania efektywnej stawki podatku dla kodu podatku.
        - Pole **Podstawa podatku (sprzedaż)**, które służy do drukowania łącznej kwoty sprzedaży gotówkowej objętej paragonem dla kodu podatku. Przedpłaty i operacje związane z kartami upominkowymi są wykluczane.
        - Pole **Kwota podatku (sprzedaż)**, które służy do drukowania kwoty podatku od sprzedaży gotówkowej objętej paragonem dla kodu podatku.
        - Pole **Drukowany kod podatku detalicznego**, które służy do drukowania skróconego kodu odpowiadającego kodowi podatku.

    - Pola zawierające zabezpieczone dane transakcji zwracane przez usługę rejestracji fiskalnej:

        - Pole **Identyfikator transakcji**, które identyfikuje numer transakcji kasowej w usłudze rejestracji fiskalnej
        - Pole **Data i godzina rozpoczęcia transakcji**
        - Pole **Data i godzina zakończenia transakcji**
        - Pole **Numer seryjny elementu zabezpieczeń**
        - Pole **Licznik podpisów**
        - Pole **Wartość sprawdzania**
        - Pole **Kod QR**, które służy do drukowania odwołania do zarejestrowanej transakcji kasowej w formie kodu QR

        > [!NOTE]
        > Wartość **Kod QR** jest pobierana z odpowiedzi rejestru fiskalnego. Usługa EFR zwraca kod QR w swojej odpowiedzi, tylko jeśli wartość pola **Atrybuty** w konfiguracji usługi EFR została opisana w dokumentacji firmy EFSTA. Format kodu QR w polu **Atrybuty** w konfiguracji usługi EFR musi mieć wartość **BMP**.

    - Pole **Komunikat informacyjny** umożliwiające umieszczanie na paragonach komunikatów z powiadomieniami z usługi rejestracji fiskalnej. Na przykład jeśli urządzenie do podpisywania jest uszkodzone, na paragonie można wydrukować specjalny tekst.

Aby uzyskać więcej informacji o sposobie pracy z formatami paragonów, zobacz [Konfigurowanie i projektowanie formatów paragonów](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-germany"></a>Konfigurowanie integracji fiskalnej dla Niemiec

Przykład integracji usługi rejestracji fiskalnej dla Niemiec jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu SDK do Commerce. Próbka znajduje się w folderze **src\\FiscalIntegration\\Efr** w repozytorium [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). [Próbka](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) składa się z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji Commerce Runtime (CRT), oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu SDK do Commerce, zobacz [Pobieranie próbek i pakietów referencyjnych zestawu SDK do Retail z GitHub i NuGet](../dev-itpro/retail-sdk/sdk-github.md) i [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!NOTE]
> Przykładowa integracja usługi rejestracji obrachunkowej dla Niemiec jest dostępna w zestawie SDK do Commerce w wersji 10.0.29. W wersji Commerce 10.0.28 lub wcześniejszej musisz użyć poprzedniej wersji zestawu SDK do Retail na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Niemiec (starsza wersja)](emea-deu-fi-sample-sdk.md).

Wykonaj kroki konfiguracji integracji fiskalnej w sposób opisany w [Konfigurowanie integracji fiskalnej dla kanałów Commerce](setting-up-fiscal-integration-for-retail-channel.md):

1. [Konfigurowanie procesu rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Zwróć też uwagę na ustawienia dla procesu rejestracji fiskalnej [specyficzne dla tego przykładu integracji usługi rejestracji fiskalnej](#set-up-the-registration-process).
1. [Określanie ustawienia ustawień obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

    > [!WARNING]
    > Możliwości obsługi błędów struktury integracji fiskalnej mogą nie być w pełni zgodne z lokalnymi przepisami fiskalnymi.
    >
    > - Zalecamy pozostawienie wyłączonej opcji **Kontynuuj przy błędzie** na stronie **Proces rejestracji fiskalnej**, ponieważ wszystkie transakcje muszą zostać poprawnie zarejestrowane, nawet jeśli pierwsza próba rejestracji fiskalnej nie powiedzie się.
    > - Przed włączeniem opcji **Pomiń** lub **Oznacz jako zarejestrowane** na stronie **Proces rejestracji fiskalnej** należy omówić te zmiany w procesie rejestracji fiskalnej z doradcą podatkowym lub lokalnym urzędem skarbowym.

1. [Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).
1. [Konfiguracja składników kanału](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Konfigurowanie procesu rejestracji

Aby włączyć proces rejestracji, wykonaj następujące kroki w celu skonfigurowania centrali w rozwiązaniu Commerce. Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji fiskalnej dla kanałów rozwiązania Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Pobierz pliki konfiguracji dla dostawcy dokumentów fiskalnych i łącznika fiskalnego:

    1. Otwórz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji.
    1. Otwórz folder **src \> FiscalIntegration \> Efr**.
    1. Pobierz plik konfiguracji dostawcy dokumentów fiskalnych z lokalizacji **Configurations \> DocumentProviders \> DocumentProviderFiscalEFRSampleGermany.xml**.
    1. Pobierz plik konfiguracji łącznika fiskalnego z lokalizacji **Configurations \> Connectors \> ConnectorEFRSample.xml**.

    > [!NOTE]
    > W wersji Commerce 10.0.28 lub wcześniejszej musisz użyć poprzedniej wersji zestawu SDK do Retail na maszynie wirtualnej dewelopera w usłudze LCS. Pliki konfiguracji dla tego przykładu integracji fiskalnej znajdują się w wymienionych poniżej folderach zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS:
    >
    > - **Plik konfiguracji dostawcy dokumentów fiskalnych:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleGermany.xml
    > - **Plik konfiguracji łącznika fiskalnego:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration\\ConnectorEFRSample.xml

1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Wspólne parametry handlu**. Na karcie **Ogólne** ustaw dla opcji **Włącz integrację fiskalną** wartość **Tak**.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Dostawcy dokumentów fiskalnych** i załaduj pobrany wcześniej plik konfiguracji dostawcy dokumentów fiskalnych.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Łączniki fiskalne** i załaduj pobrany wcześniej plik konfiguracji łącznika fiskalnego.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile funkcjonalności łącznika**. Utwórz nowy profil funkcjonalny łącznika. Wybierz dostawcę dokumentów oraz łącznik, które załadowano wcześniej. Zaktualizuj [ustawienia mapowania danych](#default-data-mapping) zgodnie z wymaganiami.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile techniczne łącznika**. Utwórz nowy profil techniczny łącznika i wybierz załadowany wcześniej łącznik fiskalny. Zaktualizuj [ustawienia łącznika](#fiscal-connector-settings) zgodnie z wymaganiami.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Grupy łączników fiskalnych**. Utwórz nową grupę łączników fiskalnych dla utworzonego wcześniej profilu funkcjonalnego łącznika.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnej**. Utwórz nowy proces rejestracji fiskalnej oraz krok procesu rejestracji fiskalnej, a następnie wybierz utworzoną wcześniej grupę łączników fiskalnych.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**. Wybierz profil funkcjonalności połączony ze sklepem, w którym należy aktywować proces rejestracji. Na skróconej karcie **Proces rejestracji fiskalnej** wybierz utworzony wcześniej proces rejestracji fiskalnej.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile sprzętu**. Wybierz profil sprzętu połączony ze stacją sprzętową, z którą będzie połączona fiskalna usług rejestracji. Na skróconej karcie **Fiskalne urządzenia peryferyjne** wybierz utworzony wcześniej profil techniczny łącznika.
1. Otwórz harmonogram dystrybucji (**Handel detaliczny i inny \> Składniki IT w handlu detalicznym i innym \> Harmonogram dystrybucji**) i wybierz zadania **1070** i **1090** do przesyłania danych do bazy danych kanału.

#### <a name="default-data-mapping"></a>Domyślne mapowanie danych

Następujące domyślne mapowanie danych jest uwzględnione w bieżącej konfiguracji dostawcy dokumentu fiskalnego dostarczanego jako część przykładowej integracji fiskalnej:

- **Mapowanie typów metod płatności** — mapowanie metod płatności na wartości atrybutu **PayG** (grupa płatności) w żądaniach wysyłanych do usługi fiskalnej. Poniżej pokazano mapowanie domyślne:

    ```
    1: 0; 2: 1; 3: 3; 4: 8; 5: 2; 6: 0; 7: 7; 8: 6; 9: 0; 10: 8; 11: 1
    ```

    Pierwszy składnik w każdej parze reprezentuje metodę płatności skonfigurowaną dla sklepu. Drugi składnik reprezentuje odpowiadającą jej grupę płatności, która jest obsługiwana przez usługę rejestracji fiskalnej EFR. Aby uzyskać więcej informacji dotyczących grup płatności obsługiwanych przez usługę EFR dla Niemiec, zobacz [Informacje referencyjne usługi EFR](https://public.efsta.net/efr/).

    Przykładowe mapowanie metod płatności odpowiada metodom płatności sklepu, które zostały skonfigurowane w standardowych danych demonstracyjnych.

    | Metoda płatności | Nazwa metody płatności |
    |----------------|---------------------|
    | 1              | Kasa                |
    | 2              | Sprawdzanie               |
    | 3              | Karta                |
    | 4              | Konto odbiorcy    |
    | 5              | Inne               |
    | 6              | Waluta            |
    | 7              | Załącznik             |
    | 8              | Karta upominkowa           |
    | 9              | Usunięcie/zmiana środków płatniczych |
    | 10             | Karty lojalnościowe       |
    | 11             | Czeki inne niż lokalne    |

    Z tego powodu musisz zmodyfikować przykładowe mapowanie pod kątem metod płatności skonfigurowanych w Twojej aplikacji.

- **Uwzględnij dane odbiorcy** — jeśli ten parametr jest włączony, żądania kierowane do usługi fiskalnej będą zawierać informacje dotyczące odbiorcy, takie jak nazwy i adresy, w sytuacjach, gdy odbiorca zostanie dodany do transakcji.
- **Mapowanie stawek podatku VAT** — mapowanie wartości procentowych podatku skonfigurowanych dla kodów podatków na wartości atrybutu **TaxG** (grupa podatków) w żądaniach wysyłanych do usługi fiskalnej. Poniżej pokazano mapowanie domyślne:

    ```
    A: 19.00; B: 7.00; C: 10.70; D: 5.50; E: 0.00
    ```

    Pierwszy składnik każdej pary reprezentuje grupę podatków VAT, która jest obsługiwana przez usługę rejestracji fiskalnej EFR. Drugi składnik reprezentuje odpowiadającą jej stawkę podatku VAT. Aby uzyskać więcej informacji dotyczących grup podatków VAT obsługiwanych przez usługę EFR dla Niemiec, zobacz [Informacje referencyjne usługi EFR](https://public.efsta.net/efr/).

- **Grupa podatków dla kart upominkowych i wpłat** — wartość atrybutu **TaxG** w żądaniach wysyłanych do usługi fiskalnej ustalana na podstawie operacji, które dotyczą kart upominkowych lub wpłat. Poniżej pokazano mapowanie domyślne:

    ```
    G
    ```

- **Grupa podatków dla zwolnienia z podatku VAT** — wartość atrybutu **TaxG** w żądaniach wysyłanych do usługi fiskalnej ustalana na podstawie operacji objętych zwolnieniem ze zobowiązań podatkowych. Poniżej pokazano mapowanie domyślne:

    ```
    F
    ```

> [!NOTE]
> Ustawienia podatków w domyślnym mapowaniu danych są odpowiedzialne za dopasowanie ustawień podatków w systemie i grupach podatków w usłudze EFR. Grupy podatków można drukować na paragonach tylko wtedy, gdy na stronie **Kody podatków** jest ustawione pole **Kod do drukowania**.

#### <a name="fiscal-connector-settings"></a>Ustawienia łącznika fiskalnego

Wymienione poniżej ustawienia wchodzą w skład konfiguracji łącznika fiskalnego dostarczanej jako część przykładu integracji fiskalnej:

- **Adres punktu końcowego** — adres URL usługi rejestracji fiskalnej.
- **Limit czasu** — ilość czasu (w milisekundach), przez który łącznik fiskalny będzie czekał na odpowiedź z usługi rejestracji fiskalnej.
- **Pokaż powiadomienia rejestracji fiskalnej** — ta flaga określa, czy powiadomienia zwracane przez usługę rejestracji fiskalnej mają być wyświetlane operatorowi.

### <a name="configure-channel-components"></a>Konfiguracja składników kanału.

> [!NOTE]
> - Przykładowa integracja usługi rejestracji obrachunkowej dla Niemiec jest dostępna w zestawie SDK do Commerce w wersji 10.0.29. W wersji Commerce 10.0.28 lub wcześniejszej musisz użyć poprzedniej wersji zestawu SDK do Retail na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Niemiec (starsza wersja)](emea-deu-fi-sample-sdk.md).
> - Przykłady Commerce wdrożone w środowisku nie są automatycznie aktualizowane po zastosowaniu aktualizacji usług lub jakości do składników usług Commerce. Wymagane próbki należy zaktualizować ręcznie.

#### <a name="set-up-the-development-environment"></a>Konfigurowanie środowiska projektowego

Aby skonfigurować środowisko projektowe w celu testowania i rozszerzania przykładu, wykonaj poniższe kroki.

1. Sklonuj lub pobierz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions). Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji. Aby uzyskać więcej informacji, zobacz [Pobieranie przykładów i pakietów referencyjnych zestawu SDK do Commerce z witryn GitHub i NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Otwórz rozwiązanie EFR w lokalizacji **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln** i skompiluj je.
1. Zainstaluj rozszerzenia kolekcji Commerce Runtime:

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

Przykład integracji usługi rejestracji fiskalnej dla Niemiec jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu SDK do Commerce. Próbka znajduje się w folderze **src\\FiscalIntegration\\Efr** w repozytorium [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). [Przykład](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) składa się z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji CRT, oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu SDK do Commerce, zobacz [Pobieranie próbek i pakietów referencyjnych zestawu SDK do Retail z GitHub i NuGet](../dev-itpro/retail-sdk/retail-sdk-overview.md) i [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!NOTE]
> Przykładowa integracja usługi rejestracji obrachunkowej dla Niemiec jest dostępna w zestawie SDK do Commerce w wersji 10.0.29. W wersji Commerce 10.0.28 lub wcześniejszej musisz użyć poprzedniej wersji zestawu SDK do Retail na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Niemiec (starsza wersja)](emea-deu-fi-sample-sdk.md).

### <a name="crt-extension-design"></a>Projekt rozszerzenia kolekcji CRT

Rozszerzenie (dostawca dokumentów fiskalnych) służy do generowania dokumentów specyficznych dla usługi oraz obsługi odpowiedzi z usługi rejestracji fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Istnieje jeden program obsługi żądań dla dostawcy dokumentów o nazwie **DocumentProviderEFRFiscalDEU**. Ten program obsługi służy do generowania dokumentów fiskalnych dla usługi rejestracji fiskalnej. Jest on dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla usługi, który ma zostać zarejestrowany w usłudze rejestracji fiskalnej.
- **GetFiscalTransactionExtendedDataDocumentProviderRequest** — to żądanie zwraca odpowiedź wraz z rozszerzonymi danymi.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji dla dostawcy dokumentów fiskalnych znajduje się w lokalizacji **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleGermany.xml** w repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ten plik umożliwia skonfigurowanie ustawień dostawcy dokumentów fiskalnych z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Rozszerzenie (łącznik fiskalny) służy do komunikacji z usługą rejestracji fiskalnej.

Rozszerzenie stacji sprzętowej to **HardwareStation.Extension.EFRSample**. Używa ono protokołu HTTP w celu przesyłania dokumentów generowanych przez rozszerzenie kolekcji CRT do usługi rejestracji fiskalnej. Obsługuje również odpowiedzi odbierane z usługi rejestracji fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **EFRHandler** jest punktem wejściowym obsługi żądań kierowanych do usługi rejestracji fiskalnej. Ten program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

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
