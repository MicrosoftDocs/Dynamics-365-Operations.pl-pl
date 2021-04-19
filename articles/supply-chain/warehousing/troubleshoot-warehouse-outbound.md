---
title: Rozwiązywanie problemów dotyczących wychodzących operacji magazynowych
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z wychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 919b6f433db47f24adc9a474942557a1467d1f71
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828185"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a><span data-ttu-id="59caf-103">Rozwiązywanie problemów dotyczących wychodzących operacji magazynowych</span><span class="sxs-lookup"><span data-stu-id="59caf-103">Troubleshoot outbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59caf-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z wychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="59caf-104">This topic describes how to fix common issues that you might encounter while you work with outbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a><span data-ttu-id="59caf-105">Otrzymuję następujący komunikat o błędzie: „Nie można zwolnić zamówienia sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="59caf-105">I receive the following error message: "Sales order could not be released."</span></span>

### <a name="issue-description"></a><span data-ttu-id="59caf-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="59caf-106">Issue description</span></span>

<span data-ttu-id="59caf-107">Ten problem może wystąpić z kilku powodów.</span><span class="sxs-lookup"><span data-stu-id="59caf-107">This issue can occur for several reasons.</span></span> <span data-ttu-id="59caf-108">Na przykład zamówienie jest wstrzymane z zarządzaniem kredytami i nie można tworzyć żadnych wysyłek, dopóki nie zostanie wprowadzony prawidłowy adres pocztowy dla wszystkich wierszy sprzedaży, które są skojarzone z zamówieniem sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="59caf-108">For example, the order is on credit management hold, and no shipments can be created until a valid postal address is entered for all sales lines that are associated with a sales order.</span></span> <span data-ttu-id="59caf-109">Alternatywnie istnieje wstrzymanie zamówienia, na które należy się odnieść, zanim zamówienie zostanie zwolnione do magazynu.</span><span class="sxs-lookup"><span data-stu-id="59caf-109">Alternatively, there is an order hold that must be addressed before the order can be released to the warehouse.</span></span> <span data-ttu-id="59caf-110">Ta wstrzymanie może być właściwe dla zamówienia lub na być na koncie odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="59caf-110">This hold might be order-specific, or it might be on the customer account.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="59caf-111">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="59caf-111">Issue resolution</span></span>

<span data-ttu-id="59caf-112">Dodaj lub zaktualizuj adres w wierszach zamówienia sprzedaży i zamówienia, a następnie zwolnij zamówienie do magazynu.</span><span class="sxs-lookup"><span data-stu-id="59caf-112">Add or update the address on the sales order and order lines, and then release the order to the warehouse.</span></span> <span data-ttu-id="59caf-113">Zamówienia mogą być zwalniane do magazynu tylko wtedy, gdy mają prawidłowy adres dostawy (zgodnie z konfiguracją formatu adresu w module **Administrowanie organizacją**).</span><span class="sxs-lookup"><span data-stu-id="59caf-113">Orders can be released to the warehouse only if they have a valid delivery address (per the address format setup in the **Organization administration** module).</span></span>

<span data-ttu-id="59caf-114">Zbadaj wstrzymanie zamówienia i rozwiąż problemy.</span><span class="sxs-lookup"><span data-stu-id="59caf-114">Investigate the order hold, and address the issues.</span></span> <span data-ttu-id="59caf-115">Następnie usuń wstrzymanie z zamówienia lub klienta i zwolnij zamówienie do magazynu.</span><span class="sxs-lookup"><span data-stu-id="59caf-115">Then remove the hold from the order or customer, and release the order to the warehouse.</span></span>

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a><span data-ttu-id="59caf-116">Wyświetlany jest następujący komunikat: „Wysyłka ładunku 1% została potwierdzona.”</span><span class="sxs-lookup"><span data-stu-id="59caf-116">I receive the following message: "The shipment for load 1% has been confirmed."</span></span> <span data-ttu-id="59caf-117">Nie są jednak księgowane żadne wiersze.</span><span class="sxs-lookup"><span data-stu-id="59caf-117">However, no lines are posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="59caf-118">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="59caf-118">Issue description</span></span>

<span data-ttu-id="59caf-119">Wysyłka w ładunku została potwierdzona, ale dalsze księgowanie nie wystąpiło.</span><span class="sxs-lookup"><span data-stu-id="59caf-119">A shipment on a load was confirmed, but no further posting occurred.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="59caf-120">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="59caf-120">Issue resolution</span></span>

<span data-ttu-id="59caf-121">Potwierdzenie wysyłki nie ma wpływu na księgowanie.</span><span class="sxs-lookup"><span data-stu-id="59caf-121">Shipment confirmation doesn't affect posting.</span></span> <span data-ttu-id="59caf-122">Właśnie aktualizuje stan wysyłki i ładunku.</span><span class="sxs-lookup"><span data-stu-id="59caf-122">It just updates the shipment and load status.</span></span> <span data-ttu-id="59caf-123">Księgowanie musi nastąpić w oddzielnym procesie.</span><span class="sxs-lookup"><span data-stu-id="59caf-123">Posting must occur in a separate process.</span></span>

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a><span data-ttu-id="59caf-124">Otrzymuję następujący komunikat o błędzie: „Nie można przetworzyć dostawy bezpośredniej dla magazynu 1%, ponieważ ma włączone zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="59caf-124">I receive the following error message: "Direct delivery is not able to process for warehouse 1% as it has warehouse management enabled.</span></span> <span data-ttu-id="59caf-125">Proszę określić inny magazyn, który nie obsługuje zarządzania magazynem”.</span><span class="sxs-lookup"><span data-stu-id="59caf-125">Please specify another warehouse that is not enabled for warehouse management."</span></span>

### <a name="issue-description"></a><span data-ttu-id="59caf-126">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="59caf-126">Issue description</span></span>

<span data-ttu-id="59caf-127">Towar jest dodawany do wiersza sprzedaży w celu bezpośredniej dostawy z magazynu, który obsługuje zarządzanie magazynem (WMS).</span><span class="sxs-lookup"><span data-stu-id="59caf-127">An item is added to a sales line for direct delivery from a warehouse that is enabled for warehouse management (WMS).</span></span> <span data-ttu-id="59caf-128">Ten komunikat o błędzie jest wyświetlany po zaktualizowaniu wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="59caf-128">You receive this error message when the sales line is updated.</span></span> 

### <a name="issue-resolution"></a><span data-ttu-id="59caf-129">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="59caf-129">Issue resolution</span></span>

<span data-ttu-id="59caf-130">Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji.</span><span class="sxs-lookup"><span data-stu-id="59caf-130">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="59caf-131">Obecnie usługa WMS nie obsługuje dostawy bezpośredniej.</span><span class="sxs-lookup"><span data-stu-id="59caf-131">Currently, WMS doesn't support direct delivery.</span></span> <span data-ttu-id="59caf-132">Dlatego też, aby można było skorzystać z dostawy bezpośredniej, należy wybrać pozycję i magazyn spoza WMS.</span><span class="sxs-lookup"><span data-stu-id="59caf-132">Therefore, to use direct delivery, you must select a non-WMS item and warehouse.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]