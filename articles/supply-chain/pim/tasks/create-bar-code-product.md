---
title: Tworzenie kodu kreskowego dla produktu
description: W tej procedurze pokazano sposób ręcznego tworzenia kodu kreskowego przy użyciu przykładowego numeru towaru M0001.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, InventItemBarcode, InventItemBarcodeLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ae2765a125045d60566267d01e380069d5d527c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "329397"
---
# <a name="create-a-bar-code-for-a-product"></a><span data-ttu-id="2fc03-103">Tworzenie kodu kreskowego dla produktu</span><span class="sxs-lookup"><span data-stu-id="2fc03-103">Create a bar code for a product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2fc03-104">W tej procedurze pokazano sposób ręcznego tworzenia kodu kreskowego przy użyciu przykładowego numeru towaru M0001.</span><span class="sxs-lookup"><span data-stu-id="2fc03-104">This procedure shows how to manually create a bar code using the item number M0001 as an example.</span></span> <span data-ttu-id="2fc03-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="2fc03-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="2fc03-106">Kliknij pozycję Obsługa zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="2fc03-106">Click Released product maintenance.</span></span>
2. <span data-ttu-id="2fc03-107">Kliknij opcję Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="2fc03-107">Click Released products.</span></span>
3. <span data-ttu-id="2fc03-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2fc03-108">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="2fc03-109">W okienku akcji kliknij pozycję Zarządzaj zapasami.</span><span class="sxs-lookup"><span data-stu-id="2fc03-109">On the Action Pane, click Manage inventory.</span></span>
5. <span data-ttu-id="2fc03-110">Kliknij opcję Kody kreskowe.</span><span class="sxs-lookup"><span data-stu-id="2fc03-110">Click Bar codes.</span></span>
6. <span data-ttu-id="2fc03-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2fc03-111">Click New.</span></span>
7. <span data-ttu-id="2fc03-112">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="2fc03-112">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="2fc03-113">W polu Konfiguracja kodów kreskowych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2fc03-113">In the Barcode setup field, enter or select a value.</span></span>
9. <span data-ttu-id="2fc03-114">W polu Kod kreskowy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2fc03-114">In the Bar code field, enter or select a value.</span></span>
10. <span data-ttu-id="2fc03-115">W polu Kod kreskowy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2fc03-115">In the Bar code field, type a value.</span></span>
    * <span data-ttu-id="2fc03-116">Naciśnij klawisz Tab.</span><span class="sxs-lookup"><span data-stu-id="2fc03-116">Press the Tab key.</span></span>  
11. <span data-ttu-id="2fc03-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2fc03-117">Close the page.</span></span>
12. <span data-ttu-id="2fc03-118">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="2fc03-118">In the Quantity field, enter a number.</span></span>
13. <span data-ttu-id="2fc03-119">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2fc03-119">Click Save.</span></span>
    * <span data-ttu-id="2fc03-120">Gdy klikniesz przycisk Zapisz, zostanie wykonane sprawdzanie kodu kreskowego.</span><span class="sxs-lookup"><span data-stu-id="2fc03-120">When you click Save, the barcode check is run, and in this case it will display an error stating that the expected check digit is 8, but that 3 was found.</span></span> <span data-ttu-id="2fc03-121">W tym przypadku pojawi się komunikat o błędzie informujący, że oczekiwano cyfry kontrolnej 8, a znaleziono cyfrę 3. Ręcznie zaktualizuj numer kodu kreskowego, tak aby na końcu znalazła się cyfra 8.</span><span class="sxs-lookup"><span data-stu-id="2fc03-121">Manually update the barcode number so that 8 is at the end.</span></span>  
14. <span data-ttu-id="2fc03-122">W polu Kod kreskowy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2fc03-122">In the Bar code field, enter or select a value.</span></span>
15. <span data-ttu-id="2fc03-123">W polu Kod kreskowy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2fc03-123">In the Bar code field, type a value.</span></span>
    * <span data-ttu-id="2fc03-124">Naciśnij klawisz Tab.</span><span class="sxs-lookup"><span data-stu-id="2fc03-124">Press the Tab key.</span></span>  
16. <span data-ttu-id="2fc03-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2fc03-125">Close the page.</span></span>
17. <span data-ttu-id="2fc03-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2fc03-126">Click Save.</span></span>
18. <span data-ttu-id="2fc03-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2fc03-127">Close the page.</span></span>

