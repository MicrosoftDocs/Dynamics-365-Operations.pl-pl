---
title: Moduł płatności
description: W tym artykule omówiono moduł płatności i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: a89ca5dd4f46611e75faccd3213028750fa48d35
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850282"
---
# <a name="payment-module"></a>Moduł płatności

[!include [banner](includes/banner.md)]

W tym artykule omówiono moduł płatności i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.

Odbiorcy przysługujący modułowi płatności płacą za zamówienia za pomocą kart kredytowych lub debetowych. Integrację płatności dla tego modułu zapewnia Dynamics 365 Payment Connector dla Adyen. Aby uzyskać więcej informacji na temat konfigurowania i konfigurowania łącznika płatności, zobacz temat [Łącznik płatności usługi Dynamics 365 dla Adyen](dev-itpro/adyen-connector.md).  

Począwszy od wersji Commerce 10.0.14, moduł płatności został również zintegrowany z Dynamics 365 Payment Connector dla PayPal, aby umożliwić klientom płacenie za zamówienia za pomocą PayPal. Aby uzyskać więcej informacji na temat sposobu konfigurowania i konfigurowania Dynamics 365 Payment Connector dla PayPal, zobacz temat [Łącznik płatności usługi Dynamics 365 dla PayPal](paypal.md). 

## <a name="dynamics-365-payment-connector-for-adyen"></a>Łącznik płatności usługi Dynamics 365 dla Adyen 

Moduł płatności obsługuje informacje o płatności, które są obsługiwane za pośrednictwem Adyen w ramce w wierszu HTML (iframe). Moduł płatności współdziała z Commerce Scale Unit, aby pobrać informacje o płatności Adyen. W ramach interakcji Commerce Scale Unit moduł płatności może umożliwić podawanie informacji o adresie rozliczeniowym w ramce iframe poprzez Adyen lub jako oddzielny moduł. W motywie Fabrikam adres bilingowy jest włączony jako oddzielny moduł. Takie podejście pozwala na większą elastyczność formatowania, ponieważ wiersze adresu mogą być renderowane w taki sposób, aby były podobne do wierszy adresu wysyłkowego.

Ponadto moduł płatności umożliwia odbiorcom zalogowanych zapisanie informacji o płatności. Informacje o płatności i adres rozliczeniowy są zapisywane i zarządzane za pośrednictwem łącznika płatności Adyen.

Moduł płatności obejmuje wszelkie opłaty za zamówienia, które nie są jeszcze objęte punktami lojalnościowymi lub kartami upominkowymi. Jeśli suma dla zamówienia jest w pełni objęta punktami lojalnościowymi lub kredytami upominkowymi, moduł płatności zostanie ukryty, a odbiorca będzie mógł je złożyć bez tego zamówienia.

Złącze płatności Adyen obsługuje również silne uwierzytelnianie klienta (SCA). Część znowelizowanej dyrektywy Unii Europejskiej (UE) w sprawie usług płatniczych (PSD2) wymaga, aby kupujący online byli uwierzytelniani poza doświadczeniem związanym z zakupami online, gdy używają elektronicznej metody płatności. Podczas realizacji transakcji klienci są przekierowywani do swojej witryny bankowej, a następnie po uwierzytelnieniu są przekierowywani z powrotem do przepływu płatności w aplikacji Commerce. Podczas tego przekierowania informacje, które klient wprowadził podczas realizacji transakcji (na przykład adres wysyłki, opcje dostawy, informacje o karcie upominkowej i informacje o lojalności) będą zachowane. Aby można było włączyć łącznik Ayden, łącznik płatności musi być skonfigurowany dla SCA w module Commerce Headquarter. Aby uzyskać więcej informacji, zajrzyj do [silnych uwierzytelnień klientów przy użyciu Adyen](adyen_redirect.md). Ta funkcja została włączona w wersji Commerce 10.0.12.

> [!NOTE]
> W przypadku łącznika płatności Adyen moduł iframe w module płatności można renderować tylko wtedy, gdy zostanie dodany adres URL Adyen do listy dozwolonych w witrynie. Aby wykonać ten krok, dodaj **\*adyen.com** do **child-src**, **connect-src**, **img-src**, **script-src** i **style-src** dyrektyw zasad bezpieczeństwa witryny. Aby uzyskać więcej informacji, zajrzyj do [Zarządzanie zasadami zabezpieczeń zawartości](manage-csp.md). 

Poniższa ilustracja przedstawia przykład karty upominkowej, modułów lojalnościowych i płatności Ayden na stronie kasy.

![Przykład karty podarunkowej, punktów lojalnościowych i płatności Ayden na stronie realizacji transakcji.](./media/ecommerce-payments.PNG)

## <a name="dynamics-365-payment-connector-for-paypal"></a>Dynamics 365 Payment Connector dla PayPal

