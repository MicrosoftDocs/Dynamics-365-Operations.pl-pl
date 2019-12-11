---
title: Moduł realizacji transakcji
description: W tym temacie opisano sposób dodawania modułu realizacji transakcji do strony i ustawiania wymaganych właściwości.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 4b810441fd25d41ee0893b119b4f7d91e7435d21
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697090"
---
# <a name="checkout-module"></a>Moduł realizacji transakcji

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano sposób dodawania modułu realizacji transakcji do strony i ustawiania wymaganych właściwości.

## <a name="overview"></a>Omówienie

Moduł realizacji transakcji to specjalny kontener, w którym są przechowywane wszystkie moduły wymagane do utworzenia zamówienia. Moduł realizacji transakcji może zawierać moduły obsługujące adres wysyłkowy, metody wysyłki, informacje bilingowe, podsumowanie zamówień oraz inne informacje związane z zamówieniem klienta. Przedstawia przepływ krok po kroku, którego odbiorca używa do wprowadzenia wszystkich odpowiednich informacji w celu dokonania zakupu.

Moduł realizacji transakcji renderuje dane na podstawie identyfikatora koszyka. Ten identyfikator koszyka jest zapisany jako plik cookie przeglądarki. Identyfikator koszyka jest wymagany do renderowania informacji w module realizacji transakcji, takich jak towary w zamówieniu, łączna kwota i rabaty.

## <a name="checkout-module-properties"></a>Właściwości modułu realizacji transakcji

Moduł realizacji transakcji obsługuje zbiór znajdujących się w nim modułów. Właściwość szerokości umożliwia określenie, czy pozycje w module realizacji zamówienia powinny być dostosowane do szerokości czy wypełniać ekran.

Moduł realizacji transakcji ma wiele gniazd, takich jak gniazdo **Informacje dotyczące realizacji zamówienia**, gniazdo **Podsumowania zamówienia** i gniazdo **Złóż zamówienie**. Każde gniazdo obsługuje zbiór modułów, które będą wyświetlane w określonym układzie na stronie. Na przykład gniazdo z **Informacje dotyczące realizacji zamówienia** zawiera wszystkie moduły wymagane do wyzwolenia na proces realizacji transakcji, takie jak moduły adresu wysyłkowego i metody płatności. W gnieździe **Podsumowanie zamówienia** wyświetlane jest podsumowanie zamówienia i jest obsługiwane działanie związane z wprowadzaniem zamówienia. Gniazdo **Złóż zamówienie** umożliwia także obsługę akcji związanej z wprowadzaniem zamówienia. Moduły składania zamówień można definiować w dwóch gniazdach w celu zoptymalizowania procesu składania zamówień z różnych platform.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Moduły, których można używać w module realizacji

