---
title: Konfigurowanie usługi Google Pay z Adyen
description: Ten artykuł opisuje, jak skonfigurować Google Pay z Adyen w Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 07/05/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: cdf950fc7b3720543d93e108d4e3c3c2ab254e09
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838399"
---
# <a name="configure-google-pay-with-adyen"></a>Konfigurowanie usługi Google Pay z Adyen

[!include [banner](../includes/banner.md)]

Ten artykuł opisuje, jak skonfigurować Google Pay z Adyen w Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce oferuje integrację z Google Pay, gdy używana jest usługa bramki płatniczej Adyen. Google Pay to metoda płatności za pomocą portfela cyfrowego, która wykorzystuje konto handlowe Google Pay w połączeniu z usługą płatniczą Adyen. Po skonfigurowaniu przycisk Google Pay jest dostępny jako metoda płatności do wyboru podczas składania zamówienia online. Gdy użytkownicy wybiorą **Google Pay** w obsługiwanej przeglądarce lub urządzeniu, zostaną skierowani do zakończenia płatności bezpośrednio w usłudze Google Pay. Następnie są odsyłani do sklepu internetowego, aby dokończyć zamówienie.

Kiedy Google Pay jest używane z modułem kas ekspresowych w Commerce, informacje o koncie płatniczym użytkownika są automatycznie wstępnie wypełniane w formularzu kasowym, aby pomóc użytkownikowi szybciej przejść przez proces kasowy. Commerce zawiera moduł ekspresowej płatności, który umożliwia ekspresowe dokonywanie płatności przy kasie. Moduł płatności ekspresowej może być używany we fragmencie, który można znaleźć na stronie realizacji zamówienia lub koszyka. Referencja konektora Dynamics 365 Payment Connector dla Google Pay jest używana dodatkowo do Dynamics 365 Payment Connector dla Adyen w celu włączenia zarówno opcji ekspresowej płatności, jak i zwykłej kasy, gdy skonfigurowany jest PayPal. Google Pay można również skonfigurować z terminalami płatniczymi Adyen i punktami sprzedaży Commerce (POS) do użytku w sklepach.

## <a name="key-terms"></a>Kluczowe terminy

| Okres | Opis |
|---|---|
| Google Pay | Google Pay, znany również jako "przycisk" Google Pay, to usługa płatności portfelowych, która jest obsługiwana przez złącze Adyen. Umożliwia on obsługę klienta i integrację, które są obsługiwane przez Dynamics Google Pay Connector. |
| Portfel | Typ płatności, który nie uwzględnia tradycyjnej charakterystyki płatności, taki jak zakres numeru identyfikacyjnego banku (BIN) i data ważności, który służy do rozróżniania typów kart kredytowych i debetowych. |
| Moduł ekspresowej płatności | Moduł Dynamics 365 Commerce, który wspiera szybsze działanie kasy przy użyciu obsługiwanych metod płatności. |

## <a name="prerequisites"></a>Wymagania wstępne