Od wersji Commerce 10.0.14 moduł płatności jest również zintegrowany z Dynamics 365 Payment Connector dla PayPal. Aby uzyskać więcej informacji na temat konfigurowania i konfigurowania łącznika płatności, zobacz temat [Łącznik płatności usługi Dynamics 365 dla PayPal](paypal.md).
 
Na stronie kasy możesz skonfigurować łączniki Adyen i PayPal. Moduł płatności został wzbogacony o dodatkowe właściwości, które pomagają określić, z którym złączem powinien współpracować. Aby uzyskać szczegółowe informacje, zajrzyj do **Obsługiwane typy płatności** oraz właściwości modułu **Jest płatnością podstawową** w poniższej tabeli.
  
Jeśli moduł płatności jest skonfigurowany do używania łącznika płatności PayPal, na stronie realizacja transakcji zostanie wyświetlony przycisk PayPal. Po wywołaniu przez klienta moduł płatności renderuje ramkę iframe zawierającą informacje PayPal. Klient może się zalogować i podać swoje dane PayPal w tym ramce iframe, aby zakończyć transakcję. Gdy klient zdecyduje się zapłacić w systemie PayPal, pozostałe saldo zamówienia zostanie pobrane za pośrednictwem systemu PayPal.

Złącze płatności PayPal nie wymaga modułu adresu rozliczeniowego, ponieważ wszystkie informacje związane z rozliczeniami są obsługiwane przez PayPal w ramach jego elementu iframe. Wymagany jest jednak adres wysyłkowy i moduły opcji dostawy.

Na poniższej ilustracji przedstawiono przykład dwóch modułów płatności na stronie realizacji zamówienia, jeden został skonfigurowany za pomocą łącznika płatności Adyen, a drugi za pomocą łącznika płatności PayPal.
![Przykład modułów płatności Adyen i PayPal na stronie realizacji transakcji.](./media/ecommerce-paypal.png)

Poniższa ilustracja przedstawia przykład elementu iframe PayPal wywołanego za pomocą przycisku PayPal. 
![Przykład iframe Paypal na stronie realizacji transakcji.](./media/ecommerce-paypal-iframe.png)

## <a name="payment-module-properties"></a>Właściwości modułu płatności

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Nagłówek | Tekst nagłówka | Opcjonalny nagłówek modułu płatności. |
| Wysokość ramki iframe | Piksele | Wysokość ramki iframe (w pikselach). W razie potrzeby można regulować wysokość. |
| Pokaż adres do faktury | **Prawda** lub **Fałsz** | Jeśli dla tej właściwości ustawiono wartość **Prawda**, adres bilingowy będzie obsługiwany przez Adyen w module iframe modułu płatności. Jeśli zostanie ustawiona wartość **Fałsz**, adres bilingowy nie będzie obsługiwany przez Adyen, a użytkownik Commerce musi skonfigurować moduł w celu wyświetlenia adresu na fakturze na stronie realizacja zamówienia. W przypadku łącznika płatności PayPal to pole nie ma wpływu, ponieważ adres rozliczeniowy jest w pełni obsługiwany w systemie PayPal. |
| Zastąpienie stylu płatności | Kod arkuszy stylów kaskadowych (CSS) | Ponieważ moduł płatności jest obsługiwany w iframe, istnieje ograniczona możliwość tworzenia stylów. Aby uzyskać więcej stylów, należy użyć tej właściwości. Aby zastąpić style witryny, musisz wkleić kod CSS jako wartość tej właściwości. Zastąpienia i style konstruktora witryn CSS nie mają zastosowania do tego modułu. |
|Obsługiwane typy metod płatności| Ciąg| Jeśli skonfigurowano wiele łączników płatności, należy podać ciąg obsługiwanego typu oferty zgodnie z definicją w konfiguracji łącznika płatności w siedzibie firmy Commerce (patrz poniższy obraz). Jeśli pole jest puste, domyślnie jest używany łącznik płatności Adyen. Dodane do modułu Commerce Release 10.0.14.|
|Jest płatnością główną|  **Prawda** lub **Fałsz** | Jeśli **Prawda**, wszelkie komunikaty o błędach będą generowane na podstawie podstawowego łącznika płatności na stronie realizacja transakcji. Jeśli są skonfigurowane zarówno Adyen, jak i łączniki płatności PayPal, należy określić wartość **Prawda** dla Adyen , która została dodana do modułu Commerce w wydaniu 10.0.14.|
|Użyj identyfikatora łącznika| **Prawda** lub **Fałsz** | Użyj tej właściwości, jeśli dla witryny skonfigurowano wiele łączników płatności. Jeśli **wartość True**, łączniki muszą używać identyfikatora łącznika dla korelacji płatności.|
|Użyj kodu języka zestawu przeglądarki dla iFrame|  **Prawda** lub **Fałsz** | (Tylko dla Adyen) Jeśli **True**, ramka Adyen iFrame będzie renderować język na podstawie kontekstu przeglądarki użytkownika witryny, zamiast używać kodu języka kanału Commerce skonfigurowanego dla witryny. Dodane do modułu Commerce Release 10.0.27.|

