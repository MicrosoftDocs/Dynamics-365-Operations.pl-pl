---
title: Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia
description: Podczas tworzenia zapotrzebowania na zakup może istnieć konieczność wybrania preferowanego lub zatwierdzonego dostawcy, w zależności od konfiguracji zasad zakupów.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b783d1ce8f02ad119dc6768e6d9cd3c61ae07e70
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566440"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="f76a0-103">Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="f76a0-103">Approve vendors for specific procurement categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f76a0-104">Podczas tworzenia zapotrzebowania na zakup może istnieć konieczność wybrania preferowanego lub zatwierdzonego dostawcy, w zależności od konfiguracji zasad zakupów.</span><span class="sxs-lookup"><span data-stu-id="f76a0-104">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="f76a0-105">W tej procedurze pokazano sposób określania, że dostawca jest zatwierdzony lub preferowany dla określonej kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="f76a0-105">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="f76a0-106">To zadanie jest zazwyczaj wykonywane przez pracownika działu zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="f76a0-106">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="f76a0-107">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="f76a0-107">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="f76a0-108">Wybierz kolejno opcje Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy.</span><span class="sxs-lookup"><span data-stu-id="f76a0-108">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="f76a0-109">Zaznacz dostawcę, którego chcesz ustawić jako preferowanego lub zatwierdzonego dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="f76a0-109">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="f76a0-110">W okienku akcji kliknij pozycję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="f76a0-110">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="f76a0-111">Kliknij opcję Kategorie.</span><span class="sxs-lookup"><span data-stu-id="f76a0-111">Click Categories.</span></span>
5. <span data-ttu-id="f76a0-112">Kliknij opcję Dodaj kategorię.</span><span class="sxs-lookup"><span data-stu-id="f76a0-112">Click Add category.</span></span>
6. <span data-ttu-id="f76a0-113">W polu Kategoria wybierz pozycję AKCESORIA BIUROWE I TECHNICZNE (AKCESORIA BIUROWE I TECHNICZNE).</span><span class="sxs-lookup"><span data-stu-id="f76a0-113">In the Category field, select OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).</span></span>
7. <span data-ttu-id="f76a0-114">W polu Stan kategorii dostawcy wybierz wartość „Preferowany”.</span><span class="sxs-lookup"><span data-stu-id="f76a0-114">In the Vendor category status field, select 'Preferred'.</span></span>
    * <span data-ttu-id="f76a0-115">Istnieje możliwość określenia więcej niż jednego preferowanego dostawcy dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="f76a0-115">It’s possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="f76a0-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f76a0-116">Click Save.</span></span>
9. <span data-ttu-id="f76a0-117">Wybierz kolejno opcje Zaopatrzenie i sourcing > Kategorie zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="f76a0-117">Go to Procurement and sourcing > Procurement categories.</span></span>
10. <span data-ttu-id="f76a0-118">W drzewie zaznacz element „KATEGORIE ZAOPATRZENIA W FIRMIE\AKCESORIA BIUROWE I TECHNICZNE”.</span><span class="sxs-lookup"><span data-stu-id="f76a0-118">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES'.</span></span>
11. <span data-ttu-id="f76a0-119">Rozwiń sekcję Dostawcy.</span><span class="sxs-lookup"><span data-stu-id="f76a0-119">Expand the Vendors section.</span></span>
    * <span data-ttu-id="f76a0-120">Sprawdź, czy wybrany dostawca jest wyświetlany jako preferowany dostawca dla kategorii Akcesoria biurowe i techniczne.</span><span class="sxs-lookup"><span data-stu-id="f76a0-120">Check if the vendor that you selected  appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="f76a0-121">Jeżeli wykonujesz procedurę jako przewodnik po zadaniu, może być konieczne kliknięcie przycisku Odblokuj, aby przewinąć w dół do listy dostawców.</span><span class="sxs-lookup"><span data-stu-id="f76a0-121">If you’re running this procedure as a task guide, you may have to click the Unlock button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="f76a0-122">Na tej stronie można również dodawać preferowanych i zatwierdzonych dostawców.</span><span class="sxs-lookup"><span data-stu-id="f76a0-122">It’s also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="f76a0-123">W drzewie rozwiń węzeł „AKCESORIA BIUROWE I TECHNICZNE”.</span><span class="sxs-lookup"><span data-stu-id="f76a0-123">In the tree, expand 'OFFICE AND DESK ACCESSORIES'.</span></span>
13. <span data-ttu-id="f76a0-124">W drzewie zaznacz element „Nożyczki”.</span><span class="sxs-lookup"><span data-stu-id="f76a0-124">In the tree, select 'Scissors'.</span></span>
14. <span data-ttu-id="f76a0-125">W polu Dziedzicz dostawców po kategorii nadrzędnej: zaznacz wartość Nie.</span><span class="sxs-lookup"><span data-stu-id="f76a0-125">Select No in the Inherit vendors from parent category: field.</span></span>
15. <span data-ttu-id="f76a0-126">W polu Dziedzicz dostawców po kategorii nadrzędnej: zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="f76a0-126">Select Yes in the Inherit vendors from parent category: field.</span></span>

