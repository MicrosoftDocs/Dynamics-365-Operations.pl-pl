--- 
title: "Ręczne uzgadnianie frachtu"
description: "Ta procedura pokazuje, jak uzgadniać fracht ręcznie."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 15148725664d839694ede8419213d881c7be83dd
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="372af-103">Ręczne uzgadnianie frachtu</span><span class="sxs-lookup"><span data-stu-id="372af-103">Reconcile freight manually</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="372af-104">Ta procedura pokazuje, jak uzgadniać fracht ręcznie.</span><span class="sxs-lookup"><span data-stu-id="372af-104">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="372af-105">Zazwyczaj jest to realizowane przez koordynatora transportu.</span><span class="sxs-lookup"><span data-stu-id="372af-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="372af-106">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="372af-106">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="372af-107">Wybór ładunku do uzgodnienia</span><span class="sxs-lookup"><span data-stu-id="372af-107">Select a load to reconcile</span></span>
1. <span data-ttu-id="372af-108">Wybierz kolejno opcje Zarządzanie transportem > Planowanie > Warsztat planowania wysyłki ładunku.</span><span class="sxs-lookup"><span data-stu-id="372af-108">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="372af-109">Wyczyść pole wyboru Ukryj wysłane i odebrane.</span><span class="sxs-lookup"><span data-stu-id="372af-109">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="372af-110">Na liście zaznacz ładunek o identyfikatorze 00006.</span><span class="sxs-lookup"><span data-stu-id="372af-110">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="372af-111">Tworzenie faktury przewoźnika</span><span class="sxs-lookup"><span data-stu-id="372af-111">Create a carrier invoice</span></span>
    * <span data-ttu-id="372af-112">Jeśli uzgadniasz fracht ręcznie i nie otrzymujesz faktur przewoźnika automatycznie, można utworzyć fakturę na podstawie dokumentu opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="372af-112">If you reconcile freight manually and don’t receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="372af-113">Kliknij opcję Informacje pokrewne.</span><span class="sxs-lookup"><span data-stu-id="372af-113">Click Related information.</span></span>
2. <span data-ttu-id="372af-114">Kliknij opcję Szczegóły opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="372af-114">Click Freight bill details.</span></span>
3. <span data-ttu-id="372af-115">Kliknij opcję Generowanie faktury za opłatę frachtową.</span><span class="sxs-lookup"><span data-stu-id="372af-115">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="372af-116">W polu Faktura wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="372af-116">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="372af-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="372af-117">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="372af-118">Uzgadnianie faktury</span><span class="sxs-lookup"><span data-stu-id="372af-118">Reconcile the invoice</span></span>
    * <span data-ttu-id="372af-119">Podczas uzgadniania faktury przewoźnika z dokumentem opłaty frachtowej operacja odbywa się wiersz po wierszu.</span><span class="sxs-lookup"><span data-stu-id="372af-119">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="372af-120">Kliknij opcję Dopasuj opłaty frachtowe i faktury.</span><span class="sxs-lookup"><span data-stu-id="372af-120">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="372af-121">Rozwiń sekcję Szczegóły faktury.</span><span class="sxs-lookup"><span data-stu-id="372af-121">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="372af-122">Rozwiń sekcję Szczegóły niedopasowanej opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="372af-122">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="372af-123">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="372af-123">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="372af-124">Kliknij przycisk Uzgodnij.</span><span class="sxs-lookup"><span data-stu-id="372af-124">Click Match.</span></span>
6. <span data-ttu-id="372af-125">Rozwiń sekcję Szczegóły dopasowanej opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="372af-125">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="372af-126">Prześlij fakturę do zatwierdzenia</span><span class="sxs-lookup"><span data-stu-id="372af-126">Submit the invoice for approval</span></span>
1. <span data-ttu-id="372af-127">Kliknij opcję Prześlij do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="372af-127">Click Submit for approval.</span></span>
2. <span data-ttu-id="372af-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="372af-128">Close the page.</span></span>
3. <span data-ttu-id="372af-129">Zaznacz pole wyboru Ukryj zatwierdzone.</span><span class="sxs-lookup"><span data-stu-id="372af-129">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="372af-130">Kliknij opcję Arkusze faktur dostawcy.</span><span class="sxs-lookup"><span data-stu-id="372af-130">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="372af-131">Kliknij, aby otworzyć łącze znajdujące się w polu Odwołanie do identyfikatora arkusza.</span><span class="sxs-lookup"><span data-stu-id="372af-131">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="372af-132">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="372af-132">Click Lines.</span></span>


