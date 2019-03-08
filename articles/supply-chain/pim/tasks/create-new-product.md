---
title: Tworzenie nowego produktu
description: To zadanie pokazuje sposób tworzenia nowego produktu udostępnionego.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a603d89749242a4c6039ab83da286ec6ab727d8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "328546"
---
# <a name="create-a-new-product"></a><span data-ttu-id="ed928-103">Tworzenie nowego produktu</span><span class="sxs-lookup"><span data-stu-id="ed928-103">Create a new product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ed928-104">To zadanie pokazuje sposób tworzenia nowego produktu udostępnionego.</span><span class="sxs-lookup"><span data-stu-id="ed928-104">This task shows how to create a new shared product.</span></span> <span data-ttu-id="ed928-105">Zwykle robi to projektant produktów.</span><span class="sxs-lookup"><span data-stu-id="ed928-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="ed928-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ed928-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="ed928-107">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkty > Produkty.</span><span class="sxs-lookup"><span data-stu-id="ed928-107">Go to Product information management > Products > Products.</span></span>

## <a name="create-a-product"></a><span data-ttu-id="ed928-108">Tworzenie produktu</span><span class="sxs-lookup"><span data-stu-id="ed928-108">Create a product</span></span>
1. <span data-ttu-id="ed928-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ed928-109">Click New.</span></span>
2. <span data-ttu-id="ed928-110">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ed928-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ed928-111">Jeśli dla numeru produktu nie skonfigurowano sekwencji identyfikatorów, należy ją wprowadzić ręcznie.</span><span class="sxs-lookup"><span data-stu-id="ed928-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
3. <span data-ttu-id="ed928-112">W polu Nazwa produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ed928-112">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="ed928-113">Nazwa produktu jest domyślnie aliasem.</span><span class="sxs-lookup"><span data-stu-id="ed928-113">The product name defaults to the search name.</span></span> <span data-ttu-id="ed928-114">W razie potrzeby można to zmienić.</span><span class="sxs-lookup"><span data-stu-id="ed928-114">You can change this if needed.</span></span>  
4. <span data-ttu-id="ed928-115">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ed928-115">Click OK.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="ed928-116">Konfigurowanie grup wymiarów</span><span class="sxs-lookup"><span data-stu-id="ed928-116">Set up dimension groups</span></span>
1. <span data-ttu-id="ed928-117">Kliknij przycisk Grupy wymiarów, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ed928-117">Click Dimension groups to open the drop dialog.</span></span>
2. <span data-ttu-id="ed928-118">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ed928-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ed928-119">Grupa wymiarów magazynowania określa, które wymiary magazynowania należy wprowadzić w każdej transakcji produktu i jak będą one śledzone w zapasach.</span><span class="sxs-lookup"><span data-stu-id="ed928-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="ed928-120">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ed928-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ed928-121">Grupa wymiarów śledzenia określa, które wymiary śledzenia należy wprowadzić dla każdej transakcji produktu i jak będą one obsługiwane w zapasach.</span><span class="sxs-lookup"><span data-stu-id="ed928-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="ed928-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ed928-122">Click OK.</span></span>

