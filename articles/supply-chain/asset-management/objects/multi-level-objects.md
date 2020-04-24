---
title: Wielopoziomowe składniki majątku
description: W tym temacie wyjaśniono, jak tworzyć i usuwać wielopoziomowe składniki majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b7609a85f0315ee5cb5fae62d151b271ef5febe
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214898"
---
# <a name="multi-level-assets"></a><span data-ttu-id="429d5-103">Wielopoziomowe składniki majątku</span><span class="sxs-lookup"><span data-stu-id="429d5-103">Multi-level assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="429d5-104">W tym temacie wyjaśniono, jak tworzyć i usuwać wielopoziomowe składniki majątku.</span><span class="sxs-lookup"><span data-stu-id="429d5-104">This topic explains how to create and delete multi-level assets.</span></span> <span data-ttu-id="429d5-105">Składniki majątku i powiązane z nimi składniki podrzędne można tworzyć w hierarchicznej strukturze drzewa.</span><span class="sxs-lookup"><span data-stu-id="429d5-105">You can create assets and related sub-assets in a hierarchical tree structure.</span></span> <span data-ttu-id="429d5-106">W ten sposób można wyświetlać relacje i zależności między zasobami.</span><span class="sxs-lookup"><span data-stu-id="429d5-106">In this way, you can show relations and dependencies among assets.</span></span> <span data-ttu-id="429d5-107">Zadania konserwacji mogą być powiązane ze wszystkimi poziomami struktury drzewa.</span><span class="sxs-lookup"><span data-stu-id="429d5-107">Maintenance jobs can be related to all levels of the tree structure.</span></span> <span data-ttu-id="429d5-108">Statystyki mogą być również tworzone dla indywidualnego poziomu lub jako suma wszystkich poziomów podrzędnych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="429d5-108">Statistics can also be created for an individual level or as a sum of all sub-asset levels.</span></span>

<span data-ttu-id="429d5-109">Na stronie listy **Wszystkie składniki majątku** (**Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki**) kolumna **Składnik majątku** zawiera listę składników majątku w porządku hierarchicznym.</span><span class="sxs-lookup"><span data-stu-id="429d5-109">On the **All Assets** list page (**Asset management** \> **Common** \> **Assets** \> **All assets**), the **Asset** column lists assets in hierarchical order.</span></span> <span data-ttu-id="429d5-110">Kolumna **Nadrzędny** pokazuje pokrewny składnik nadrzędny.</span><span class="sxs-lookup"><span data-stu-id="429d5-110">The **Parent** column shows the related parent.</span></span> <span data-ttu-id="429d5-111">Ponadto jeśli składnik majątku i składnik podrzędny zostały utworzone , sekcja **Drzewo składników majątku** w okienku **Powiązane informacje** pokazuje składniki majątku w strukturze drzewa.</span><span class="sxs-lookup"><span data-stu-id="429d5-111">Additionally, if assets and sub-assets have already been created, the **Asset tree** section in the **Related information** pane shows the assets in a tree structure.</span></span>

