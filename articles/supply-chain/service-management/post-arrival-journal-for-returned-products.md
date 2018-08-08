---
title: "Księgowanie arkusza przyjęcia dla zwrotu produktów"
description: "Można zaksięgować arkusz przywozu zwróconych produktów."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 75f37ce016acb4b479a9cf4dff205562ce00f02c
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---


# <a name="post-arrival-journal-for-returned-products"></a><span data-ttu-id="344b0-103">Księgowanie arkusza przyjęcia dla zwrotu produktów</span><span class="sxs-lookup"><span data-stu-id="344b0-103">Post arrival journal for returned products</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="344b0-104">Aby przetworzyć zwrot, najpierw sprawdź poprawność wielkości zwrotu i zaktualizuj pole wielkości w arkuszu przyjęć towarów.</span><span class="sxs-lookup"><span data-stu-id="344b0-104">To process a return, first validate the return quantity, update the quantity field in the item arrival journal.</span></span> <span data-ttu-id="344b0-105">Następnie wybierz kod dyspozycji lub wskaż, że zwracane towary muszą być sprawdzone.</span><span class="sxs-lookup"><span data-stu-id="344b0-105">Then select a disposition code or indicate that the returned items have to be inspected.</span></span> <span data-ttu-id="344b0-106">Po wykonaniu tych kroków można zaksięgować arkusz przyjęcia towaru dla zamówienia zwrotu.</span><span class="sxs-lookup"><span data-stu-id="344b0-106">After completing these steps, you can post the item arrival journal for the return order.</span></span>

1.  <span data-ttu-id="344b0-107">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Okresowe** \> **Przegląd przyjęć**.</span><span class="sxs-lookup"><span data-stu-id="344b0-107">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="344b0-108">W filtrze **Nazwa konfiguracji** wybierz opcję **Zamówienie zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="344b0-108">In the **Setup name** filter, select **Return order**.</span></span>

3.  <span data-ttu-id="344b0-109">Jeśli lista przyjęć jest długa, użyj pól w obszarze **Zakres**, aby ją zawęzić.</span><span class="sxs-lookup"><span data-stu-id="344b0-109">If the list of receipts is long, use the fields in the **Range** area to narrow the list.</span></span>

4.  <span data-ttu-id="344b0-110">Zlokalizuj wiersz zamówienia zwrotu, który chcesz zaksięgować, zaznacz jego pole wyboru **Zaznacz do przyjęcia**, a następnie kliknij przycisk **Rozpocznij przyjęcie**.</span><span class="sxs-lookup"><span data-stu-id="344b0-110">Locate the line of the return order that you want to post, select its **Select for arrival** box, and then click **Start arrival**.</span></span>

5.  <span data-ttu-id="344b0-111">Kliknij kolejno opcje **Arkusze** \> **Pokaż arkusze przyjęcia**, aby otworzyć formularz **Arkusz lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="344b0-111">Click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="344b0-112">Aby wyświetlić szczegółowe informacje, wybierz arkusz, a następnie kliknij opcję <STRONG>Wiersze</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="344b0-112">To view detailed information, select a journal, and then click <STRONG>Lines</STRONG>.</span></span></P>


6.  <span data-ttu-id="344b0-113">Wprowadź wszelkie niezbędne aktualizacje, a następnie kliknij przycisk **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="344b0-113">Make any necessary updates, and then click **Post**.</span></span>

<span data-ttu-id="344b0-114">Po zaksięgowaniu arkusza zwrócone towary są rejestrowane w zapasach, a formularz **Zamówienia zwrotu** wskazuje, że towary zostały przyjęte na magazyn.</span><span class="sxs-lookup"><span data-stu-id="344b0-114">After the journal is posted, the returned items are registered in inventory, and the **Return orders** form indicates that the items have arrived at the warehouse.</span></span>

## <a name="see-also"></a><span data-ttu-id="344b0-115">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="344b0-115">See also</span></span>

<span data-ttu-id="344b0-116">[Arkusz lokalizacji (formularz)](https://technet.microsoft.com/en-us/library/aa584822\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="344b0-116">[Location journal (form)](https://technet.microsoft.com/en-us/library/aa584822\(v=ax.60\))</span></span>

  



