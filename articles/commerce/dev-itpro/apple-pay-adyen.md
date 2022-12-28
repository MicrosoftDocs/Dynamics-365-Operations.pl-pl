---
title: Konfigurowanie usługi Apple Pay z Adyen w Dynamics 365 Commerce
description: W tym artykule opisano, jak skonfigurować Apple Pay z Adyen w Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: 896847cee696e221b2114f7f28a0b56e73fc911b
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838237"
---
# <a name="set-up-apple-pay-with-adyen-in-dynamics-365-commerce"></a>Konfigurowanie usługi Apple Pay z Adyen w Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

W tym artykule opisano, jak skonfigurować Apple Pay z Adyen w Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Kluczowe terminy

| Okres | Opis |
|---|---|
| Apple Pay | Znany również jako „przycisk” Apple Pay, Apple Pay to oferta płatności portfelowych obsługiwana przez złącze Adyen. Umożliwia on obsługę klienta i integrację, które są obsługiwane przez Microsoft Dynamics 365 Apple Pay Connector. |
| Portfel | Typ płatności, który nie uwzględnia tradycyjnej charakterystyki płatności, taki jak zakres numeru identyfikacyjnego banku (BIN) i data ważności, który służy do rozróżniania typów kart kredytowych i debetowych. |

Dynamics 365 Commerce oferuje integrację z Apple Pay, gdy używana jest usługa bramki płatniczej Adyen. Apple Pay to metoda płatności za pomocą portfela cyfrowego, która wykorzystuje konto handlowe Apple Pay w połączeniu z usługą płatniczą Adyen. Po skonfigurowaniu przycisk Apple Pay jest wybieralną metodą płatności, która jest częścią strony realizacji zamówienia w sklepie internetowym. Przycisk Apple Pay jest prezentowany jako opcja płatności tylko dla obsługiwanych urządzeń Apple Pay. Gdy użytkownicy wybiorą **Apple Pay** w obsługiwanej przeglądarce lub urządzeniu, zostaną skierowani do zakończenia płatności bezpośrednio w usłudze Apple Pay. Następnie są odsyłani do sklepu internetowego, aby dokończyć zamówienie.

Odniesienie do łącznika Dynamics 365 Payment Connector for Apple Pay jest używane oprócz łącznika Dynamics 365 Payment Connector for Adyen w celu umożliwienia płatności Apple Pay i kartą kredytową w witrynie. Usługę Apple Pay można również skonfigurować do użytku w sklepach, które mają terminale płatnicze Adyen korzystające z Dynamics 365 Payment Connector for Adyen z punktem sprzedaży Commerce (POS). W tym przypadku Dynamics 365 Payment Connector for Adyen obsługuje dotknięcie urządzenia Apple Payment przez terminal.

## <a name="prerequisites"></a>Wymagania wstępne

