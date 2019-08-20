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
ms.openlocfilehash: 26c62aa72a7919c780bb709b185b48c97066c538
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836319"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="6ca56-103">Tworzenie zamówienia zakupu dla dostawcy jednorazowego</span><span class="sxs-lookup"><span data-stu-id="6ca56-103">Create a purchase order for a one-time supplier</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6ca56-104">W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego.</span><span class="sxs-lookup"><span data-stu-id="6ca56-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="6ca56-105">Dostawca jest tworzony automatycznie razem z zamówieniem zakupu, a nie ręcznie.</span><span class="sxs-lookup"><span data-stu-id="6ca56-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="6ca56-106">W przypadku tworzenia ręcznego najczęściej robi to pracownik działu zakupów.</span><span class="sxs-lookup"><span data-stu-id="6ca56-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="6ca56-107">Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="6ca56-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="6ca56-108">Warunkiem wstępnym jest wcześniejsze utworzenie konta dostawcy jednorazowego na stronie Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="6ca56-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="6ca56-109">Tworzenie zamówienia zakupu dla dostawcy jednorazowego</span><span class="sxs-lookup"><span data-stu-id="6ca56-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="6ca56-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6ca56-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="6ca56-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6ca56-111">Click New.</span></span>
3. <span data-ttu-id="6ca56-112">W polu Dostawca jednorazowy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="6ca56-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="6ca56-113">Konto dostawcy jest automatycznie tworzone i przypisywane do zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6ca56-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="6ca56-114">Konto dostawcy jest tworzone na podstawie szablonu określonego na karcie Ogólne na stronie Parametry modułu rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="6ca56-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="6ca56-115">W polu Nazwa nadaj nazwę dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6ca56-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="6ca56-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6ca56-116">Click OK.</span></span>
    * <span data-ttu-id="6ca56-117">Zamówienie zakupu można teraz sfinalizować i przetwarzać jak każde inne zamówienie.</span><span class="sxs-lookup"><span data-stu-id="6ca56-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="6ca56-118">Nie istnieją żadne specjalne cechy w tym procesie.</span><span class="sxs-lookup"><span data-stu-id="6ca56-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="6ca56-119">Faktura uwzględni planowaną transakcję na koncie dostawcy utworzonym razem z zamówieniem, po czym zostanie przetworzona płatność.</span><span class="sxs-lookup"><span data-stu-id="6ca56-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span> <span data-ttu-id="6ca56-120">Po zakończeniu tej operacji można usunąć konto dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6ca56-120">When this is completed, the vendor account can be deleted.</span></span> <span data-ttu-id="6ca56-121">Zazwyczaj jest to realizowane przez dział rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="6ca56-121">This is typically done by the accounts payable department.</span></span>  