Na poniższej ilustracji pokazano przykład wartości **Obsługiwane typy płatności** ustawionej na „PayPal” w konfiguracji łącznika płatności w centrali Commerce.
![Przykład obsługiwanych typów metod płatności w centrali Commerce.](./media/ecommerce-paymenttendertypes.png)

## <a name="billing-address"></a>Adres na fakturze

Moduł adresu rozliczeniowego może zostać użyty na stronie kasy, jeśli wiersze adresu rozliczeniowego złącza płatności Adyen nie pasują wystarczająco do wyglądu reszty witryny. 

Aby użyć modułu adresu rozliczeniowego na stronie kasy, gdy moduł płatności jest zintegrowany ze złączem płatności Adyen, ustaw właściwość **Pokaż adres rozliczeniowy** na **Fałsz**, aby można było użyć dedykowanego modułu adresu rozliczeniowego zamiast domyślnego adresu rozliczeniowego Adyen. W takim przypadku autor strony powinien dołączyć moduł adresu rozliczeniowego na stronie kasy. Złącze płatności Adyen umożliwia również użycie adresu wysyłki jako adresu rozliczeniowego, aby zminimalizować liczbę kroków dla użytkownika witryny.

Podobnie jak moduły płatności, właściwość **Obsługiwane typy płatności** została dodana do modułu adres rozliczeniowy w wydaniu Commerce 10.0.14. Wartość tej właściwości powinna być identyczna z wartością podaną w module płatności, aby zapewnić ich współdziałanie. W przypadku złącza płatności Adyen zarówno moduł płatności, jak i moduł adresu rozliczeniowego powinny pozostawić tę wartość pustą (stan domyślny). W przypadku łącznika usługi PayPal nie jest wymagany dedykowany moduł adresu rozliczeniowego. W przypadku innych typów łączników płatności ciąg należy podać zgodnie z konfiguracją w centrali Commerce.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Dodaj moduł płatności do strony kasy i ustaw wymagane właściwości

Moduł płatności można dodać tylko do modułu realizacji transakcji. Aby uzyskać więcej informacji na temat konfigurowania modułu płatności dla strony kasy, zapoznaj się z tematem [Moduł realizacji transakcji](add-checkout-module.md).

## <a name="configure-the-adyen-and-paypal-payment-connectors-when-both-are-used"></a>Skonfiguruj łączniki płatności Adyen i PayPal, jeśli oba są używane

Jeśli oba łączniki płatności (Adyen i PayPal) będą używane w twojej witrynie, wykonaj poniższe kroki w kreatorze witryn Commerce, aby dodać moduły płatności dla każdego łącznika do modułu kasy, a następnie skonfigurować właściwości każdego modułu.

1. W panelu właściwości modułu płatności PayPal wykonaj poniższe kroki:

    1. W polu właściwości **Obsługiwane typy płatności** wprowadź wartość **PayPal**.
    1. Wyczyść pole wyboru dla właściwości **Płatność główna**.
    1. Zaznacz pole wyboru właściwości **Użyj identyfikatora łącznika**.

1. W panelu właściwości modułu płatności Adyen wykonaj poniższe kroki:

    1. W polu właściwości **Obsługiwane typy płatności** pozostaw pustą wartość.
    1. Zaznacz pole wyboru dla właściwości **Płatność główna**.
    1. Zaznacz pole wyboru właściwości **Użyj identyfikatora łącznika**.

> [!NOTE]
> Kiedy konfigurujesz łączniki Adyen i PayPal do wspólnego użytku, konfiguracja **Łącznika płatności Dynamics 365 dla Adyen** musi znajdować się na pierwszej pozycji w konfiguracji **Konta płatności** łączniki kanału online w centrali Commerce. Aby potwierdzić lub zmienić kolejność łącznika, przejdź do **Sklepy internetowe** i wybierz kanał dla swojej witryny. Następnie w zakładce **Ustawienia**, na skróconej karcie **Konta płatnicze**, pod **Łącznik** upewnij się, że konfiguracja **Łącznika płatności Dynamics 365 dla Adyen** znajduje się na pierwszej pozycji (czyli w górnej linii), a konfiguracja **Łącznika płatności Dynamics 365 dla PayPal** drugiej linii. W razie potrzeby dodaj lub usuń łączniki, aby zmienić kolejność.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł koszyka](add-cart-module.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł adresu wysyłki](ship-address-module.md)

[Moduł opcji dostawy](delivery-options-module.md)

[Moduł informacji o odbiorze](pickup-info-module.md)

[Moduł szczegółów zamówienia](order-confirmation-module.md)

[Moduł karty upominkowej](add-giftcard.md)

[Łącznik płatności usługi Dynamics 365 dla Adyen](dev-itpro/adyen-connector.md)

[Dynamics 365 Payment Connector dla PayPal](paypal.md)

[Silne uwierzytelnianie klienta za pomocą Adyen](adyen_redirect.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
