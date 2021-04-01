---
title: Przegląd procesu subskrypcji
description: Ten temat zawiera omówienie przepływu pracy subskrypcji.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 05111ab53e8bf19bb25869155284cdc9d6ea3b2a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5242284"
---
# <a name="subscription-workflow-overview"></a><span data-ttu-id="ec651-103">Przegląd procesu subskrypcji</span><span class="sxs-lookup"><span data-stu-id="ec651-103">Subscription workflow overview</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ec651-104">Pracujesz jako administrator subskrypcji w firmie, która oferuje abonament na konserwację osprzętu oświetleniowego.</span><span class="sxs-lookup"><span data-stu-id="ec651-104">You are the subscriptions administrator for a light company that offers subscriptions for lighting rig maintenance.</span></span> <span data-ttu-id="ec651-105">Klient skontaktował się w sprawie zakupu rocznej subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="ec651-105">A customer contacts your company to purchase a yearly subscription for lighting rig maintenance.</span></span>

## <a name="setting-up-subscriptions"></a><span data-ttu-id="ec651-106">Konfigurowanie subskrypcji</span><span class="sxs-lookup"><span data-stu-id="ec651-106">Setting up subscriptions</span></span>

<span data-ttu-id="ec651-107">Aby skonfigurować subskrypcję, należy najpierw utworzyć grupę subskrypcji dla nowej umowy serwisowej, o ile taka grupa subskrypcji jeszcze nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="ec651-107">To set up a subscription, you must first create a subscription group for the new service agreement or verify that a subscription group exists.</span></span> <span data-ttu-id="ec651-108">Jeśli grupa już istnieje, to musi zostać tak skonfigurowana, aby klient był rozliczany przez rok i aby przychody z tytułu sprzedaży były naliczane dla każdego miesiąca w roku.</span><span class="sxs-lookup"><span data-stu-id="ec651-108">If a subscription group exists, you must set it up to invoice the customer yearly and to accrue sales revenue every month of the year.</span></span> <span data-ttu-id="ec651-109">Aby uzyskać więcej informacji o ustawianiu subskrypcji, zobacz [Konfigurowanie grup subskrypcji](set-up-subscription-groups.md).</span><span class="sxs-lookup"><span data-stu-id="ec651-109">For more information about how to set up subscriptions, see [Set up subscription groups](set-up-subscription-groups.md).</span></span>

<span data-ttu-id="ec651-110">Po utworzeniu grupy subskrypcji można utworzyć subskrypcję.</span><span class="sxs-lookup"><span data-stu-id="ec651-110">After the subscription group is created, you can create the subscription.</span></span> <span data-ttu-id="ec651-111">Aby uzyskać więcej informacji na temat tworzenia subskrypcji serwisu, zobacz [Tworzenie subskrypcji serwisu z grupy subskrypcji](create-service-subscriptions-from-subscription-group.md).</span><span class="sxs-lookup"><span data-stu-id="ec651-111">For more information about how to create service subscriptions, see [Create service subscriptions from a subscription group](create-service-subscriptions-from-subscription-group.md).</span></span>

## <a name="create-and-modify-subscription-transactions"></a><span data-ttu-id="ec651-112">Tworzenie i modyfikowanie transakcji subskrypcji</span><span class="sxs-lookup"><span data-stu-id="ec651-112">Create and modify subscription transactions</span></span>

