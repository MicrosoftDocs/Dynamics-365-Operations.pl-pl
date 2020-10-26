---
title: Tworzenie nowego produktu
description: W tym temacie opisano sposób tworzenia nowego udostępnionego produktu.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a4745fe4fc44f85bcfd388ee573f5a6d0cd8519
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986175"
---
# <a name="create-a-new-product"></a><span data-ttu-id="ef270-103">Tworzenie nowego produktu</span><span class="sxs-lookup"><span data-stu-id="ef270-103">Create a new product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ef270-104">W tym temacie opisano sposób tworzenia nowego udostępnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="ef270-104">This topic describes how to create a new shared product.</span></span> <span data-ttu-id="ef270-105">Zwykle robi to projektant produktów.</span><span class="sxs-lookup"><span data-stu-id="ef270-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="ef270-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ef270-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-product"></a><span data-ttu-id="ef270-107">Tworzenie produktu</span><span class="sxs-lookup"><span data-stu-id="ef270-107">Create a product</span></span>
1. <span data-ttu-id="ef270-108">W okienku nawigacji przejdź do opcji **Moduły > Zarządzanie informacjami o produktach > Produkty > Produkty**.</span><span class="sxs-lookup"><span data-stu-id="ef270-108">In the Navigation pane, go to **Modules > Product information management > Products > Products**.</span></span>
2. <span data-ttu-id="ef270-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ef270-109">Select **New**.</span></span>
3. <span data-ttu-id="ef270-110">W polu **Numer produktu** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef270-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="ef270-111">Jeśli dla numeru produktu nie skonfigurowano sekwencji identyfikatorów, należy ją wprowadzić ręcznie.</span><span class="sxs-lookup"><span data-stu-id="ef270-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
4. <span data-ttu-id="ef270-112">W polu **Nazwa produktu** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ef270-112">In the **Product name** field, type a value.</span></span> <span data-ttu-id="ef270-113">Nazwa produktu jest domyślnie aliasem.</span><span class="sxs-lookup"><span data-stu-id="ef270-113">The product name defaults to the search name.</span></span> <span data-ttu-id="ef270-114">W razie potrzeby można to zmienić.</span><span class="sxs-lookup"><span data-stu-id="ef270-114">You can change this if needed.</span></span>  
5. <span data-ttu-id="ef270-115">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef270-115">Select **OK**.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="ef270-116">Konfigurowanie grup wymiarów</span><span class="sxs-lookup"><span data-stu-id="ef270-116">Set up dimension groups</span></span>
1. <span data-ttu-id="ef270-117">Wybierz **Grupy wymiarów**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ef270-117">Select **Dimension groups** to open the drop dialog.</span></span>
2. <span data-ttu-id="ef270-118">W polu **Grupa wymiaru magazynowania** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef270-118">In the **Storage dimension group** field, enter or select a value.</span></span> <span data-ttu-id="ef270-119">Grupa wymiarów magazynowania określa, które wymiary magazynowania należy wprowadzić w każdej transakcji produktu i jak będą one śledzone w zapasach.</span><span class="sxs-lookup"><span data-stu-id="ef270-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="ef270-120">W polu **Grupa wymiaru śledzenia** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ef270-120">In the **Tracking dimension group** field, enter or select a value.</span></span> <span data-ttu-id="ef270-121">Grupa wymiarów śledzenia określa, które wymiary śledzenia należy wprowadzić dla każdej transakcji produktu i jak będą one obsługiwane w zapasach.</span><span class="sxs-lookup"><span data-stu-id="ef270-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="ef270-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef270-122">Select **OK**.</span></span>

