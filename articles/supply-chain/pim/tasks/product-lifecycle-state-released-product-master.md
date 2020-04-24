---
title: Przypisywanie cyklu życia produktu do zwolnionego produktu głównego
description: W tej procedurze pokazano sposób przypisywania stanu cyklu życia produktu do zwolnionego produktu głównego i jego wariantów.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab8c4e02a064fe84446fa54cc05b9a6a902c1860
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213154"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="dd0a7-103">Przypisywanie cyklu życia produktu do zwolnionego produktu głównego</span><span class="sxs-lookup"><span data-stu-id="dd0a7-103">Assign a product lifecycle state to a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd0a7-104">W tej procedurze pokazano sposób przypisywania stanu cyklu życia produktu do zwolnionego produktu głównego i jego wariantów.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="dd0a7-105">Warunek wstępny: przed odtworzeniem tego przewodnika zadania należy najpierw odtworzyć przewodnik zadania „Tworzenie nowego stanu cyklu życia produktu”, aby się upewnić, że dostępny jest co najmniej jeden utworzony stan cyklu życia produktu.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="dd0a7-106">Znajdowanie zwolnionego produktu głównego</span><span class="sxs-lookup"><span data-stu-id="dd0a7-106">Find a released product master</span></span>
1. <span data-ttu-id="dd0a7-107">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="dd0a7-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="dd0a7-109">Produkt główny zawiera podtyp produktu Produkt główny.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="dd0a7-110">Aktualizacja stan cyklu życia</span><span class="sxs-lookup"><span data-stu-id="dd0a7-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="dd0a7-111">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-111">Click Edit.</span></span>
2. <span data-ttu-id="dd0a7-112">W polu Stan cyklu życia produktu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="dd0a7-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-113">Click Save.</span></span>
4. <span data-ttu-id="dd0a7-114">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="dd0a7-115">W przypadku zaznaczenia opcji Tak wszystkie powiązane zwolnione warianty produktu o takim samym stanie początkowym, jak zwolniony produkt główny, również zostaną zaktualizowane z godnie z nowym stanem cyklu życia produktu.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="dd0a7-116">W przypadku zaznaczenie opcji Nie wszystkie warianty zachowają swój rzeczywisty stan.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="dd0a7-117">Warianty ze stanem cyklu życia produktu innym niż stan zwolnionego produktu głównego nie zostaną zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="dd0a7-118">Sprawdzanie stan cyklu życia wariantów</span><span class="sxs-lookup"><span data-stu-id="dd0a7-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="dd0a7-119">Kliknij warianty zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="dd0a7-120">Należy zauważyć, że wszystkie warianty odziedziczyły wybrany stan cyklu życia ze zwolnionego produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="dd0a7-121">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="dd0a7-122">W polu Stan cyklu życia produktu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-122">In the Product lifecycle state field, enter or select a value.</span></span>

