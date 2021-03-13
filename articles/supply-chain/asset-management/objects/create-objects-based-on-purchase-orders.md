---
title: Tworzenie składników majątku na podstawie zamówień zakupu
description: W tym temacie wyjaśniono, w jaki sposób można utworzyć listę pozycji składników majątku, które mogą służyć jako podstawa do tworzenia składników majątku dla zadań konserwacyjnych w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectItem, EntAssetPendingAssets
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 83419fa5c6b6aee0b321c526565c3518deaf4bd0
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016991"
---
# <a name="create-assets-based-on-purchase-orders"></a><span data-ttu-id="e06ac-103">Tworzenie składników majątku na podstawie zamówień zakupu</span><span class="sxs-lookup"><span data-stu-id="e06ac-103">Create assets based on purchase orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e06ac-104">W tym temacie wyjaśniono, w jaki sposób można utworzyć listę pozycji składników majątku, które mogą służyć jako podstawa do tworzenia składników majątku dla zadań konserwacyjnych w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-104">This topic explains how you can create a list of asset items that can be used as a basis for creating assets for maintenance jobs in Asset Management.</span></span> <span data-ttu-id="e06ac-105">Na podstawie pozycji składników majątku można wyświetlić listę wierszy zamówienia zakupu, które zostały utworzone dla tych pozycji.</span><span class="sxs-lookup"><span data-stu-id="e06ac-105">Based on the asset items, you are able to view a list of the purchase order lines that have been created on those items.</span></span> <span data-ttu-id="e06ac-106">Celem tej funkcji jest łatwe tworzenie składnika majątku w module Zarządzanie składnikami majątku na podstawie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="e06ac-106">The purpose of this functionality is to easily create an asset in Asset Management based on a purchase order.</span></span>

<span data-ttu-id="e06ac-107">Najpierw należy skonfigurować pozycje, które mają być używane do tworzenia składników majątku z zamówienia zakupu w obszarze **Pozycje składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-107">First, you set up the items to be used for creating assets from a purchase order in **Asset items**.</span></span> <span data-ttu-id="e06ac-108">Po utworzeniu wiersza zamówienia zakupu należy utworzyć składniki majątku w obszarze **Oczekujące składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-108">After creating a purchase order line, you create the assets in **Pending assets**.</span></span> <span data-ttu-id="e06ac-109">Można zdecydować, na którym etapie zamówienia zakupu ma zostać utworzony składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-109">It is possible to decide at which stage of the purchase order the asset should be created.</span></span>


## <a name="select-asset-items"></a><span data-ttu-id="e06ac-110">Wybieranie pozycji składnika majątku</span><span class="sxs-lookup"><span data-stu-id="e06ac-110">Select asset items</span></span>

1. <span data-ttu-id="e06ac-111">Kliknij **Zarządzanie składnikami majątku** > **Ustawienia** > **Składniki majątku** > **Pozycje**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-111">Click **Asset management** > **Setup** > **Assets** > **Items**.</span></span>
2. <span data-ttu-id="e06ac-112">Kliknij przycisk **Nowy**, aby utworzyć nową pozycję składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-112">Click **New** to create a new asset item.</span></span>
3. <span data-ttu-id="e06ac-113">Wybierz pozycję w polu **Kod pozycji**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-113">Select the item in the **Item number** field.</span></span> <span data-ttu-id="e06ac-114">Po opuszczeniu tego pola nazwa pozycji jest automatycznie wstawiana w polu **Nazwa produktu**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-114">When you leave that field, the item name is automatically inserted in the **Product name** field.</span></span>
4. <span data-ttu-id="e06ac-115">Na karcie skróconej **Ogólne** wybierz typ składnika majątku dla pozycji.</span><span class="sxs-lookup"><span data-stu-id="e06ac-115">On the **General** FastTab, select an asset type for the item.</span></span>
5. <span data-ttu-id="e06ac-116">Wybierz producenta i model składnika majątku dla pozycji.</span><span class="sxs-lookup"><span data-stu-id="e06ac-116">Select asset manufacturer and model for the item.</span></span>
6. <span data-ttu-id="e06ac-117">Zapisz pozycję.</span><span class="sxs-lookup"><span data-stu-id="e06ac-117">Save the item.</span></span>


## <a name="create-assets-from-pending-assets"></a><span data-ttu-id="e06ac-118">Tworzenie składników majątku z oczekujących pozycji</span><span class="sxs-lookup"><span data-stu-id="e06ac-118">Create assets from pending assets</span></span>

