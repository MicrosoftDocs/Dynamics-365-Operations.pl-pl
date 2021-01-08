---
title: Rozwiązywanie problemów dotyczących przychodzących operacji magazynowych
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z przychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 60b6e37ec9d716f635c2d25374ac25a82286660e
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645979"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="c9407-103">Rozwiązywanie problemów dotyczących przychodzących operacji magazynowych</span><span class="sxs-lookup"><span data-stu-id="c9407-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c9407-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z przychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c9407-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="c9407-105">Zgłaszany jest następujący komunikat o błędzie: Wygenerowano „Zlecenie kontroli jakości %1.</span><span class="sxs-lookup"><span data-stu-id="c9407-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="c9407-106">Nie można odnaleźć profilu grupy. Sprawdź konfigurację".</span><span class="sxs-lookup"><span data-stu-id="c9407-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c9407-107">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c9407-107">Issue description</span></span>

<span data-ttu-id="c9407-108">Ten komunikat o błędzie jest związany z procesem odbierania, w którym jest włączona funkcja zarządzania jakością (QMS).</span><span class="sxs-lookup"><span data-stu-id="c9407-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="c9407-109">W zależności od konfiguracji w danym środowisku dodatkowe szczegóły dotyczące transakcji, która generuje komunikat o błędzie, mogą pomóc w rozwiązaniu problemu.</span><span class="sxs-lookup"><span data-stu-id="c9407-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c9407-110">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c9407-110">Issue resolution</span></span>

<span data-ttu-id="c9407-111">Najpierw przejrzyj ustawienia [pobierania dla grupy](set-up-cluster-picking.md) i upewnij się, że profile grup są skonfigurowane poprawnie.</span><span class="sxs-lookup"><span data-stu-id="c9407-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="c9407-112">Nie można skorzystać z elementu menu urządzenia przenośnego do pobierania grup, dopóki nie zostaną skonfigurowane Profile grup.</span><span class="sxs-lookup"><span data-stu-id="c9407-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="c9407-113">W zależności od środowiska konieczne może być również przejrzenie innych pokrewnych konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c9407-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="c9407-114">Odbieranie mieszanego numeru identyfikacyjnego nie działa dla kodu dyspozycji z wyjątkiem kredytu.</span><span class="sxs-lookup"><span data-stu-id="c9407-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c9407-115">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c9407-115">Issue description</span></span>

<span data-ttu-id="c9407-116">Jeśli pole **Akcja** dla kodu dyspozycji ma wartość *Kredyt* lub *Odpadki*, do przetwarzania zwróconych towarów można używać tylko elementu menu [Odbieranie mieszanych numerów identyfikacyjnych](mixed-license-plate-receiving.md).</span><span class="sxs-lookup"><span data-stu-id="c9407-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c9407-117">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c9407-117">Issue resolution</span></span>

<span data-ttu-id="c9407-118">Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji.</span><span class="sxs-lookup"><span data-stu-id="c9407-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="c9407-119">Obecnie tylko [kody dyspozycji](../service-management/set-up-disposition-codes.md), w których pole **Akcja** ma wartość *Kredyt* lub *Odpadki*, są obsługiwane w przypadku otrzymywania mieszanego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="c9407-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="c9407-120">Kiedy uruchamiam zadanie okresowe Aktualizuj przyjęcia produktów, niepotwierdzone zamówienia zakupu są potwierdzane.</span><span class="sxs-lookup"><span data-stu-id="c9407-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c9407-121">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c9407-121">Issue description</span></span>

<span data-ttu-id="c9407-122">Po uruchomieniuzadania okresowego *Aktualizowanie dokumentów przyjęcia produktów* system automatycznie potwierdza niepotwierdzone zamówienia zakupu ze stanem transakcji magazynowej *Zarejestrowane*.</span><span class="sxs-lookup"><span data-stu-id="c9407-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c9407-123">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c9407-123">Issue resolution</span></span>

<span data-ttu-id="c9407-124">Nowa funkcja obsługi ładunków przychodzących *Przekroczenie przyjmowania ilości ładunku* rozwiązuje ten problem.</span><span class="sxs-lookup"><span data-stu-id="c9407-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="c9407-125">Aby włączyć tę funkcję, przejdź do [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz następujące funkcje (w kolejności, w jakiej są wymienione):</span><span class="sxs-lookup"><span data-stu-id="c9407-125">To turn on this feature, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="c9407-126">Skojarz transakcje magazynowe zamówienia zakupu z ładunkiem</span><span class="sxs-lookup"><span data-stu-id="c9407-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="c9407-127">Przyjęcie nadmiernej ilości obciążenia pracą</span><span class="sxs-lookup"><span data-stu-id="c9407-127">Over receipt of load quantities</span></span>

<span data-ttu-id="c9407-128">Aby uzyskać więcej informacji, zajrzyj do [Księguj zarejestrowane ilości produktów na podstawie zamówień zakupu](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="c9407-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>
