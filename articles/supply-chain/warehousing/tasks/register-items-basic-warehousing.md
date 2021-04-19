---
title: Rejestrowanie elementów dla podstawowego magazynowania umożliwia obsługę elementów z arkuszem przyjęć towarów
description: W tej procedurze pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używana funkcja „podstawowego magazynowania” w module Zarządzanie zapasami.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 61ce76c5aac82ec95b7113066b47b85a9c944307
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830865"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a><span data-ttu-id="4b540-103">Rejestrowanie elementów dla podstawowego magazynowania umożliwia obsługę elementów z arkuszem przyjęć towarów</span><span class="sxs-lookup"><span data-stu-id="4b540-103">Register items for a basic warehousing enabled item using an item an item arrival journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4b540-104">W tej procedurze pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używana funkcja „podstawowego magazynowania” w module Zarządzanie zapasami.</span><span class="sxs-lookup"><span data-stu-id="4b540-104">This procedure shows you how to register items using the item arrival journal when you are using "basic warehousing" in the Inventory management module.</span></span> <span data-ttu-id="4b540-105">Zazwyczaj wykonuje to pracownik przyjmujący.</span><span class="sxs-lookup"><span data-stu-id="4b540-105">This would usually be done by a receiving clerk.</span></span> <span data-ttu-id="4b540-106">Tę procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF z przykładowymi wartościami, które są wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="4b540-106">You can run this procedure in demo data company USMF with the example values that are shown.</span></span>  <span data-ttu-id="4b540-107">Jeśli nie używasz firmy USMF, przed rozpoczęciem wykonywania zadań z przewodnika musisz mieć potwierdzone zamówienie zakupu z otwartym wierszem zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="4b540-107">If you are not using USMF, you need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="4b540-108">Towar w wierszu musi być magazynowany.</span><span class="sxs-lookup"><span data-stu-id="4b540-108">The item on the line must be stocked.</span></span> <span data-ttu-id="4b540-109">Towar musi być także skojarzony z grupą wymiarów magazynowania, gdzie oddział i magazyn są aktywne.</span><span class="sxs-lookup"><span data-stu-id="4b540-109">And the item needs to be associated with a storage dimension group, where site and warehouse are active.</span></span>


## <a name="create-item-arrival-journal-header"></a><span data-ttu-id="4b540-110">Tworzenie nagłówka arkusza przyjęcia towaru</span><span class="sxs-lookup"><span data-stu-id="4b540-110">Create item arrival journal header</span></span>
1. <span data-ttu-id="4b540-111">Wybierz kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Przyjęcie towaru > Przyjęcie towaru.</span><span class="sxs-lookup"><span data-stu-id="4b540-111">Go to Inventory management > Journal entries > Item arrival > Item arrival.</span></span>
2. <span data-ttu-id="4b540-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4b540-112">Click New.</span></span>
3. <span data-ttu-id="4b540-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4b540-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="4b540-114">Jeśli używasz firmy USMF, możesz wpisać WHS.</span><span class="sxs-lookup"><span data-stu-id="4b540-114">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="4b540-115">Jeśli korzystasz z innych danych, to arkusz, którego nazwę wybierzesz, musi mieć następujące właściwości: w polu Sprawdzanie lokalizacji pobrania ustawiona wartość Nie oraz w polu Zarządzanie kwarantanną ustawiona wartość Nie.</span><span class="sxs-lookup"><span data-stu-id="4b540-115">If you're using other data, the journal whose name you choose has to have the following properties: cheque picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="4b540-116">W polu Dokument dostawy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4b540-116">In the Packing slip field, type a value.</span></span>
    * <span data-ttu-id="4b540-117">Jest to identyfikator dokumentu dostawy wystawionego przez dostawcę.</span><span class="sxs-lookup"><span data-stu-id="4b540-117">This is the packing slip ID from the packing slip issued by the vendor.</span></span> <span data-ttu-id="4b540-118">Dodaj unikatowy numer.</span><span class="sxs-lookup"><span data-stu-id="4b540-118">Add a unique number.</span></span>  
5. <span data-ttu-id="4b540-119">W polu Numer wybierz zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="4b540-119">In the Number field, In the Number field, select the purchase order..</span></span>
6. <span data-ttu-id="4b540-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4b540-120">Click OK.</span></span>

## <a name="add-lines-to-item-arrival-journal"></a><span data-ttu-id="4b540-121">Dodawanie wierszy do arkusza przyjęcia towaru</span><span class="sxs-lookup"><span data-stu-id="4b540-121">Add lines to item arrival journal</span></span>
1. <span data-ttu-id="4b540-122">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="4b540-122">Click Functions.</span></span>
2. <span data-ttu-id="4b540-123">Kliknij opcję Utwórz wiersze.</span><span class="sxs-lookup"><span data-stu-id="4b540-123">Click Create lines.</span></span>
    * <span data-ttu-id="4b540-124">Wiersze można wprowadzić ręcznie w tym arkuszu lub mogą być tworzone automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4b540-124">The lines can be entered manually into this journal or created automatically.</span></span> <span data-ttu-id="4b540-125">Tutaj pokażemy, jak będą tworzone automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4b540-125">This will show you how to create this automatically.</span></span>  
3. <span data-ttu-id="4b540-126">Zaznacz pole wyboru Inicjuj ilość lub usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="4b540-126">Check or uncheck the Initialize quantity checkbox.</span></span>
    * <span data-ttu-id="4b540-127">Spowoduje to zainicjowanie ilości w wierszach arkusza przy użyciu ilości niezarejestrowanej z wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="4b540-127">This will initialize the quantity on the journal lines with the quantity not registered from the purchase order line.</span></span>  
4. <span data-ttu-id="4b540-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4b540-128">Click OK.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="4b540-129">Księguj arkusz</span><span class="sxs-lookup"><span data-stu-id="4b540-129">Post the journal</span></span>
1. <span data-ttu-id="4b540-130">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="4b540-130">Click Post.</span></span>
2. <span data-ttu-id="4b540-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4b540-131">Click OK.</span></span>

## <a name="generate-the-product-receipt"></a><span data-ttu-id="4b540-132">Generowanie dokumentu przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="4b540-132">Generate the product receipt</span></span>
1. <span data-ttu-id="4b540-133">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="4b540-133">Click Functions.</span></span>
2. <span data-ttu-id="4b540-134">Kliknij opcję Dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="4b540-134">Click Product receipt.</span></span>
3. <span data-ttu-id="4b540-135">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4b540-135">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]