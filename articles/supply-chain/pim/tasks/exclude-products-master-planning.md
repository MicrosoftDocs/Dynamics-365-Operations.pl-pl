---
title: Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego
description: Ta procedura dotyczy tworzenia nowego cyklu życia produktu który wyklucza produkty z planowania głównego i obliczeń na poziomie BOM.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62de37b5a84a1771b77ef2566942b7ffe8895f16
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149948"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a><span data-ttu-id="c4c49-103">Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego</span><span class="sxs-lookup"><span data-stu-id="c4c49-103">Create a product lifecycle state to exclude products from Master planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c4c49-104">Ta procedura dotyczy tworzenia nowego cyklu życia produktu który wyklucza produkty z planowania głównego i obliczeń na poziomie BOM.</span><span class="sxs-lookup"><span data-stu-id="c4c49-104">This procedure shows how to create a new product lifecycle state that excludes the products from Master planning and BOM-level calculation.</span></span>


## <a name="create-an-obsolete-state"></a><span data-ttu-id="c4c49-105">Tworzenie stanu przestarzałego</span><span class="sxs-lookup"><span data-stu-id="c4c49-105">Create an obsolete state</span></span>
1. <span data-ttu-id="c4c49-106">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Ustawienia > Stan cyklu życia produktu.</span><span class="sxs-lookup"><span data-stu-id="c4c49-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="c4c49-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c4c49-107">Click New.</span></span>
3. <span data-ttu-id="c4c49-108">W polu Stan wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4c49-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="c4c49-109">W polu Jest aktywna dla planowania zaznacz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="c4c49-109">Select No in the Is active for planning field.</span></span>
5. <span data-ttu-id="c4c49-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c4c49-110">In the Description field, type a value.</span></span>

## <a name="associate-the-obsolete-state-to-a-released-product"></a><span data-ttu-id="c4c49-111">Kojarzenie stanu przestarzałego ze zwolnionym produktem</span><span class="sxs-lookup"><span data-stu-id="c4c49-111">Associate the obsolete state to a released product</span></span>
1. <span data-ttu-id="c4c49-112">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c4c49-112">Close the page.</span></span>
2. <span data-ttu-id="c4c49-113">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="c4c49-113">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="c4c49-114">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="c4c49-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="c4c49-115">Na przykład wyfiltruj według pola Wyszukaj nazwę, wprowadzając wartość „M00”.</span><span class="sxs-lookup"><span data-stu-id="c4c49-115">For example, filter on the Search name field with a value of 'M00'.</span></span>
4. <span data-ttu-id="c4c49-116">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="c4c49-116">Click Edit.</span></span>
5. <span data-ttu-id="c4c49-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c49-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="c4c49-118">W polu Stan cyklu życia produktu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4c49-118">In the Product lifecycle state field, enter or select a value.</span></span>

