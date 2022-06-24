---
title: Przetwarzanie niepołączonych zwrotów z łącznikiem Dynamics 365 Commerce Payment Connector dla Adyen
description: W tym artykule opisano, jak działają niepołączone zwroty w przypadku korzystania z łącznika Microsoft Dynamics 365 Payment Connector dla Adyen.
author: BrianShook
ms.date: 10/07/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 634b30de7adbfb0c316fe14456581ea8eb89d070
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885204"
---
# <a name="process-unlinked-refunds-with-the-dynamics-365-commerce-payment-connector-for-adyen"></a>Przetwarzanie niepołączonych zwrotów z łącznikiem Dynamics 365 Commerce Payment Connector dla Adyen

[!include [banner](../includes/banner.md)]

W tym artykule opisano, jak działają niepołączone zwroty w przypadku korzystania z łącznika [Microsoft Dynamics 365 Payment Connector dla Adyen](adyen-connector.md). Przegląda również możliwość przetwarzania zwrotu na nową formę płatności w punkcie sprzedaży (POS) lub biurze obsługi.

Łącznik Dynamics 365 Payment Connector dla Adyen obsługuje możliwość przetwarzania zwrotów przy użyciu innej formy płatności, niż ta użyta w oryginalnej transakcji. Mimo że zalecane jest korzystanie z [połączonych zwrotów](linked-refunds.md) w celu przetwarzania zwrotu na podstawie dostarczonej pierwszej formy płatności, w niektórych scenariuszach wymagane są zwroty do innych form. Na przykład karta użyta do oryginalnej płatności może utracić ważność lub zostać zgubiona bądź anulowana przez użytkownika.

## <a name="prerequisites"></a>Wymagania wstępne

Następujące warunki wstępne muszą zostać spełnione, aby łącznik Dynamics 365 Payment Connector dla Adyen mógł przetwarzać niepołączone zwroty:

- Konfigurowanie [form płatności](../payment-methods.md).
- Konfigurowanie [płatności wielokanałowych](../omni-channel-payments.md).

## <a name="additional-configuration"></a>Dodatkowa konfiguracja

Łącznik Dynamics 365 Payment Connector dla Adyen stanowi gotową do użycia implementacją dla każdego obsługiwanego scenariusza zwrotu opisanego w następnej sekcji. Użytkownicy, którzy nie korzystają z gotowej implementacji łącznika Dynamics 365 Payment Connector dla Adyen, muszą skonfigurować łącznik, który obsługuje tokenizację kart kredytowych.

## <a name="supported-refund-scenarios"></a>Obsługiwane scenariusze zwrotów

Usługa Dynamics 365 Commerce obsługuje zwroty poprzednio zatwierdzonych i potwierdzonych transakcji. Zwroty mogą obejmować zarówno pełny zwrot, jak i częściowy zwrot transakcji. Zwroty nie mogą przekraczać pełnej kwoty oryginalnej autoryzacji płatności. Niepołączone zwroty są obsługiwane tylko w punkcie sprzedaży i biurze obsługi.

## <a name="enable-unlinked-refunds-functionality"></a>Włącz funkcję niepołączonych zwrotów

Aby włączyć funkcję niepołączonych zwrotów w centrali Commerce Headquarters, wykonaj następujące kroki.

1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Wspólne parametry handlu**.
1. Na karcie **Płatności wielokanałowe** zmień ustawienie opcji **Użyj płatności wielokanałowych** na **Tak**.

### <a name="supported-payment-method-variants"></a>Obsługiwane warianty formy płatności

Następujące warianty form płatności obsługują niepołączone zwroty:

- Karty
- Portfel

Nie wszystkie warianty form płatności obsługują niepołączone zwroty. W poniższej tabeli przedstawiono listę wspólnych form płatności i pokazano możliwości obsługi poszczególnych form dla połączonych i niepołączonych zwrotów.

| Metoda płatności        | Połączony zwrot | Niepołączony zwrot |
|-----------------------|:-------------:|:---------------:|
| amexcommercial        | Tak           | Tak             |
| amexconsumer          | Tak           | Tak             |
| amexcorporate         | Tak           | Tak             |
| amexdebit             | Tak           | Tak             |
| amexprepaid           | Tak           | Tak             |
| amexprepaidreloadable | Tak           | Tak             |
| amexsmallbusiness     | Tak           | Tak             |
| discover              | Tak           | Tak             |
| maestro               | Tak           | Tak             |
| maestrouk             | Tak           | Tak             |
| mc                    | Tak           | Tak             |
| mcalphabankbonus      | Tak           | Tak             |
| mcprepaidanonymous    | Tak           | Tak             |
| visa                  | Tak           | Tak             |
| visaalphabankbonus    | Tak           | Tak             |
| visacheckout          | Tak           | Tak             |
| visadankort           | Tak           | Tak             |
| visahipotecario       | Tak           | Tak             |
| visasaraivacard       | Tak           | Tak             |
| vpay                  | Tak           | Tak             |
| givex                 | **Nie**        | Tak             |
| svs                   | **Nie**        | Tak             |
| cup                   | Tak           | Tak             |
| diners                | Tak           | Tak             |
| interac               | **Nie**        | Tak             |
| jcb                   | Tak           | Tak             |
| jcb_applepay          | Tak           | Tak             |
| unionpay              | Tak           | Tak             |

### <a name="process-an-unlinked-refund-in-pos"></a>Przetwarzanie niepołączonego zwrotu w punkcie sprzedaży

Klient zwraca towar do kasjera punktu sprzedaży w ramach dozwolonego okresu zwrotów i ma prawidłowy dowód zakupu. Podczas przetwarzania zwrotu okno dialogowe **Płatność zwrotu** zawiera opcję **Wybierz formę płatności**. Kasjer może następnie wybrać formę płatności spośród obsługiwanych form płatności dla zwrotów (karty i portfel).

### <a name="process-an-unlinked-refund-in-call-center"></a>Przetwarzanie niepołączonego zwrotu w biurze obsługi

Gdy niepołączony zwrot jest przetwarzany względem zamówienia w biurze obsługi, pracownik etatowy biura obsługi wybiera formę płatności, która różni się od oryginalnej. Pracownik etatowy będzie następnie monitowany o uzyskanie osobistego numeru identyfikacyjnego (PIN) zastąpienia administratora. Numer PIN jest wymagany, aby można było przetworzyć inną formę płatności dla zwrotu.

#### <a name="set-up-an-administrator-override-pin-for-call-center"></a>Konfigurowanie numeru PIN zastąpienia administratora dla biura obsługi

Aby skonfigurować numer PIN zastąpienia administratora dla biura obsługi w usłudze Commerce Headquarters, należy wykonać następujące kroki.

1. Przejdź do ustawień **Retail i Commerce \> Konfiguracja kanału \> Konfiguracja biura obsługi** lub wyszukaj „Uprawnienia zastąpienia”.
1. Wybierz rolę, której chcesz udzielić uprawnienia do przetwarzania niepołączonego zwrotu.
1. Na skróconej karcie **Zwroty**, w opcji **Zezwalaj na alternatywną płatność** ustaw wartość **Tak**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dynamics 365 Payment Connector dla Adyen](adyen-connector.md)

[Połączone zwroty poprzednio zatwierdzonych i potwierdzonych transakcji](linked-refunds.md)
