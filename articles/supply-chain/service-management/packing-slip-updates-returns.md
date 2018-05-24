---
title: "Aktualizowanie dokumentów dostawy w związku ze zwrotami"
description: "Aby zwrócone towary mogły zostać przyjęte do magazynu, najpierw trzeba zaktualizować dokument dostawy dla zamówienia, do którego one należą."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
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
ms.openlocfilehash: 7532c5b1debdb498c2d6bab129208a412387c8fa
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="packing-slip-updates-for-returns"></a><span data-ttu-id="ca713-103">Aktualizowanie dokumentów dostawy w związku ze zwrotami</span><span class="sxs-lookup"><span data-stu-id="ca713-103">Packing slip updates for returns</span></span>  

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ca713-104">Aby zwrócone towary mogły zostać przyjęte do magazynu, najpierw trzeba zaktualizować dokument dostawy dla zamówienia, do którego one należą.</span><span class="sxs-lookup"><span data-stu-id="ca713-104">Before returned items can be received into inventory, the packing slip for the order to which they belong must be updated.</span></span> <span data-ttu-id="ca713-105">Podobnie jak proces aktualizacji faktury jest aktualizacją transakcji finansowej, tak proces aktualizacji dokumentu dostawy jest fizyczną aktualizacją rekordu zapasów, tzn. zatwierdza zmiany w zapasach.</span><span class="sxs-lookup"><span data-stu-id="ca713-105">Just as the invoice update process is the update to the financial transaction, the packing slip update process is the physical update of the inventory record, which means that it commits the changes to inventory.</span></span> <span data-ttu-id="ca713-106">W przypadku zwrotów kroki przypisane do akcji dyspozycji są implementowane podczas aktualizacji dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="ca713-106">In the case of returns, the steps that are assigned to the disposition action are implemented during the packing slip update.</span></span>

<span data-ttu-id="ca713-107">Aktualizację dokumentu dostawy można przetworzyć w arkuszu przyjęcia towaru lub zamówieniu zwrotu.</span><span class="sxs-lookup"><span data-stu-id="ca713-107">The packing slip update can be processed in either the item arrival journal or the return order.</span></span>

<span data-ttu-id="ca713-108">W trakcie procesu księgowania dokumentów dostawy numer odwołania dokumentu dostawy z dokumentów wysyłki odbiorcy można skojarzyć z wierszami zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ca713-108">As part of the process for posting packing slips, the packing slip reference number from the customer’s shipping documents can be associated with the order lines.</span></span> <span data-ttu-id="ca713-109">To skojarzenie jest opcjonalne i ma charakter wyłącznie informacyjny.</span><span class="sxs-lookup"><span data-stu-id="ca713-109">This association is optional and for reference only.</span></span> <span data-ttu-id="ca713-110">Nie tworzy żadnych aktualizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="ca713-110">It does not create any transactional updates.</span></span>

<span data-ttu-id="ca713-111">Jeśli nie wszystkie oczekiwane towary do zwrotu nadejdą, w aktualizacji dokumentu dostawy należy uwzględnić tylko ilość przyjętą.</span><span class="sxs-lookup"><span data-stu-id="ca713-111">If not all of the expected return items have arrived, you should include only the quantity that has been received in the packing slip update.</span></span> <span data-ttu-id="ca713-112">Pozostałe towary należy pozostawić w zamówieniu, dopóki nie nadejdzie reszta wysyłki zwrotu.</span><span class="sxs-lookup"><span data-stu-id="ca713-112">Leave the remaining items on the order until the rest of the return shipment has arrived.</span></span>

<span data-ttu-id="ca713-113">Ponadto jeśli towar zostanie odesłany z kwarantanny do działu wysyłek i przyjęć, na przykład w przypadku, gdy inspektor kwarantanny nie wie, gdzie ma być przechowywany towar w zapasach, należy zaktualizować odpowiedni dokument dostawy, aby poprawnie zarejestrować i obsługiwać kod dyspozycji określony w wyniku kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="ca713-113">If an item is sent back from quarantine to the Shipping and Receiving department, such as when the quarantine inspector does not know where to store the item in inventory, the corresponding packing slip must be updated to correctly register and act on the disposition code that is specified as a result of the quarantine.</span></span>

<span data-ttu-id="ca713-114">Podczas aktualizacji dokumentu dostawy dla towaru zwróconego na podstawie umowy sprzedaży zobowiązanie umowy sprzedaży dla tego towaru jest automatycznie aktualizowane, aby odzwierciedlało zmianę ilości lub kwoty.</span><span class="sxs-lookup"><span data-stu-id="ca713-114">When you update a packing slip for a returned item that is from a sales agreement, the sales agreement commitment for that item is automatically updated to reflect the change in the quantity or the amount.</span></span> 

## <a name="see-also"></a><span data-ttu-id="ca713-115">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="ca713-115">See also</span></span>

[<span data-ttu-id="ca713-116">Aktualizowanie faktur w związku ze zwrotami</span><span class="sxs-lookup"><span data-stu-id="ca713-116">Perform invoice updates for returns</span></span>](perform-invoice-updates-for-returns.md)

  



