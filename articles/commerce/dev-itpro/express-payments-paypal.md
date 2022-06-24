---
title: Konfigurowanie płatności ekspresowych dla płatności PayPal
description: W tym artykule opisano sposób konfigurowania płatności ekspresowych dla usługi PayPal w celu włączenia funkcji szybszego realizacji zamówienia w systemie Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: b69b7384992fb86370ff6881824a7d2c9a77d2c4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905289"
---
# <a name="configure-express-payments-for-paypal"></a>Konfigurowanie płatności ekspresowych dla płatności PayPal

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób konfigurowania płatności ekspresowych dla usługi PayPal w celu włączenia funkcji szybszego realizacji zamówienia w systemie Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Kluczowe terminy

| Okres | Opis |
|---|---|
| Portfel PayPal | Środowisko klienta i integracja, które są obsługiwane przez łącznik PayPal. Jest on również znany jako przycisk PayPal. |
| Portfel | Typ płatności, który nie uwzględnia tradycyjnej charakterystyki płatności, taki jak zakres numeru identyfikacyjnego banku (BIN) i data ważności, który służy do rozróżniania typów kart kredytowych i debetowych. |
| Płatność ekspresowa | Moduł Commerce, który obsługuje szybsze realizacji transakcji w przypadku korzystania z obsługiwanych metod płatności. W tym artykule zajmą się tematy dotyczące używania modułu płatności ekspresowych z usługą PayPal. |

Dynamics 365 Commerce oferuje dostęp do integracji out-of-box dla PayPal Wallet. Gdy Łącznik płatności Dynamics 365 dla PayPal jest skonfigurowany, przycisk PayPal pojawia się jako metoda płatności do wyboru podczas realizacji zamówienia online. Gdy użytkownicy wybierzą opcję PayPal, są skierowane do ukończenia płatności bezpośrednio przez system PayPal, a następnie są zwracani do sklepu internetowego w celu ukończenia zamówienia. Dokonanie płatności za pomocą koszyka PayPal umożliwia klientom wykorzystanie informacji o koncie płatniczym do wstępnego wypełnienia formularza płatności, dzięki czemu mogą szybciej zakończyć proces realizacji transakcji.

W celu realizacji realizacji transakcji ekspresowych moduł Commerce dodano moduł płatności ekspresowych. Moduł płatności ekspresowej może być używany we fragmencie, który można znaleźć na stronie realizacji zamówienia lub koszyka. Po skonfigurowaniu systemu PayPal to samo odniesienie do łącznika Dynamics 365 Payment Connector dla PayPal jest używane zarówno dla opcji płatności ekspresowej, jak i opcji zwykłej realizacji transakcji.

## <a name="paypal-checkout-in-commerce"></a>Realizacja transakcji w usługach PayPal w handlu elektronicznym

### <a name="prerequisites"></a>Wymagania wstępne

Skonfiguruj obiekt PayPal Dla swojego środowiska zgodnie z opisem [w programie Dynamics 365 Payment Connector dla PayPal](../paypal.md).

Jeśli korzystasz z systemu PayPal jako opcji w zwykłym procesie realizacji transakcji (gdzie użytkownicy ręcznie wprowadzają informacje o swoim koncie bez korzystania z operacji wstępnego wypełniania płatności ekspresowych), postępuj zgodnie z instrukcjami konfiguracji w [Moduł płatności](../payment-module.md).

### <a name="payment-express-module-with-paypal"></a>Moduł płatności ekspresowych z usługą PayPal

Moduł płatności ekspresowych współpracuje z obsługą metod płatności, aby zaoferować klientom więcej możliwości wyewidencjonowania przez wstępne wypełnienie informacji o koncie usługi płatności podczas procesu realizacji zamówienia. Moduł płatności ekspresowej używa skonfigurowanego łącznika płatności do wstępnego wypełniania formularza realizacji zamówienia ze szczegółami konta użytkownika, takimi jak adres, informacje o kontakcie i wybrana metoda płatności.

Gdy używana jest ekspresowa realizacja transakcji PayPal, a użytkownik wybierze przycisk PayPal w sekcji ekspresowej płatności na stronie realizacji transakcji, zostanie otwarte okno płatności PayPal iFrame. Następnie użytkownik loguje się na swoje konto PayPal, aby użyć adresu wysyłkowego, adresu rozliczeniowego, adresu e-mail i wybranej metody płatności PayPal do opłacenia transakcji.

Gdy użytkownik zakończy czynność w oknie PayPal, zostanie przekierowany z powrotem do strony kasy witryny handlowej, gdzie formularz kasy jest wstępnie wypełniony wybranymi danymi. W przypadku przepływu ekspresowego płatności pierwsza dostępna opcja dostawy dla zwracanych adresów wysyłkowych zostanie wstępnie przepełniona przez użytkownika. Użytkownik ma wtedy możliwość przejrzenia zamówienia i zmiany szczegółów zamówienia w kasie, zanim wybierze **Złóż zamówienie** w celu sfinalizowania zamówienia.

### <a name="add-the-payment-express-module-with-paypal-to-a-fragment"></a>Dodaj moduł płatności ekspresowych z usługą PayPal do fragmentu

Aby dodać moduł ekspresowy płatności z PayPal do fragmentu w narzędziu do tworzenia witryn handlowych, wykonaj następujące kroki.

