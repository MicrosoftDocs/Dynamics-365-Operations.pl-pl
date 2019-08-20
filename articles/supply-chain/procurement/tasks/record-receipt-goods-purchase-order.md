---
title: Rejestrowanie przyjęcia towarów w zamówieniu zakupu
description: W tym temacie pokazano sposób rejestrowania przyjęcia towarów bezpośrednio w zamówieniu zakupu.
author: FrankDahl
manager: AnnBe
ms.date: 07/09/19
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e81bb3fe95326636c28885d4decad69f841e3db
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844016"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="88ca6-103">Rejestrowanie przyjęcia towarów w zamówieniu zakupu</span><span class="sxs-lookup"><span data-stu-id="88ca6-103">Record the receipt of goods on the purchase order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="88ca6-104">W tym temacie pokazano sposób rejestrowania przyjęcia towarów bezpośrednio w zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="88ca6-104">This topic explains how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="88ca6-105">Istnieje również możliwość rejestrowanie przyjęcia produktów w magazynie, a później zarejestrowania go w zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="88ca6-105">It’s also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="88ca6-106">To zadanie jest zwykle wykonywane przez pracownika działu zakupów lub osobę odpowiedzialną za rozrachunki z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="88ca6-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="88ca6-107">Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="88ca6-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="88ca6-108">W przykładzie uwzględniono kroki utworzenia prostego zamówienie zakupu, dzięki czemu można odtworzyć procedurę jako przewodnik po zadaniu.</span><span class="sxs-lookup"><span data-stu-id="88ca6-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="88ca6-109">Jeśli wykonujesz procedurę przy użyciu danych swojej firmy, zacznij od podzadania **Rejestrowanie przyjęcia towarów**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-109">If you were using the procedure on your own data, you would start at the **Record receipt of goods** subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="88ca6-110">Przygotowywanie nowego zamówienia zakupu w celu przyjęcia towarów</span><span class="sxs-lookup"><span data-stu-id="88ca6-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="88ca6-111">Wybierz kolejno **okienko nawigacji> Moduły > Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-111">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="88ca6-112">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-112">Select **New**.</span></span>
3. <span data-ttu-id="88ca6-113">W polu **Konto dostawcy** wpisz wartość `US-101`.</span><span class="sxs-lookup"><span data-stu-id="88ca6-113">In the **Vendor account** field, enter `US-101`.</span></span>
4. <span data-ttu-id="88ca6-114">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-114">Select **OK**.</span></span>
5. <span data-ttu-id="88ca6-115">W polu **Numer pozycji** wpisz `M0001`.</span><span class="sxs-lookup"><span data-stu-id="88ca6-115">In the **Item number** field, enter `M0001`.</span></span>
6. <span data-ttu-id="88ca6-116">W polu **Ilość** wpisz wartość `5`.</span><span class="sxs-lookup"><span data-stu-id="88ca6-116">In the **Quantity** field, enter `5`.</span></span>
7. <span data-ttu-id="88ca6-117">W okienku akcji wybierz **Zakup**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-117">On the Action Pane, select **Purchase**.</span></span>
8. <span data-ttu-id="88ca6-118">Wybierz opcję **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-118">Select **Confirm**.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="88ca6-119">Rejestrowanie przyjęcia towarów</span><span class="sxs-lookup"><span data-stu-id="88ca6-119">Record receipt of goods</span></span>
1. <span data-ttu-id="88ca6-120">W okienku akcji wybierz pozycję **Odbierz**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-120">On the Action Pane, select **Receive**.</span></span>
2. <span data-ttu-id="88ca6-121">Wybierz pozycję **Przyjęcie produktu**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-121">Select **Product receipt**.</span></span> <span data-ttu-id="88ca6-122">W polu **Ilość** można wybrać różne opcje dotyczące ilości, która ma zostać przyjęta.</span><span class="sxs-lookup"><span data-stu-id="88ca6-122">The **Quantity** field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="88ca6-123">Na przykład jeśli ilość została wcześniej zarejestrowana w magazynie, można wybrać opcję **Ilość zarejestrowana**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-123">For example, if a quantity has previously been registered in the warehouse, you can select **Registered quantity**.</span></span> <span data-ttu-id="88ca6-124">W tym przykładzie należy użyć wartości **Ilość zamówiona**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-124">For this example, use the value **Ordered quantity**.</span></span>
3. <span data-ttu-id="88ca6-125">Rozwiń sekcję **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-125">Expand the **Overview** section.</span></span>
4. <span data-ttu-id="88ca6-126">W polu **Dokument przyjęcia** produktów wpisz dowolną wartość.</span><span class="sxs-lookup"><span data-stu-id="88ca6-126">In the **Product receipt** field, type any value.</span></span> <span data-ttu-id="88ca6-127">To pole służy do wprowadzania odwołania, które będzie używane jako załącznik dla arkusza dokumentu przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="88ca6-127">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
5. <span data-ttu-id="88ca6-128">Rozwiń sekcję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-128">Expand the **Lines** section.</span></span>
6. <span data-ttu-id="88ca6-129">W polu **Ilość** wpisz wartość 4.</span><span class="sxs-lookup"><span data-stu-id="88ca6-129">Set **Quantity** to '4'.</span></span> <span data-ttu-id="88ca6-130">W tym miejscu można ręcznie określić ilość przyjmowaną dla każdego wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="88ca6-130">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
7. <span data-ttu-id="88ca6-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="88ca6-131">Select **OK**.</span></span> <span data-ttu-id="88ca6-132">Towary zostały teraz zarejestrowane jako przyjęte w zamówieniu zakupu, a w celu odzwierciedlenia tego utworzono arkusz dokumentu przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="88ca6-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="88ca6-133">Można użyć akcji Dokument przyjęcia produktów, aby przejrzeć arkusze utworzone z zamówieniem zakupu i sprawdzić, co zostało przyjęte i kiedy.</span><span class="sxs-lookup"><span data-stu-id="88ca6-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  

