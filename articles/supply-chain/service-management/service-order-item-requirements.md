---
title: Zapotrzebowanie na towary w zleceniu serwisowym
description: Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a0ce40c26e3d3028064b73a80a247180d6a9009
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226672"
---
# <a name="service-order-item-requirements"></a><span data-ttu-id="ca8f5-103">Zapotrzebowanie na towary w zleceniu serwisowym</span><span class="sxs-lookup"><span data-stu-id="ca8f5-103">Service order item requirements</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ca8f5-104">Można utworzyć zlecenie serwisowe do śledzenia i zarządzania usługami świadczonymi odbiorcom.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="ca8f5-105">Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="ca8f5-106">Zapotrzebowania na towary mogą być realizowane bezpośrednio z magazynu lub mogą zainicjować zlecenie produkcyjne dla towaru.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="ca8f5-107">Dzięki użyciu zapotrzebowań na towary zamiast transakcji towarowych można zaplanować czas dostawy dokładnie w momencie użycia towaru oraz można utworzyć zamówienie zakupu, dołączyć towar do struktury umowy handlowej i dołączyć zapotrzebowanie na towary w planie produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="ca8f5-108">Zapotrzebowania na towary dla zlecenia serwisowego są przetwarzane za pomocą projektu.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="ca8f5-109">W celu utworzenia zapotrzebowania na towary dla zlecenia serwisowego, takie zlecenie musi być powiązane z projektem.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-109">To create an item requirement on a service order, the service order must be attached to a project.</span></span>

<span data-ttu-id="ca8f5-110">Po utworzeniu zapotrzebowania na towary dla zlecenia serwisowego można je przejrzeć przy użyciu opcji **Projekt** dla pojedynczego zlecenia serwisowego albo przy użyciu formularza **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-110">As soon as an item requirement is created for a service order, it can be viewed from **Project** in the individual service order or through the **Sales order** form.</span></span>

## <a name="view-an-item-requirement-from-a-service-order"></a><span data-ttu-id="ca8f5-111">Przeglądanie zapotrzebowania na towary dla zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="ca8f5-111">View an item requirement from a service order</span></span>

1.  <span data-ttu-id="ca8f5-112">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="ca8f5-113">Kliknij opcję **Wysyłka**, a następnie opcję **Zapotrzebowanie na towary**, a zostanie otwarty formularz **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-113">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span>

3.  <span data-ttu-id="ca8f5-114">Kliknij kartę **Projekt**, a następnie sprawdź pole **Zlecenie serwisowe**, aby obejrzeć zlecenia serwisowe dla zapotrzebowania na towary.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-114">Click the **Project** tab, and check the **Service order** field to see the service orders of the item requirement.</span></span>

## <a name="delete-service-orders-with-item-requirements"></a><span data-ttu-id="ca8f5-115">Usuwanie zleceń serwisowych z zapotrzebowaniem na towary</span><span class="sxs-lookup"><span data-stu-id="ca8f5-115">Delete service orders with item requirements</span></span>

<span data-ttu-id="ca8f5-116">Jeśli dla zlecenia serwisowego jest utworzone zapotrzebowanie na towary, to takiego zlecenia nie można usunąć.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-116">If an item requirement is created on a service order, you cannot delete the service order.</span></span> <span data-ttu-id="ca8f5-117">Należy najpierw usunąć zapotrzebowanie na towary i dopiero potem usunąć zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-117">You must delete the item requirement before you can delete the service order.</span></span>

1.  <span data-ttu-id="ca8f5-118">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-118">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="ca8f5-119">Kliknij opcję **Wysyłka**, a następnie opcję **Zapotrzebowanie na towary**, a zostanie otwarty formularz **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-119">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span> <span data-ttu-id="ca8f5-120">Ten formularz zawiera listę zapotrzebowań na towary utworzonych dla określonego zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-120">This form lists the item requirements that are created on the service order.</span></span>

3.  <span data-ttu-id="ca8f5-121">Wybierz odpowiednie zapotrzebowanie na towar do usunięcia, a następnie kliknij przycisk **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-121">Select the item requirement to delete, and then click **Delete**.</span></span>

<span data-ttu-id="ca8f5-122">– lub –</span><span class="sxs-lookup"><span data-stu-id="ca8f5-122">–or–</span></span>

1.  <span data-ttu-id="ca8f5-123">Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Wspólne** \> **Projekty** \> **Wszystkie projekty**.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-123">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="ca8f5-124">Otwórz projekt, w którego skład wchodzi zlecenie serwisowe, dla którego utworzono zapotrzebowanie na towary.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-124">Open the project that has the service order in which an item requirement is created.</span></span>

3.  <span data-ttu-id="ca8f5-125">W formularzu **Projekty** w okienku po prawej stronie kliknij przycisk **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-125">In the **Projects** form, in the right pane, click **Item requirements**.</span></span> <span data-ttu-id="ca8f5-126">Formularz **Zapotrzebowanie na towary** będzie zawierał spis wszystkich zapotrzebowań na towary powiązanych z wybranym projektem.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-126">The **Item requirements** form lists the item requirements that are associated with the selected project.</span></span>

4.  <span data-ttu-id="ca8f5-127">Wybierz odpowiednie zapotrzebowanie na towar do usunięcia, a następnie kliknij przycisk **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-127">Select the item requirement to delete, and then click **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca8f5-128">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="ca8f5-128">See also</span></span>

<span data-ttu-id="ca8f5-129">[Zapotrzebowanie na towary (formularz)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="ca8f5-129">[Item requirements (form)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]