Do korzystania z Apple Pay z Adyen w handlu wymagane jest konto sprzedawcy Apple. Aby uzyskać informacje dotyczące sposobu skonfigurowania usługi Apple Pay w obszarze klientów testowych, zobacz temat Integracja [z usługą Drop-in Apple Pay](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#set-up-apple-pay). Aby uzyskać informacje na temat tego, co można zrobić, gdy wszystko będzie gotowe do pracy w środowisku produkcyjnym, zobacz [Produkcja na żywo](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).

Metoda płatności Apple Pay musi być również zintegrowana z twoim kontem Adyen. Adyen pomoże w skonfigurowaniu metody płatności, a także upewnij się, że domeny, dla których używasz certyfikatu, są przypisane do tego certyfikatu.

Aby włączyć flagę ulepszonej funkcji portfela w Commerce headquarters, przejdź do **Przestrzeni roboczej \> Zarządzanie funkcjami**, wyszukaj cechę **Zwiększona obsługa portfela i ulepszenia płatności**. Wybierz funkcję, a następnie wybierz **Wyłącz**. Po włączeniu funkcji uruchom harmonogram dystrybucji **1110**, aby zmiana była dostępna we wszystkich kanałach.

## <a name="map-the-apple-pay-payment-method"></a>Mapowanie metody płatności Apple Pay

Apple Pay to metoda płatności za pomocą cyfrowego portfela. Aby dowiedzieć się, jak skonfigurować mapowanie płatności dla Apple Pay, zobacz [Obsługa płatności portfelowych](../wallets.md).

Aby zmapować metodę płatności Apple Pay w Commerce headquarters, wykonaj następujące kroki.

1. Przejdź do **Sprzedaż detaliczna i handel \> Ustawienia kanału \> Formy płatności \> Typy kart**.
1. Wybierz polecenie **Nowy**, aby dodać dodatkowy wiersz Apple Pay i określ następujące wartości:

    - **Identyfikator:** ApplePay
    - **Nazwa płatności elektronicznej:** Apple Pay
    - **Typ:** Portfel
    - **Wystawca:** Firma Apple

1. Wybierz **Mapowanie procesora**, aby otworzyć okno dialogowe **Metody mapowania płatności procesora**. W kolumnie **Niezamapowane metody płatności** procesora jest wymieniona obsługiwana metoda płatności dla każdego dostępnego łącznika (Adyen, PayPal i Firma Apple).
1. Zmapuj obsługiwane metody płatności dla łącznika **Dynamics 365 Payment Connector for Adyen** (do użytku w punkcie sprzedaży) i **Dynamics 365 Payment Connector for Apple Pay** (dla kanału online).
1. Dla każdego wiersza mapowania w kolumnie **Metody płatności z wykorzystaniem niemapowanego procesora** wybierz wiersz do obsługi, a następnie wybierz opcję **Dodaj**, aby przenieść wybory do kolumny **Metody płatności z mapowanym procesorem**.
1. Wybierz **przycisk OK**, a następnie na stronie **Typy kart** wybierz pozycję **Zapisz**.

## <a name="set-up-the-apple-pay-certificate-for-your-site"></a>Skonfiguruj certyfikat Apple Pay dla swojej witryny

Dla każdej witryny musisz przesłać plik powiązania domeny (znany również jako certyfikat Apple Pay), jak opisano w dokumentacji [Adyen Apple Pay](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live). Za pomocą Konstruktora witryn portalu Commerce można przekazać plik skojarzenia domeny do biblioteki multimediów w witrynie.

Aby skonfigurować certyfikat Apple Pay w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Pobierz certyfikat (plik skojarzenia domen) z [Adyen](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).
1. Dodaj rozszerzenie txt do pliku skojarzenia domeny.
1. W Konstruktorze witryn [przekaż](../upload-serve-static-files.md) plik skojarzenia domen do biblioteki multimediów swojej witryny.
1. Przejdź do okna **Adresy URL**.
1. Wybierz pozycję **Nowy \> Nowy adres URL**.
1. W oknie dialogowym **Nowy adres URL** wybierz opcję **Zasób biblioteki multimediów**.
1. W polu **ścieżki** adresu URL wprowadź ścieżkę URL (jeśli jeszcze nie została wprowadzona). Po podstawowym adresie URL domeny wprowadź następujący wymagany ciąg firmy Apple: `<domain>/.well-known/apple-developer-merchantid-domain-association.txt`.
1. Wybierz pozycję **Następny**. Biblioteka multimediów zawiera wszystkie przesłane zasoby multimedialne typu **dokument** (.txt).
1. Wybierz plik skojarzenia domeny, który ma być obsługiwany w przypadku żądań kierowanych na zdefiniowany wcześniej adres URL.
1. Wybierz opcję **Utwórz**.

W tym momencie utworzony adres URL jest w stanie wersji roboczej. Opublikuj adres URL, aby zakończyć proces. Plik, do którego wskazuje adres URL, nie zostanie zwrócony do momentu opublikowania adresu URL.

## <a name="configure-a-commerce-online-store-for-apple-pay"></a>Konfiguracja sklepu internetowego Commerce dla Apple Pay

Aby skonfigurować sklep internetowy Commerce do korzystania z Apple Pay, wykonaj poniższe kroki.

1. W centrali Commerce headquarters przejdź do **Handel detaliczny i inny \> Kanały \> Sklepy internetowe**.
1. Wybierz wartość **Identyfikator kanału sprzedaży detalicznej** dla kanału sklepu internetowego Twojej witryny.
1. Na skróconej karcie **Konta płatności** dodaj łącznik płatności usługi **Dynamics 365 dla programu Adyen**, jeśli nie jest on jeszcze ustawiony, zgodnie z instrukcjami wyświetlanymi w [Konfiguracja programu Dynamics 365 Payment Connector dla Adyen](adyen-connector-setup.md).
1. Po skonfigurowaniu łącznika Adyen wybierz opcję **Dodaj**, aby dodać łącznik **płatności usługi Dynamics 365 dla programu Apple Pay**.
1. Wprowadź wartości dla właściwości łącznika handlowca.

    | Właściwość               | Opis | Wymagane | Ustawienie automatyczne | Wartość przykładowa |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Nazwa zestawu          | Nazwa zespołu dla Dynamics 365 Payment Connector dla Apple Pay. | Tak | Tak | Nazwa binarna |
    | Identyfikator konta usługi     | Unikalny identyfikator dla ustawienia właściwości handlowych. Ten identyfikator jest umieszczany na transakcjach płatniczych i określa właściwości handlowca, z których powinny korzystać dalsze procesy (np. fakturowanie). | Tak | Tak | Guid |
    | Identyfikator konta izby rozliczeniowej    | Wprowadź unikalny identyfikator sprzedawcy Adyen. Ta wartość jest dostarczana podczas rejestracji w Adyen, jak opisano w [Zarejestruj się w Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Tak | Nie | MerchantIdentifier |
    | Klucz chmurowego interfejsu API          | Wprowadź klucz API chmury Adyen. Możesz uzyskać ten klucz, postępując zgodnie z instrukcjami w [Jak uzyskać klucz API](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Tak | Nr | abcdefg |
    | Środowisko bramy    | Wprowadź Środowisko bramy Adyen, na które ma być nałożona mapa. Możliwe wartości to **Test** i **Live**. Pole to należy ustawić na **Aktywny** tylko dla urządzeń i transakcji produkcyjnych. | Tak | Tak | Aktywny |
    | Obsługiwane waluty   | Wprowadź waluty, które łącznik ma przetwarzać. W scenariuszach z użyciem kart, Adyen może obsługiwać dodatkowe waluty poprzez [Dynamiczną konwersję walut](https://www.adyen.com/pos-payments/dynamic-currency-conversion) po wysłaniu żądania transakcji do terminala płatniczego. Skontaktuj się z pomocą techniczną Adyen, aby uzyskać listę obsługiwanych walut. | Tak | Tak | USD;EUR |
    | Obsługiwane typy metod płatności | Wprowadź typy płatności, które powinien przetwarzać łącznik. | Tak | Tak | ApplePay |

1. Po wprowadzeniu informacji o handlowcu uruchom zadanie harmonogramu dystrybucji konfiguracji kanału **1070**.


### <a name="configure-content-security-policies-in-site-builder"></a>Konfigurowanie zasad zabezpieczeń zawartości w Konstruktorze witryn

Zanim skonfigurujesz swoje fragmenty lub strony do korzystania z usługi Apple Pay, musisz upewnić się, że zasady bezpieczeństwa treści (CSP) są skonfigurowane w narzędziu do tworzenia witryn Commerce dla Twojej witryny.

Aby skonfigurować zasady bezpieczeństwa zawartości w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Przejdź do **Ustawień witryny \> Rozszerzenia**.
1. Na karcie **Polityka bezpieczeństwa treści** i wybierz **Dodaj** i dodaj linię z `https://applepay.cdn-apple.com/jsapi/v1/apple-pay-sdk.js` w sekcjach **child-src**, **connect-src**, **frame-src**, **img-src**, **script-src** i **style-src**.
1. Po zakończeniu wybierz opcję **Zapisz i opublikuj**, aby zatwierdzić zmiany.

### <a name="set-up-apple-pay-as-a-checkout-payment-option"></a>Konfigurowanie usługi Apple Pay jako opcji płatności wyewidencjonowania

Aby skonfigurować usługę Apple Pay jako opcję płatności przy kasie na (nieekspresowej) stronie kasy w swojej witrynie, wykonaj następujące czynności.

1. W kreatorze witryn wybierz pozycję **Fragmenty**, a następnie wybierz fragment.
1. Wybierz opcję **Edycja**.
1. W slocie **Kontener sekcji wyewidencjonowywania**, wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduł** wybierz moduł **Apple Pay** i wybierz przycisk **OK**.
1. Wybierz opcję **Zapisz**.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby go opublikować.

Ustawienia modułu **Apple Pay** są wbudowane w ten moduł i łączą się ze skonfigurowanym łącznikiem płatności usługi Dynamics 365 dla aplikacji Apple Pay skonfigurowanym dla kanału online w programie Commerce Headquarters.

### <a name="apple-pay-payment-behavior"></a>Zachowanie płatności Apple Pay

Przycisk płatności **Apple Pay** jest wyświetlany tylko na obsługiwanych urządzeniach Apple Pay (iPhone'ach, iPadach i przeglądarkach Safari obsługujących Apple Pay). Jeśli użytkownik nie korzysta z żadnego z tych urządzeń, przycisk płatności **Apple Pay** jest niewidoczny.

Gdy użytkownik wybierze przycisk płatności **Apple Pay**, pojawi się okno dialogowe **Apple Pay**. W tym miejscu użytkownik może uwierzytelnić się na swoim urządzeniu lub przeglądarce usługi Apple Pay. Okno dialogowe **Apple Pay** zawiera podsumowanie kwoty zamówienia i metody płatności, którą użytkownik skonfigurował w swoim Apple Wallet. Użytkownik może przejrzeć te szczegóły, a następnie wybrać opcję **Zapłać**, aby dokończyć płatność. Po zakończeniu płatności użytkownik jest przekierowywowany na stronę witryny **Zakończenie zamówienia**, na która znajduje się szczegółowe podsumowanie zamówienia dla zakończonej transakcji.

## <a name="configure-commerce-pos-for-apple-pay"></a>Konfiguracja Commerce POS dla Apple Pay

Konfiguracja punktu sprzedaży wykorzystuje ustawienie pola **Usługa EFT** profilu sprzętowego dla Dynamics 365 Payment Connector dla Adyen. W Commerce headquarters skonfiguruj usługę EFT dla Dynamics 365 Payment Connector for Adyen zgodnie z opisem w [Ustawianie profilu sprzętowego Dynamics 365 POS](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Upewnij się, że dodałeś **ApplePay** do listy rodzajów płatności w polu **Obsługiwane typy płatności**. Użyj średników (;), aby oddzielić typy procedur płatniczych na liście.

Mapowanie procesora dla złącza Adyen przechwyci typy kart portfela, które są używane przez Apple Pay na terminalu POS.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Płatności — często zadawane pytania](payments-retail.md)

[Moduł realizacji transakcji](../add-checkout-module.md)

[Moduł płatności](../payment-module.md)
