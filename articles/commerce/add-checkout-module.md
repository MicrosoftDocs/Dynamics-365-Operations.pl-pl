---
title: Moduł realizacji transakcji
description: W tym temacie opisano sposób dodawania modułu realizacji transakcji do strony i ustawiania wymaganych właściwości.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 389e3e9d631574eac499f7c6146e2776b8126a52
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761112"
---
# <a name="checkout-module"></a>Moduł realizacji transakcji

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano sposób dodawania modułu realizacji transakcji do strony i ustawiania wymaganych właściwości.

## <a name="overview"></a>Omówienie

Moduł realizacji transakcji to specjalny kontener, w którym są przechowywane wszystkie moduły wymagane do utworzenia zamówienia. Przedstawia przepływ krok po kroku, którego odbiorca używa do wprowadzenia wszystkich odpowiednich informacji w celu dokonania zakupu. System przechwytuje adres wysyłkowy, metodę wysyłki i informacje bilingowe. Ponadto zawiera podsumowanie zamówień i inne informacje związane z zamówieniem odbiorcy.

Moduł realizacji transakcji renderuje dane na podstawie identyfikatora koszyka. Ten identyfikator koszyka jest zapisany jako plik cookie przeglądarki. Identyfikator koszyka jest wymagany do renderowania informacji w module realizacji transakcji, takich jak towary w zamówieniu, łączna kwota i rabaty. 

Poniższy obraz pokazuje przykład modułu realizacji zamówienia Fabrikam na stronie realizacji zamówienia.

![Przykład modułu realizacji zamówienia](./media/Checkout.PNG)

## <a name="checkout-module-properties"></a>Właściwości modułu realizacji transakcji

W module realizacji transakcji jest wyświetlane podsumowanie zamówień oraz funkcje służące do składania zamówienia. Aby zebrać wszystkie informacje dotyczące odbiorcy wymagane do umieszczenia zamówienia, należy dodać do modułu realizacji transakcji dodatkowe moduły. Dzięki temu detaliści mają możliwość dodawania modułów niestandardowych do przepływu realizacji transakcji lub do wykluczania modułów na podstawie ich wymagań.

| Nazwa właściwości | Wartości | opis |
|----------------|--------|-------------|
| Nagłówek realizacji zamówienia | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Nagłówek do modułu kasy. |
| Nagłówek podsumowania zamówienia | Tekst nagłówka | Nagłówek sekcji podsumowania zamówień w module. |
| Nagłówek pozycji koszyka | Tekst nagłówka | Nagłówek pozycji w wierszu koszyka wyświetlany w module realizacji transakcji. |
| Pokazuj pozycję online opłat za wysyłkę | **Prawda** lub **Fałsz** | Jeśli ta właściwość ma wartość **Prawda**, opłaty za wysyłkę, które mają zastosowanie do pozycji zamówienia, zostaną wyświetlone w wierszach koszyka. Jeśli funkcja **Opłata za nagłówek bez podziału** jest włączona w centrali Commerce, opłata za wysyłkę zostanie zastosowana na poziomie nagłówka, a nie na poziomie wiersza. Ta funkcja została dodana w wersji Commerce 10.0.13. |

## <a name="modules-that-can-be-used-in-the-checkout-module"></a>Moduły, których można używać w module realizacji

- **Adres wysyłkowy** — ten moduł umożliwia odbiorcy dodawanie lub wybieranie adresu wysyłki dla zamówienia. Aby uzyskać więcej informacji dotyczących tego modułu, przejdź do [Moduł adresu wysyłki](ship-address-module.md).

    Poniższy obraz pokazuje przykład modułu adresu wysyłki na stronie realizacji zamówienia.

    ![Przykład modułu adres wysyłki](./media/ecommerce-shippingaddress.PNG)

- **Opcje dostawy** — ten moduł umożliwia odbiorcy wybranie metody dostawy dla zamówienia. Aby uzyskać więcej informacji dotyczących tego modułu, przejdź do [Moduł Opcje dostawy](delivery-options-module.md).

    Poniższy obraz pokazuje przykład opcji dostawy na stronie realizacji zamówienia.
 
    ![Przykład modułu opcji dostawy](./media/ecommerce-deliveryoptions.PNG)

- **Kontener sekcji wyewidencjonowywania** — ten moduł jest kontenerem, w ramach którego można umieścić wiele modułów w celu utworzenia sekcji w ramach przepływu realizacji transakcji. Na przykład można umieścić w tym kontenerze wszystkie moduły powiązane z płatnością, aby były wyświetlane w jednej sekcji. Ten moduł ma wpływ tylko na układ przepływu.

- **Karta upominkowa** — ten moduł umożliwia odbiorcy zapłatę za zamówienie za pomocą karty upominkowej. Aby uzyskać więcej informacji dotyczących tego modułu, przejdź do [Moduł karty upominkowej](add-giftcard.md).

