---
title: Funkcje sprzedaży przez biuro obsługi
description: Ten temat zawiera omówienie funkcji sprzedaży przez biuro obsługi w Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2e44770af4a30f539e56d38b21c897cacd2707e7
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812346"
---
# <a name="call-center-sales-functionality"></a>Funkcje sprzedaży przez biuro obsługi

[!include [banner](includes/banner.md)]


W programie Dynamics 365 Retail biuro obsługi jest typem kanału sprzedaży detalicznej, który można zdefiniować w aplikacji. Zdefiniowanie określonego kanału dla jednostek biura obsługi umożliwi systemowi łączenie określonych domyślnych wartości danych i domyślnych ustawień przetwarzania zamówień z zamówieniami sprzedaży tworzonymi przez użytkownika w kanale biura obsługi.

Funkcje biura obsługi obejmują zaawansowane konfigurowanie cen detalicznych i promocji, katalogi, karty upominkowe, programy lojalnościowe i kupony. Zamówienia z biura obsługi są również wykorzystywane przez aplikację punktu sprzedaży (POS) do obsługi scenariuszy realizacji zamówień między kanałami.

Należy pamiętać, że o ile moduł biura obsługi może być wykorzystywany przez inne branże poza handlem detalicznym, obecna wersja funkcjonalności biura obsługi w aplikacji Retail nie została zoptymalizowana do używania w scenariuszach przetwarzania zamówień między firmami (B2B) ani w scenariuszach, gdzie zamówienia mają dużo wierszy sprzedaży. Zalecamy, aby użytkownicy, którzy chcą wykorzystywać funkcje biura obsługi do przetwarzania zamówień poza typowymi scenariuszami przetwarzania transakcji zawieranych bezpośrednio z klientami, poświęcili czas na adekwatne przetestowanie tych funkcji i sprawdzenie, czy spełniają one wymagania funkcjonalne i wydajnościowe.

Moduł biura obsługi nie tylko pozwala tworzyć zamówienia, ale również oferuje przyjazną dla użytkownika aplikację obsługi klienta, która ułatwia znajdowanie kont odbiorców oraz przeglądanie wszystkich powiązanych danych i atrybutów zamówień odbiorców. Na ekranie obsługi klienta użytkownik może szybko przejść do danych powiązanych z zamówieniem, które pozwolą mu odpowiedzieć na pytania, jakie w sprawie zamówień najczęściej zadają odbiorcy.

Ta strona zawiera łącza do odnośnej dokumentacji związanej z instalacją, konfiguracją i merytorycznym użytkowaniem funkcji biura obsługi w usłudze Retail.


## <a name="configure-the-call-center"></a>Konfigurowanie biura obsługi

[Konfigurowanie kanałów biura obsługi](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a>Konfigurowanie przetwarzania zamówień

[Konfigurowanie i praca z alertami o oszustwach w biurze obsługi](set-up-fraud-alerts.md)

[Konfigurowanie i używanie wstrzymań zamówień w biurze obsługi](work-with-order-holds.md)

## <a name="configure-payment-processing"></a>Konfigurowanie przetwarzania płatności

[Metody płatności w biurach obsługi](work-with-payments.md)

## <a name="configure-delivery-modes"></a>Konfigurowanie metod dostawy

[Konfigurowanie metod dostawy i opłat w biurze obsługi](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a>Konfigurowanie marketingu bezpośredniego

[Katalogi biura obsługi](call-center-catalogs.md)

[Konfigurowanie analizy RFM (wg daty ostatniego zakupu, częstotliwości i wartości pieniężnej)](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a>Konfigurowanie programów sprzedaży ciągłej

[Konfigurowanie programów sprzedaży ciągłej dla biur obsługi](set-up-continuity-program.md)
