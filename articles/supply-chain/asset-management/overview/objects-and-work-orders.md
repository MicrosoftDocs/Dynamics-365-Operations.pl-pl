---
title: Składniki majątku i zlecenia pracy
description: W tym temacie opisano składniki majątku i zlecenia pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0cddb0a25286c8ce9d72aef0b835809705ad577a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020946"
---
# <a name="assets-and-work-orders"></a><span data-ttu-id="d75f7-103">Składniki majątku i zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="d75f7-103">Assets and work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d75f7-104">W tym temacie opisano składniki majątku i zlecenia pracy w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="d75f7-104">This topic describes assets and work orders in Asset Management.</span></span> <span data-ttu-id="d75f7-105">Składniki majątku i zlecenia pracy są centralnymi częściami modułu Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="d75f7-105">Assets and work orders are the central parts of Asset Management.</span></span> <span data-ttu-id="d75f7-106">*Składnik majątku* jest maszyną lub częścią maszyny, która wymaga ciągłej konserwacji i serwisowania.</span><span class="sxs-lookup"><span data-stu-id="d75f7-106">An *asset* is a machine or machine part that requires continuous maintenance and service.</span></span> <span data-ttu-id="d75f7-107">Składniki majątku mogą być tworzone w strukturze hierarchicznej i mogą być powiązane z lokalizacjami czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="d75f7-107">Assets can be created in a hierarchical structure, and they can be related to functional locations.</span></span> <span data-ttu-id="d75f7-108">Zadania konserwacji mogą być planowane na wszystkich poziomach struktury składników majątku.</span><span class="sxs-lookup"><span data-stu-id="d75f7-108">Maintenance jobs can be planned at all levels in the asset structure.</span></span>

<span data-ttu-id="d75f7-109">Dla każdego składnika majątku są skonfigurowane różne dane, takie jak informacje o produkcie i specyfikacja składnika majątku oraz wymagane plany konserwacji.</span><span class="sxs-lookup"><span data-stu-id="d75f7-109">Various data, such as product information and asset specification, and required maintenance plans are set up on each asset.</span></span> <span data-ttu-id="d75f7-110">Poniższa ilustracja przedstawia omówienie danych o składnikach majątku i przynależności składników majątku do typów zadań.</span><span class="sxs-lookup"><span data-stu-id="d75f7-110">The following illustration shows an overview of asset data and the affiliation of assets to job types.</span></span> <span data-ttu-id="d75f7-111">Czerwony tekst jest używany dla przykładów, które pokazują dziedziczenie i zależności.</span><span class="sxs-lookup"><span data-stu-id="d75f7-111">Red text is used for examples that show inheritance and dependencies.</span></span>

![Diagram pokazujący dane elementów składnika majątku powiązane z typami stanowisk](media/05-overview-image.png)

<span data-ttu-id="d75f7-113">Każde zlecenie pracy ma typ zlecenia, np. konserwacja zapobiegawcza, konserwacja naprawcza lub inspekcja.</span><span class="sxs-lookup"><span data-stu-id="d75f7-113">Every work order has a work order type, such preventive maintenance, corrective maintenance, or inspection.</span></span> <span data-ttu-id="d75f7-114">Zlecenie pracy zawiera jedno lub więcej zadań zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d75f7-114">The work order contains one or more work order jobs.</span></span> <span data-ttu-id="d75f7-115">Każde zadanie zlecenia pracy definiuje zadanie, które należy wykonać na składniku majątku i pokrewnym typie zadania.</span><span class="sxs-lookup"><span data-stu-id="d75f7-115">Every work order job defines a job that must be performed on an asset and a related job type.</span></span> <span data-ttu-id="d75f7-116">Przykłady powiązanych typów stanowisk obejmują remont po 10 000 km, 50 000 km, 1 roku oraz inspekcję bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="d75f7-116">Examples of related job types include 10,000 km, 50,000 km, 1-year overhaul, and safety inspection.</span></span> <span data-ttu-id="d75f7-117">Jedno zlecenie pracy może być powiązane z wieloma składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="d75f7-117">One work order can be related to multiple assets.</span></span>

<span data-ttu-id="d75f7-118">Na poniższej ilustracji przedstawiono omówienie kluczowych danych w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="d75f7-118">The following illustration shows an overview of the key data in a work order.</span></span>

![Diagram przedstawiający kluczowe dane w zleceniu pracy](media/06-overview-image.png)

<span data-ttu-id="d75f7-120">Zlecenie pracy może być powiązane z innym zamówieniem pracy, a typy zadań mogą zawierać kolejne zadania, tworzące zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="d75f7-120">A work order can be related to another work order, and job types can contain succeeding jobs that create a work order.</span></span> <span data-ttu-id="d75f7-121">Ogólnie, nie istnieją żadne zależności między zleceniami pracy.</span><span class="sxs-lookup"><span data-stu-id="d75f7-121">In general, there are no dependencies between work orders.</span></span> <span data-ttu-id="d75f7-122">Dzięki temu mogą one zmienić swój stan cyklu życia zlecenia pracy i mogą być planowane niezależnie od siebie.</span><span class="sxs-lookup"><span data-stu-id="d75f7-122">Therefore, they can change their work order lifecycle state and can be scheduled independently of each other.</span></span>

<span data-ttu-id="d75f7-123">Zlecenia pracy mogą być tworzone na różne sposoby, które odnoszą się do konserwacji korekcyjnej, zapobiegawczej lub reaktywnej.</span><span class="sxs-lookup"><span data-stu-id="d75f7-123">Work orders can be created in various ways that are related to corrective, preventive, or reactive maintenance.</span></span> <span data-ttu-id="d75f7-124">Można także ręcznie tworzyć zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d75f7-124">You can also create work orders manually.</span></span> <span data-ttu-id="d75f7-125">Na poniższej ilustracji przedstawiono omówienie procesu automatycznego lub ręcznego tworzenia zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="d75f7-125">The following illustration shows an overview of the process for automatic or manual creation of work orders.</span></span>

![Diagram pokazujący automatyczne lub ręczne tworzenie zleceń pracy](media/07-overview-image.png)

<span data-ttu-id="d75f7-127">Aby zaplanować i uruchomić zadanie konserwacji w zleceniu pracy, należy wykonać kilka czynności.</span><span class="sxs-lookup"><span data-stu-id="d75f7-127">Several steps must be completed when you want to schedule and run a maintenance job on a work order.</span></span> <span data-ttu-id="d75f7-128">Na poniższej ilustracji przedstawiono omówienie przetwarzania w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="d75f7-128">The following illustration shows an overview of the processing for a work order.</span></span>

![Diagram pokazujący przegląd przetwarzania zlecenia pracy](media/08-overview-image.png)

> [!NOTE]
> <span data-ttu-id="d75f7-130">Generalnie w trakcie pracy w Dynamics 365 Supply Chain Management i module **Zarządzania składnikami majątku** wybierz opcję **Nowy**, aby utworzyć nowy rekord, wybierz **Edytuj**, aby zaktualizować istniejący rekord, a następnie wybierz **Zapisz**, aby zapisać nowy lub edytować dane.</span><span class="sxs-lookup"><span data-stu-id="d75f7-130">In general, when you work in Dynamics 365 Supply Chain Management and the **Asset Management** module, you select **New** to create a new record, you select **Edit** to update an existing record, and you select **Save** to save new or edited data.</span></span>
