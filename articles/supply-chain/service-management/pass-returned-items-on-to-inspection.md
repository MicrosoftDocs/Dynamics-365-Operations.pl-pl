---
title: Przekazywanie zwróconych towarów do inspekcji
description: Rejestrując zwrócony towar, można określić, że przed zwróceniem do magazynu lub likwidacją towar powinien zostać wysłany do inspekcji.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7207c54a88b8a7fc6c38db50c4916d1fc16b5ec4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006691"
---
# <a name="pass-returned-items-on-to-inspection"></a><span data-ttu-id="ef9bf-103">Przekazywanie zwróconych towarów do inspekcji</span><span class="sxs-lookup"><span data-stu-id="ef9bf-103">Pass returned items on to inspection</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ef9bf-104">Rejestrując zwrócony towar, można określić, że przed zwróceniem do magazynu lub likwidacją towar powinien zostać wysłany do inspekcji.</span><span class="sxs-lookup"><span data-stu-id="ef9bf-104">When registering a returned item, you may determine that an item should be sent for inspection before it is returned to inventory or disposed of in some other way.</span></span>

1.  <span data-ttu-id="ef9bf-105">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Arkusze** \> **Przyjęcie pozycji** \> **Przyjęcie pozycji**.</span><span class="sxs-lookup"><span data-stu-id="ef9bf-105">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>
    
    <span data-ttu-id="ef9bf-106">\-lub-</span><span class="sxs-lookup"><span data-stu-id="ef9bf-106">\-or-</span></span>
    
    <span data-ttu-id="ef9bf-107">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Arkusze** \> **Przyjęcie pozycji** \> **Przyjęcie z produkcji**.</span><span class="sxs-lookup"><span data-stu-id="ef9bf-107">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Production input**.</span></span>

2.  <span data-ttu-id="ef9bf-108">W formularzu **Arkusz lokalizacji** zarejestruj przyjęcie towaru w zwykły sposób.</span><span class="sxs-lookup"><span data-stu-id="ef9bf-108">On the **Location journal** form, register the receipt of an item as usual.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="ef9bf-109">Aby uzyskać informacje o rejestrowaniu przyjęcia zwróconych towarów, zobacz <A href="register-the-receipt-of-returned-items.md">Rejestrowanie przyjęcia zwróconych towarów</A></span><span class="sxs-lookup"><span data-stu-id="ef9bf-109">For information about registering the receipt of returned items, see <A href="register-the-receipt-of-returned-items.md">Register the receipt of returned items</A></span></span></P>



3.  <span data-ttu-id="ef9bf-110">Na karcie **Wartości domyślne** w obszarze **Tryb obsługi** zaznacz pole wyboru **Zarządzanie kwarantanną**.</span><span class="sxs-lookup"><span data-stu-id="ef9bf-110">On the **Default values** tab, in the **Mode of handling** area, select the **Quarantine management** box.</span></span>

<span data-ttu-id="ef9bf-111">Spowoduje to utworzenie w systemie zlecenia kwarantanny, a osoba lub dział wykonujący inspekcje odpowie na to zlecenie za pomocą formularza **Zlecenie kwarantanny**.</span><span class="sxs-lookup"><span data-stu-id="ef9bf-111">This will prompt the system to create a quarantine order, and the person or department that performs inspections will respond to this order using the **Quarantine order** form.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef9bf-112">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="ef9bf-112">See also</span></span>

[<span data-ttu-id="ef9bf-113">Poddawanie zwróconych towarów inspekcji</span><span class="sxs-lookup"><span data-stu-id="ef9bf-113">Take returned items through inspection</span></span>](take-returned-items-through-inspection.md)

[<span data-ttu-id="ef9bf-114">Określanie sposobu likwidacji zwróconych towarów</span><span class="sxs-lookup"><span data-stu-id="ef9bf-114">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)