<span data-ttu-id="ec651-113">Po skonfigurowaniu subskrypcji należy utworzyć transakcję opłaty subskrypcyjnej za pierwszy rozliczany okres, czyli za jeden rok.</span><span class="sxs-lookup"><span data-stu-id="ec651-113">After you set up the subscription, you create the subscription fee transaction for the first invoicing period, which is one year.</span></span> <span data-ttu-id="ec651-114">Transakcje są typu **Normalna**.</span><span class="sxs-lookup"><span data-stu-id="ec651-114">The transactions are of the **Regular** type.</span></span> <span data-ttu-id="ec651-115">W związku z tym można tworzyć tylko transakcje subskrypcji, których daty początkowa i końcowa odpowiadają okresom utworzonym wcześniej w formularzu **Typy okresu**.</span><span class="sxs-lookup"><span data-stu-id="ec651-115">Therefore, you can only create subscription transactions where the from date and the to date correspond to periods that were previously created in the **Period types** form.</span></span> <span data-ttu-id="ec651-116">Aby uzyskać więcej informacji o transakcjach opłat, zobacz [Tworzenie transakcji opłat subskrypcji](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="ec651-116">For more information about fee transactions, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="ec651-117">Po skonfigurowaniu subskrypcji dla klienta przypominasz sobie o wynegocjowanym rabacie o wysokości 10 procent na wszystkie pozycje cennikowe w ofercie.</span><span class="sxs-lookup"><span data-stu-id="ec651-117">After you set up the subscription for your customer, you remember that they have negotiated a 10 percent discount on all list prices for service offerings.</span></span> <span data-ttu-id="ec651-118">Należy więc obniżyć wysokość już utworzonej opłaty transakcji.</span><span class="sxs-lookup"><span data-stu-id="ec651-118">Therefore, you must reduce the price of the transaction fee that you created.</span></span>

<span data-ttu-id="ec651-119">Jeszcze tego samego dnia osoba kontaktowa od klienta dzwoni z informacją, że nadal chcą zawrzeć umowę serwisową na konserwację oświetlenia, ale w ciągu roku jest tam planowana instalacja nowego oświetlenia.</span><span class="sxs-lookup"><span data-stu-id="ec651-119">Later in the day, your customer contact calls to say that, although they still want the service agreement for the lighting rig, they plan to introduce a new lighting rig later in the year.</span></span> <span data-ttu-id="ec651-120">W związku z tym konserwacja jest potrzebna tylko na okres do października 2013 roku.</span><span class="sxs-lookup"><span data-stu-id="ec651-120">Therefore, they only need maintenance coverage until October 2013.</span></span> <span data-ttu-id="ec651-121">Aby zredukować liczbę miesięcy w subskrypcji klienta, trzeba utworzyć nową transakcję opłaty subskrypcji typu **Dni redukcji**.</span><span class="sxs-lookup"><span data-stu-id="ec651-121">To reduce the number of months for the customer’s subscription, you create a new subscription fee transaction of the **Reduction days** type.</span></span> <span data-ttu-id="ec651-122">Aby uzyskać więcej informacji o zmniejszaniu liczby dni, zobacz [Zmniejszanie dni na opłaty subskrypcji](reduce-the-days-on-subscription-fees.md).</span><span class="sxs-lookup"><span data-stu-id="ec651-122">For more information about how to reduce days, see [Reduce the days on subscription fees](reduce-the-days-on-subscription-fees.md).</span></span>

## <a name="invoice-and-accrue-subscription-transactions"></a><span data-ttu-id="ec651-123">Fakturowanie i naliczanie transakcji subskrypcji</span><span class="sxs-lookup"><span data-stu-id="ec651-123">Invoice and accrue subscription transactions</span></span>

<span data-ttu-id="ec651-124">Konfigurowanie subskrypcji zostało zakończone i można rozliczać klienta z tytułu subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="ec651-124">You have now finished setting up the subscription, and you are ready to invoice your customer for it.</span></span> <span data-ttu-id="ec651-125">Aby uzyskać więcej informacji o fakturowaniu subskrypcji, zobacz [Fakturowanie transakcji subskrypcji](invoice-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="ec651-125">For more information about how to invoice subscriptions, see [Invoice subscription transactions](invoice-subscription-transactions.md).</span></span>

<span data-ttu-id="ec651-126">Dwa dni później klient zadzwonił z informacją, że subskrypcja powinna być rozliczana w dolarach amerykańskich, a nie w euro.</span><span class="sxs-lookup"><span data-stu-id="ec651-126">Two days later, your customer calls to say that the subscription should be invoiced in U.S. dollars, not Euros.</span></span> <span data-ttu-id="ec651-127">Trzeba więc sporządzić fakturę korygującą oraz utworzyć nową transakcję subskrypcji we właściwej walucie.</span><span class="sxs-lookup"><span data-stu-id="ec651-127">Therefore, you create a credit note, and you also create a new subscription transaction in the correct currency.</span></span> <span data-ttu-id="ec651-128">Aby uzyskać więcej informacji o stosowaniu uznań do transakcji subskrypcji, zobacz [Transakcje subskrypcji kredytu](credit-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="ec651-128">For more information about how to credit subscription transactions, see [Credit subscription transactions](credit-subscription-transactions.md).</span></span>

<span data-ttu-id="ec651-129">Na koniec każdego miesiąca miesięczne przychody z tytułu subskrypcji od klienta można naliczać na koncie wynikowym i na kontach PWT.</span><span class="sxs-lookup"><span data-stu-id="ec651-129">At the end of each month, one month's revenue can be accrued from the customer's subscription to the profit and loss account and the WIP accounts.</span></span> <span data-ttu-id="ec651-130">Aby uzyskać więcej informacji o naliczaniu przychodów z subskrypcji, zobacz [Naliczanie przychodu z subskrypcji](accrue-subscription-revenue.md).</span><span class="sxs-lookup"><span data-stu-id="ec651-130">For more information about how to accrue revenue for subscriptions, see [Accrue subscription revenue](accrue-subscription-revenue.md).</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]