1. Przejdź do swojej witryny.
1. W okienku nawigacji wybierz pozycję **Fragmenty**, a następnie wybierz opcję **Nowy**.
1. W oknie dialogowym **Nowy fragment** znajdź i wybierz moduł **Payment express**, a następnie w polu **Nazwa fragmentu** wpisz nazwę fragmentu (na przykład **Express kasa**).
1. Wybierz przycisk **OK**, aby utworzyć fragment.
1. W widoku konspektu wybierz gniazdo utworzonego modułu płatności ekspresowych.
1. W okienku właściwości wybierz pozycję **Nagłówek**.
1. W oknie dialogowym **Nagłówek** w polu **Tekst nagłówka** wprowadź tekst nagłówka, który ma być pokazywany w sekcji zamówienia ekspresowego w witrynie (na przykład **Ekspresowa realizacja zamówienia**).
1. W **obszarze Poziom nagłówka** wybierz poziom nagłówka (na przykład **H2**).
1. Kliknij przycisk **OK**.
1. W panelu właściwości w polu **Wysokość iFrame** wprowadź lub dostosuj wysokość elementu iFrame (na przykład **60**).
1. W polu **Obsługiwane typy płatności** wprowadź wartość **PayPal**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Dodaj ekspresowy fragment płatności do strony realizacji zamówienia

Aby dodać fragment płatności express do strony kasy w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Przejdź do swojej witryny.
1. W lewym okienku nawigacji wybierz pozycję **Strony**, a następnie wybierz stronę realizacji zamówienia witryny.
1. Aby edytować aplikację, wybierz pozycję **Edytuj**.
1. W gnieździe **Główny** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Kontener** i wybierz przycisk **OK**.

    > [!NOTE]
    > Jeśli moduł kontenera zawierający fragment realizacji zamówienia już istnieje, przenieś sekcję płatności ekspresowej, aby była widoczna powyżej istniejącego kontenera realizacji w gnieździe **głównym**. Sekcja płatności ekspresowej będzie wówczas renderowana powyżej zwykłego kontenera realizacji zamówienia. Aby przenieść moduł w górę lub w dół, wybierz przycisk wielokropeka (**...**) dla modułu, a następnie wybierz opcję **Przenieś w górę** lub **Przenieś w dół**.

1. W okienku **Właściwości kontenera** zalecane jest skonfigurowanie tych ustawień w następujący sposób:

    - **Układ kontenera** – wybierz **skumulowany**.
    - **Szerokość** — wybierz kontener **wypełniania**.
    - **Pokazywane są elementy podrzędne** — wybierz **trzy**.

1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj fragment**.
1. W oknie dialogowym **Wybierz fragment** znajdź i wybierz utworzony fragment płatności ekspresowej, a następnie wybierz **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Dodaj ekspresowy fragment płatności do strony realizacji zamówienia

Aby dodać fragment płatności express do strony koszyka w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Przejdź do swojej witryny.
1. W lewym okienku nawigacji wybierz pozycję **Strony**, a następnie wybierz stronę koszyka zamówienia witryny.
1. Aby edytować aplikację, wybierz pozycję **Edytuj**.
1. W gnieździe **głównym** znajdź kontener zawierający **moduł Koszyk**. Moduł **Koszyk** będzie zawierał gniazdo **płatności ekspresowej**.
1. Na nowej stronie wybierz gniazdo **Płatność ekspresowa**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Płatność ekspresowa** i wybierz przycisk **OK**.
1. W panelu właściwości w polu **Obsługiwane typy ofert** wpisz **Paypal**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

### <a name="modes-of-delivery"></a>Metody dostawy

Gdy moduł płatności ekspresowych jest skonfigurowany do używania funkcji PayPal, pierwsza opcja dostawy zwracana dla adresu wysyłkowego wybranego dla konta PayPal zostanie wstępnie skonfigurowana. Użytkownicy będą mogli zmienić adres wysyłkowy, jeśli będą.

Kolejność trybu dostawy jest konfigurowana w sekcji **Tryby dostawy** dla kanału w Commerce headquarters. Aby uzyskać więcej informacji, zobacz temat [Ustaw metody dostawy](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Moduł realizacji zamówienia będzie również korzystać z modułu opcji dostawy, gdy tryby dostawy są renderowane podczas realizacji zamówienia. Aby uzyskać więcej informacji, przejdź do [Moduł Opcje dostawy](../delivery-options-module.md).

Tryby dostawy są dodawane do listy sklepów internetowych w programie Commerce Headquarters. Przejdź do **Handel detaliczny \> kanały \> sklepy internetowe** i wybierz identyfikator kanału dla swojego sklepu. Następnie wybierz **Ustawienia \> Typy dostawy**. Tryby dostawy modułu widoczne w konfiguracji będą wyświetlane w podobny sposób w witrynie. Aby dodać lub usunąć tryby dostawy dla kanału sprzedaży lub produktu, wybierz **opcję Zarządzanie trybami dostawy** w okienku akcji.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Płatności — często zadawane pytania](payments-retail.md)

[Moduł realizacji transakcji](../add-checkout-module.md)

[Moduł płatności](../payment-module.md)

[Ustaw metody dostawy](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Moduł opcji dostawy](../delivery-options-module.md)
