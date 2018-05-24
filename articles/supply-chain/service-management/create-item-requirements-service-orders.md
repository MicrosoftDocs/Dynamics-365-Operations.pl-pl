---
title: "Tworzenie zapotrzebowań na towary na podstawie zleceń serwisowych"
description: "Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e76b0c636470a89ba2091363efe2f34eb3d58f88
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="create-item-requirements-for-service-orders"></a><span data-ttu-id="ee3ba-103">Tworzenie zapotrzebowań na towary na podstawie zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="ee3ba-103">Create item requirements for service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ee3ba-104">Można utworzyć zlecenie serwisowe do śledzenia i zarządzania usługami świadczonymi odbiorcom.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="ee3ba-105">Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="ee3ba-106">Zapotrzebowania na towary mogą być realizowane bezpośrednio z magazynu lub mogą zainicjować zlecenie produkcyjne dla towaru.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="ee3ba-107">Dzięki użyciu zapotrzebowań na towary zamiast transakcji towarowych można zaplanować czas dostawy dokładnie w momencie użycia towaru oraz można utworzyć zamówienie zakupu, dołączyć towar do struktury umowy handlowej i dołączyć zapotrzebowanie na towary w planie produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="ee3ba-108">Zapotrzebowania na towary dla zlecenia serwisowego są przetwarzane za pomocą projektu.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="ee3ba-109">W celu utworzenia zapotrzebowania na towary dla zlecenia serwisowego, takie zlecenie musi być powiązane z projektem.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-109">To create an item requirement on a service order, the service order must be assigned to a project.</span></span> <span data-ttu-id="ee3ba-110">Po utworzeniu zapotrzebowania na towary dla zlecenia serwisowego można wyświetlić to zapotrzebowanie w formularzu **Projekty** dla wybranego projektu.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-110">After you create an item requirement for a service order, you can view the item requirement in the **Projects** form for the selected project.</span></span>

## <a name="create-an-item-requirement-for-a-service-order"></a><span data-ttu-id="ee3ba-111">Tworzenie zapotrzebowania na towary dla zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="ee3ba-111">Create an item requirement for a service order</span></span>

1.  <span data-ttu-id="ee3ba-112">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="ee3ba-113">Wybierz zlecenie serwisowe, dla którego chcesz utworzyć zapotrzebowanie na towar.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-113">Select the service order that you want to create an item requirement for.</span></span>

3.  <span data-ttu-id="ee3ba-114">W **okienku akcji** na karcie **Wysyłka** kliknij opcję **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-114">On the **Action Pane**, on the **Dispatch** tab, click **Item requirement**.</span></span>

4.  <span data-ttu-id="ee3ba-115">W formularzu **Zapotrzebowanie na towary** wprowadź informacje dla wymaganego towaru.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-115">In the **Item requirements** form, enter information for the required item.</span></span> <span data-ttu-id="ee3ba-116">Aby uzyskać więcej informacji o konkretnych polach, zobacz [Zapotrzebowanie na towary (formularz)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\)).</span><span class="sxs-lookup"><span data-stu-id="ee3ba-116">For more information about the specific fields, see [Item requirements (form)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\)).</span></span>

## <a name="create-an-item-requirement-for-a-service-agreement"></a><span data-ttu-id="ee3ba-117">Tworzenie zapotrzebowania na towary do umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="ee3ba-117">Create an item requirement for a service agreement</span></span>

1.  <span data-ttu-id="ee3ba-118">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="ee3ba-119">Otwórz umowę serwisową, dla której chcesz utworzyć zapotrzebowanie na towar.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-119">Open the service agreement for which you want to create an item requirement.</span></span>

3.  <span data-ttu-id="ee3ba-120">Na skróconej karcie **Wiersze** kliknij przycisk **Dodaj**, aby utworzyć nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-120">On the **Lines** FastTab, click **Add** to create a new line.</span></span>

4.  <span data-ttu-id="ee3ba-121">W polu **Typ transakcji** wybierz opcję **Towar**.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-121">In the **Transaction type** field, select **Item**.</span></span>

5.  <span data-ttu-id="ee3ba-122">W polu **Ustawienia pozycji** wybierz opcję **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-122">In the **Item setup** field, select **Item requirement**.</span></span>

6.  <span data-ttu-id="ee3ba-123">W polu **Numer pozycji** wybierz towar, który jest wymagany dla umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-123">In the **Item number** field, select the item that is required for the service agreement.</span></span>

7.  <span data-ttu-id="ee3ba-124">Na skróconej karcie **Szczegóły wiersza** na karcie **Wymiary produktu** w polu **Oddział** wybierz oddział zapasów dla towaru.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-124">On the **Line details** FastTab, on the **Product dimensions** tab, in the **Site** field, select the inventory site for the item.</span></span>

8.  <span data-ttu-id="ee3ba-125">Aby utworzyć zlecenie serwisowe z wiersza umowy, na skróconej karcie **Wiersze** kliknij opcję **Utwórz zlecenia serwisowe**, a następnie wprowadź odpowiednie informacje w formularzu **Utwórz zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="ee3ba-125">To create a service order from the agreement line, on the **Lines** FastTab, click **Create service orders**, and then enter the relevant information in the **Create service orders** form.</span></span> 


## <a name="see-also"></a><span data-ttu-id="ee3ba-126">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="ee3ba-126">See also</span></span>

<span data-ttu-id="ee3ba-127">[Automatyczne tworzenie zleceń serwisowych](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="ee3ba-127">[Create service orders automatically](create-service-orders-automatically.md).</span></span>

  



