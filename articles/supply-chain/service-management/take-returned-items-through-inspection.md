---
title: "Poddawanie zwróconych towarów inspekcji"
description: "Zwrócone towary można poddawać inspekcji."
author: YuyuScheller
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQuarantineOrder
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
ms.openlocfilehash: df209cfdbdef591e9f24161b3651316c43d69ee0
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---


# <a name="take-returned-items-through-inspection"></a><span data-ttu-id="5d2c3-103">Poddawanie zwróconych towarów inspekcji</span><span class="sxs-lookup"><span data-stu-id="5d2c3-103">Take returned items through inspection</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="5d2c3-104">Kliknij kolejno opcje **Zarządzanie zapasami** \> **Okresowe** \> **Zarządzanie jakością** \> **Zlecenia kwarantanny**.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-104">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="5d2c3-105">Znajdź wiersz zamówienia odpowiadający zwracanemu towarowi, który jest sprawdzany.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-105">Locate the order line that corresponds to the returned item that you are inspecting.</span></span>

    > [!NOTE]
    > <P><span data-ttu-id="5d2c3-106">Zlecenie kwarantanny może być skojarzone tylko z jednym kodem towaru.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-106">A quarantine order can be associated with just a single item number.</span></span> <span data-ttu-id="5d2c3-107">Jeśli dziesięć towarów o różnych kodach zostanie zwróconych w ramach jednej wysyłki i wysłanych do kwarantanny, spowoduje to utworzenie dziesięciu odrębnych zleceń kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-107">If 10 items that have different item numbers are returned in a single shipment and sent to quarantine, 10 individual quarantine orders are created.</span></span></P>

3.  <span data-ttu-id="5d2c3-108">Po sprawdzeniu towaru należy w polu **Kod dyspozycji** wybrać odpowiednią opcję wskazującą, co zrobić z towarem i jak mają być obsługiwane powiązane transakcji finansowe.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-108">After examining the item, make a selection in the **Disposition code** field to indicate what should be done with the item and how to handle the related financial transaction.</span></span> <span data-ttu-id="5d2c3-109">Jako przykłady można tu wymienić zwrócenie towaru do magazynu i zwrócenie pieniędzy odbiorcy, przeznaczenie towaru na odpadki i wysłanie odbiorcy towaru zastępczego lub zwrócenie towaru klientowi bez zwracania pieniędzy.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-109">Examples include returning the item to stock and refunding the customer, scrapping the item and sending a replacement to the customer, or returning the item to the customer without credit.</span></span>
    
    > [!NOTE]
    > <P><span data-ttu-id="5d2c3-110">Jeśli tego samego kodu dyspozycji nie można przypisać do wielu zwróconych towarów w partii o jednym numerze towaru, należy podzielić zlecenie kwarantanny (<STRONG>Funkcje</STRONG> &gt; <STRONG>Podziel</STRONG>), aby przypisać inny kod dyspozycji do każdej podpartii.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-110">If multiple returned items in a single item number batch cannot be assigned the same disposition code, you must split the quarantine order (<STRONG>Functions</STRONG> &gt; <STRONG>Split</STRONG>) to assign a different disposition code to each sub-batch.</span></span></P>


4.  <span data-ttu-id="5d2c3-111">Po zakończeniu inspekcji kliknij przycisk **Zgłoszenie wyrobów gotowych**, aby zwolnić zwrócone towary i utworzyć wpis w arkuszu przyjazdu towaru.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-111">When you are finished with the inspection, click **Report as finished** to release the returned items and create an item arrival journal entry.</span></span> <span data-ttu-id="5d2c3-112">Następnie osoba lub dział, który przyjął towary, przetworzy arkusz w odniesieniu do towarów oczekujących na zwrot do magazynu.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-112">The person or department that receives the items then processes the journal for the items to be returned to inventory.</span></span>
    
    <span data-ttu-id="5d2c3-113">– lub –</span><span class="sxs-lookup"><span data-stu-id="5d2c3-113">–or–</span></span>
    
    <span data-ttu-id="5d2c3-114">Zakończ zlecenie kwarantanny i przenieś towary bezpośrednio z powrotem do zapasów, używając jednej z funkcji **Zapasy**.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-114">End the quarantine order, and move the items back into inventory directly by using one of the **Inventory** functions.</span></span>

5.  <span data-ttu-id="5d2c3-115">Zamknij formularz, aby zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-115">Close the form to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d2c3-116">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="5d2c3-116">See also</span></span>

[<span data-ttu-id="5d2c3-117">Określanie sposobu likwidacji zwróconych towarów</span><span class="sxs-lookup"><span data-stu-id="5d2c3-117">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)

  



