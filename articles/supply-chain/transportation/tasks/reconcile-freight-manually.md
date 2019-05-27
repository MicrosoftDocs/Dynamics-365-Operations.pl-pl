---
title: Ręczne uzgadnianie frachtu
description: Ta procedura pokazuje, jak uzgadniać fracht ręcznie.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee2d114b0a725b947add3e155cc6445021fee998
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556741"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="ec94d-103">Ręczne uzgadnianie frachtu</span><span class="sxs-lookup"><span data-stu-id="ec94d-103">Reconcile freight manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ec94d-104">Ta procedura pokazuje, jak uzgadniać fracht ręcznie.</span><span class="sxs-lookup"><span data-stu-id="ec94d-104">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="ec94d-105">Zazwyczaj jest to realizowane przez koordynatora transportu.</span><span class="sxs-lookup"><span data-stu-id="ec94d-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="ec94d-106">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ec94d-106">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="ec94d-107">Wybór ładunku do uzgodnienia</span><span class="sxs-lookup"><span data-stu-id="ec94d-107">Select a load to reconcile</span></span>
1. <span data-ttu-id="ec94d-108">Wybierz kolejno opcje Zarządzanie transportem > Planowanie > Warsztat planowania wysyłki ładunku.</span><span class="sxs-lookup"><span data-stu-id="ec94d-108">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="ec94d-109">Wyczyść pole wyboru Ukryj wysłane i odebrane.</span><span class="sxs-lookup"><span data-stu-id="ec94d-109">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="ec94d-110">Na liście zaznacz ładunek o identyfikatorze 00006.</span><span class="sxs-lookup"><span data-stu-id="ec94d-110">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="ec94d-111">Tworzenie faktury przewoźnika</span><span class="sxs-lookup"><span data-stu-id="ec94d-111">Create a carrier invoice</span></span>
    * <span data-ttu-id="ec94d-112">Jeśli uzgadniasz fracht ręcznie i nie otrzymujesz faktur przewoźnika automatycznie, można utworzyć fakturę na podstawie dokumentu opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="ec94d-112">If you reconcile freight manually and don’t receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="ec94d-113">Kliknij opcję Informacje pokrewne.</span><span class="sxs-lookup"><span data-stu-id="ec94d-113">Click Related information.</span></span>
2. <span data-ttu-id="ec94d-114">Kliknij opcję Szczegóły opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="ec94d-114">Click Freight bill details.</span></span>
3. <span data-ttu-id="ec94d-115">Kliknij opcję Generowanie faktury za opłatę frachtową.</span><span class="sxs-lookup"><span data-stu-id="ec94d-115">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="ec94d-116">W polu Faktura wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ec94d-116">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="ec94d-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ec94d-117">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="ec94d-118">Uzgadnianie faktury</span><span class="sxs-lookup"><span data-stu-id="ec94d-118">Reconcile the invoice</span></span>
    * <span data-ttu-id="ec94d-119">Podczas uzgadniania faktury przewoźnika z dokumentem opłaty frachtowej operacja odbywa się wiersz po wierszu.</span><span class="sxs-lookup"><span data-stu-id="ec94d-119">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="ec94d-120">Kliknij opcję Dopasuj opłaty frachtowe i faktury.</span><span class="sxs-lookup"><span data-stu-id="ec94d-120">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="ec94d-121">Rozwiń sekcję Szczegóły faktury.</span><span class="sxs-lookup"><span data-stu-id="ec94d-121">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="ec94d-122">Rozwiń sekcję Szczegóły niedopasowanej opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="ec94d-122">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="ec94d-123">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ec94d-123">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="ec94d-124">Kliknij przycisk Uzgodnij.</span><span class="sxs-lookup"><span data-stu-id="ec94d-124">Click Match.</span></span>
6. <span data-ttu-id="ec94d-125">Rozwiń sekcję Szczegóły dopasowanej opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="ec94d-125">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="ec94d-126">Prześlij fakturę do zatwierdzenia</span><span class="sxs-lookup"><span data-stu-id="ec94d-126">Submit the invoice for approval</span></span>
1. <span data-ttu-id="ec94d-127">Kliknij opcję Prześlij do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="ec94d-127">Click Submit for approval.</span></span>
2. <span data-ttu-id="ec94d-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ec94d-128">Close the page.</span></span>
3. <span data-ttu-id="ec94d-129">Zaznacz pole wyboru Ukryj zatwierdzone.</span><span class="sxs-lookup"><span data-stu-id="ec94d-129">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="ec94d-130">Kliknij opcję Arkusze faktur dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ec94d-130">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="ec94d-131">Kliknij, aby otworzyć łącze znajdujące się w polu Odwołanie do identyfikatora arkusza.</span><span class="sxs-lookup"><span data-stu-id="ec94d-131">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="ec94d-132">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="ec94d-132">Click Lines.</span></span>

