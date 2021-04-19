---
title: Konfigurowanie hierarchii organizacyjnych
description: W tym temacie opisano sposób konfigurowania hierarchii organizacyjnych w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4238d1aa277bf2f1df30825ef20dbf3095d13ebc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800574"
---
# <a name="set-up-organization-hierarchies"></a><span data-ttu-id="82372-103">Konfigurowanie hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="82372-103">Set up organization hierarchies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="82372-104">W tym temacie opisano sposób konfigurowania hierarchii organizacyjnych w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="82372-104">This topic describes how to set up organization hierarchies in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="82372-105">Przed utworzeniem kanałów należy upewnić się, że zostały skonfigurowane hierarchie organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="82372-105">Before creating channels, you'll want to ensure you have set up your organization hierarchies.</span></span>

<span data-ttu-id="82372-106">Hierarchie organizacyjne umożliwiają przeglądanie i raportowanie działalności biznesowej z różnych perspektyw.</span><span class="sxs-lookup"><span data-stu-id="82372-106">You can use organization hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="82372-107">Można na przykład skonfigurować jedną hierarchię na potrzeby tworzenia raportów podatkowych, statutowych i ustawowych.</span><span class="sxs-lookup"><span data-stu-id="82372-107">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="82372-108">Następnie można ustawić inną hierarchię do raportowania informacji finansowych nie wymaganych przez prawo, ale używanych w raportach wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="82372-108">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span>

<span data-ttu-id="82372-109">Przed utworzeniem hierarchii organizacyjnej należy utworzyć organizacje.</span><span class="sxs-lookup"><span data-stu-id="82372-109">Before you create an organization hierarchy, you must create organizations.</span></span> <span data-ttu-id="82372-110">Aby uzyskać więcej informacji, zobacz zadania [Tworzenie firmy](channels-legal-entities.md) lub [Tworzenie jednostki operacyjnej](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="82372-110">For more information, see [Create legal entities](channels-legal-entities.md) or [Create operating units](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span></span>


<span data-ttu-id="82372-111">Aby uzyskać więcej informacji, zobacz następujące tematy.</span><span class="sxs-lookup"><span data-stu-id="82372-111">For more information, see the following topics.</span></span>
- [<span data-ttu-id="82372-112">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="82372-112">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="82372-113">Planowanie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="82372-113">Plan your organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="82372-114">Tworzenie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="82372-114">Create an organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a><span data-ttu-id="82372-115">Tworzenie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="82372-115">Create an organizational hierarchy</span></span>

<span data-ttu-id="82372-116">Aby utworzyć hierarchię organizacyjną, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="82372-116">To create an organizational hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="82372-117">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Hierarchie organizacyjne**.</span><span class="sxs-lookup"><span data-stu-id="82372-117">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="82372-118">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="82372-118">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="82372-119">Wprowadź wartość w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="82372-119">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="82372-120">W sekcji **Cel** wybierz **Przypisywanie celu**.</span><span class="sxs-lookup"><span data-stu-id="82372-120">In the **Purpose** section, select **Assign purpose**.</span></span>
1. <span data-ttu-id="82372-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="82372-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="82372-122">Wybierz cel, który zostanie przypisany do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="82372-122">Select a purpose to assign to your organization hierarchy.</span></span>
1. <span data-ttu-id="82372-123">W sekcji **Przypisane hierarchie** wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="82372-123">In the **Assigned hierarchies** section, select **Add**.</span></span>
1. <span data-ttu-id="82372-124">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="82372-124">In the list, mark the selected row.</span></span> <span data-ttu-id="82372-125">Znajdź właśnie utworzoną hierarchię.</span><span class="sxs-lookup"><span data-stu-id="82372-125">Find the hierarchy you just created.</span></span>
1. <span data-ttu-id="82372-126">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="82372-126">Select **OK**.</span></span>

<span data-ttu-id="82372-127">Poniższy rysunek przedstawia przykładową hierarchię organizacyjną utworzoną dla fikcyjnego zbioru sklepów „Adventure Works”.</span><span class="sxs-lookup"><span data-stu-id="82372-127">The following image shows an example organizational hierarchy created for a fictitious "Adventure Works" set of stores.</span></span>

![Przykład hierarchii organizacyjnej](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a><span data-ttu-id="82372-129">Dodawanie organizacji do hierarchii</span><span class="sxs-lookup"><span data-stu-id="82372-129">Add organizations to a hierarchy</span></span>

<span data-ttu-id="82372-130">Aby dodać organizację do hierarchii, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="82372-130">To add organizations to a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="82372-131">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="82372-131">In the list, find and select the desired record.</span></span> <span data-ttu-id="82372-132">Zaznacz hierarchię.</span><span class="sxs-lookup"><span data-stu-id="82372-132">Select your hierarchy.</span></span>
1. <span data-ttu-id="82372-133">Na okienku akcji wybierz opcję **Widok**.</span><span class="sxs-lookup"><span data-stu-id="82372-133">On the action pane, select **View**.</span></span>
1. <span data-ttu-id="82372-134">W razie potrzeby dodaj organizację.</span><span class="sxs-lookup"><span data-stu-id="82372-134">Add organizations, as necessary.</span></span>
1. <span data-ttu-id="82372-135">Aby dodać organizację, wybierz opcję **Edytuj**, a następnie wybierz opcję **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="82372-135">To add an organization, select **Edit** and then select **Insert**.</span></span> <span data-ttu-id="82372-136">Po zakończeniu wprowadzania zmian można zapisać wersję roboczą i opublikować zmiany.</span><span class="sxs-lookup"><span data-stu-id="82372-136">When you are done making changes you can save a draft and publish the changes.</span></span>

<span data-ttu-id="82372-137">Na poniższej karcie przedstawiono firmę dodaną w katalogu głównym hierarchii z czterema centrami kosztów dodanymi do kanałów „biurowych”, „gniazd”, „online” i „biura obsługi”.</span><span class="sxs-lookup"><span data-stu-id="82372-137">The following image shows a legal entity added at the hierarchy root with four cost centers added for "Mall", "Outlet", "Online" and "Call Center" channels.</span></span> <span data-ttu-id="82372-138">Do każdego z nich można dodać różne gniazda sieci sprzedaży, biura obsługi i kanały online.</span><span class="sxs-lookup"><span data-stu-id="82372-138">Various retail, call center and online channels can then be added to each.</span></span>

![Przykład projektanta hierarchii](media/hierarchy-designer.png)

## <a name="additional-resources"></a><span data-ttu-id="82372-140">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="82372-140">Additional resources</span></span>

[<span data-ttu-id="82372-141">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="82372-141">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="82372-142">Planowanie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="82372-142">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="82372-143">Tworzenie firm</span><span class="sxs-lookup"><span data-stu-id="82372-143">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="82372-144">Tworzenie jednostek operacyjnych</span><span class="sxs-lookup"><span data-stu-id="82372-144">Create operating units</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="82372-145">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="82372-145">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="82372-146">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="82372-146">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
