--- 
title: "Przenoszenie środka trwałego"
description: "W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b193cf6fbed810f0d5234514573d0f5c23c7b2c8
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-a-fixed-asset"></a><span data-ttu-id="c3294-103">Przenoszenie środka trwałego</span><span class="sxs-lookup"><span data-stu-id="c3294-103">Transfer a fixed asset</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c3294-104">W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="c3294-104">This task guide will transfer the financial information for a fixed asset book from one financial dimension set to a new financial dimension set.</span></span>  <span data-ttu-id="c3294-105">Przewodnik korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="c3294-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="c3294-106">Przejdź do Środki trwałe > Środki trwałe > Środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="c3294-106">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="c3294-107">Na liście odszukaj i zaznacz środek trwały, który ma zostać przeniesiony.</span><span class="sxs-lookup"><span data-stu-id="c3294-107">In the list, find and select the fixed asset to transfer.</span></span>
3. <span data-ttu-id="c3294-108">W okienku akcji kliknij pozycję Środek trwały.</span><span class="sxs-lookup"><span data-stu-id="c3294-108">On the Action Pane, click Fixed asset.</span></span>
4. <span data-ttu-id="c3294-109">Kliknij opcję Przenieś środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="c3294-109">Click Transfer fixed assets.</span></span>
5. <span data-ttu-id="c3294-110">W polu Data przeniesienia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c3294-110">In the Transfer date field, enter a date.</span></span>
6. <span data-ttu-id="c3294-111">Wprowadź komentarze opisujące przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="c3294-111">Enter comments to describe the transfer.</span></span>
    * <span data-ttu-id="c3294-112">Ta lista przedstawia wszystkie księgi dla środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="c3294-112">This list shows all books for the fixed asset.</span></span>  
7. <span data-ttu-id="c3294-113">Oznacz księgi, które mają zostać przeniesione do nowego zestawu wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="c3294-113">Mark the books you want to transfer to a new financial dimension set.</span></span>
    * <span data-ttu-id="c3294-114">Ta lista przedstawia istniejące wartości wymiarów finansowych dla wybranej księgi.</span><span class="sxs-lookup"><span data-stu-id="c3294-114">This list shows the existing financial dimension values for the selected book.</span></span>  
    * <span data-ttu-id="c3294-115">Zaznacz wymiar finansowy, który chcesz zaktualizować dla wybranej księgi środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="c3294-115">Select the financial dimension you want to update for the selected fixed asset book.</span></span>  
8. <span data-ttu-id="c3294-116">W polu Wymiar finansowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c3294-116">In the Financial dimension field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="c3294-117">Ustaw wartości odpowiednich innych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="c3294-117">Set other financial dimension values as appropriate.</span></span>  
    * <span data-ttu-id="c3294-118">Po przeniesieniu zmieniają się wszystkie wartości wymiarów finansowych, niezależnie od tego, czy wartość została wprowadzona czy też pole było puste.</span><span class="sxs-lookup"><span data-stu-id="c3294-118">All financial dimension values change when a transfer occurs, whether a value has been entered or left blank.</span></span> <span data-ttu-id="c3294-119">Na przykład mogła być wprowadzono wartość wymiaru Jednostka biznesowa, a niewypełnione wymiary Centrum kosztów i Dział.</span><span class="sxs-lookup"><span data-stu-id="c3294-119">For example, if you entered a value for the BusinessUnit and left the CostCenter and Department financial dimensions blank.</span></span> <span data-ttu-id="c3294-120">Jeśli struktura konta pozwala na puste wartości wymiarów Centrum kosztu i Dział, przeniesienie spowoduje, że każdy model ewidencji otrzyma nową wartość wymiaru Jednostka biznesowa, a puste wartości wymiarów Centrum kosztów i Dział.</span><span class="sxs-lookup"><span data-stu-id="c3294-120">If your account structure allows blank values for CostCenter and Department, the transfer would result in each value model having the new value for BusinessUnit and a blank value for CostCenter and Department.</span></span>  
9. <span data-ttu-id="c3294-121">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="c3294-121">Click Update.</span></span>
    * <span data-ttu-id="c3294-122">Przed sfinalizowaniem przeniesienia masz możliwość podglądu efektów zmian.</span><span class="sxs-lookup"><span data-stu-id="c3294-122">You have the opportunity to preview the changes before finalizing the transfer.</span></span>  
    * <span data-ttu-id="c3294-123">Przejrzyj wyniki przed przeniesieniem ksiąg środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="c3294-123">Review results before transferring the fixed asset books.</span></span>  
10. <span data-ttu-id="c3294-124">Kliknij przycisk Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="c3294-124">Click Transfer.</span></span>


