---
title: Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia
description: W tym temacie opisano sposób zatwierdzania dostawców dla poszczególnych kategorii zaopatrzenia w programie Dynamics 365 Supply Chain Management.
author: RichardLuan
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c337fd6c2c7cea088b2151bebb54cec326c5240d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237332"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="10d6a-103">Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="10d6a-103">Approve vendors for specific procurement categories</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="10d6a-104">W tym temacie opisano sposób zatwierdzania dostawców dla poszczególnych kategorii zaopatrzenia w programie Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="10d6a-104">This topic explains how to approve vendors for specific procurement categories in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="10d6a-105">Podczas tworzenia zapotrzebowania na zakup może istnieć konieczność wybrania preferowanego lub zatwierdzonego dostawcy, w zależności od konfiguracji zasad zakupów.</span><span class="sxs-lookup"><span data-stu-id="10d6a-105">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="10d6a-106">W tej procedurze pokazano sposób określania, że dostawca jest zatwierdzony lub preferowany dla określonej kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="10d6a-106">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="10d6a-107">To zadanie jest zazwyczaj wykonywane przez pracownika działu zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="10d6a-107">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="10d6a-108">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="10d6a-108">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="10d6a-109">W okienku nawigacji przejdź do **Moduły > Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-109">In the navigation pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="10d6a-110">Zaznacz dostawcę, którego chcesz ustawić jako preferowanego lub zatwierdzonego dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="10d6a-110">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="10d6a-111">W okienku akcji wybierz pozycję **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-111">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="10d6a-112">Wybierz **Kategorie**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-112">Select **Categories**.</span></span>
5. <span data-ttu-id="10d6a-113">Wybierz **Dodaj kategorię**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-113">Select **Add category**.</span></span>
6. <span data-ttu-id="10d6a-114">W polu **Kategoria** wybierz pozycję **AKCESORIA BIUROWE I TECHNICZNE (AKCESORIA BIUROWE I TECHNICZNE)**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-114">In the **Category** field, select **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span></span>
7. <span data-ttu-id="10d6a-115">W polu **Stan kategorii dostawcy** wybierz wartość **Preferowany**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-115">In the **Vendor category status** field, select **Preferred**.</span></span> <span data-ttu-id="10d6a-116">Istnieje możliwość określenia więcej niż jednego preferowanego dostawcy dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="10d6a-116">It's possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="10d6a-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-117">Select **Save**.</span></span>
9. <span data-ttu-id="10d6a-118">W okienku nawigacji, wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Kategorie zaopatrzenia**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-118">In the navigation pane, go to **Modules > Procurement and sourcing > Procurement categories**.</span></span>
10. <span data-ttu-id="10d6a-119">W drzewie zaznacz element **KATEGORIE ZAOPATRZENIA W FIRMIE\AKCESORIA BIUROWE I TECHNICZNE**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-119">In the tree, select **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span></span>
11. <span data-ttu-id="10d6a-120">Rozwiń sekcję **Dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-120">Expand the **Vendors** section.</span></span> <span data-ttu-id="10d6a-121">Sprawdź, czy wybrany dostawca jest wyświetlany jako preferowany dostawca dla kategorii Akcesoria biurowe i techniczne.</span><span class="sxs-lookup"><span data-stu-id="10d6a-121">Check if the vendor that you selected appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="10d6a-122">Jeżeli wykonujesz procedurę jako przewodnik zadania, może być konieczne kliknięcie przycisku **Odblokuj**, aby przewinąć w dół do listy dostawców.</span><span class="sxs-lookup"><span data-stu-id="10d6a-122">If you're running this procedure as a task guide, you may have to select the **Unlock** button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="10d6a-123">Na tej stronie można również dodawać preferowanych i zatwierdzonych dostawców.</span><span class="sxs-lookup"><span data-stu-id="10d6a-123">It's also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="10d6a-124">W drzewie rozwiń **AKCESORIA BIUROWE I TECHNICZNE** i wybierz **Nożyczki**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-124">In the tree, expand **OFFICE AND DESK ACCESSORIES** and select **Scissors**.</span></span>
13. <span data-ttu-id="10d6a-125">Zaznacz wartość **Nie** w polu **Dziedzicz dostawców po kategorii nadrzędnej:**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-125">Select **No** in the **Inherit vendors from parent category:** field.</span></span>
14. <span data-ttu-id="10d6a-126">Zaznacz wartość **Tak** w polu **Dziedzicz dostawców po kategorii nadrzędnej:**.</span><span class="sxs-lookup"><span data-stu-id="10d6a-126">Select **Yes** in the **Inherit vendors from parent category:** field.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]