Używanie Google Pay z Adyen w Commerce wymaga posiadania konta Google Merchant. Informacje o tym, jak skonfigurować swoje konto kupca Google, można znaleźć w [Dokumentacji Adyen dotyczącej Google Pay](https://docs.adyen.com/payment-methods/google-pay/) oraz w [Liście kontrolnej Google dotyczącej integracji](https://developers.google.com/pay/api/web/guides/test-and-deploy/integration-checklist).

Metoda płatności Google Pay musi być również zintegrowana z twoim kontem Adyen. Instrukcje dotyczące linku integracyjnego znajdziesz na stronie [Adyen Google Pay](https://www.adyen.com/payment-methods/google-pay).

Należy także włączyć rozszerzoną funkcję obsługi w centrali Dynamics 365 Commerce headquarters. Przejdź do **Przestrzeni roboczej \> Zarządzanie funkcjami**, wyszukaj cechę **Zwiększona obsługa portfela i ulepszenia płatności**, wybierz cechę, a następnie wybierz **Włącz** Po włączeniu funkcji uruchom harmonogram dystrybucji **1110**, aby zmiana była dostępna we wszystkich kanałach.

## <a name="map-the-google-pay-payment-method"></a>Mapowanie metody płatności Google Pay

Google Pay to metoda płatności za pomocą cyfrowego portfela. Aby dowiedzieć się, jak skonfigurować mapowanie płatności dla Google Pay, zobacz [Obsługa płatności portfelowych](../wallets.md).

Aby zmapować metodę płatności Google Pay do typów płatności kartą w kanałach POS i online, wykonaj poniższe kroki.

1. W centrali Commerce headquarters przejdź do **Handel detaliczny i inny \> Ustawienia kanału \> Metody płatności \> Typy kart**.
1. Wybierz **Nowy**, aby dodać linię dla Google Pay.
1. Wprowadź **ID** w polu, wpisz **GooglePay**.
1. W polu **Nazwa płatności elektronicznej** wpisz **Google Pay**.
1. W polu **Typ** wprowadź **Portfel**.
1. Wprowadź **Wydawca** w polu, wpisz **Google**.
1. Na pasku akcji wybierz **Mapowanie procesora**, aby otworzyć okno dialogowe **Metody mapowania płatności procesora**.
1. W sekcji **Niezidentyfikowane metody płatności procesora** zobaczysz listę niezidentyfikowanych metod płatności procesora, z których każda jest połączona z odpowiednim łącznikiem. Aby zmapować niezamapowane metody płatności procesora Google Pay do typów płatności kartą, wykonaj poniższe kroki dla każdego typu płatności:

    1. W części **Typy płatności kartą** wybierz typ płatności.
    1. W kolumnie **Niewykorzystane metody płatności procesora** wybierz zarówno łączniki **Dynamics 365 Payment Connector dla Adyen** (do użytku w punkcie sprzedaży), jak i łącznik **Dynamics 365 Payment Connector dla Google Pay** (do użytku w kanałach online).
    1. Wybierz opcję **Dodaj**. Wybrane opcje zostaną dodane do kolumny **Wybrane opcje zostaną dodane do kolumny**.

1. Po zakończeniu mapowania metod płatności wybierz **Zapisz**.
1. Na stronie **Typy kart** wybierz **Zapisz**.

## <a name="configure-a-commerce-online-store-for-google-pay"></a>Konfiguracja sklepu internetowego Commerce dla Google Pay

Aby skonfigurować sklep internetowy Commerce do korzystania z Google Pay, wykonaj poniższe kroki.

1. W centrali Commerce headquarters przejdź do **Handel detaliczny i inny \> Kanały \> Sklepy internetowe**.
1. Wybierz kanał sklepu internetowego swojej witryny, wybierając wartość kanału **Retail Channel Id**.
1. Na skróconej karcie **Konta płatności** w obszarze **Łącznik** potwierdź , że jest wymieniony **łącznik płatności usługi Dynamics 365 dla łącznika Adyen**. Jeśli nie ma go na liście, wykonaj instrukcje w [Skonfiguruj Dynamics 365 Payment Connector dla Adyen](adyen-connector-setup.md), aby go dodać.

    > [!NOTE]
    > W większości przypadków łącznik **Dynamics 365 Payment Connector dla Adyen** musi być wymieniony jako pierwszy łącznik dla twojego kanału (pierwszy łącznik jest również znany jako łącznik główny). Po nim muszą następować inne łączniki, które będą używane, takie jak łączniki **Dynamics 365 Payment Connector dla PayPal** i **Dynamics 365 Payment Connector dla GooglePay**.

1. Po dodaniu łącznika **Dynamics 365 Payment Connector dla Adyen** wybierz **Dodaj**, aby dodać łącznik **Dynamics 365 Payment Connector dla GooglePay**. Następnie ustaw następujące właściwości łącznik.

    | Pole                  | Opis | Wymagane | Ustawienie automatyczne | Wartość przykładowa |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Nazwa zestawu          | Nazwa zespołu dla Dynamics 365 Payment Connector dla GooglePay. | Tak | Tak | *Nazwa binarna* |
    | Identyfikator konta usługi     | Unikalny identyfikator dla ustawienia właściwości handlowych. Ten identyfikator jest umieszczany na transakcjach płatniczych i określa właściwości handlowca, z których powinny korzystać dalsze procesy (np. fakturowanie). | Tak | Tak | *GUID* |
    | Identyfikator sprzedawcy Google     | Wpisz identyfikator sprzedawcy Google, który jest przypisany do twojego konta sprzedawcy Google. Ta właściwość jest wymagana dla środowisk produkcyjnych, ale opcjonalna dla środowisk testowych. Aby uzyskać więcej informacji, odwiedź <https://pay.google.com/>. | Tak | Nie | *Identyfikator numeryczny* |
    | Identyfikator konta izby rozliczeniowej    | Wprowadź unikalny identyfikator sprzedawcy Adyen. Ta wartość jest dostarczana podczas rejestracji w Adyen, jak opisano w [Zarejestruj się w Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Tak | Nie | *Identyfikator handlowca* |
    | Klucz chmurowego interfejsu API          | Wprowadź klucz API chmury Adyen. Aby uzyskać ten klucz, postępuj zgodnie z instrukcjami w rozdziale [Jak uzyskać klucz API](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Tak | Nie | "abcdefg" |
    | Środowisko bramy    | Środowisko bramy Adyen, na które ma być nałożona mapa. Możliwe wartości to **Test** i **Live**. Pole to należy ustawić na **Aktywny** tylko dla urządzeń i transakcji produkcyjnych. | Tak | Tak | "Aktywny" |
    | Obsługiwane waluty   | Waluty, które ma przetwarzać złącze. W scenariuszach z użyciem kart, Adyen może obsługiwać dodatkowe waluty poprzez [Dynamiczną konwersję walut](https://www.adyen.com/pos-payments/dynamic-currency-conversion) po wysłaniu żądania transakcji do terminala płatniczego. Skontaktuj się z obsługą Adyen, aby uzyskać listę obsługiwanych walut. | Tak | Tak | "USD;EUR" |
    | Obsługiwane typy metod płatności | Typy płatności, które powinien przetwarzać łącznik. | Tak | Tak | "GooglePay" |

1. Po zakończeniu ustawiania właściwości łącznika uruchom zadanie harmonogramu dystrybucji **1070 (konfiguracja kanałów**).


### <a name="use-the-payment-express-module-with-google-pay"></a>Użyj modułu ekspresu płatniczego z Google Pay

Moduł ekspresu płatniczego Commerce współpracuje z metodami płatności, aby dać klientom witryny możliwość szybszego wymeldowania się dzięki wykorzystaniu informacji o ich koncie w serwisie płatniczym podczas procesu wymeldowywania. Moduł ekspresu płatniczego odwołuje się do skonfigurowanego przycisku łącznika i zwraca wybrane przez użytkownika szczegóły zamówienia (adres, dane kontaktowe i sposób płatności), aby wstępnie wypełnić formularz kasy.

Kiedy moduł ekspresu płatniczego jest używany z Google Pay, po wybraniu przez klienta przycisku Google Pay w sekcji **Wyspy płatnicze** otwiera się okno iframe Google Pay. Następnie użytkownicy mogą zalogować się na swoje konto Google i użyć adresu do wysyłki, adresu do faktury, adresu e-mail oraz wybranej metody płatności Google Pay, aby zapłacić za transakcję.

Kiedy użytkownicy wykonają akcję w oknie Google Pay, zostaną przekierowani na stronę kasową serwisu Commerce, gdzie formularz kasowy zostanie wstępnie wypełniony danymi ich konta Google Pay. Po powrocie do strony kasy z okna Google Pay użytkownicy zobaczą następujące szczegóły:

- W ekspresowym przepływie płatności dla klienta zostanie wstępnie wybrana pierwsza opcja dostawy, która jest dostępna dla zwróconego adresu wysyłki.
- W przypadku korzystania z usługi Google Pay nie jest zwracany kontaktowy adres e-mail. Użytkownicy kasy dla gości będą musieli podać adres e-mail w sekcji kontaktowej na stronie kasy. Dane kontaktowe zalogowanych użytkowników zostaną automatycznie uzupełnione z ich konta klienta Dynamics (podstawowy adres e-mail, którego użyli do uwierzytelnienia).

Klienci mają możliwość przejrzenia zamówień i zmiany szczegółów zamówienia, zanim wybiorą opcję **Złóż zamówienie**, aby sfinalizować zamówienie.

### <a name="configure-google-pay-in-site-builder"></a>Skonfiguruj Google Pay w kreatorze witryn 

Zanim skonfigurujesz swoje fragmenty lub strony z Google Pay, musisz upewnić się, że zasady bezpieczeństwa treści dla twojej witryny zostały ustawione w kreatorze witryn Commerce.

Aby upewnić się, że zasady bezpieczeństwa treści zostały ustawione w module budowania witryn, wykonaj poniższe kroki.

1. Przejdź do **Ustawień witryny \> Rozszerzenia**.
1. Na karcie **Polityka bezpieczeństwa treści** dodaj linię dla `*.google.com` do dyrektyw **child-src**, **connect-src**, **frame-ancestors**, **frame-src**, **img-src**, **script-src** i **style-src**.
1. Po zakończeniu wybierz przycisk **Zapisz i opublikuj**.

### <a name="configure-the-payment-express-fragment-with-google-pay-in-site-builder"></a>Skonfiguruj fragment ekspresu płatniczego z Google Pay w konstruktorze witryny

Aby skonfigurować fragment ekspresu płatniczego z Google Pay dla sklepu internetowego, wykonaj następujące kroki.

1. W Konstruktorze witryn przejdź do witryny **Fragmenty**.
1. Wybierz pozycję **Nowy**.
1. W oknie dialogowym **Nowy fragment** wybierz moduł **Kontener**, moduł, wprowadź nazwę fragmentu (na przykład **Kasa ekspresowa**), a następnie wybierz **OK**. 
1. Wybierz dla nowego fragmentu gniazdo **Domyślny pojemnik**.
1. W okienku właściwości po prawej stronie ustaw właściwości modułu pojemnika:

    - **Nagłówek** - Wprowadź nagłówek, który będzie wyświetlany w sekcji kasy ekspresowej na twojej stronie (na przykład **Kasa ekspresowa**).
    - **Układ kontenera** – wybierz **Przepływ**.
    - **Szerokość** — wybierz kontener **wypełniania**.
    - **Pokazane podrzędne** - Wybierz **Trzy**, aby określić liczbę podrzędnych, które zmieszczą się w wierszu sekcji ekspresowej kasy na stronie kasy (na przykład pole tekstowe, ekspresowa płatność dla PayPal i ekspresowa płatność dla Google Pay).
    - **Nazwa klasy CSS** - wprowadź **msc-express-payment-container** (wymagane).

    > [!IMPORTANT]
    > - Wartość **Nazwa klasy CSS** musi być ustawiona na **msc-express-payment-container**, aby kontrolować zachowanie kontenera podczas kasy. To zachowanie obejmuje ukrywanie, zwijanie i inne działania, które dotyczą sekcji kasy ekspresowej podczas przepływu kasy. Klasa **msc-express-payment-container** pracuje z domyślnymi operacjami, które zostały udostępnione wraz z modułem biblioteki kasy.
    > - W nazwie klasy można uwzględniać dodatkowe **Nazwie klasy CSS**. Jeśli dostosowujesz zachowanie modułu, sprawdź, czy kontrole stylu używają tego samego zachowania zakodowanego w bibliotece modułu dla ekspresowego zachowania kasy.

1. W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Płatność ekspresowa** i wybierz przycisk **OK**.
1. W okienku właściwości modułu **Wyraz płatniczy** ustaw lub dostosuj wartość **Wysokość iFrame** w pikselach (na przykład **60**).
1. W polu **Obsługiwane typy płatności** wprowadź wartość **GooglePay**. Wartość ta musi odpowiadać ciągowi **Wspierane typy płatności** w łączniku, który jest skonfigurowany dla kanału (jak opisano w sekcji [Konfiguracja sklepu internetowego Commerce dla Google Pay](#configure-a-commerce-online-store-for-google-pay) we wcześniejszej części tego artykułu).

    > [!NOTE]
    > Możesz powtórzyć kroki od 6. do 9., aby dodać moduły **Płatności ekspresowe** dla innych metod płatności. Dopasuj wartość **obsługiwanych typów metod** płatności do dodatkowych skonfigurowanych typów płatności (na przykład **Paypal**).

1. Opcjonalnie: Do domyślnego modułu kontenera możesz dodać moduł bloku tekstowego, aby dołączyć instrukcje lub informacje o ujawnieniu. Po dodaniu modułu, w oknie właściwości, w polu **Szczegółowy tekst** wpisz żądany tekst. Tekst można umieścić nad lub pod modułami ekspresów płatniczych, zaznaczając elipsę (**...**) w polu **Blok tekstowy**, a następnie wybierając **Przesuń w górę** lub **Przesuń w dół**.
1. Wybierz **Zapisz**, aby zapisać zmiany, a następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**, aby opublikować fragment.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Dodaj ekspresowy fragment płatności do strony realizacji zamówienia

Aby dodać fragment płatności ekspresowych do strony kasy w narzędziu, wykonaj następujące kroki.

1. W kreatorze witryn wybierz pozycję **Strony**, a następnie wybierz stronę realizacji zamówienia witryny.
1. Wybierz opcję **Edycja**.
1. W gnieździe **Główny** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W okienku właściwości po prawej stronie ustaw właściwości modułu pojemnika:

    - **Układ kontenera** – wybierz **skumulowany**.
    - **Szerokość** — wybierz kontener **wypełniania**.
    - **Pokazane podrzędne** - Wybierz **Trzy**, aby określić liczbę podrzędnych, które zmieszczą się w wierszu sekcji ekspresowej kasy na stronie kasy (na przykład pole tekstowe, ekspresowa płatność dla PayPal i ekspresowa płatność dla Google Pay).

1. W gnieździe modułu **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj fragment**.
1. W oknie dialogowym **Wybierz fragment** wybierz utworzony fragment płatności ekspresowej, a następnie wybierz **OK**.
1. Wybierz **Zapisz**, aby zapisać zmiany, a następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**, aby opublikować stronę.

> [!NOTE]
> Jeśli strona kasy zawiera już kontener z fragmentem kasy, a Ty chcesz, aby moduł ekspresu płatniczego był wyświetlany powyżej normalnego kontenera kasy, możesz umieścić go powyżej lub poniżej istniejącej kasy, wybierając elipsę (**...**) w polu **Główne gniazdo**, a następnie wybierając **Przesuń w górę** lub **Przesuń w dół**.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Dodaj ekspresowy fragment płatności do strony realizacji zamówienia

Aby dodać fragment ekspresu płatności do strony koszyka, wykonaj następujące kroki.

1. W kreatorze witryn wybierz pozycję **Strony**, a następnie wybierz stronę koszyka swojej witryny.
2. Wybierz opcję **Edycja**.
3. W widoku konspektu rozwiń **Gniazdo główne** w widoku drzewa i znajdź kontener, który zawiera moduł **Koszyk**.
4. W gnieździe modułu **Koszyk** wybierz **Płatność ekspresowa**, wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
5. W oknie dialogowym **Wybierz moduły** wybierz moduł **Płatność ekspresowa** i wybierz przycisk **OK**.
6. Wybierz gniazdo modułu **Płatność ekspresowa**. Następnie w okienku właściwości po prawej stronie, pod **Obsługiwane typy płatności**, wpisz **GooglePay**. Wartość ta musi odpowiadać ciągowi **Wspierane typy płatności** w łączniku, który jest skonfigurowany dla kanału (jak opisano w sekcji [Konfiguracja sklepu internetowego Commerce dla Google Pay](#configure-a-commerce-online-store-for-google-pay) we wcześniejszej części tego artykułu).
1. Wybierz **Zapisz**, aby zapisać zmiany, a następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**, aby opublikować stronę.

Użytkownicy mogą uwzględnić maksymalnie trzy obsługiwane moduły **Płatność ekspresowa** (czyli trzy dostępne obsługiwane opcje płatności) w gnieździe **Płatność ekspresowa** koszyka.

### <a name="set-up-google-pay-as-an-option-in-the-checkout-payment-section"></a>Ustaw Google Pay jako opcję w sekcji płatności przy kasie

Możesz skonfigurować Google Pay jako opcję w sekcji płatności w kasie, aby korzystać z funkcji płatności tylko w trybie ekspresowym. Formularz kasy zostanie wypełniony przez użytkownika, a strona płatności Google Pay przygotuje kasę tylko do płatności przez Google Pay. Żadne informacje z konta Google nie zostaną użyte do nadpisania wypełnionych danych kasy.

> [!NOTE]
> Poniższa procedura zakłada, że twoja witryna używa fragmentu kasy, który jest skonfigurowany z informacjami o odbiorze, adresem dostawy, opcjami dostawy, informacjami kontaktowymi, opcjonalnym regulaminem i warunkami oraz sekcją dla elementów kasy. Domyślna biblioteka modułów kasy jest wydana z kontenerem sekcji kasy, który zawiera blok tekstowy, punkty lojalnościowe, kartę podarunkową i moduły płatności. Aby uzyskać więcej informacji, zajrzyj do [Moduł płatności](../payment-module.md).

Aby ustawić Google Pay jako zwykłą opcję płatności w sekcji **Metoda płatności** na stronie kasy, wykonaj następujące kroki.

1. W kreatorze witryn wybierz pozycję **Fragmenty**, a następnie wybierz fragment.
1. Wybierz opcję **Edycja**.
1. Na nowej stronie wybierz gniazdo **Informacje dotyczące realizacji zamówienia**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Płatność ekspresowa** i wybierz przycisk **OK**.
1. W okienku **Płatności** po prawej stronie ustaw właściwości modułu pojemnika:

    - **Nagłówek** - Wprowadź nagłówek, który będzie wyświetlany w sekcji kasy ekspresowej na twojej stronie (na przykład **Google Pay**).
    - **Wysokość iFrame** - Zmień wartość na preferowaną wysokość projektu w pikselach (np. **75**). 
    - **Obsługiwane typy płatności** - Wprowadź **GooglePay**, aby dopasować konfigurację dla łącznika Google Pay w centrali Commerce headquarters headquarters.
    - **Jest płatnością główną** — pozostaw to pole wyboru wyczyszczone. (Ta właściwość jest zwykle włączona dla modułu kasowego Adyen).
    - **Zastąpienie stylu płatności** — Ta właściwość nie jest obsługiwana w konfiguracji Google Pay.
    - **Użyj identyfikatora łącznika** — Ta właściwość musi być zaznaczona, jeśli na stronie jest używanych wiele łączników płatności.

1. Umieść moduł powyżej lub poniżej innych modułów płatności, wybierając elipsę (**...**) w polu **Płatność**, a następnie wybierając **Przesuń w górę** lub **Przesuń w dół**.
1. Wybierz **Zapisz**, aby zapisać zmiany, a następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**.

### <a name="modes-of-delivery"></a>Metody dostawy

W module ekspresu płatniczego, który korzysta z Google Pay, zostanie wstępnie wybrana pierwsza opcja dostawy, która zostanie zwrócona w odniesieniu do wybranego adresu wysyłki z konta Google Pay. Użytkownicy mają możliwość zmiany adresu wysyłki na inny, jeśli chcą.

Kolejność wyświetlania sposobów dostawy w module payment express jest konfigurowana na stronie kanału **Mody dostawy** w centrali Commerce headquarters. W centrali Commerce headquarters przejdź do **Handel detaliczny i nny \> Channels \> Sklepy online** i wybierz wartość **Identyfikator kanału Retail** dla swojego sklepu. W okienku akcji na karcie **Ustawienia** wybierz opcję **Metody dostawy**. Wymienione sposoby dostawy zostaną wyświetlone w tej samej kolejności w module ekspresu płatniczego. Wybierz **Zarządzanie sposobami dostawy** na pasku akcji, aby dodać lub usunąć sposoby dostawy dla kanału detalicznego lub produktu. Aby uzyskać więcej informacji na temat konfigurowania trybów doręczeń, zobacz [Ustawianie trybów dostawy](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Moduł realizacji zamówienia będzie również korzystać z modułu opcji dostawy, gdy tryby dostawy są renderowane podczas realizacji zamówienia. Aby uzyskać więcej informacji, przejdź do [Moduł Opcje dostawy](../delivery-options-module.md).

Sposoby dostawy są wyświetlane po dodaniu ich do listy **Sposoby dostawy** w sklepie internetowym.

## <a name="configure-commerce-pos-for-google-pay"></a>Konfiguracja Commerce POS dla Google Pay

Konfiguracja punktu sprzedaży wykorzystuje ustawienie pola **UsługaEFT** profilu sprzętowego dla Dynamics 365 Payment Connector dla Adyen. Aby dowiedzieć się, jak skonfigurować usługę elektronicznego przelewu środków (EFT) dla Dynamics 365 Payment Connector for Adyen w Commerce headquarters, zobacz [Ustawianie profilu sprzętowego Dynamics 365 POS](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Mapowanie procesora dla łącznika Adyen pozwala uchwycić typy kart portfelowych, których Google Pay używa w terminalu POS.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Płatności — często zadawane pytania](payments-retail.md)

[Moduł realizacji transakcji](../add-checkout-module.md)

[Moduł płatności](../payment-module.md)
