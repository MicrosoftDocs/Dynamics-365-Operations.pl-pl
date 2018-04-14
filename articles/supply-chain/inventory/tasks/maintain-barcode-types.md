---
title: "Obsługa typów kodów kreskowych"
description: "W tej procedurze pokazano sposób konfigurowania nowej definicji kodu kreskowego, która następnie może służyć jako część raportu listy pobrania."
author: perlynne
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 18d453a95024e15816113b80e103605650d581c4
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="maintain-bar-code-types"></a><span data-ttu-id="6cdaa-103">Obsługa typów kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="6cdaa-103">Maintain bar code types</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6cdaa-104">W tej procedurze pokazano sposób konfigurowania nowej definicji kodu kreskowego, która następnie może służyć jako część raportu listy pobrania.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="6cdaa-105">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="6cdaa-106">Jeśli używasz firmy USMF, można wybrać wyświetlone przykładowe wartości.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="6cdaa-107">Te zadania zazwyczaj wykonuje kierownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="6cdaa-108">Przejdź do okna Kody kreskowe.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="6cdaa-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-109">Click New.</span></span>
3. <span data-ttu-id="6cdaa-110">W polu Konfiguracja kodów kreskowych wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="6cdaa-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6cdaa-112">W polu Typ kodu kreskowego wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="6cdaa-113">Jeśli używasz firmy demonstracyjnej USMF, można wybrać opcję „Kod 39”.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="6cdaa-114">W polu Rozmiar wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="6cdaa-115">W polu Długość maksymalna wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="6cdaa-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-116">Click Save.</span></span>
9. <span data-ttu-id="6cdaa-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-117">Close the page.</span></span>
10. <span data-ttu-id="6cdaa-118">Przejdź do okna Parametry modułu Zarządzanie zapasami i magazynem.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="6cdaa-119">W polu Konfiguracja kodów kreskowych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="6cdaa-120">Wybierz utworzoną wcześniej konfigurację kodu kreskowego, ale pamiętaj, że format kodu kreskowego musi być zgodny z formatem unikatowego identyfikatora typu rekordu używanego w procesie.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="6cdaa-121">Na przykład dla marszrut pobrania format kodu kreskowego musi być zgodny z formatem odwołania do marszruty pobrania, który jest zazwyczaj sekwencją numeracji.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="6cdaa-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-122">Click Save.</span></span>
13. <span data-ttu-id="6cdaa-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6cdaa-123">Close the page.</span></span>

