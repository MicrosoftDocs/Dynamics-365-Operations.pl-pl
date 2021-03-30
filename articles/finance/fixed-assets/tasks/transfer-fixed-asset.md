---
title: Przenoszenie środka trwałego
description: W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 365fa7a54dcf6817f933c0d305561c5fd0f8ba27
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213491"
---
# <a name="transfer-a-fixed-asset"></a><span data-ttu-id="b07c2-103">Przenoszenie środka trwałego</span><span class="sxs-lookup"><span data-stu-id="b07c2-103">Transfer a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b07c2-104">W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="b07c2-104">This task guide will transfer the financial information for a fixed asset book from one financial dimension set to a new financial dimension set.</span></span>  <span data-ttu-id="b07c2-105">Przewodnik korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="b07c2-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="b07c2-106">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Środki trwałe > Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-106">In the Navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="b07c2-107">Na liście odszukaj i zaznacz środek trwały, który ma zostać przeniesiony.</span><span class="sxs-lookup"><span data-stu-id="b07c2-107">In the list, find and select the fixed asset to transfer.</span></span>
3. <span data-ttu-id="b07c2-108">W okienku akcji kliknij pozycję **Środek trwały**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-108">On the Action Pane, click **Fixed asset**.</span></span>
4. <span data-ttu-id="b07c2-109">Kliknij opcję **Przenieś środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-109">Click **Transfer fixed assets**.</span></span>
5. <span data-ttu-id="b07c2-110">W polu **Data przeniesienia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="b07c2-110">In the **Transfer date** field, enter a date.</span></span>
6. <span data-ttu-id="b07c2-111">Wprowadź komentarze opisujące przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="b07c2-111">Enter comments to describe the transfer.</span></span>
    
    <span data-ttu-id="b07c2-112">Ta lista przedstawia wszystkie księgi dla środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="b07c2-112">This list shows all books for the fixed asset.</span></span>  
7. <span data-ttu-id="b07c2-113">Oznacz księgi, które mają zostać przeniesione do nowego zestawu wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="b07c2-113">Mark the books you want to transfer to a new financial dimension set.</span></span>
    * <span data-ttu-id="b07c2-114">Ta lista przedstawia istniejące wartości wymiarów finansowych dla wybranej księgi.</span><span class="sxs-lookup"><span data-stu-id="b07c2-114">This list shows the existing financial dimension values for the selected book.</span></span>  
    * <span data-ttu-id="b07c2-115">Zaznacz wymiar finansowy, który chcesz zaktualizować dla wybranej księgi środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="b07c2-115">Select the financial dimension you want to update for the selected fixed asset book.</span></span>  
8. <span data-ttu-id="b07c2-116">W polu **Wymiar finansowy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="b07c2-116">In the **Financial dimension** field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="b07c2-117">Ustaw wartości odpowiednich innych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="b07c2-117">Set other financial dimension values as appropriate.</span></span>  
    * <span data-ttu-id="b07c2-118">Po przeniesieniu zmieniają się wszystkie wartości wymiarów finansowych, niezależnie od tego, czy wartość została wprowadzona czy też pole było puste.</span><span class="sxs-lookup"><span data-stu-id="b07c2-118">All financial dimension values change when a transfer occurs, whether a value has been entered or left blank.</span></span> <span data-ttu-id="b07c2-119">Na przykład mogła być wprowadzono wartość wymiaru Jednostka biznesowa, a niewypełnione wymiary Centrum kosztów i Dział.</span><span class="sxs-lookup"><span data-stu-id="b07c2-119">For example, if you entered a value for the BusinessUnit and left the CostCenter and Department financial dimensions blank.</span></span> <span data-ttu-id="b07c2-120">Jeśli struktura konta pozwala na puste wartości wymiarów Centrum kosztu i Dział, przeniesienie spowoduje, że każdy model ewidencji otrzyma nową wartość wymiaru Jednostka biznesowa, a puste wartości wymiarów Centrum kosztów i Dział.</span><span class="sxs-lookup"><span data-stu-id="b07c2-120">If your account structure allows blank values for CostCenter and Department, the transfer would result in each value model having the new value for BusinessUnit and a blank value for CostCenter and Department.</span></span>  
9. <span data-ttu-id="b07c2-121">Kliknij przycisk **Aktualizuj**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-121">Click **Update**.</span></span>
    * <span data-ttu-id="b07c2-122">Przed sfinalizowaniem przeniesienia masz możliwość podglądu efektów zmian.</span><span class="sxs-lookup"><span data-stu-id="b07c2-122">You have the opportunity to preview the changes before finalizing the transfer.</span></span>  
    * <span data-ttu-id="b07c2-123">Przejrzyj wyniki przed przeniesieniem ksiąg środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="b07c2-123">Review results before transferring the fixed asset books.</span></span>  
10. <span data-ttu-id="b07c2-124">Kliknij przycisk **Przeniesienie**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-124">Click **Transfer**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]