---
title: Integrowanie aplikacji Dynamics 365 Supply Chain Management (zarządzanie składnikami majątku) z aplikacją Dynamics 365 Guides
description: W tym temacie objaśniono sposób integrowania modułu zarządzania składnikami majątku w aplikacji Microsoft Dynamics 365 Supply Chain Management z aplikacją Dynamics 365 Guides. Pozwoli to na korzystanie z zalet przewodników po rzeczywistości mieszanej w codziennych przepływach pracy dotyczących usług i konserwacji.
author: kamaybac
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 50cfea6656e1f13532b018784fa64b2aac10fc7f
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908574"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a><span data-ttu-id="c20bf-103">Integrowanie aplikacji Dynamics 365 Supply Chain Management (zarządzanie składnikami majątku) z aplikacją Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="c20bf-103">Integrate Dynamics 365 Supply Chain Management (Asset management) with Dynamics 365 Guides</span></span>

<span data-ttu-id="c20bf-104">Możesz zintegrować moduł **Zarządzanie składnikami majątku** w aplikacji Microsoft Dynamics 365 Supply Chain Management z aplikacją Dynamics 365 Guides, aby korzystać z zalet przewodników po rzeczywistości mieszanej w codziennych przepływach pracy dotyczących usług i konserwacji.</span><span class="sxs-lookup"><span data-stu-id="c20bf-104">You can integrate the **Asset management** module in Microsoft Dynamics 365 Supply Chain Management with Dynamics 365 Guides to take advantage of mixed-reality guides in your day-to-day service and maintenance workflows.</span></span> <span data-ttu-id="c20bf-105">Jeśli przewodnik został skojarzony ze zleceniem pracy modułu Zarządzanie składnikami majątku, pracownik, który otworzy listę kontrolną konserwowanego składnika majątku ze zlecenia pracy w aplikacji mobilnej Supply Chain Management (Dynamics 365), zobaczy, że przewodnik jest dostępny.</span><span class="sxs-lookup"><span data-stu-id="c20bf-105">If a guide is associated with an Asset Management work order, a worker who opens the work order's maintenance checklist in the Supply Chain Management (Dynamics 365) mobile app sees that a guide is available.</span></span> <span data-ttu-id="c20bf-106">Pracownik może następnie znaleźć i otworzyć przewodnik w aplikacji Dynamics 365 Guides dla urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c20bf-106">The worker can then find and open the guide in the Dynamics 365 Guides HoloLens app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c20bf-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="c20bf-107">Prerequisites</span></span>

<span data-ttu-id="c20bf-108">Przed dołączeniem przewodników do zleceń pracy modułu Zarządzanie składnikami majątku należy spełnić następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="c20bf-108">Before you can attach guides to Asset management work orders, you must complete these prerequisites:</span></span>

