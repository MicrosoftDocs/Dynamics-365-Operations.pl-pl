---
title: Konfigurowanie magazynów dla zamówień przeniesienia
description: W tym temacie opisano, jak można skonfigurować magazyny do obsługi zamówień przeniesienia.
author: Mirzaab
manager: tfehr
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: e482567eb92b9ab891d41d82d10cbb87f9b7fb01
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017490"
---
# <a name="set-up-warehouses-for-transfer-orders"></a><span data-ttu-id="56583-103">Konfigurowanie magazynów dla zamówień przeniesienia</span><span class="sxs-lookup"><span data-stu-id="56583-103">Set up warehouses for transfer orders</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56583-104">W celu utworzenia hierarchii obsługującej zamówienia między magazynami można korzystać z poziomów magazynowych.</span><span class="sxs-lookup"><span data-stu-id="56583-104">You can use warehouse levels to create a hierarchy that supports transfer orders between warehouses.</span></span> <span data-ttu-id="56583-105">Na podstawie tego ustawienia moduł planowania głównego oblicza zapotrzebowanie na towary na danym poziomie magazynowym i generuje zaplanowane zamówienia przeniesienia z przypisanego magazynu źródłowego w celu spełnienia zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="56583-105">Based on this setup, master scheduling calculates item requirements at the individual warehouse level and generates planned transfer orders from an assigned source warehouse to fulfill them.</span></span>

1.  <span data-ttu-id="56583-106">Kliknij kolejno **Zarządzanie zapasami > Konfiguracja > Podział magazynu > Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="56583-106">Click **Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>

2.  <span data-ttu-id="56583-107">Wybierz magazyn, którego zapasy mają zostać uzupełnione.</span><span class="sxs-lookup"><span data-stu-id="56583-107">Select the warehouse that you want to refill.</span></span>

3.  <span data-ttu-id="56583-108">Na skróconej karcie **Planowanie główne** zaznacz pole wyboru **Uzupełnianie**.</span><span class="sxs-lookup"><span data-stu-id="56583-108">On the **Master planning** FastTab, select the **Refilling** check box.</span></span>

4.  <span data-ttu-id="56583-109">W polu **Magazyn główny** wybierz magazyn, który ma zostać przypisany, jako magazyn uzupełniający.</span><span class="sxs-lookup"><span data-stu-id="56583-109">In the **Main warehouse** field, select the warehouse that you want to assign as the refilling warehouse.</span></span> <span data-ttu-id="56583-110">Moduł planowania głównego obliczy wymagane przeniesienie dla wybranego magazynu i wygeneruje zamówienie zaplanowanego przeniesienia z magazynu przypisanego w polu **Magazyn główny**.</span><span class="sxs-lookup"><span data-stu-id="56583-110">Master scheduling calculates a transfer requirement for the selected warehouse and generates a planned transfer order from the assigned **Main warehouse**.</span></span>
   
    > [!NOTE]
    > <P><span data-ttu-id="56583-111">Jeśli pole <STRONG>Uzupełnianie</STRONG> pozostanie puste, wybrany magazyn będzie miał przypisany poziom magazynowy względem <STRONG>Magazynu głównego</STRONG>, lecz<STRONG>Magazyn główny</STRONG> nie będzie ustawiony jako magazyn uzupełnień.</span><span class="sxs-lookup"><span data-stu-id="56583-111">If you clear the <STRONG>Refilling</STRONG> check box, the selected warehouse is assigned a warehouse level in regard to the <STRONG>Main warehouse</STRONG>, but the <STRONG>Main warehouse</STRONG> is not set up as a refilling warehouse.</span></span></P>

5.  <span data-ttu-id="56583-112">Zamknij stronę, aby zastosować nowe ustawienie.</span><span class="sxs-lookup"><span data-stu-id="56583-112">Close the page to apply the new setup.</span></span>


> [!TIP]
> <P><span data-ttu-id="56583-113">Aby przypisać magazyn uzupełnień, należy najpierw ustawić magazyn jako wymiar magazynowy na stronie <STRONG>Grupy wymiarów magazynowych</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="56583-113">If you want to assign a warehouse for refilling, you must first set up the warehouse as a storage dimension on the <STRONG>Storage dimension groups</STRONG> page.</span></span> <span data-ttu-id="56583-114">Na tej stronie zaznacz pole <STRONG>Aktywne</STRONG> i pole <STRONG>Plan zapotrzebowania wg wymiaru</STRONG> dla danego magazynu.</span><span class="sxs-lookup"><span data-stu-id="56583-114">On this page, select the <STRONG>Active</STRONG> field and the <STRONG>Coverage plan by dimension</STRONG> field for the warehouse.</span></span></P>

## <a name="set-up-transport-lead-time"></a><span data-ttu-id="56583-115">Ustawianie czasu realizacji dostawy</span><span class="sxs-lookup"><span data-stu-id="56583-115">Set up transport lead time</span></span>

<span data-ttu-id="56583-116">Należy także skonfigurować czas realizacji dostawy między magazynami na stronie **Dni transportu**.</span><span class="sxs-lookup"><span data-stu-id="56583-116">You must also set up the transport lead time between the warehouses on the **Transport days** page.</span></span> 
1. <span data-ttu-id="56583-117">Przejdź do **Zarządzanie zapasami > Ustawienia > Dystrybucja > Dni transportu**.</span><span class="sxs-lookup"><span data-stu-id="56583-117">Go to **Inventory management > Setup > Distribution > Transport days**.</span></span>
2. <span data-ttu-id="56583-118">W polu **Punkt przyjęcia** wybierz **magazyn**.</span><span class="sxs-lookup"><span data-stu-id="56583-118">In the **Receiving point** field, select **warehouse**.</span></span>
3. <span data-ttu-id="56583-119">Wybierz **Magazyn wysyłki** , **Magazyn przyjęcia** i **Dni transportu**.</span><span class="sxs-lookup"><span data-stu-id="56583-119">Select the **Shipping warehouse** , **Receiving warehouse** , and **Transport days**.</span></span> 
4. <span data-ttu-id="56583-120">(Opcjonalnie) Można również ustawić czas transportu, w zależności od metody dostawy, w obszarze **Dni transportu na metodę dostawy**.</span><span class="sxs-lookup"><span data-stu-id="56583-120">(Optional) You can also set transport time, depending on the mode of delivery, under the **Transport days per mode of delivery** tab.</span></span>
