---
title: Moduł informacji o odbiorze
description: W tym temacie omówiono moduł informacji o odbiorze i opisano, jak dodać go do stron realizacji transakcji w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 61b97d72b6a397737c10476cd6c02764e60f10b1
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665355"
---
# <a name="pickup-information-module"></a>Moduł informacji o odbiorze

[!include [banner](includes/banner.md)]

W tym temacie omówiono moduł informacji o odbiorze i opisano, jak dodać go do stron realizacji transakcji w Microsoft Dynamics 365 Commerce.

Moduł informacji o odbiorze może być używany w module realizacji transakcji do wyświetlania informacji o odbiorze zamówienia. Klienci mogą przeglądać dostępne daty odbioru i przedziały czasowe, a następnie wybrać odpowiedni czas na odebranie zamówienia. Na przykład klient może odebrać zamówienie o godzinie 15:00 21 marca ze sklepu w San Francisco.

Przedziały czasowe odbioru dla odpowiednich sklepów muszą być skonfigurowane w centrali Commerce. Aby uzyskać więcej informacji, zobacz [Tworzenie i aktualizowanie przedziałów czasu na potrzeby odbiorów przez odbiorcę](dev-itpro/pickup-timeslots.md).

Jeśli moduł informacji o odbiorze jest utworzony na stronie kasy, ale dla sklepu wybranego do odbioru nie zdefiniowano żadnych przedziałów czasowych, moduł wyświetli informacje, ale użytkownik nie będzie mógł wybrać żadnych przedziałów czasowych. Przedziały czasu są opcjonalne i nie są wymagane do złożenia zamówienia.

Jeśli do odbioru w wielu sklepach wybrano wiele pozycji, moduł informacji o odbiorze pozwoli użytkownikowi wybrać przedział czasowy dla każdego sklepu, pod warunkiem, że dostępne są dla niego przedziały czasowe.

> [!NOTE]
> Obsługa przedziałów czasu i modułu informacji o odbiorze zamówienia jest dostępna w Dynamics 365 Commerce w wersji 10.0.15 lub nowszej.

Poniższa ilustracja przedstawia przykład wyboru przedziału czasu za pośrednictwem modułu informacji o odbiorze, znajdującego się na stronie realizacja transakcji.

![Przykład modułu informacji o odbiorze na stronie realizacja zamówienia](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a>Właściwości modułu

- **Nagłówek** – Wprowadź nagłówek modułu.

## <a name="show-time-slot-information-after-an-order-is-placed"></a>Pokaż informacje o przedziale czasowym po złożeniu zamówienia

Po umieszczeniu zamówienia informacje o wybranym przedziale czasu można przejrzeć w [module potwierdzenia zamówienia](order-confirmation-module.md) oraz w [module szczegóły zamówienia](account-management.md#order-details-page). Oba moduły mają właściwość **Pokaż informacje o przedziale czasu**. Aby można było wyświetlić wybrany przedział czasu w procesie przetwarzania, ta właściwość musi mieć ustawioną wartość **Prawda**.

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a>Dodaj do strony moduł informacji o odbiorze kasy

Aby uzyskać instrukcje dotyczące dodawania modułu informacji o odbiorze do strony kasy i ustawiania wymaganych właściwości, należy zapoznać się z [Moduł realizacji transakcji](add-checkout-module.md).

Na poniższej ilustracji przedstawiono przykład strony płatności handlu elektronicznego, która zawiera przedziały czasowe dla elementów zamówienia odbioru.

![Przykład strony płatności handlu elektronicznego, która zawiera przedziały czasowe dla elementów zamówienia odbioru](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie i aktualizowanie przedziałów czasu na potrzeby odbiorów przez odbiorcę](dev-itpro/pickup-timeslots.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł szczegółów zamówienia](account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]