---
title: Moduł realizacji transakcji
description: W tym temacie opisano sposób dodawania modułu realizacji transakcji do strony i ustawiania wymaganych właściwości.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bd1d66fc39872019fc38dbbfb56dc3015d57d0dd
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411221"
---
# <a name="checkout-module"></a>Moduł realizacji transakcji


[!include [banner](includes/banner.md)]

W tym temacie opisano sposób dodawania modułu realizacji transakcji do strony i ustawiania wymaganych właściwości.

## <a name="overview"></a>Omówienie

Moduł realizacji transakcji to specjalny kontener, w którym są przechowywane wszystkie moduły wymagane do utworzenia zamówienia. Przedstawia przepływ krok po kroku, którego odbiorca używa do wprowadzenia wszystkich odpowiednich informacji w celu dokonania zakupu. System przechwytuje adres wysyłkowy, metodę wysyłki i informacje bilingowe. Ponadto zawiera podsumowanie zamówień i inne informacje związane z zamówieniem odbiorcy.

Moduł realizacji transakcji renderuje dane na podstawie identyfikatora koszyka. Ten identyfikator koszyka jest zapisany jako plik cookie przeglądarki. Identyfikator koszyka jest wymagany do renderowania informacji w module realizacji transakcji, takich jak towary w zamówieniu, łączna kwota i rabaty. 

Poniższy obraz pokazuje przykład modułu realizacji zamówienia Fabrikam na stronie realizacji zamówienia.

![Przykład modułu realizacji zamówienia](./media/Checkout.PNG)

## <a name="checkout-module-properties"></a>Właściwości modułu realizacji transakcji

W module realizacji transakcji jest wyświetlane podsumowanie zamówień oraz funkcje służące do składania zamówienia. Aby zebrać wszystkie informacje dotyczące odbiorcy wymagane do umieszczenia zamówienia, należy dodać do modułu realizacji transakcji dodatkowe moduły. Dzięki temu detaliści mają możliwość dodawania modułów niestandardowych do przepływu realizacji transakcji lub do wykluczania modułów na podstawie ich wymagań.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Moduły, których można używać w module realizacji

- **Adres wysyłkowy** — ten moduł umożliwia odbiorcy dodawanie lub wybieranie adresu wysyłki dla zamówienia. Jeśli odbiorca jest zalogowany, wyświetlany jest każdy adres, który został wcześniej zapisany dla tego odbiorcy. Następnie odbiorca może wybrać spośród tych adresów. Odbiorca może również dodać nowy adres. Adres wysyłkowy jest używany dla wszystkich towarów w zamówieniu wymagających wysyłki. Nie można go dostosować dla poszczególnych pozycji w wierszu. Formaty adresów wysyłkowych są definiowane dla każdego kraju lub regionu, a reguły specyficzne dla kraju/regionu są wymuszane przez ten moduł. Chociaż w tym module nie są sprawdzane adresy, sprawdzanie poprawności adresów może być wykonywane za pośrednictwem dostosowania. Jeśli zamówienie uwzględnia tylko towary, które zostaną odebrane w sklepie, ten moduł jest automatycznie ukrywany.

    Poniższy obraz pokazuje przykład modułu adresu wysyłki na stronie realizacji zamówienia.

    ![Przykład modułu adres wysyłki](./media/ecommerce-shippingaddress.PNG)

- **Opcje dostawy** — ten moduł umożliwia odbiorcy wybranie opcji dostawy dla zamówienia Opcje dostawy są oparte na adresie wysyłkowym. W przypadku zmiany adresu dostawy należy ponownie pobrać opcje dostawy. Jeśli zamówienie uwzględnia tylko towary, które zostaną odebrane w sklepie, ten moduł jest automatycznie ukrywany.

    Poniższy obraz pokazuje przykład opcji dostawy na stronie realizacji zamówienia.

    ![Przykład modułu opcji dostawy](./media/ecommerce-deliveryoptions.PNG)