- <span data-ttu-id="c20bf-109">[Skonfigurowanie aplikacji Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) w wersji 10.0.9 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="c20bf-109">[Set up Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 or later.</span></span>
- <span data-ttu-id="c20bf-110">[Włączenie podwójnego zapisu w aplikacji Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="c20bf-110">[Turn on dual-write for Supply Chain Management apps](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span></span>
- <span data-ttu-id="c20bf-111">[Włączenie dystrybucji testowej](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) funkcji **MRGuidesFeature**.</span><span class="sxs-lookup"><span data-stu-id="c20bf-111">[Turn on flight](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) for the **MRGuidesFeature** feature.</span></span> <span data-ttu-id="c20bf-112">(W przypadku środowisk produkcyjnych należy najpierw przesłać bilet pomocy technicznej, aby dzierżawa została dodana do grupy dystrybucji testowej).</span><span class="sxs-lookup"><span data-stu-id="c20bf-112">(For production environments, you must first submit a support ticket to have your tenant added to the flighting group.)</span></span>
- <span data-ttu-id="c20bf-113">[Włączenie następujących kluczy konfiguracji](/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) na stronie **Konfiguracja licencji**:</span><span class="sxs-lookup"><span data-stu-id="c20bf-113">[Turn on the following configuration keys](/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) on the **License configuration** page:</span></span>

    - <span data-ttu-id="c20bf-114">Zarządzanie składnikami majątku \> Rzeczywistość mieszana zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c20bf-114">Asset management \> Asset management mixed reality</span></span>
    - <span data-ttu-id="c20bf-115">Rzeczywistość mieszana \> Przewodnik w rzeczywistości mieszanej</span><span class="sxs-lookup"><span data-stu-id="c20bf-115">Mixed reality \> Mixed reality guide</span></span>

- <span data-ttu-id="c20bf-116">[Skonfigurowanie aplikacji Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) w wersji 200.0.0.96 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="c20bf-116">[Set up Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 or later.</span></span>

## <a name="use-dynamics-365-guides-with-asset-management"></a><span data-ttu-id="c20bf-117">Używanie aplikacji Dynamics 365 Guides z zarządzaniem składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c20bf-117">Use Dynamics 365 Guides with Asset management</span></span>

<span data-ttu-id="c20bf-118">Aby skojarzyć przewodnik, należy skorzystać z wiersza listy kontrolnej konserwowanego składnika majątku w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="c20bf-118">To associate a guide, you use a maintenance checklist line in Asset management.</span></span> <span data-ttu-id="c20bf-119">Skojarzenie można utworzyć za pomocą szablonu listy kontrolnej konserwowanego składnika majątku, typu zadania konserwacji lub zlecenia produkcyjnego, ponieważ wszystkie trzy zawierają wiersze listy kontrolnej konserwowanego składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="c20bf-119">You can create the association through a maintenance checklist template, a maintenance job type, or a work order, because all three contain maintenance checklist lines.</span></span> <span data-ttu-id="c20bf-120">Użycie szablonu umożliwi zaoszczędzenie czasu, ponieważ szablon można skojarzyć ze wszystkimi typami zadań konserwacji, które go używają.</span><span class="sxs-lookup"><span data-stu-id="c20bf-120">You can save time by using a template, because a template can be associated with all the maintenance job types that use it.</span></span> <span data-ttu-id="c20bf-121">Na przykład przewodnik skojarzony z typem zadania konserwacji jest automatycznie kojarzony ze wszystkimi zleceniami pracy określającymi ten typ zadania.</span><span class="sxs-lookup"><span data-stu-id="c20bf-121">For example, a guide that is associated with a maintenance job type is automatically associated with all work orders that specify that job type.</span></span> <span data-ttu-id="c20bf-122">Z drugiej strony przewodnik skojarzony bezpośrednio ze zleceniem pracy istnieje tylko dla tego zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="c20bf-122">On the other hand, a guide that is associated directly with a work order exists only for that work order.</span></span>

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a><span data-ttu-id="c20bf-123">Kojarzenie przewodnika z szablonem listy kontrolnej konserwowanego składnika majątku</span><span class="sxs-lookup"><span data-stu-id="c20bf-123">Associate a guide with a maintenance checklist template</span></span>

<span data-ttu-id="c20bf-124">Aby skojarzyć przewodnik z szablonem listy kontrolnej konserwowanego składnika majątku, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="c20bf-124">To associate a guide with a maintenance checklist template, follow these steps.</span></span>

1. <span data-ttu-id="c20bf-125">Utwórz przewodnik, korzystając z aplikacji Dynamics 365 Guides na komputer i urządzenie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c20bf-125">Create a guide by using the Dynamics 365 Guides PC and HoloLens apps.</span></span> <span data-ttu-id="c20bf-126">Aby uzyskać więcej informacji dotyczących sposobu tworzenia przewodnika, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="c20bf-126">For information about how to create a guide, see the following topics:</span></span>

    - [<span data-ttu-id="c20bf-127">Tworzenie przewodnika przy użyciu aplikacji komputerowej</span><span class="sxs-lookup"><span data-stu-id="c20bf-127">Use the PC app to create a guide</span></span>](/dynamics365/mixed-reality/guides/pc-app-overview)
    - [<span data-ttu-id="c20bf-128">Umieszczanie hologramów przy użyciu aplikacji HoloLens</span><span class="sxs-lookup"><span data-stu-id="c20bf-128">Use the HoloLens app to place your holograms</span></span>](/dynamics365/mixed-reality/guides/hololens-app-overview)

1. <span data-ttu-id="c20bf-129">W aplikacji Supply Chain Management [utwórz szablon listy konserwowanego składnika majątku](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span><span class="sxs-lookup"><span data-stu-id="c20bf-129">In Supply Chain Management, [create a maintenance checklist template](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span></span>
1. <span data-ttu-id="c20bf-130">Skojarz utworzony przewodnik z wierszem listy kontrolnej konserwowanego składnika majątku w nowym szablonie listy kontrolnej konserwowanego składnika majątku:</span><span class="sxs-lookup"><span data-stu-id="c20bf-130">Associate the guide that you created with a maintenance checklist line in the new maintenance checklist template:</span></span>

    1. <span data-ttu-id="c20bf-131">Na skróconej karcie **Wiersze listy kontrolnej konserwowanego składnika majątku** wybierz wiersz, z którym chcesz skojarzyć przewodnik.</span><span class="sxs-lookup"><span data-stu-id="c20bf-131">On the **Maintenance checklist lines** FastTab, select the line that you want to associate the guide with.</span></span>
    1. <span data-ttu-id="c20bf-132">Na skróconej karcie **Skojarzone przewodniki** wybierz pozycję **Dodaj przewodnik**.</span><span class="sxs-lookup"><span data-stu-id="c20bf-132">On the **Associated guides** FastTab, select **Add Guide**.</span></span>

        <span data-ttu-id="c20bf-133">![Kojarzenie przewodnika z wierszem listy kontrolnej konserwowanego składnika majątku](media/am-guides-integration-add-guide.png "Kojarzenie przewodnika z wierszem listy kontrolnej konserwowanego składnika majątku")</span><span class="sxs-lookup"><span data-stu-id="c20bf-133">![Associate a guide with a maintenance checklist line](media/am-guides-integration-add-guide.png "Associate a guide with a maintenance checklist line")</span></span>

    1. <span data-ttu-id="c20bf-134">W polu **Nazwa** wybierz przewodnik, a następnie wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c20bf-134">In the **Name** field, select a guide, and then select **Save**.</span></span>

        <span data-ttu-id="c20bf-135">![Wybieranie przewodnika w polu Nazwa](media/am-guides-integration-select-guide.png "Wybieranie przewodnika w polu Nazwa")</span><span class="sxs-lookup"><span data-stu-id="c20bf-135">![Select a guide in the Name field](media/am-guides-integration-select-guide.png "Select a guide in the Name field")</span></span>

1. <span data-ttu-id="c20bf-136">Skojarz szablon listy kontrolnej konserwowanego składnika majątku z typem pracy:</span><span class="sxs-lookup"><span data-stu-id="c20bf-136">Associate the maintenance checklist template with a job type:</span></span>

    1. <span data-ttu-id="c20bf-137">[Utwórz typ zadania konserwacji](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) lub wybierz istniejący typ zadania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="c20bf-137">[Create a maintenance job type](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type), or select an existing maintenance job type.</span></span>
    1. <span data-ttu-id="c20bf-138">W okienku akcji wybierz pozycję **Ustawienia domyślne typu zadania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="c20bf-138">On the Action Pane, select **Maintenance job type defaults**.</span></span>

        <span data-ttu-id="c20bf-139">![Przycisk Ustawienia domyślne typu zadania konserwacji](media/am-guides-integration-job-defaults.png "Przycisk Ustawienia domyślne typu zadania konserwacji")</span><span class="sxs-lookup"><span data-stu-id="c20bf-139">![Maintenance job type defaults button](media/am-guides-integration-job-defaults.png "Maintenance job type defaults button")</span></span>

    1. <span data-ttu-id="c20bf-140">Utwórz wiersz i wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c20bf-140">Create a line, and then select **Save**.</span></span>

        <span data-ttu-id="c20bf-141">![Tworzenie wiersza](media/am-guides-integration-add-line.png "Tworzenie wiersza")</span><span class="sxs-lookup"><span data-stu-id="c20bf-141">![Create a line](media/am-guides-integration-add-line.png "Create a line")</span></span>

    1. <span data-ttu-id="c20bf-142">W okienku akcji wybierz pozycję **Lista kontrolna konserwowanego składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="c20bf-142">On the Action Pane, select **Maintenance checklist**.</span></span>

        <span data-ttu-id="c20bf-143">![Przycisk Lista kontrolna konserwowanego składnika majątku](media/am-guides-integration-maintenance-checklist.png "Przycisk Lista kontrolna konserwowanego składnika majątku")</span><span class="sxs-lookup"><span data-stu-id="c20bf-143">![Maintenance checklist button](media/am-guides-integration-maintenance-checklist.png "Maintenance checklist button")</span></span>

    1. <span data-ttu-id="c20bf-144">Na skróconej karcie **Wiersze listy kontrolnej konserwowanego składnika majątku** dodaj wiersz, a następnie zmień wartość w polu **Typ** na **Szablon**.</span><span class="sxs-lookup"><span data-stu-id="c20bf-144">On the **Maintenance checklist lines** FastTab, add a line, and then change the value of the **Type** field to **Template**.</span></span>

        <span data-ttu-id="c20bf-145">![Zmienianie wartości typu](media/am-guides-integration-checklist-lines.png "Zmienianie wartości typu")</span><span class="sxs-lookup"><span data-stu-id="c20bf-145">![Change the Type value](media/am-guides-integration-checklist-lines.png "Change the Type value")</span></span>

    1. <span data-ttu-id="c20bf-146">Na skróconej karcie **Szczegóły wiersza** w polu **Szablon** wybierz szablon, z którym został skojarzony przewodnik, a następnie wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c20bf-146">On the **Line details** FastTab, in the **Template** field, select the template that you associated the guide with, and then select **Save**.</span></span>

        <span data-ttu-id="c20bf-147">![Wybieranie szablonu](media/am-guides-integration-checklist-line-details.png "Wybieranie szablonu")</span><span class="sxs-lookup"><span data-stu-id="c20bf-147">![Select the template](media/am-guides-integration-checklist-line-details.png "Select the template")</span></span>

1. <span data-ttu-id="c20bf-148">[Utwórz zlecenie pracy](work-orders/manually-created-workorders.md#create-work-order), a następnie wybierz typ zadania konserwacji, w którym jest używany szablon listy kontrolnej konserwowanego składnika majątku, z którym skojarzono dany przewodnik.</span><span class="sxs-lookup"><span data-stu-id="c20bf-148">[Create a work order](work-orders/manually-created-workorders.md#create-work-order), and then select the maintenance job type that uses the maintenance checklist template that you associated the guide with.</span></span> <span data-ttu-id="c20bf-149">Przewodnik zostanie automatycznie skojarzony ze zleceniem pracy.</span><span class="sxs-lookup"><span data-stu-id="c20bf-149">The guide is automatically associated with the work order.</span></span>

    <span data-ttu-id="c20bf-150">![Wybieranie typu zadania konserwacji](media/am-guides-integration-create-work-order.png "Wybieranie typu zadania konserwacji")</span><span class="sxs-lookup"><span data-stu-id="c20bf-150">![Select a maintenance job type](media/am-guides-integration-create-work-order.png "Select a maintenance job type")</span></span>

1. <span data-ttu-id="c20bf-151">Wyświetl przewodnik skojarzony ze zleceniem pracy i pracownikami:</span><span class="sxs-lookup"><span data-stu-id="c20bf-151">View the guide that is associated with the work order and workers:</span></span>

    1. <span data-ttu-id="c20bf-152">Otwórz [obszar roboczy zarządzania składnikami majątku](asset-management-mobile-workspace.md), aby uzyskać dostęp do zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="c20bf-152">Open the [Asset management mobile workspace](asset-management-mobile-workspace.md) to access the work order.</span></span>
    1. <span data-ttu-id="c20bf-153">[Otwórz listę kontrolną konserwowanego składnika majątku](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) dla zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="c20bf-153">[Open the maintenance checklist](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) for the work order.</span></span>
    1. <span data-ttu-id="c20bf-154">Wybierz wiersz listy kontrolnej, aby wyświetlić skojarzony przewodnik.</span><span class="sxs-lookup"><span data-stu-id="c20bf-154">Select a checklist line to see the associated guide.</span></span>

        <span data-ttu-id="c20bf-155">![Przewodnik skojarzony z wierszem listy kontrolnej](media/am-guides-integration-show-guide.png "Przewodnik skojarzony z wierszem listy kontrolnej")</span><span class="sxs-lookup"><span data-stu-id="c20bf-155">![Guide associated with a checklist line](media/am-guides-integration-show-guide.png "Guide associated with a checklist line")</span></span>

    1. <span data-ttu-id="c20bf-156">Otwórz przewodnik na urządzeniu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c20bf-156">Open the guide on HoloLens.</span></span>

        <span data-ttu-id="c20bf-157">![Otwieranie przewodnika na urządzeniu HoloLens](media/am-guides-integration-hololens-select.png "Otwieranie przewodnika na urządzeniu HoloLens")</span><span class="sxs-lookup"><span data-stu-id="c20bf-157">![Open the guide on HoloLens](media/am-guides-integration-hololens-select.png "Open the guide on HoloLens")</span></span>

> [!NOTE]
> <span data-ttu-id="c20bf-158">Można również skojarzyć przewodnik bezpośrednio z listą kontrolną konserwowanego składnika majątku zlecenia pracy lub typu pracy.</span><span class="sxs-lookup"><span data-stu-id="c20bf-158">You can also associate a guide directly in the maintenance checklist of a work order or a job type.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c20bf-159">Znany jest problem polegający na tym, że w przypadku skojarzenia szablonu listy kontrolnej konserwowanego składnika majątku z domyślnym typem zadania konserwacji przewodnik połączony z szablonem nie jest wyświetlany na skróconej karcie **Skojarzone przewodniki** strony **Ustawienia domyślne typu zadania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="c20bf-159">There is a known issue where, when you associate a maintenance checklist template with a default maintenance job type, the guide that is linked to the template doesn't appear on the **Associated guides** FastTab of the **Maintenance job type defaults** page.</span></span> <span data-ttu-id="c20bf-160">Jednak przewodnik będzie wyświetlany po zastosowaniu tego typu zadania do zlecenia pracy na skróconej karcie **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="c20bf-160">However, the guide will appear after that job type is applied to a work order on the **Associated guides** FastTab.</span></span>

## <a name="see-also"></a><span data-ttu-id="c20bf-161">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="c20bf-161">See also</span></span>

- [<span data-ttu-id="c20bf-162">Przegląd o podwójnym zapisie</span><span class="sxs-lookup"><span data-stu-id="c20bf-162">Dual-write overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [<span data-ttu-id="c20bf-163">Omówienie zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="c20bf-163">Asset management overview</span></span>](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]