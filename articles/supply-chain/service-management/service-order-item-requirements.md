---
title: Zapotrzebowanie na towary w zleceniu serwisowym
description: Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3ed17e968debf47d7d212a945975ae1cfaccdff4
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743252"
---
# <a name="service-order-item-requirements"></a><span data-ttu-id="bda66-103">Zapotrzebowanie na towary w zleceniu serwisowym</span><span class="sxs-lookup"><span data-stu-id="bda66-103">Service order item requirements</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="bda66-104">Można utworzyć zlecenie serwisowe do śledzenia i zarządzania usługami świadczonymi odbiorcom.</span><span class="sxs-lookup"><span data-stu-id="bda66-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="bda66-105">Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia.</span><span class="sxs-lookup"><span data-stu-id="bda66-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="bda66-106">Zapotrzebowania na towary mogą być realizowane bezpośrednio z magazynu lub mogą zainicjować zlecenie produkcyjne dla towaru.</span><span class="sxs-lookup"><span data-stu-id="bda66-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="bda66-107">Dzięki użyciu zapotrzebowań na towary zamiast transakcji towarowych można zaplanować czas dostawy dokładnie w momencie użycia towaru oraz można utworzyć zamówienie zakupu, dołączyć towar do struktury umowy handlowej i dołączyć zapotrzebowanie na towary w planie produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="bda66-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="bda66-108">Zapotrzebowania na towary dla zlecenia serwisowego są przetwarzane za pomocą projektu.</span><span class="sxs-lookup"><span data-stu-id="bda66-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="bda66-109">W celu utworzenia zapotrzebowania na towary dla zlecenia serwisowego, takie zlecenie musi być powiązane z projektem.</span><span class="sxs-lookup"><span data-stu-id="bda66-109">To create an item requirement on a service order, the service order must be attached to a project.</span></span>

<span data-ttu-id="bda66-110">Po utworzeniu zapotrzebowania na towary dla zlecenia serwisowego można je przejrzeć przy użyciu opcji **Projekt** dla pojedynczego zlecenia serwisowego albo przy użyciu formularza **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="bda66-110">As soon as an item requirement is created for a service order, it can be viewed from **Project** in the individual service order or through the **Sales order** form.</span></span>

## <a name="view-an-item-requirement-from-a-service-order"></a><span data-ttu-id="bda66-111">Przeglądanie zapotrzebowania na towary dla zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="bda66-111">View an item requirement from a service order</span></span>

1.  <span data-ttu-id="bda66-112">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="bda66-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="bda66-113">Kliknij opcję **Wysyłka**, a następnie opcję **Zapotrzebowanie na towary**, a zostanie otwarty formularz **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="bda66-113">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span>

3.  <span data-ttu-id="bda66-114">Kliknij kartę **Projekt**, a następnie sprawdź pole **Zlecenie serwisowe**, aby obejrzeć zlecenia serwisowe dla zapotrzebowania na towary.</span><span class="sxs-lookup"><span data-stu-id="bda66-114">Click the **Project** tab, and check the **Service order** field to see the service orders of the item requirement.</span></span>

## <a name="delete-service-orders-with-item-requirements"></a><span data-ttu-id="bda66-115">Usuwanie zleceń serwisowych z zapotrzebowaniem na towary</span><span class="sxs-lookup"><span data-stu-id="bda66-115">Delete service orders with item requirements</span></span>

<span data-ttu-id="bda66-116">Jeśli dla zlecenia serwisowego jest utworzone zapotrzebowanie na towary, to takiego zlecenia nie można usunąć.</span><span class="sxs-lookup"><span data-stu-id="bda66-116">If an item requirement is created on a service order, you cannot delete the service order.</span></span> <span data-ttu-id="bda66-117">Należy najpierw usunąć zapotrzebowanie na towary i dopiero potem usunąć zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="bda66-117">You must delete the item requirement before you can delete the service order.</span></span>

1.  <span data-ttu-id="bda66-118">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="bda66-118">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="bda66-119">Kliknij opcję **Wysyłka**, a następnie opcję **Zapotrzebowanie na towary**, a zostanie otwarty formularz **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="bda66-119">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span> <span data-ttu-id="bda66-120">Ten formularz zawiera listę zapotrzebowań na towary utworzonych dla określonego zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="bda66-120">This form lists the item requirements that are created on the service order.</span></span>

3.  <span data-ttu-id="bda66-121">Wybierz odpowiednie zapotrzebowanie na towar do usunięcia, a następnie kliknij przycisk **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="bda66-121">Select the item requirement to delete, and then click **Delete**.</span></span>

<span data-ttu-id="bda66-122">– lub –</span><span class="sxs-lookup"><span data-stu-id="bda66-122">–or–</span></span>

1.  <span data-ttu-id="bda66-123">Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Wspólne** \> **Projekty** \> **Wszystkie projekty**.</span><span class="sxs-lookup"><span data-stu-id="bda66-123">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="bda66-124">Otwórz projekt, w którego skład wchodzi zlecenie serwisowe, dla którego utworzono zapotrzebowanie na towary.</span><span class="sxs-lookup"><span data-stu-id="bda66-124">Open the project that has the service order in which an item requirement is created.</span></span>

3.  <span data-ttu-id="bda66-125">W formularzu **Projekty** w okienku po prawej stronie kliknij przycisk **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="bda66-125">In the **Projects** form, in the right pane, click **Item requirements**.</span></span> <span data-ttu-id="bda66-126">Formularz **Zapotrzebowanie na towary** będzie zawierał spis wszystkich zapotrzebowań na towary powiązanych z wybranym projektem.</span><span class="sxs-lookup"><span data-stu-id="bda66-126">The **Item requirements** form lists the item requirements that are associated with the selected project.</span></span>

4.  <span data-ttu-id="bda66-127">Wybierz odpowiednie zapotrzebowanie na towar do usunięcia, a następnie kliknij przycisk **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="bda66-127">Select the item requirement to delete, and then click **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="bda66-128">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="bda66-128">See also</span></span>

<span data-ttu-id="bda66-129">[Zapotrzebowanie na towary (formularz)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="bda66-129">[Item requirements (form)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))</span></span>

