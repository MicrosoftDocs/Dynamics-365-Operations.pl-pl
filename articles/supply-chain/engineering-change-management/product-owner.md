---
title: Właściciele produktów
description: Ten temat zawiera informacje dotyczące właścicieli produktów. Właściciele produktów to grupa użytkowników odpowiedzialnych za określone produkty. Tylko członkowie grupy mogą zwolnić te produkty. Właściciel produktu może być również używany w przepływie pracy zatwierdzania.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4308020d66995d857e547be47216cb82caacf035
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "4435672"
---
# <a name="product-owners"></a><span data-ttu-id="1beed-106">Właściciele produktów</span><span class="sxs-lookup"><span data-stu-id="1beed-106">Product owners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1beed-107">Właściciele produktu to grupa użytkowników odpowiedzialnych za określone produkty.</span><span class="sxs-lookup"><span data-stu-id="1beed-107">The product owner is a group of users who are responsible for specific products.</span></span> <span data-ttu-id="1beed-108">Gdy grupa właściciela produktu jest przypisana do produktu, tylko członkowie tej grupy mogą zwolnić produkt.</span><span class="sxs-lookup"><span data-stu-id="1beed-108">When a product owner group is assigned to a product, only the members of that group can release the product.</span></span> <span data-ttu-id="1beed-109">Właściciel produktu może być również używany w przepływie pracy zatwierdzania w zarządzaniu zmianami inżynieryjnymi.</span><span class="sxs-lookup"><span data-stu-id="1beed-109">The product owner can also be used in the approval workflow in engineering change management.</span></span>

<span data-ttu-id="1beed-110">Właściciele produktów są ustawieniami globalnymi.</span><span class="sxs-lookup"><span data-stu-id="1beed-110">Product owners are global settings.</span></span> <span data-ttu-id="1beed-111">Z tego względu są dostępne dla wszystkich firm.</span><span class="sxs-lookup"><span data-stu-id="1beed-111">Therefore, they are available to all legal entities.</span></span>

## <a name="create-a-product-owner-group"></a><span data-ttu-id="1beed-112">Tworzenie grupy właścicieli produktów</span><span class="sxs-lookup"><span data-stu-id="1beed-112">Create a product owner group</span></span>

<span data-ttu-id="1beed-113">Aby utworzyć grupę właścicieli produktów i dodać do niej członków, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1beed-113">To create a product owner group and add members to it, follow these steps.</span></span>

1. <span data-ttu-id="1beed-114">Przejdź do **Zarządzanie zmianami projektowymi \> Konfiguracja \> Właściciele produktów**.</span><span class="sxs-lookup"><span data-stu-id="1beed-114">Go to **Engineering change management \> Setup \> Product owners**.</span></span>
2. <span data-ttu-id="1beed-115">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="1beed-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="1beed-116">W polu **Właściciel produktu** wpisz opisową nazwę grupy produktów.</span><span class="sxs-lookup"><span data-stu-id="1beed-116">In the **Product owner** field, enter a name for the group.</span></span>
4. <span data-ttu-id="1beed-117">W polu **Nazwa** wprowadź krótki opis grupy.</span><span class="sxs-lookup"><span data-stu-id="1beed-117">In the **Name** field, enter a description of the group.</span></span>
5. <span data-ttu-id="1beed-118">Na skróconej karcie **Członkowie** dodaj pracowników, którzy powinni być członkami grupy.</span><span class="sxs-lookup"><span data-stu-id="1beed-118">On the **Members** FastTab, add the workers who should be members of the group.</span></span>

## <a name="assign-a-product-owner-to-a-product"></a><span data-ttu-id="1beed-119">Przypisz właściciela produktu do produktu</span><span class="sxs-lookup"><span data-stu-id="1beed-119">Assign a product owner to a product</span></span>

<span data-ttu-id="1beed-120">Aby przypisać właściciela produktu do produktu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1beed-120">To assign a product owner to a product, follow these steps.</span></span>

1. <span data-ttu-id="1beed-121">Otwórz stronę **Szczegóły produktu** odpowiedniego produktu lub produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="1beed-121">Open the **Product details** page for the relevant product or product master.</span></span>
1. <span data-ttu-id="1beed-122">Na skróconej karcie **Ogólnym** w polu **Właściciel produktu** należy określić nazwę odpowiedniej grupy właścicieli produktów.</span><span class="sxs-lookup"><span data-stu-id="1beed-122">On the **General** FastTab, set the **Product owner** field to the name of the relevant product owner group.</span></span>

