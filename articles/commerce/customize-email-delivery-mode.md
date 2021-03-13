---
title: Dostosowywanie wiadomości e-mail dotyczących transakcji według metod dostawy
description: W tym temacie opisano sposób konfigurowania niestandardowych szablonów wiadomości e-mail dla określonych typów powiadomień i metod dostawy w firmie Microsoft Dynamics 365 Commerce.
author: stuharg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: f4ecb990cfe792e92142f922c43c71ef8494e117
ms.sourcegitcommit: da17648c296b22d517eadb2f71c7803672e5648d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2021
ms.locfileid: "5031855"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a><span data-ttu-id="6f6fb-103">Dostosowywanie wiadomości e-mail dotyczących transakcji według metod dostawy</span><span class="sxs-lookup"><span data-stu-id="6f6fb-103">Customize transactional emails by mode of delivery</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6f6fb-104">W tym temacie opisano sposób konfigurowania niestandardowych szablonów wiadomości e-mail dla określonych typów powiadomień i metod dostawy w firmie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-104">This topic describes how to set up custom email templates for specific notification types and modes of delivery in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="6f6fb-105">Można teraz dostosować wiadomości transakcyjne, aby utworzyć kombinację typu powiadomienia (np. **utworzone zamówienie**, **zapakowane** lub **zafakturowane zamówienie**) oraz metody dostawy (np. na następny dzień, odbiór w sklepie lub odbiór spod domu).</span><span class="sxs-lookup"><span data-stu-id="6f6fb-105">Transactional emails can now be customized for a combination of a notification type (for example, **Order created**, **Order packed**, or **Order invoiced**) and a mode of delivery (for example, overnight, in-store pickup, or curbside pickup).</span></span> <span data-ttu-id="6f6fb-106">Niestandardowe wiadomości transakcyjne umożliwiają detalistom dostarczanie ich klientom zamówień na realizację, które są dostosowane do metody dostawy zamówienia.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-106">Custom transactional emails let retailers provide their customers order with fulfillment experiences that are tailored to the order's mode of delivery.</span></span> <span data-ttu-id="6f6fb-107">Na przykład zdarzenie „zapakowanie zapakowane” może być dostosowywane w taki sposób, aby dostarcza klientom Curbside instrukcje dotyczące odbioru, którzy wybierają Curbside pobrania.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-107">For example, the "order packed" event can be customized so that it provides curbside pickup instructions for customers who choose curbside pickup.</span></span> <span data-ttu-id="6f6fb-108">Można również udostępnić informacje o firmie przewozowej i dostawie dla odbiorców, którzy wybierają zamówienie wysyłki.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-108">Alternatively, it can provide shipping carrier and delivery information for customers who choose to have their order shipped.</span></span>

> [!NOTE]
> <span data-ttu-id="6f6fb-109">Aby skorzystać z funkcji niestandardowych transakcyjnych wiadomości e-mail, należy najpierw włączyć **funkcję zarządzania szablonami transakcyjnych wiadomości e-mail według metod dostawy** przechodząc do **obszaru obszary robocze \> w module** Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-109">To use the functionality for customized transactional emails, you first must turn on the **Customize transactional email templates by mode of delivery** feature by going to **Workspaces \> Feature management** in Commerce headquarters.</span></span>

<span data-ttu-id="6f6fb-110">Wiadomości e-mail można dostosowywać za pomocą metody dostawy dla następujących typów powiadomień:</span><span class="sxs-lookup"><span data-stu-id="6f6fb-110">Emails can be customized by mode of delivery for the following notification types:</span></span>

- <span data-ttu-id="6f6fb-111">**Anulowanie zamówienia** — ten typ powiadomienia e-mail jest nowy.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-111">**Order cancellation** – This email notification type is new.</span></span>
- <span data-ttu-id="6f6fb-112">**Zamówienie utworzone**</span><span class="sxs-lookup"><span data-stu-id="6f6fb-112">**Order created**</span></span>
- <span data-ttu-id="6f6fb-113">**Zamówienie potwierdzone**</span><span class="sxs-lookup"><span data-stu-id="6f6fb-113">**Order confirmed**</span></span>
- <span data-ttu-id="6f6fb-114">**Zamówienie zafakturowane** — ten typ powiadomienia e-mail jest nowy.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-114">**Order invoiced** – This email notification type is new.</span></span> <span data-ttu-id="6f6fb-115">Można go użyć zamiast **typu powiadomienia o wysyłce zamówienia**, który wyśle powiadomienie dla dowolnego zdarzenia faktury, które ma metodę dostawy (a nie odbiór, wysyłka lub elektroniczna metoda dostawy).</span><span class="sxs-lookup"><span data-stu-id="6f6fb-115">It can be used instead of the **Order shipped** notification type that will send a notification for any invoice event that has a shipped mode of delivery (not a pickup, carry out, or electronic mode of delivery).</span></span>
- <span data-ttu-id="6f6fb-116">**Zamówienie pobrane**</span><span class="sxs-lookup"><span data-stu-id="6f6fb-116">**Order picked**</span></span>
- <span data-ttu-id="6f6fb-117">**Zamówienie spakowane**</span><span class="sxs-lookup"><span data-stu-id="6f6fb-117">**Order packed**</span></span>
- <span data-ttu-id="6f6fb-118">**Zamówienie gotowe do pobrania** — ten typ powiadomienia można dostosować za pomocą metody dostawy tylko **w przypadku włączenia obsługi wielu metod dostawy**.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-118">**Order ready for pickup** – This notification type can be customized by mode of delivery only if the **Support for multiple pickup delivery modes** feature is turned on.</span></span> <span data-ttu-id="6f6fb-119">W takim przypadku ten typ powiadomienia jest funkcjonalnie równoważny **typowi zapakowanego** powiadomienia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-119">In that case, this notification type is functionally equivalent to the **Order packed** notification type.</span></span>
- <span data-ttu-id="6f6fb-120">**Płatność nie powiodła się**</span><span class="sxs-lookup"><span data-stu-id="6f6fb-120">**Payment failed**</span></span>
- <span data-ttu-id="6f6fb-121">**Zamówienie wymiany utworzone**</span><span class="sxs-lookup"><span data-stu-id="6f6fb-121">**Replacement order created**</span></span>

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a><span data-ttu-id="6f6fb-122">Konfigurowanie szablonów wiadomości e-mail dla konkretnych metod dostawy</span><span class="sxs-lookup"><span data-stu-id="6f6fb-122">Configure email templates for specific modes of delivery</span></span>

