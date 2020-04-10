---
title: Tworzenie zamówienia zakupu dla dostawcy jednorazowego
description: W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a55cd8f21b99589a44f7509123d3417fd9dc07f6
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147441"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="e03c5-103">Tworzenie zamówienia zakupu dla dostawcy jednorazowego</span><span class="sxs-lookup"><span data-stu-id="e03c5-103">Create a purchase order for a one-time supplier</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e03c5-104">W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego.</span><span class="sxs-lookup"><span data-stu-id="e03c5-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="e03c5-105">Dostawca jest tworzony automatycznie razem z zamówieniem zakupu, a nie ręcznie.</span><span class="sxs-lookup"><span data-stu-id="e03c5-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="e03c5-106">W przypadku tworzenia ręcznego najczęściej robi to pracownik działu zakupów.</span><span class="sxs-lookup"><span data-stu-id="e03c5-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="e03c5-107">Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e03c5-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="e03c5-108">Warunkiem wstępnym jest wcześniejsze utworzenie konta dostawcy jednorazowego na stronie Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="e03c5-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="e03c5-109">Tworzenie zamówienia zakupu dla dostawcy jednorazowego</span><span class="sxs-lookup"><span data-stu-id="e03c5-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="e03c5-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="e03c5-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="e03c5-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e03c5-111">Click New.</span></span>
3. <span data-ttu-id="e03c5-112">W polu Dostawca jednorazowy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="e03c5-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="e03c5-113">Konto dostawcy jest automatycznie tworzone i przypisywane do zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="e03c5-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="e03c5-114">Konto dostawcy jest tworzone na podstawie szablonu określonego na karcie Ogólne na stronie Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="e03c5-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="e03c5-115">W polu Nazwa nadaj nazwę dostawcy.</span><span class="sxs-lookup"><span data-stu-id="e03c5-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="e03c5-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e03c5-116">Click OK.</span></span>
    * <span data-ttu-id="e03c5-117">Zamówienie zakupu można teraz sfinalizować i przetwarzać jak każde inne zamówienie.</span><span class="sxs-lookup"><span data-stu-id="e03c5-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="e03c5-118">Nie istnieją żadne specjalne cechy w tym procesie.</span><span class="sxs-lookup"><span data-stu-id="e03c5-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="e03c5-119">Faktura uwzględni planowaną transakcję na koncie dostawcy utworzonym razem z zamówieniem, po czym zostanie przetworzona płatność.</span><span class="sxs-lookup"><span data-stu-id="e03c5-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span>

