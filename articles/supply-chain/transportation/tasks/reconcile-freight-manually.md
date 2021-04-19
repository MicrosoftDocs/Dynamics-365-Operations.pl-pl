---
title: Ręczne uzgadnianie frachtu
description: Ta procedura pokazuje, jak uzgadniać fracht ręcznie.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a0a5450697a09e5e54e74b35b2576eb6bbd4cdf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838521"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="aa81d-103">Ręczne uzgadnianie frachtu</span><span class="sxs-lookup"><span data-stu-id="aa81d-103">Reconcile freight manually</span></span>

<span data-ttu-id="aa81d-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="aa81d-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="aa81d-105">Ta procedura pokazuje, jak uzgadniać fracht ręcznie.</span><span class="sxs-lookup"><span data-stu-id="aa81d-105">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="aa81d-106">Zazwyczaj jest to realizowane przez koordynatora transportu.</span><span class="sxs-lookup"><span data-stu-id="aa81d-106">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="aa81d-107">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="aa81d-107">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="aa81d-108">Wybór ładunku do uzgodnienia</span><span class="sxs-lookup"><span data-stu-id="aa81d-108">Select a load to reconcile</span></span>
1. <span data-ttu-id="aa81d-109">Wybierz kolejno opcje Zarządzanie transportem > Planowanie > Warsztat planowania wysyłki ładunku.</span><span class="sxs-lookup"><span data-stu-id="aa81d-109">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="aa81d-110">Wyczyść pole wyboru Ukryj wysłane i odebrane.</span><span class="sxs-lookup"><span data-stu-id="aa81d-110">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="aa81d-111">Na liście zaznacz ładunek o identyfikatorze 00006.</span><span class="sxs-lookup"><span data-stu-id="aa81d-111">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="aa81d-112">Tworzenie faktury przewoźnika</span><span class="sxs-lookup"><span data-stu-id="aa81d-112">Create a carrier invoice</span></span>
<span data-ttu-id="aa81d-113">Jeśli uzgadniasz fracht ręcznie i nie otrzymujesz faktur przewoźnika automatycznie, można utworzyć fakturę na podstawie dokumentu opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="aa81d-113">If you reconcile freight manually and don't receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="aa81d-114">Kliknij opcję Informacje pokrewne.</span><span class="sxs-lookup"><span data-stu-id="aa81d-114">Click Related information.</span></span>
2. <span data-ttu-id="aa81d-115">Kliknij opcję Szczegóły opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="aa81d-115">Click Freight bill details.</span></span>
3. <span data-ttu-id="aa81d-116">Kliknij opcję Generowanie faktury za opłatę frachtową.</span><span class="sxs-lookup"><span data-stu-id="aa81d-116">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="aa81d-117">W polu Faktura wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="aa81d-117">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="aa81d-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="aa81d-118">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="aa81d-119">Uzgadnianie faktury</span><span class="sxs-lookup"><span data-stu-id="aa81d-119">Reconcile the invoice</span></span>
<span data-ttu-id="aa81d-120">Podczas uzgadniania faktury przewoźnika z dokumentem opłaty frachtowej operacja odbywa się wiersz po wierszu.</span><span class="sxs-lookup"><span data-stu-id="aa81d-120">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="aa81d-121">Kliknij opcję Dopasuj opłaty frachtowe i faktury.</span><span class="sxs-lookup"><span data-stu-id="aa81d-121">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="aa81d-122">Rozwiń sekcję Szczegóły faktury.</span><span class="sxs-lookup"><span data-stu-id="aa81d-122">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="aa81d-123">Rozwiń sekcję Szczegóły niedopasowanej opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="aa81d-123">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="aa81d-124">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="aa81d-124">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="aa81d-125">Kliknij przycisk Uzgodnij.</span><span class="sxs-lookup"><span data-stu-id="aa81d-125">Click Match.</span></span>
6. <span data-ttu-id="aa81d-126">Rozwiń sekcję Szczegóły dopasowanej opłaty frachtowej.</span><span class="sxs-lookup"><span data-stu-id="aa81d-126">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="aa81d-127">Prześlij fakturę do zatwierdzenia</span><span class="sxs-lookup"><span data-stu-id="aa81d-127">Submit the invoice for approval</span></span>
1. <span data-ttu-id="aa81d-128">Kliknij opcję Prześlij do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="aa81d-128">Click Submit for approval.</span></span>
2. <span data-ttu-id="aa81d-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="aa81d-129">Close the page.</span></span>
3. <span data-ttu-id="aa81d-130">Zaznacz pole wyboru Ukryj zatwierdzone.</span><span class="sxs-lookup"><span data-stu-id="aa81d-130">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="aa81d-131">Kliknij opcję Arkusze faktur dostawcy.</span><span class="sxs-lookup"><span data-stu-id="aa81d-131">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="aa81d-132">Kliknij, aby otworzyć łącze znajdujące się w polu Odwołanie do identyfikatora arkusza.</span><span class="sxs-lookup"><span data-stu-id="aa81d-132">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="aa81d-133">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="aa81d-133">Click Lines.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]