<span data-ttu-id="429d5-112">Aby uzyskać więcej informacji o tworzeniu składnika majątku, zobacz temat [Tworzenie składnika majątku](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="429d5-112">For information about how to create an asset, see [Create an asset](../objects/create-an-object.md).</span></span> <span data-ttu-id="429d5-113">Aby utworzyć podrzędny składnik majątku, wybierz nadrzędny składnik majątku w polu **Nadrzędny** na skróconej karcie **Ogólne.**</span><span class="sxs-lookup"><span data-stu-id="429d5-113">To create a sub-asset, select the parent asset in the **Parent** field on the **General** FastTab.</span></span>

## <a name="copy-an-asset-or-asset-structure"></a><span data-ttu-id="429d5-114">Kopiowanie składnika majątku lub struktury składników majątku</span><span class="sxs-lookup"><span data-stu-id="429d5-114">Copy an asset or asset structure</span></span>

<span data-ttu-id="429d5-115">Jeśli firma ma kilka podobnych struktur składników majątku, można użyć funkcji Kopiuj w module Zarządzanie składnikami majątku, aby szybko je utworzyć.</span><span class="sxs-lookup"><span data-stu-id="429d5-115">If your company has several similar asset structures, you can use the Copy function in Asset Management to quickly create them.</span></span>

1. <span data-ttu-id="429d5-116">Wybierz kolejno **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="429d5-116">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="429d5-117">Na stronie listy **Wszystkie składniki majątku** wybierz składnik majątku do skopiowania.</span><span class="sxs-lookup"><span data-stu-id="429d5-117">On the **All assets** list page, select the asset to copy.</span></span> <span data-ttu-id="429d5-118">Jeśli na przykład chcesz skopiować całą strukturę składników majątku, w tym podrzędne składniki majątku, wybierz nadrzędny składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="429d5-118">For example, if you want to copy the whole asset structure, including sub-assets, select a parent asset.</span></span>
3. <span data-ttu-id="429d5-119">Wybierz **Kopiuj składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="429d5-119">Select **Copy asset**.</span></span> <span data-ttu-id="429d5-120">W sekcji **Kopiuj z** pole **Składnik majątku** jest ustawione na składnik majątku wybrany na stronie listy.</span><span class="sxs-lookup"><span data-stu-id="429d5-120">In the **Copy from** section, the **Asset** field is set to the asset that you selected on the list page.</span></span>
4. <span data-ttu-id="429d5-121">W sekcji **Kopiuj do** w polu **Składnik majątku** wprowadź nazwę nowego składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="429d5-121">In the **Copy to** section, in the **Asset** field, enter the name of the new asset.</span></span>
5. <span data-ttu-id="429d5-122">Jeśli składnik majątku, który tworzysz powinien być częścią istniejącej struktury składników majątku, w sekcji **Nadrzędny składnik majątku** w polu **Składnik majątku** wybierz identyfikator nadrzędny.</span><span class="sxs-lookup"><span data-stu-id="429d5-122">If the asset that you're creating should be part of an existing asset structure, in the **Parent asset** section, in the **Asset** field, select a parent ID.</span></span>
6. <span data-ttu-id="429d5-123">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="429d5-123">Select **OK**.</span></span> <span data-ttu-id="429d5-124">Nowa struktura składników majątku jest wyświetlana na stronie listy **Wszystkie składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="429d5-124">The new asset structure is shown on the **All assets** list page.</span></span> <span data-ttu-id="429d5-125">Wszystkie atrybuty składników majątku, plany konserwacji i serie czynności konserwacyjnych związane ze skopiowanym składnikiem majątku są przenoszone do nowego składnika majątku lub nowej struktury składników majątku.</span><span class="sxs-lookup"><span data-stu-id="429d5-125">All asset attributes, maintenance plans, and maintenance rounds that are related to the asset that you copied are transferred to the new asset or asset structure.</span></span>

<span data-ttu-id="429d5-126">Podczas kopiowania struktury składników majątku, podrzędny składnik majątku w nowej strukturze ma taką samą nazwę jak podrzędny składnik majątku, który został skopiowane.</span><span class="sxs-lookup"><span data-stu-id="429d5-126">When you copy an asset structure, the sub-assets in the new structure have the same name as the sub-assets that you copied.</span></span> <span data-ttu-id="429d5-127">Po zakończeniu procedury kopiowania można łatwo zmienić nazwę i inne ustawienia dla składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="429d5-127">After the copy procedure is completed, you can easily change the name and other settings for an asset.</span></span> <span data-ttu-id="429d5-128">Wybierz składnik majątku na stronie listy **Wszystkie składniki majątku**, a następnie wybierz przycisk **Edytuj.**</span><span class="sxs-lookup"><span data-stu-id="429d5-128">Select the asset on the **All assets** list page, and then select the **Edit** button.</span></span>

> [!NOTE]
> <span data-ttu-id="429d5-129">Podczas kopiowania składnika majątku lub struktury składników majątku stan cyklu życia nowych składników majątku jest resetowany do dowolnego stanu zdefiniowanego jako początkowy stan cyklu życia składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="429d5-129">When you copy an asset or asset structure, the lifecycle state of the new assets is reset to whatever state you defined as the initial lifecycle state for assets.</span></span> <span data-ttu-id="429d5-130">Lokalizacja czynności konserwacyjnych jest resetowana do domyślnej lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="429d5-130">The functional location is reset to the default functional location.</span></span>

## <a name="delete-an-asset-or-asset-structure"></a><span data-ttu-id="429d5-131">Usuwanie składnika majątku lub struktury składników majątku</span><span class="sxs-lookup"><span data-stu-id="429d5-131">Delete an asset or asset structure</span></span>

<span data-ttu-id="429d5-132">Jeśli składnik majątku ma powiązane podrzędne składniki majątku, można go usunąć tylko wtedy, gdy żadne żądania konserwacji, zadania zlecenia pracy, rejestracje błędów ani oceny warunków nie są rejestrowane na żadnym ze składników majątku.</span><span class="sxs-lookup"><span data-stu-id="429d5-132">If an asset has related sub-assets, you can delete it only if no maintenance requests, work order jobs, fault registrations, or condition assessments are registered on any of the assets.</span></span>

1. <span data-ttu-id="429d5-133">Na stronie listy **Wszystkie składniki majątku** wybierz składnik majątku do usunięcia.</span><span class="sxs-lookup"><span data-stu-id="429d5-133">On the **All assets** list page, select the asset to delete.</span></span>
2. <span data-ttu-id="429d5-134">Wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="429d5-134">Select **Delete**.</span></span>

> [!NOTE]
> <span data-ttu-id="429d5-135">Jeśli nie można usunąć składnika majątku przy użyciu tej procedury, innym sposobem obsługi usuwania jest Konfigurowanie stanu cyklu życia składnika majątku w tym celu.</span><span class="sxs-lookup"><span data-stu-id="429d5-135">If you can't delete an asset by using this procedure, another way to handle deletion is to set up an asset lifecycle state for this purpose.</span></span> <span data-ttu-id="429d5-136">Na przykład można skonfigurować stan cyklu życia jako **Uznany za odpadki** lub **Usunięty** na stronie **Stany cyklu życia składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="429d5-136">For example, you can set up a **Scrapped** or **Deleted** lifecycle state on the **Asset lifecycle states** page.</span></span>