<span data-ttu-id="6f6fb-123">W przypadku tej procedury przyjęto założenie, że utworzono już nowe, niestandardowe szablony wiadomości e-mail i dodano je do **strony szablony wiadomości e-mail organizacji**.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-123">For this procedure, the assumption is that you've already created your new, custom email templates and added them to the **Organization email templates** page.</span></span> <span data-ttu-id="6f6fb-124">Aby uzyskać informacje na temat tworzenia i przekazywania szablonów wiadomości e-mail, należy zapoznać się z tematem [Tworzenie szablonów wiadomości e-mail dla zdarzeń transakcyjnych ](email-templates-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="6f6fb-124">For information about how to create and upload email templates, see [Create email templates for transactional events](email-templates-transactions.md).</span></span>

<span data-ttu-id="6f6fb-125">Aby skonfigurować szablony wiadomości e-mail dla konkretnych metod dostawy w programie Commerce Central, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-125">To configure email templates for specific modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6f6fb-126">Przejdź do **profilu powiadomień e-mail w portalu Commerce**.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-126">Go to **Commerce email notification profile**.</span></span>
1. <span data-ttu-id="6f6fb-127">W obszarze **Ustawienia powiadamiania o zdarzeniach sieci sprzedaży** Wybierz istniejący typ powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-127">Under **Retail event notification settings**, select an existing notification type.</span></span>
1. <span data-ttu-id="6f6fb-128">Gdy typ powiadomienia jest wciąż wybrany, wybierz opcję **Konfiguruj metody dostawy**.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-128">While the notification type is still selected, select **Configure modes of delivery**.</span></span>
1. <span data-ttu-id="6f6fb-129">Na stronie **Metody dostawy** wybierz opcję **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-129">In the **Modes of delivery** dialog box, select **New**.</span></span>
1. <span data-ttu-id="6f6fb-130">W polu **Metoda dostawy** wybierz metodę dostawy do skojarzenia z tym profilem.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-130">In the new row, in the **Mode of delivery** field, select a mode of delivery.</span></span>
1. <span data-ttu-id="6f6fb-131">W **polu Identyfikator wiadomości e-mail** wybierz szablon wiadomości e-mail, który ma zostać zamapowany do metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-131">In the **Email ID** field, select the email template to map to the mode of delivery.</span></span>
1. <span data-ttu-id="6f6fb-132">Zaznacz pole wyboru **Aktywne**.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-132">Select the **Active** check box.</span></span>
1. <span data-ttu-id="6f6fb-133">Powtórz kroki od 4 do 7, aby dodać kolejne metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-133">Repeat steps 4 through 7 to add more modes of delivery.</span></span>
1. <span data-ttu-id="6f6fb-134">Po zakończeniu wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-134">When you've finished, select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="6f6fb-135">Jeśli w wierszach zamówienia sprzedaży znajduje się więcej niż jeden tryb dostawy, zostanie użyty szablon domyślny.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-135">When more than one mode of delivery is present across lines in a sales order, the default template will be used.</span></span> <span data-ttu-id="6f6fb-136">Szablon domyślny jest mapowany na typ powiadomienia na **stronie profil powiadomień pocztą e-mail w module Commerce**.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-136">The default template is the template that is mapped to the notification type on the **Commerce email notification profile** page.</span></span>
> - <span data-ttu-id="6f6fb-137">Jeśli zamówienie sprzedaży ma tryb dostawy, który nie został skonfigurowany dla niestandardowego szablonu wiadomości e-mail, zostanie użyty domyślny szablon wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="6f6fb-137">If a sales order has a mode of delivery that hasn't been configured for a custom email template, the default email template will be used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f6fb-138">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6f6fb-138">Additional resources</span></span>

[<span data-ttu-id="6f6fb-139">Tworzenie zamówień w biurach obsługi</span><span class="sxs-lookup"><span data-stu-id="6f6fb-139">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="6f6fb-140">Zmienianie metody dostawy w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6f6fb-140">Change mode of delivery in POS</span></span>](pos-change-delivery-mode.md)