- **Kontener sekcji wyewidencjonowywania** — ten moduł jest kontenerem, w ramach którego można umieścić wiele modułów w celu utworzenia sekcji w ramach przepływu realizacji transakcji. Na przykład można umieścić w tym kontenerze wszystkie moduły powiązane z płatnością, aby były wyświetlane w jednej sekcji. Ten moduł ma wpływ tylko na układ przepływu.
- **Karta upominkowa** — ten moduł umożliwia odbiorcy zapłatę za zamówienie za pomocą karty upominkowej. Obsługuje tylko karty upominkowe Microsoft Dynamics 365 Commerce. Do zamówienia można zastosować jedną lub więcej kart upominkowych. Jeśli saldo karty upominkowej nie pokrywa kwoty w koszyku, można połączyć kartę upominkową z inną metodą płatności. Karty upominkowe mogą zostać zrealizowane tylko wtedy, gdy odbiorca jest zalogowany do systemu.
- **Punkty lojalnościowe** — ten moduł umożliwia zapłatę odbiorcy za zamówienie za pomocą punktów lojalnościowych. System udostępnia podsumowanie dostępnych punktów i wygasających punktów i pozwala klientowi wybrać liczbę punktów do zrealizowania. Jeśli odbiorca nie jest zalogowany lub nie jest członkiem karty lojalnościowej lub jeśli łączna kwota w koszyku wynosi 0 (zero), ten moduł jest automatycznie ukrywany.
- **Płatności** — ten moduł umożliwia odbiorcy zapłatę za zamówienie za pomocą karty kredytowej. Jeśli całkowita kwota w koszyku jest objęta punktami lojalnościowymi lub kartą podarunkową lub jeśli wynosi 0 (zero), moduł ten jest automatycznie ukryty. Integracja z kartą kredytową jest zapewniona przez łącznik płatności Adyen dla tego modułu. Aby uzyskać więcej informacji na temat korzystania z tego łącznika, zapoznajsię z tematem [Łącznik płatności Adyen Dynamics 365](dev-itpro/adyen-connector.md).
- **Adres fakturowania** — ten moduł umożliwia klientowi udostępnianie informacji bilingowych. Te informacje są przetwarzane razem z informacjami o karcie kredytowej przez Adyen. Ten moduł zawiera opcję, która pozwala klientom na korzystanie z adresu rozliczeniowego w adresie wysyłkowym.

    Poniższy obraz przedstawia przykład modułów karty upominkowej, punktów lojalnościowych, płatności i adresu rozliczeniowego na stronie realizacja zamówienia.

    ![Przykład modułów karty upominkowej, punktów lojalnościowych, płatności i adresu rozliczeniowego](./media/ecommerce-payments.PNG)

- **Informacje kontaktowe** — ten moduł umożliwia odbiorcy dodanie lub zmianę informacji kontaktowych (adres e-mail) dla zamówienia.

- **Blok zaawansowanej zawartości** — ten moduł zawiera wszelkie wiadomości związane z systemem zarządzania zawartością (CMS). Na przykład może zawierać komunikat informujący „w przypadku problemów z zamówieniem, kontakt 1-800-Fabrikam”. 

## <a name="commerce-scale-unit-interaction"></a>Interakcja Commerce Scale Unit

Większość informacji dotyczących realizacji transakcji, takich jak adres wysyłkowy i metoda wysyłki, jest przechowywana w koszyku i przetwarzana w ramach zamówienia. Jedyny wyjątek to informacje o karcie kredytowej. Te informacje są przetwarzane bezpośrednio przy użyciu łącznika płatności Adyen. Płatność jest autoryzowana, ale nie jest naliczana.

## <a name="add-a-checkout-module-to-a-page-and-set-the-required-properties"></a>Dodaj moduł realizacji transakcji do strony i ustaw wymagane właściwości.

Aby dodać moduł realizacji transakcji do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Fragmenty strony**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.
1. W oknie dialogowym **Nowy fragment strony** wybierz moduł **Realizacji zamówienia**.
1. W obszarze **Nazwa fragmentu strony** wprowadź nazwę **Fragment realizacji zamówienia**, a następnie kliknij przycisk **OK**.
1. Wybierz gniazdo **Moduł realizacji zamówienia**.
1. W okienku właściwości po prawej stronie wybierz symbol ołówka, wprowadź tekst nagłówka w polu, a następnie zaznacz symbol znacznika wyboru.
1. Na nowej stronie wybierz gniazdo **Informacje dotyczące realizacji zamówienia**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduły **Adres wysyłki**, **Opcje dostawy**, **Kontener sekcji wyewidencjonowywania** i **Informacje o kontakcie**, a następnie kliknij przycisk **OK**.
1. W module **Kontener sekcji wyewidencjonowywania**, wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduły **Karta upominkowa**, **Lojalność** i **Płatność** i wybierz przycisk **OK**. W ten sposób użytkownik będzie mieć pewność, że wszystkie metody płatności zostaną wyświetlone w sekcji.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd fragmentu. Niektóre moduły, które nie mają kontekstu koszyka, mogą nie być renderowane w podglądzie.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby go opublikować.
1. Utwórz szablon, w którym jest używany nowy fragment realizacji transakcji.
1. Utwórz stronę kasy, która korzysta z nowego szablonu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
