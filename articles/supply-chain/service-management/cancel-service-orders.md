---
title: Anuluj zlecenia serwisowe
description: "Zlecenie serwisowe lub wiersz zlecenia serwisowego można anulować z samego zlecenia serwisowego lub można anulować wiele zleceń serwisowych, uruchamiając zadanie okresowe."
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
ms.openlocfilehash: 8e5ad119c28bba18b75bb5ed7854e94a4e734d55
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="cancel-service-orders"></a><span data-ttu-id="e7de0-103">Anuluj zlecenia serwisowe</span><span class="sxs-lookup"><span data-stu-id="e7de0-103">Cancel service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e7de0-104">Zlecenie serwisowe lub wiersz zlecenia serwisowego można anulować z samego zlecenia serwisowego lub można anulować wiele zleceń serwisowych, uruchamiając zadanie okresowe.</span><span class="sxs-lookup"><span data-stu-id="e7de0-104">You can cancel a service order or service order line from the service order itself, or you can cancel multiple service orders by running a periodic job.</span></span>


> [!NOTE]
> <P><span data-ttu-id="e7de0-105">Zlecenia serwisowego nie można anulować, jeśli nie pozwala na to etap, na jakim znajduje się zlecenie serwisowe, jeśli są z nim związane zapotrzebowania na towary lub jeśli zlecenie zostało już zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="e7de0-105">Service orders cannot be canceled if the stage of the service order does not allow cancelation, if the service order has item requirements, or if the service order has already been posted.</span></span></P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a><span data-ttu-id="e7de0-106">Anulowanie zlecenia serwisowego w formularzu Zlecenia serwisowe</span><span class="sxs-lookup"><span data-stu-id="e7de0-106">Cancel a service order in the Service orders form</span></span>

1.  <span data-ttu-id="e7de0-107">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-107">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="e7de0-108">Wybierz zlecenie serwisowe, a następnie w okienku akcji kliknij przycisk **Anuluj zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-108">Select the service order, and on the Action Pane, click **Cancel order**.</span></span>

## <a name="cancel-a-service-order-line"></a><span data-ttu-id="e7de0-109">Anulowanie wiersza zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="e7de0-109">Cancel a service order line</span></span>

1.  <span data-ttu-id="e7de0-110">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-110">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="e7de0-111">Kliknij dwukrotnie zlecenie serwisowe zawierające wiersz, który chcesz anulować.</span><span class="sxs-lookup"><span data-stu-id="e7de0-111">Double-click the service order that contains the line you want to cancel.</span></span>

2.  <span data-ttu-id="e7de0-112">Zaznacz wiersz zlecenia serwisowego, który chcesz anulować, a następnie kliknij opcję **Anulowanie wiersza zamówienia**, aby zmienić stan wiersza na **Anulowano**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-112">Select the service order line that you want to cancel, and then click **Cancel order line** to change the status of the line to **Canceled**.</span></span>


> [!TIP]
> <P><span data-ttu-id="e7de0-113">Aby wycofać anulowanie wiersza zlecenia serwisowego i zmienić stan z powrotem na <STRONG>Utworzono</STRONG>, kliknij przycisk <STRONG>Cofnij anulowanie</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e7de0-113">To reverse the cancellation of a service order line and change the status back to <STRONG>Created</STRONG>, click <STRONG>Revoke cancel</STRONG>.</span></span></P>


## <a name="cancel-multiple-service-orders"></a><span data-ttu-id="e7de0-114">Anulowanie wielu zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="e7de0-114">Cancel multiple service orders</span></span>

1.  <span data-ttu-id="e7de0-115">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Okresowe** \> **Zlecenia serwisowe** \> **Anuluj zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-115">Click **Service management** \> **Periodic** \> **Service orders** \> **Cancel service orders**.</span></span>

2.  <span data-ttu-id="e7de0-116">Kliknij przycisk **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-116">Click the **Select** button.</span></span>

3.  <span data-ttu-id="e7de0-117">W formularzu **Informacje** w kolumnie **Kryteria** zaznacz zlecenia serwisowe, które chcesz anulować.</span><span class="sxs-lookup"><span data-stu-id="e7de0-117">In the **Inquiry** form, in the **Criteria** column, select the service orders that you want to cancel.</span></span>

4.  <span data-ttu-id="e7de0-118">Kliknij przycisk **OK**, aby zamknąć formularz **Informacje**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-118">Click **OK** to close the **Inquiry** form.</span></span>

5.  <span data-ttu-id="e7de0-119">Zaznacz pole wyboru **Pokaż dziennik informacyjny**, aby wygenerować dziennik informacyjny pokazujący anulowane zlecenia serwisowe.</span><span class="sxs-lookup"><span data-stu-id="e7de0-119">Select the **Show Infolog** check box to generate an Infolog that lists the canceled service orders.</span></span>

6.  <span data-ttu-id="e7de0-120">Zaznacz pole wyboru **Cofnij anulowanie**, jeśli chcesz cofnąć stan **Anulowano** zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="e7de0-120">Select the **Revoke cancel** check box if you want to reverse the **Canceled** status of a service order.</span></span>

7.  <span data-ttu-id="e7de0-121">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-121">Click **OK**.</span></span>

<span data-ttu-id="e7de0-122">Zaznaczone zlecenia serwisowe zostaną anulowane lub ich stan postępu **Anulowano** zostanie cofnięty do stanu **W toku**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-122">The selected service orders are either canceled or their progress status of **Canceled** has been reversed to **In process**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="e7de0-123">W przypadku zaznaczenia pola wyboru <STRONG>Cofnij anulowanie</STRONG> zlecenia serwisowe znajdujące się w stanie postępu <STRONG>Anulowano</STRONG> zostaną wycofane, a zlecenia serwisowe znajdujące się w stanie postępu <STRONG>W toku</STRONG> nie zostaną anulowane.</span><span class="sxs-lookup"><span data-stu-id="e7de0-123">If you select the <STRONG>Revoke cancel</STRONG> check box, service orders with a progress status of <STRONG>Canceled</STRONG> are reversed and service orders with a progress status of <STRONG>In process</STRONG> are not canceled.</span></span></P>


  


