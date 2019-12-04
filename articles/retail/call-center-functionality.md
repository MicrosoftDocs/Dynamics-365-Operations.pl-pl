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
# <a name="call-center-sales-functionality"></a><span data-ttu-id="66170-103">Funkcje sprzedaży przez biuro obsługi</span><span class="sxs-lookup"><span data-stu-id="66170-103">Call center sales functionality</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="66170-104">W programie Dynamics 365 Retail biuro obsługi jest typem kanału sprzedaży detalicznej, który można zdefiniować w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="66170-104">In Dynamics 365 Retail, a call center is a type of Retail channel that can be defined in the application.</span></span> <span data-ttu-id="66170-105">Zdefiniowanie określonego kanału dla jednostek biura obsługi umożliwi systemowi łączenie określonych domyślnych wartości danych i domyślnych ustawień przetwarzania zamówień z zamówieniami sprzedaży tworzonymi przez użytkownika w kanale biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="66170-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="66170-106">Funkcje biura obsługi obejmują zaawansowane konfigurowanie cen detalicznych i promocji, katalogi, karty upominkowe, programy lojalnościowe i kupony.</span><span class="sxs-lookup"><span data-stu-id="66170-106">Call center features include advanced retail price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="66170-107">Zamówienia z biura obsługi są również wykorzystywane przez aplikację punktu sprzedaży (POS) do obsługi scenariuszy realizacji zamówień między kanałami.</span><span class="sxs-lookup"><span data-stu-id="66170-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="66170-108">Należy pamiętać, że o ile moduł biura obsługi może być wykorzystywany przez inne branże poza handlem detalicznym, obecna wersja funkcjonalności biura obsługi w aplikacji Retail nie została zoptymalizowana do używania w scenariuszach przetwarzania zamówień między firmami (B2B) ani w scenariuszach, gdzie zamówienia mają dużo wierszy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="66170-108">It's important to note that while the call center module can be utilized by other industries outside of Retail, the current release of the Retail call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large amount of sales lines.</span></span> <span data-ttu-id="66170-109">Zalecamy, aby użytkownicy, którzy chcą wykorzystywać funkcje biura obsługi do przetwarzania zamówień poza typowymi scenariuszami przetwarzania transakcji zawieranych bezpośrednio z klientami, poświęcili czas na adekwatne przetestowanie tych funkcji i sprawdzenie, czy spełniają one wymagania funkcjonalne i wydajnościowe.</span><span class="sxs-lookup"><span data-stu-id="66170-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="66170-110">Moduł biura obsługi nie tylko pozwala tworzyć zamówienia, ale również oferuje przyjazną dla użytkownika aplikację obsługi klienta, która ułatwia znajdowanie kont odbiorców oraz przeglądanie wszystkich powiązanych danych i atrybutów zamówień odbiorców.</span><span class="sxs-lookup"><span data-stu-id="66170-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="66170-111">Na ekranie obsługi klienta użytkownik może szybko przejść do danych powiązanych z zamówieniem, które pozwolą mu odpowiedzieć na pytania, jakie w sprawie zamówień najczęściej zadają odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="66170-111">The customer service screen is designed to enable a user to quickly access order related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="66170-112">Ta strona zawiera łącza do odnośnej dokumentacji związanej z instalacją, konfiguracją i merytorycznym użytkowaniem funkcji biura obsługi w usłudze Retail.</span><span class="sxs-lookup"><span data-stu-id="66170-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features in Retail.</span></span>


## <a name="configure-the-call-center"></a><span data-ttu-id="66170-113">Konfigurowanie biura obsługi</span><span class="sxs-lookup"><span data-stu-id="66170-113">Configure the call center</span></span>

[<span data-ttu-id="66170-114">Konfigurowanie kanałów biura obsługi</span><span class="sxs-lookup"><span data-stu-id="66170-114">Set up call center channels</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="66170-115">Konfigurowanie przetwarzania zamówień</span><span class="sxs-lookup"><span data-stu-id="66170-115">Configure order processing</span></span>

[<span data-ttu-id="66170-116">Konfigurowanie i praca z alertami o oszustwach w biurze obsługi</span><span class="sxs-lookup"><span data-stu-id="66170-116">Set up and work with call center fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="66170-117">Konfigurowanie i używanie wstrzymań zamówień w biurze obsługi</span><span class="sxs-lookup"><span data-stu-id="66170-117">Configure and work with call center order holds</span></span>](work-with-order-holds.md)

## <a name="configure-payment-processing"></a><span data-ttu-id="66170-118">Konfigurowanie przetwarzania płatności</span><span class="sxs-lookup"><span data-stu-id="66170-118">Configure payment processing</span></span>

[<span data-ttu-id="66170-119">Metody płatności w biurach obsługi</span><span class="sxs-lookup"><span data-stu-id="66170-119">Payment methods in call centers</span></span>](work-with-payments.md)

## <a name="configure-delivery-modes"></a><span data-ttu-id="66170-120">Konfigurowanie metod dostawy</span><span class="sxs-lookup"><span data-stu-id="66170-120">Configure delivery modes</span></span>

[<span data-ttu-id="66170-121">Konfigurowanie metod dostawy i opłat w biurze obsługi</span><span class="sxs-lookup"><span data-stu-id="66170-121">Configure call center delivery modes and charges</span></span>](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="66170-122">Konfigurowanie marketingu bezpośredniego</span><span class="sxs-lookup"><span data-stu-id="66170-122">Configure direct marketing</span></span>

[<span data-ttu-id="66170-123">Katalogi biura obsługi</span><span class="sxs-lookup"><span data-stu-id="66170-123">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="66170-124">Konfigurowanie analizy RFM (wg daty ostatniego zakupu, częstotliwości i wartości pieniężnej)</span><span class="sxs-lookup"><span data-stu-id="66170-124">Set up Recency, Frequency, and Monetary (RFM) analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="66170-125">Konfigurowanie programów sprzedaży ciągłej</span><span class="sxs-lookup"><span data-stu-id="66170-125">Configure continuity programs</span></span>

[<span data-ttu-id="66170-126">Konfigurowanie programów sprzedaży ciągłej dla biur obsługi</span><span class="sxs-lookup"><span data-stu-id="66170-126">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
