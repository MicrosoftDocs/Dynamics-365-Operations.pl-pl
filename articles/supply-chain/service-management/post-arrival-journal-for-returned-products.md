---
title: Księgowanie arkusza przyjęcia dla zwrotu produktów
description: Można zaksięgować arkusz przywozu zwróconych produktów.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14619069c0e984060f67fc4536b311c6802bfec7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214305"
---
# <a name="post-arrival-journal-for-returned-products"></a><span data-ttu-id="4f635-103">Księgowanie arkusza przyjęcia dla zwrotu produktów</span><span class="sxs-lookup"><span data-stu-id="4f635-103">Post arrival journal for returned products</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="4f635-104">Aby przetworzyć zwrot, najpierw sprawdź poprawność wielkości zwrotu i zaktualizuj pole wielkości w arkuszu przyjęć towarów.</span><span class="sxs-lookup"><span data-stu-id="4f635-104">To process a return, first validate the return quantity, update the quantity field in the item arrival journal.</span></span> <span data-ttu-id="4f635-105">Następnie wybierz kod dyspozycji lub wskaż, że zwracane towary muszą być sprawdzone.</span><span class="sxs-lookup"><span data-stu-id="4f635-105">Then select a disposition code or indicate that the returned items have to be inspected.</span></span> <span data-ttu-id="4f635-106">Po wykonaniu tych kroków można zaksięgować arkusz przyjęcia towaru dla zamówienia zwrotu.</span><span class="sxs-lookup"><span data-stu-id="4f635-106">After completing these steps, you can post the item arrival journal for the return order.</span></span>

1.  <span data-ttu-id="4f635-107">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Okresowe** \> **Przegląd przyjęć**.</span><span class="sxs-lookup"><span data-stu-id="4f635-107">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="4f635-108">W filtrze **Nazwa konfiguracji** wybierz opcję **Zamówienie zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="4f635-108">In the **Setup name** filter, select **Return order**.</span></span>

3.  <span data-ttu-id="4f635-109">Jeśli lista przyjęć jest długa, użyj pól w obszarze **Zakres**, aby ją zawęzić.</span><span class="sxs-lookup"><span data-stu-id="4f635-109">If the list of receipts is long, use the fields in the **Range** area to narrow the list.</span></span>

4.  <span data-ttu-id="4f635-110">Zlokalizuj wiersz zamówienia zwrotu, który chcesz zaksięgować, zaznacz jego pole wyboru **Zaznacz do przyjęcia**, a następnie kliknij przycisk **Rozpocznij przyjęcie**.</span><span class="sxs-lookup"><span data-stu-id="4f635-110">Locate the line of the return order that you want to post, select its **Select for arrival** box, and then click **Start arrival**.</span></span>

5.  <span data-ttu-id="4f635-111">Kliknij kolejno opcje **Arkusze** \> **Pokaż arkusze przyjęcia**, aby otworzyć formularz **Arkusz lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="4f635-111">Click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="4f635-112">Aby wyświetlić szczegółowe informacje, wybierz arkusz, a następnie kliknij opcję <STRONG>Wiersze</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4f635-112">To view detailed information, select a journal, and then click <STRONG>Lines</STRONG>.</span></span></P>


6.  <span data-ttu-id="4f635-113">Wprowadź wszelkie niezbędne aktualizacje, a następnie kliknij przycisk **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="4f635-113">Make any necessary updates, and then click **Post**.</span></span>

<span data-ttu-id="4f635-114">Po zaksięgowaniu arkusza zwrócone towary są rejestrowane w zapasach, a formularz **Zamówienia zwrotu** wskazuje, że towary zostały przyjęte na magazyn.</span><span class="sxs-lookup"><span data-stu-id="4f635-114">After the journal is posted, the returned items are registered in inventory, and the **Return orders** form indicates that the items have arrived at the warehouse.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f635-115">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4f635-115">See also</span></span>

<span data-ttu-id="4f635-116">[Arkusz lokalizacji (formularz)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="4f635-116">[Location journal (form)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]