- **Adres wysyłkowy** — ten moduł umożliwia odbiorcy dodawanie lub wybieranie adresu wysyłki dla zamówienia. Jeśli odbiorca jest zalogowany, wyświetlany jest każdy adres, który został wcześniej zapisany dla tego odbiorcy. Następnie odbiorca może wybrać spośród tych adresów. Odbiorca może również dodać nowy adres. Adres wysyłkowy jest używany dla wszystkich towarów w zamówieniu wymagających wysyłki. Nie można go dostosować dla poszczególnych pozycji w wierszu. Formaty adresów wysyłkowych są definiowane dla każdego kraju lub regionu, a reguły specyficzne dla kraju/regionu są wymuszane przez ten moduł. Chociaż w tym module nie są sprawdzane adresy, sprawdzanie poprawności adresów może być wykonywane za pośrednictwem dostosowania. Jeśli zamówienie uwzględnia tylko towary, które zostaną odebrane w sklepie, ten moduł jest automatycznie ukrywany.
- **Opcje dostawy** — ten moduł umożliwia odbiorcy wybranie opcji dostawy dla zamówienia Opcje dostawy są oparte na adresie wysyłkowym. W przypadku zmiany adresu dostawy należy ponownie pobrać opcje dostawy. Jeśli zamówienie uwzględnia tylko towary, które zostaną odebrane w sklepie, ten moduł jest automatycznie ukrywany.
- **Kontener sekcji wyewidencjonowywania** — ten moduł jest kontenerem, w ramach którego można umieścić wiele modułów w celu utworzenia sekcji w ramach przepływu realizacji transakcji. Na przykład można umieścić w tym kontenerze wszystkie moduły powiązane z płatnością, aby były wyświetlane w jednej sekcji. Ten moduł ma wpływ tylko na układ przepływu.
- **Karta upominkowa** — ten moduł umożliwia odbiorcy zapłatę za zamówienie za pomocą karty upominkowej. Obsługuje tylko karty upominkowe Microsoft Dynamics 365 Commerce. Do zamówienia można zastosować jedną lub więcej kart upominkowych. Jeśli saldo karty upominkowej nie pokrywa kwoty w koszyku, można połączyć kartę upominkową z inną metodą płatności. Karty upominkowe mogą zostać zrealizowane tylko wtedy, gdy odbiorca jest zalogowany do systemu.
- **Punkty lojalnościowe** — ten moduł umożliwia zapłatę odbiorcy za zamówienie za pomocą punktów lojalnościowych. System udostępnia podsumowanie dostępnych punktów i wygasających punktów i pozwala klientowi wybrać liczbę punktów do zrealizowania. Jeśli odbiorca nie jest zalogowany lub nie jest członkiem karty lojalnościowej lub jeśli łączna kwota w koszyku wynosi 0 (zero), ten moduł jest automatycznie ukrywany.
- **Karta kredytowa** — ten moduł umożliwia odbiorcy zapłatę za zamówienie za pomocą karty kredytowej. Jeśli całkowita kwota w koszyku jest objęta punktami lojalnościowymi lub kartą podarunkową lub jeśli wynosi 0 (zero), moduł ten jest automatycznie ukryty. Integracja z kartą kredytową jest zapewniona przez łącznik płatności Adyen. Aby uzyskać więcej informacji na temat korzystania z tego łącznika, zapoznajsię z tematem [Łącznik płatności Adyen](https://).
- **Adres fakturowania** — ten moduł umożliwia klientowi udostępnianie informacji bilingowych. Te informacje są przetwarzane razem z informacjami o karcie kredytowej przez Adyen. Ten moduł zawiera opcję, która pozwala klientom na korzystanie z adresu rozliczeniowego w adresie wysyłkowym.
- **Informacje kontaktowe** — ten moduł umożliwia odbiorcy dodanie lub zmianę informacji kontaktowych (adres e-mail) dla zamówienia.
- **Złóż zamówienie** — ten moduł pozwala odbiorcy złożyć zamówienie.
- **Blok zawartości sformatowanej** — ten moduł zawiera wszelkie wiadomości związane z systemem zarządzania zawartością (CMS). Na przykład może zawierać komunikat informujący „w przypadku problemów z zamówieniem, kontakt 1-800-FABRIKAM”. 
- **Podsumowanie zamówienia** — ten moduł pokazuje podział kosztów zamówienia.
- **Pozycje w wierszu zamówienia** – Ten moduł wyświetla podsumowanie pozycji, które zostaną uwzględnione w zamówieniu.

## <a name="retail-server-interaction"></a>Interakcja z serwerem Retail

Większość informacji dotyczących realizacji transakcji, takich jak adres wysyłkowy i metoda wysyłki, jest przechowywana w koszyku i przetwarzana w ramach zamówienia. Jedyny wyjątek to informacje o karcie kredytowej. Te informacje są przetwarzane bezpośrednio przy użyciu łącznika płatności Adyen. Płatność jest autoryzowana, ale nie jest naliczana.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Dodaj moduł realizacji transakcji do nowej strony i ustaw wymagane właściwości.

Aby dodać moduł realizacji transakcji do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Fragment \> Nowy Fragment** i nazwij nowy fragment **Wyewidencjonowanie fragmentu**.
1. Dodaj moduł realizacji transakcji do fragmentu.
1. Dodaj nagłówek do modułu realizacji transakcji.
1. W gnieździe **Informacje dotyczące realizacji zamówienia** dodaj adres wysyłkowy, opcje dostarczania, kontener sekcji wyewidencjonowywania i moduły informacji kontaktowych. W gnieździe **Informacje dotyczące realizacji zamówienia** powinny być teraz cztery sekcje.
1. W module kontener sekcji realizacja transakcji dodaj kartę upominkową, punkty lojalnościowe i moduły kart kredytowych. W ten sposób użytkownik będzie mieć pewność, że wszystkie metody płatności zostaną wyświetlone w sekcji.
1. W gnieździe **Podsumowanie zamówienia** dodaj podsumowanie zamówień, złóż zamówienie i moduły zaawansowanego bloku zawartości.
1. W module blok zawartości zaawansowanej dodaj następujący tekst: **W przypadku pytań dotyczących zamówienia skontaktuj się z 1-800-FABRIKAM.**
1. W gnieździe **Złóż zamówienie**, dodaj moduł złóż zamówienie.
1. Wybierz opcję **Zapisz**. Niektóre moduły mogą nie być renderowane w podglądzie, ponieważ nie mają kontekstu koszyka.
1. Zaewidencjonuj fragment i opublikuj go.
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
