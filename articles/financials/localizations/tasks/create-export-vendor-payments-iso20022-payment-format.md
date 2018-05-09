--- 
title: "Tworzenie i eksport płatności dla dostawcy przy użyciu formatu płatności ISO20022"
description: "W tej procedurze pokazano sposób tworzenia wierszy w arkuszu płatności dostawcy oraz generowania pliku płatności dla dostawcy na przykładzie polecenia przelewu ISO2022."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 906f9611370e19ad4f063d15608d3564c5292c96
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="b3c6e-103">Tworzenie i eksport płatności dla dostawcy przy użyciu formatu płatności ISO20022</span><span class="sxs-lookup"><span data-stu-id="b3c6e-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b3c6e-104">W tej procedurze pokazano sposób tworzenia wierszy w arkuszu płatności dostawcy oraz generowania pliku płatności dla dostawcy na przykładzie polecenia przelewu ISO2022.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-104">This procedure shows how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span> 

<span data-ttu-id="b3c6e-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DEMF.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-105">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="b3c6e-106">Jest to piąta z pięciu procedur, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-106">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="b3c6e-107">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-payment-lines"></a><span data-ttu-id="b3c6e-108">Tworzenie wierszy płatności</span><span class="sxs-lookup"><span data-stu-id="b3c6e-108">Create payment lines</span></span>
1. <span data-ttu-id="b3c6e-109">Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-109">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="b3c6e-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-110">Click New.</span></span>
3. <span data-ttu-id="b3c6e-111">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="b3c6e-112">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-112">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="b3c6e-113">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-113">Click Lines.</span></span>
6. <span data-ttu-id="b3c6e-114">Kliknij opcję Propozycja płatności.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-114">Click Payment proposal.</span></span>
7. <span data-ttu-id="b3c6e-115">Kliknij opcję Utwórz propozycję płatności.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-115">Click Create payment proposal.</span></span>
8. <span data-ttu-id="b3c6e-116">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="b3c6e-117">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-117">Click Filter.</span></span>
10. <span data-ttu-id="b3c6e-118">Na liście zaznacz wiersz dla tabeli Dostawcy i pola Konto dostawcy.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-118">In the list, select the row for Vendors table and Vendor account field.</span></span>
11. <span data-ttu-id="b3c6e-119">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="b3c6e-120">Można stosować dowolne kryteria w celu wybrania transakcji z dostawcą, które mają zostać opłacone. W tym przykładzie zostanie użyte kryterium DE-001 jako konto dostawcy.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-120">You can apply any criteria for selecting vendor transactions to pay, for this example use DE-001 as a vendor account.</span></span>  
12. <span data-ttu-id="b3c6e-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-121">Click OK.</span></span>
13. <span data-ttu-id="b3c6e-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-122">Click OK.</span></span>
14. <span data-ttu-id="b3c6e-123">Kliknij opcję Utwórz płatności.</span><span class="sxs-lookup"><span data-stu-id="b3c6e-123">Click Create payments.</span></span>

## <a name="generate-an-iso20022-payment-file"></a><span data-ttu-id="b3c6e-124">Generowanie pliku płatności ISO20022</span><span class="sxs-lookup"><span data-stu-id="b3c6e-124">Generate an ISO20022 payment file</span></span>


