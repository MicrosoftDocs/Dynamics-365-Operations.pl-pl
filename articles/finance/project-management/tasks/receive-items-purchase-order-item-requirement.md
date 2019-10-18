---
title: Przyjmowanie towarów wymienionych na zamówieniu zakupu na podstawie zapotrzebowania na towary
description: W tym temacie pokazano sposób przyjmowania towarów względem zamówienia zakupu z zapotrzebowania na towary.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7afdae65c5ae7e3196c6b9f142dd87aec39b5ea3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174427"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="73db7-103">Przyjmowanie towarów wymienionych na zamówieniu zakupu na podstawie zapotrzebowania na towary</span><span class="sxs-lookup"><span data-stu-id="73db7-103">Receive items on purchase order from item requirement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="73db7-104">W tym temacie pokazano sposób przyjmowania towarów względem zamówienia zakupu z zapotrzebowania na towary.</span><span class="sxs-lookup"><span data-stu-id="73db7-104">This topic explains how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="73db7-105">Dzięki użyciu zapotrzebowań na towary zamiast transakcji towarowych można zaplanować czas dostawy dokładnie w momencie użycia towaru oraz można utworzyć zamówienie zakupu, dołączyć towar do struktury umowy handlowej i dołączyć zapotrzebowanie na towary w planie produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="73db7-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="73db7-106">W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="73db7-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="73db7-107">W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Projekty > Wszystkie projekty**.</span><span class="sxs-lookup"><span data-stu-id="73db7-107">In the navigation pane, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="73db7-108">Na liście wybierz łącze w odpowiednim wierszu.</span><span class="sxs-lookup"><span data-stu-id="73db7-108">In the list, select the link in the desired row.</span></span>
3. <span data-ttu-id="73db7-109">W okienku akcji wybierz opcję **Plan**.</span><span class="sxs-lookup"><span data-stu-id="73db7-109">On the Action Pane, select **Plan**.</span></span>
4. <span data-ttu-id="73db7-110">Wybierz **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="73db7-110">Select **Item requirements**.</span></span>
5. <span data-ttu-id="73db7-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="73db7-111">Select **New**.</span></span>
6. <span data-ttu-id="73db7-112">W nowym wierszu, wprowadź lub wybierz wartość w polu **Identyfikator towaru**.</span><span class="sxs-lookup"><span data-stu-id="73db7-112">In the new row, enter or select a value in the **Item number** field.</span></span>
7. <span data-ttu-id="73db7-113">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="73db7-113">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="73db7-114">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="73db7-114">Select **Save**.</span></span>
9. <span data-ttu-id="73db7-115">W okienku akcji wybierz pozycję **Zarządzaj**.</span><span class="sxs-lookup"><span data-stu-id="73db7-115">On the Action Pane, select **Manage**.</span></span>
10. <span data-ttu-id="73db7-116">Wybierz **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="73db7-116">Select **Functions**.</span></span>
11. <span data-ttu-id="73db7-117">Wybierz **Tworzenie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="73db7-117">Select **Create purchase order**.</span></span>
12. <span data-ttu-id="73db7-118">Wybierz pole wyboru **Uwzględnij wszystko**.</span><span class="sxs-lookup"><span data-stu-id="73db7-118">Select the **Include all** check box.</span></span>
13. <span data-ttu-id="73db7-119">W polu **Konto dostawcy** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="73db7-119">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="73db7-120">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="73db7-120">Select **OK**.</span></span>
15. <span data-ttu-id="73db7-121">W okienku nawigacji wybierz kolejno **Moduły > Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="73db7-121">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
16. <span data-ttu-id="73db7-122">Na liście wybierz łącze w odpowiednim wierszu.</span><span class="sxs-lookup"><span data-stu-id="73db7-122">In the list, select the link in the desired row.</span></span>
17. <span data-ttu-id="73db7-123">W okienku akcji wybierz **Zakup**.</span><span class="sxs-lookup"><span data-stu-id="73db7-123">On the Action Pane, select **Purchase**.</span></span>
18. <span data-ttu-id="73db7-124">Wybierz opcję **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="73db7-124">Select **Confirm**.</span></span>
19. <span data-ttu-id="73db7-125">W okienku akcji wybierz pozycję **Odbierz**.</span><span class="sxs-lookup"><span data-stu-id="73db7-125">On the Action Pane, select **Receive**.</span></span>
20. <span data-ttu-id="73db7-126">Wybierz pozycję **Przyjęcie produktu**.</span><span class="sxs-lookup"><span data-stu-id="73db7-126">Select **Product receipt**.</span></span>
21. <span data-ttu-id="73db7-127">W polu **Dokument przyjęcia produktów** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="73db7-127">In the **Product receipt** field, type a value.</span></span>
22. <span data-ttu-id="73db7-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="73db7-128">Select **OK**.</span></span>