1. <span data-ttu-id="e06ac-119">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Oczekujące składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-119">Click **Asset management** > **Common** > **Assets** > **Pending Assets**.</span></span>
2. <span data-ttu-id="e06ac-120">Zostanie wyświetlona zaktualizowana lista zamówień zakupu na podstawie pozycji wybranych w obszarze **Pozycje składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-120">You will see an updated list of the purchase orders based on the items selected in **Asset items**.</span></span>
3. <span data-ttu-id="e06ac-121">Można filtrować stany zamówień zakupu w celu wybrania stanu cyklu życia, w którym ma zostać utworzony składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-121">You can filter the status of purchase orders to select at which lifecycle state the asset should be created.</span></span> <span data-ttu-id="e06ac-122">Na przykład czasami trzeba utworzyć składnik majątku tylko w kontekście zaksięgowania przyjęcia produktu na zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="e06ac-122">For example, you may only want to create assets when a product receipt has been posted on a purchase order.</span></span>
4. <span data-ttu-id="e06ac-123">Wybierz link **Numer odwołania** w wierszu zamówienia zakupu, aby wyświetlić szczegółowe informacje na temat pozycji.</span><span class="sxs-lookup"><span data-stu-id="e06ac-123">Select the **Reference number** link on a purchase order line to view detailed information about the item.</span></span>
5. <span data-ttu-id="e06ac-124">Jeśli chcesz edytować wymiary, które mają być wyświetlane na skróconej karcie **Wymiary magazynowe**, kliknij przycisk **Wyświetl wymiary** i wybierz odpowiednie opcje.</span><span class="sxs-lookup"><span data-stu-id="e06ac-124">If you want to edit which dimensions are displayed on the **Inventory dimensions** FastTab, click the **Display Dimensions** button, and make your selections.</span></span>
6. <span data-ttu-id="e06ac-125">Jeśli składnik majątku ma zostać utworzony na podstawie wiersza zamówienia zakupu, zaznacz pole wyboru w kolumnie **Zaznacz** dla tego wiersza na stronie listy i kliknij przycisk **Utwórz składniki majątku**</span><span class="sxs-lookup"><span data-stu-id="e06ac-125">If you want to create an asset based on a purchase order line, select the check box in the **Mark** column for that line on the list page, and click **Create assets**.</span></span> <span data-ttu-id="e06ac-126">Zostanie wyświetlony komunikat z informacją o identyfikatorze składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-126">A message will be displayed informing you of the asset ID.</span></span>
7. <span data-ttu-id="e06ac-127">Wybierz składnik majątku na liście **Wszystkie składniki majątku** i kliknij przycisk **Edytuj**, aby dodać więcej informacji do składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-127">Select the asset in the **All assets** list and click **Edit** to add more information to the asset.</span></span>
8. <span data-ttu-id="e06ac-128">W obszarze **Oczekujących składniki majątku**, jeśli chcesz usunąć wiersz, ponieważ nie chcesz tworzyć składnika majątku, zaznacz pole wyboru w kolumnie **Oznacz** dla tego wiersza i kliknij przycisk **Odrzuć oczekujące składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-128">In **Pending assets**, if you want to delete a line because you don't want to create an asset, select the check box in the **Mark** column for that line, and click **Discard pending assets**.</span></span> <span data-ttu-id="e06ac-129">Zostanie wyświetlony komunikat z informacją o identyfikatorze składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-129">A message will be displayed informing you of the asset ID.</span></span> <span data-ttu-id="e06ac-130">Nie usuwasz zamówienia zakupu ani zamówienia sprzedaży, tylko rekord, z którego utworzono składnik majątku w module **Zarządzanie składnikami majątku**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-130">You are not deleting the purchase order or sales order, just the record from which you could have created an asset in **Asset Management**.</span></span>

>[!NOTE]
><span data-ttu-id="e06ac-131">Wszystkie wymiary produktu (rozmiar, kolor, konfiguracja itp.) są automatycznie przenoszone do atrybutów składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-131">All product dimensions (size, color, configuration etc.) are automatically transferred to the asset attributes.</span></span> <span data-ttu-id="e06ac-132">Wymiary śledzenia (numer seryjny) są zapisywane bezpośrednio w składniku majątku w chwili jego utworzenia.</span><span class="sxs-lookup"><span data-stu-id="e06ac-132">Tracking dimensions (serial number) are stored directly on the asset when the asset is created.</span></span>


## <a name="find-pending-assets"></a><span data-ttu-id="e06ac-133">Znajdowanie oczekujących składników majątku</span><span class="sxs-lookup"><span data-stu-id="e06ac-133">Find pending assets</span></span>

<span data-ttu-id="e06ac-134">Można uruchomić zadanie **Liczba oczekujących składników majątku**, aby sprawdzić oczekujące składniki majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-134">You can run a **Pending asset count** to check for pending assets.</span></span> <span data-ttu-id="e06ac-135">Na przykład funkcja ta może być używana do odbierania powiadomień za każdym razem, gdy oczekujący składnik majątku jest gotowy do utworzenia jako składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-135">For example, this function can be used for receiving a notification each time a pending asset is ready to be created as an asset.</span></span>

1. <span data-ttu-id="e06ac-136">Kliknij **Zarządzanie składnikami majątku** > **Okresowe** > **Składniki majątku** > **Liczba oczekujących składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-136">Click **Asset management** > **Periodic** > **Assets** > **Pending asset count**.</span></span>
2. <span data-ttu-id="e06ac-137">Kliknij przycisk **OK**, aby uruchomić zadanie i zaktualizować listę w obszarze **oczekujące składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="e06ac-137">Click **OK** to run the job and update the list in **Pending assets**.</span></span>
3. <span data-ttu-id="e06ac-138">To zadanie można skonfigurować tak, aby było uruchamiane jako zadanie wsadowe, na przykład raz dziennie.</span><span class="sxs-lookup"><span data-stu-id="e06ac-138">You can set up this job to run as a batch job, for example, once each day.</span></span>

<span data-ttu-id="e06ac-139">**Uwaga:** Jeśli dane w zamówieniu zakupu zostały zmienione *po* utworzeniu składnika majątku na podstawie odpowiedniej pozycji, zmiany te nie zostaną odzwierciedlone w składniku majątku.</span><span class="sxs-lookup"><span data-stu-id="e06ac-139">**Caution:** If data is changed on a purchase order *after* you have created an asset based on the appertaining item, those changes will not be reflected on the asset.</span></span>