- **Punkty lojalnościowe** — ten moduł umożliwia zapłatę odbiorcy za zamówienie za pomocą punktów lojalnościowych. System udostępnia podsumowanie dostępnych punktów i wygasających punktów i pozwala klientowi wybrać liczbę punktów do zrealizowania. Jeśli odbiorca nie jest zalogowany lub nie jest członkiem karty lojalnościowej lub jeśli łączna kwota w koszyku wynosi 0 (zero), ten moduł jest automatycznie ukrywany.

- **Płatności** — ten moduł umożliwia odbiorcy zapłatę za zamówienie za pomocą karty kredytowej lub debetowej. Odbiorcy mogą również podać adres bilingowy dla wybranej przez nich opcji płatności. Aby uzyskać więcej informacji dotyczących tego modułu, przejdź do [Moduł płatności](payment-module.md).

    Poniższy obraz przedstawia przykład modułów karty upominkowej, punktów lojalnościowych i płatności na stronie realizacja zamówienia.

    ![Przykład karty podarunkowej, punktów lojalnościowych i płatności na stronie realizacji transakcji](./media/ecommerce-payments.PNG)

- **Informacje kontaktowe** — ten moduł umożliwia odbiorcy dodanie lub zmianę informacji kontaktowych (adres e-mail) dla zamówienia.

- **Blok zaawansowanej zawartości** — ten moduł zawiera wszelkie wiadomości związane z systemem zarządzania zawartością (CMS). Na przykład może zawierać komunikat informujący „w przypadku problemów z zamówieniem, kontakt 1-800-Fabrikam”. 

- **Warunki realizacji transakcji** — ten moduł zawiera tekst sformatowany zawierający warunki i warunki oraz pole wyboru dla danego odbiorcy. Pole wyboru jest opcjonalne i można je konfigurować. Dane wejściowe są przechwytywane przez moduł i mogą być używane jako sprawdzanie przed wyzwoleniem złożenia zamówienia, ale nie są dołączone do informacji podsumowania zamówienia. Ten moduł można dodać do kontenera realizacji zamówienia, kontenera sekcji realizacji zamówienia lub miejsca na warunki, w zależności od potrzeb biznesowych. Jeśli zostanie dodany do kontenera realizacji zamówienia lub gniazda kontenera sekcji realizacji zamówienia, pojawi się jako krok w procesie kasy. Jeśli zostanie dodany do gniazda warunków i postanowień, zostanie wyświetlony w pobliżu przycisku umieszczania zamówienia.

    Poniższy obraz pokazuje przykład modułu postanowień na stronie realizacji zamówienia.

    ![Przykład warunków i postanowień na stronie realizacja zamówienia](./media/ecommerce-checkout-terms.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interakcja Commerce Scale Unit

Większość informacji dotyczących realizacji transakcji, takich jak adres wysyłkowy i metoda wysyłki, jest przechowywana w koszyku i przetwarzana w ramach zamówienia. Jedyny wyjątek to informacje o karcie kredytowej. Te informacje są przetwarzane bezpośrednio przy użyciu łącznika płatności Adyen. Płatność jest autoryzowana, ale nie jest naliczana, dopóki zamówienie nie zostanie zrealizowane.

## <a name="add-a-checkout-module-to-a-page-and-set-the-required-properties"></a>Dodaj moduł realizacji transakcji do strony i ustaw wymagane właściwości.

Aby dodać moduł realizacji transakcji do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.
1. W oknie dialogowym **Nowy fragment** wybierz moduł **Realizacji zamówienia**.
1. W obszarze **Nazwa fragmentu** wprowadź nazwę **Fragment realizacji zamówienia**, a następnie kliknij przycisk **OK**.
1. Wybierz gniazdo **Moduł realizacji zamówienia**.
1. W okienku właściwości po prawej stronie wybierz symbol ołówka, wprowadź tekst nagłówka w polu, a następnie zaznacz symbol znacznika wyboru.
1. Na nowej stronie wybierz gniazdo **Informacje dotyczące realizacji zamówienia**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduły **Adres wysyłki**, **Opcje dostawy**, **Kontener sekcji wyewidencjonowywania** i **Informacje o kontakcie**, a następnie kliknij przycisk **OK**.
1. W module **Kontener sekcji wyewidencjonowywania**, wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduły **Karta upominkowa**, **Lojalność** i **Płatność** i wybierz przycisk **OK**. W ten sposób użytkownik będzie mieć pewność, że wszystkie metody płatności zostaną wyświetlone w sekcji.
1. W gnieździe **Warunków i postanowień** dodaj moduł **Warunki realizacji transakcji**, jeśli jest on wymagany. W panelu właściwości modułu odpowiednio skonfiguruj warunki i tekst warunku.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd fragmentu. Niektóre moduły, które nie mają kontekstu koszyka, mogą nie być renderowane w podglądzie.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby go opublikować.
1. Utwórz szablon, w którym jest używany nowy fragment realizacji transakcji.
1. Utwórz stronę kasy, która korzysta z nowego szablonu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł koszyka](add-cart-module.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł płatności](payment-module.md)

[Moduł adresu wysyłki](ship-address-module.md)

[Moduł Opcje dostawy](delivery-options-module.md)

[Moduł szczegółów zamówienia](order-confirmation-module.md)

[Moduł karty upominkowej](add-giftcard.md)
