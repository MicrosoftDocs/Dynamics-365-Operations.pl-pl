---
title: Omówienie portalu klienta dla Dynamics 365 Supply Chain Management
description: Ten temat zawiera informacje dotyczące portalu klienta oraz wyjaśnienie, kto powinien go używać oraz jak działa.
author: dasani-madipalli
manager: tfehr
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 86d9a40d991e915d3529e0c330f7559d8e7ce9ea
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529585"
---
# <a name="customer-portal-for-dynamics-365-supply-chain-management-overview"></a>Omówienie portalu klienta dla Dynamics 365 Supply Chain Management

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="what-is-the-customer-portal"></a>Co to jest portal klienta?

Nowoczesne systemy łańcuchów dostaw są oparte na integracji. Wymagają, aby działy zapasów, zapotrzebowania klientów i sprzedaży były zintegrowane zamiast przebywać w osobnych silosach. Portal klienta pomaga organizacjom, którzy działają na Microsoft Dynamics 365 Supply Chain Management ulepszyć tę integrację i skutecznie informować swoich klientów.

Portal odbiorców to szablon [portali Power Apps](https://docs.microsoft.com/powerapps/maker/portals/overview), który pozwala firmom tworzyć zewnętrznie firmy (B2B, Business-to-Business) dla scenariuszy związanych z przetwarzaniem zamówień sprzedaży. W szablonie jest używana funkcja [podwójnego zapisywania](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page), Supply Chain Management i portale Power Apps, które umożliwiają klientom zewnętrznym przedsiębiorstw wyświetlanie i tworzenie danych z środowiska Dynamics 365 firmy.

Szablon Portal odbiorcy zawiera wszystkie możliwości dostosowywania oferowane przez funkcję portali ofert Power Apps. Szablon można łatwo zmodyfikować w celu przedstawienia marki firmy, zwiększenia funkcjonalności i zmiany środowiska użytkownika. Wszystkie funkcje tego szablonu mogą być modyfikowane w wybranym polu.

> [!IMPORTANT]
> Nie oczekuje się, że szablon jest w pełni funkcjonalny. Służy ono tylko jako włącznik dla klientów, którzy chcą utworzyć zewnętrznie dołączający się serwis www, aby klienci przedsiębiorstwa mogli współpracować z danymi powiązanymi z Supply Chain Management.

> [!NOTE]
> Dokumentacja portalu klienta jest skierowana do administratorów, konfiguratorów i integratorów systemów, którzy skonfigurują portal klienta dla instalacji Supply Chain Management. Używa terminów _klient_ i _użytkownik_, aby opisać osoby, które są klientami organizacji, która Supply Chain Management i która będzie korzystać z samego ostatecznego portalu.

## <a name="video"></a>Wideo

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ylwW]

Plik wideo [Omówienie szablonu Portalu klienta w Dynamics 365 Supply Chain Management](https://youtu.be/nPrqoLuHfV8) (pokazany powyżej) znajduje się na [liście odtwarzania Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na platformie YouTube.

## <a name="who-should-use-it"></a>Kto powinien go używać?

Portal klientów jest przeznaczony dla firm korzystających z Supply Chain Management i mający następujące cechy:

- Chcą zbudować zewnętrzną stronę internetową, która przekazuje informacje o przetwarzaniu zamówień (takie jak status zamówienia lub informacje o koncie) bezpośrednio z Supply Chain Management do klientów korporacyjnych.
- Są one przenoszone z Dynamics AX 2012 do Supply Chain Management i poprzednio korzystały z [samoobsługowego portalu dla odbiorców AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/about-the-customer-self-service-portal).

Następujące typy organizacji **nie są** dobrym kandydatami do implementacji portalu klienta:

- Firmy, które chcą zbudować witrynę sieci Web dla odbiorców nienależących do przedsiębiorstwa. Firmy te powinny rozważyć utworzenie [witryny sieci Web e-commerce Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/create-ecommerce-site).
- Firmy, które używają już istniejących portali Power Apps w podobnym celu. Firmy te nie będą otrzymywały żadnych dodatkowych korzyści z portalu klienta. Portal odbiorców jest dostarczany jako szablon pełniący rolę przewodnika i punkt wyjścia dla odbiorców, którzy chcą „przyłączyć kropki” między dwoma odczytami, Supply Chain Management i portalami Power Apps. Jeśli została już skonfigurowana witryna sieci Web, która służy do tego celu, nie można uzyskać większej ilości wartości z szablonu portalu klienta w celu ponownego zainicjowania obsługi administracyjnej tej witryny sieci Web.

## <a name="how-does-it-work"></a>Jak to działa?

Portal odbiorców jest dostarczany jako szablon portali Power Apps. Zależy to od portali Power Apps i podwójnego zapisywania.

[Portale Power Apps](https://docs.microsoft.com/powerapps/maker/portals/overview) to funkcja umożliwiająca użytkownikom tworzenie zewnętrznej witryny sieci Web, do której mogą się logować osoby spoza organizacji. Do tworzenia portali nie jest wymagane kodowanie. Portal klienta to jeden z wielu [szablonów portalu Dynamics 365](https://docs.microsoft.com/powerapps/maker/portals/portal-templates#environment-with-model-driven-apps-in-dynamics-365) dostępnych w firmie Microsoft.

[Podwójny zapis](https://docs.microsoft.com/powerapps/maker/portals/overview) to gotowa infrastruktura umożliwiająca współpracę w czasie rzeczywistym między aplikacjami opartymi na modelach Dynamics 365 i aplikacjami Finance and Operations. Podwójny zapis toi dwukierunkowa integracja między aplikacjami Finance and Operations i Common Data Service. Tym samym umożliwia korzystanie ze zintegrowanego środowiska użytkownika w aplikacjach. Portal klienta jest zależny od jednostek synchronizowanych z podwójnym zapisywaniem. Zanim dane z modułu Supply Chain Management mogą być nadawane w portalu klienta, dla wszystkich odpowiednich jednostek musi być włączona funkcja podwójnego zapisywania.

![Zależności portalu klienta](media/customer-portal-elements.png "Zależności portalu klienta")

Portal odbiorcy działa jako punkt wyjścia dla organizacji, które chcą używać portali Power Apps, aby zbudować zewnętrznie dochodzącą witrynę sieci Web, która korzysta z danych z własnej instalacji Supply Chain Management. Pomaga organizacjom łączyć dwa zapisy, Supply Chain Management i portale Power Apps.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]