<span data-ttu-id="1beed-123">Gdy właściciel produktu jest przypisany do produktu, tylko członkowie grupy właściciel produktu mogą edytować ustawienie **Właściciel produktu**.</span><span class="sxs-lookup"><span data-stu-id="1beed-123">While a product owner is assigned to a product, only the members of the product owner group can edit the **Product owner** setting.</span></span>

<span data-ttu-id="1beed-124">Właściciel produktu jest również widoczny na stronie **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="1beed-124">The product owner is also visible on the **Released products** page.</span></span>

## <a name="product-owners-and-product-releases"></a><span data-ttu-id="1beed-125">Właściciele produktów i zwolnienia produktów</span><span class="sxs-lookup"><span data-stu-id="1beed-125">Product owners and product releases</span></span>

<span data-ttu-id="1beed-126">Tylko użytkownicy z grupy „właściciel produktu” mogą zwolnić ten produkt.</span><span class="sxs-lookup"><span data-stu-id="1beed-126">Only users from a product's product owner group can release that product.</span></span> <span data-ttu-id="1beed-127">Istnieje jednak wyjątek, gdy produkt jest elementem podrzędnym, a jego element nadrzędny jest zwalniany przez właściciela elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="1beed-127">However, there is an exception when the product is a child item, and its parent is released by the parent's owner.</span></span> <span data-ttu-id="1beed-128">Innymi słowy, jeśli produkt jest częścią BOM innego produktu, system nie sprawdza właściciela produktu dla każdej pozycji w BOM.</span><span class="sxs-lookup"><span data-stu-id="1beed-128">In other words, if the product is part of the BOM of another product, the system doesn't check the product owner of each item in the BOM.</span></span> <span data-ttu-id="1beed-129">Sprawdza tylko właściciela produktu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="1beed-129">It checks only the product owner of the parent item.</span></span>

<span data-ttu-id="1beed-130">Na przykład produkt X jest przypisany do grupy właścicieli *Szafy projektowe*.</span><span class="sxs-lookup"><span data-stu-id="1beed-130">For example, product X is assigned to the *Design cabinets* product owner group.</span></span> <span data-ttu-id="1beed-131">Produkt X jest również częścią BOM produktu Y, który jest przypisany do grupy właścicieli produktów *Głośniki projektowe*.</span><span class="sxs-lookup"><span data-stu-id="1beed-131">Product X is also part of the BOM of product Y, which is assigned to the *Design Speakers* product owner group.</span></span> <span data-ttu-id="1beed-132">Jeśli użytkownik z grupy właścicieli produktu *Głośniki projektowe* wyda produkt Y i jego BOM, produkt X zostanie zwolniony razem z produktem Y.</span><span class="sxs-lookup"><span data-stu-id="1beed-132">If a user from the *Design Speakers* product owner group releases product Y and its BOM, product X will be released together with product Y.</span></span>

## <a name="product-owners-and-approvals"></a><span data-ttu-id="1beed-133">Właściciele produktów i zatwierdzenia</span><span class="sxs-lookup"><span data-stu-id="1beed-133">Product owners and approvals</span></span>

<span data-ttu-id="1beed-134">Ponieważ właściciele produktów wiedzą, czy określone zmiany inżynieryjne przyniosą korzyści ich produktom, często warto uwzględnić je jako część procesu zatwierdzania w zarządzaniu zmianami inżynierskimi.</span><span class="sxs-lookup"><span data-stu-id="1beed-134">Because product owners know whether specific engineering changes will benefit their products, it often makes sense to include them as part of the approval process in engineering change management.</span></span> <span data-ttu-id="1beed-135">Możesz wdrożyć to podejście, ustawiając właścicieli produktów jako uczestniczących dostawców w przepływach pracy, które są używane do zarządzania zmianami inżynierskimi.</span><span class="sxs-lookup"><span data-stu-id="1beed-135">You can implement this approach by setting up the product owners as participant providers in the workflows that are used for engineering change management.</span></span> <span data-ttu-id="1beed-136">Następnie system przydzieli zadania zatwierdzania w przepływach pracy w oparciu o produkty objęte żądaniami zmian inżynieryjnych i zleceniami zmian inżynieryjnych.</span><span class="sxs-lookup"><span data-stu-id="1beed-136">The system will then assign approval tasks in the workflows, based on the products that are in engineering change requests and engineering change orders.</span></span> <span data-ttu-id="1beed-137">Aby uzyskać więcej informacji, zobacz [Zarządzanie zmianami dotyczącymi produktów inżynieryjnych](engineering-change-management.md).</span><span class="sxs-lookup"><span data-stu-id="1beed-137">For more information, see [Manage changes to engineering products](engineering-change-management.md).</span></span>
