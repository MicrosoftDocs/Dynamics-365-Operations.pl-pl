---
title: Przyjmowanie towarów względem zamówienia zakupu z zapotrzebowania na towary
description: W tej procedurze pokazano sposób przyjmowania towarów względem zamówienia zakupu z zapotrzebowania na towary.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: fee2c965b0c065f00564b849ec93504336fb3f60
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838254"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="46521-103">Przyjmowanie towarów względem zamówienia zakupu z zapotrzebowania na towary</span><span class="sxs-lookup"><span data-stu-id="46521-103">Receive items on purchase order from item requirement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46521-104">W tej procedurze pokazano sposób przyjmowania towarów względem zamówienia zakupu z zapotrzebowania na towary.</span><span class="sxs-lookup"><span data-stu-id="46521-104">This procedure shows how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="46521-105">Dzięki użyciu zapotrzebowań na towary zamiast transakcji towarowych można zaplanować czas dostawy dokładnie w momencie użycia towaru oraz można utworzyć zamówienie zakupu, dołączyć towar do struktury umowy handlowej i dołączyć zapotrzebowanie na towary w planie produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="46521-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="46521-106">W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="46521-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="46521-107">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie> Projekty > Wszystkie projekty.</span><span class="sxs-lookup"><span data-stu-id="46521-107">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="46521-108">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="46521-108">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="46521-109">W okienku akcji kliknij opcję Plan.</span><span class="sxs-lookup"><span data-stu-id="46521-109">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="46521-110">Kliknij opcję Zapotrzebowanie na towary.</span><span class="sxs-lookup"><span data-stu-id="46521-110">Click Item requirements.</span></span>
5. <span data-ttu-id="46521-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="46521-111">Click New.</span></span>
6. <span data-ttu-id="46521-112">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="46521-112">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="46521-113">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="46521-113">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="46521-114">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="46521-114">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="46521-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="46521-115">Click Save.</span></span>
10. <span data-ttu-id="46521-116">W okienku akcji kliknij pozycję Zarządzaj.</span><span class="sxs-lookup"><span data-stu-id="46521-116">On the Action Pane, click Manage.</span></span>
11. <span data-ttu-id="46521-117">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="46521-117">Click Functions.</span></span>
12. <span data-ttu-id="46521-118">Kliknij opcję Tworzenie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="46521-118">Click Create purchase order.</span></span>
13. <span data-ttu-id="46521-119">Zaznacz pole wyboru Uwzględnij.</span><span class="sxs-lookup"><span data-stu-id="46521-119">Select the Include check box.</span></span>
14. <span data-ttu-id="46521-120">W polu Konto dostawcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="46521-120">In the Vendor account field, enter or select a value.</span></span>
15. <span data-ttu-id="46521-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="46521-121">Click OK.</span></span>
16. <span data-ttu-id="46521-122">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="46521-122">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
17. <span data-ttu-id="46521-123">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="46521-123">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="46521-124">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="46521-124">On the Action Pane, click Purchase.</span></span>
19. <span data-ttu-id="46521-125">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="46521-125">Click Confirm.</span></span>
20. <span data-ttu-id="46521-126">W okienku akcji kliknij pozycję Odbierz.</span><span class="sxs-lookup"><span data-stu-id="46521-126">On the Action Pane, click Receive.</span></span>
21. <span data-ttu-id="46521-127">Kliknij opcję Dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="46521-127">Click Product receipt.</span></span>
22. <span data-ttu-id="46521-128">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="46521-128">In the list, mark the selected row.</span></span>
23. <span data-ttu-id="46521-129">W polu Dokument przyjęcia produktów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="46521-129">In the Product receipt field, type a value.</span></span>
24. <span data-ttu-id="46521-130">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="46521-130">Click OK.</span></span>

