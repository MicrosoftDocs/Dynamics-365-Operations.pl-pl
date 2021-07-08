---
title: Pozycja nie może mieć BOM ani formuły
description: Przy próbie złożenia zamówienia pojawia się komunikat o błędzie podczas sprawdzania poprawności pozycji. Stwierdza, że element nie może posiadać listy składowej (BOM) lub wzoru.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294155"
---
# <a name="item-cant-have-a-bom-or-formula"></a><span data-ttu-id="2b8f4-104">Pozycja nie może mieć BOM ani formuły</span><span class="sxs-lookup"><span data-stu-id="2b8f4-104">Item can't have a BOM or formula</span></span>

<span data-ttu-id="2b8f4-105">Kod błędu: PRO2614</span><span class="sxs-lookup"><span data-stu-id="2b8f4-105">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="2b8f4-106">Objawy</span><span class="sxs-lookup"><span data-stu-id="2b8f4-106">Symptoms</span></span>

<span data-ttu-id="2b8f4-107">Przy próbie złożenia zamówienia podczas sprawdzania poprawności pozycji pojawia się następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="2b8f4-107">When you try to firm an order, you receive the following error message during item validation:</span></span>

> <span data-ttu-id="2b8f4-108">Pozycja nie może mieć BOM ani formuły</span><span class="sxs-lookup"><span data-stu-id="2b8f4-108">Item cannot have a BOM or formula</span></span>

## <a name="resolution"></a><span data-ttu-id="2b8f4-109">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="2b8f4-109">Resolution</span></span>

<span data-ttu-id="2b8f4-110">Towary z BOM lub formułą muszą być typu *Planowanie*, *BOM* lub *formuła*.</span><span class="sxs-lookup"><span data-stu-id="2b8f4-110">Items that have a bill of materials (BOM) or formula must be of the *Planning item*, *BOM*, or *formula* type.</span></span> <span data-ttu-id="2b8f4-111">Aby zmienić typ elementu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2b8f4-111">To change the type of an item, follow these steps.</span></span>

1. <span data-ttu-id="2b8f4-112">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="2b8f4-112">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="2b8f4-113">Otwórz odpowiedni produkt.</span><span class="sxs-lookup"><span data-stu-id="2b8f4-113">Open the relevant product.</span></span>
1. <span data-ttu-id="2b8f4-114">Na skróconej karcie **Konstruuj** ustaw pole **Typ produkcji** na *Element planowania*, *BOM* lub *formuła*.</span><span class="sxs-lookup"><span data-stu-id="2b8f4-114">On the **Engineer** FastTab, set the **Production type** field to *Planning item*, *BOM*, or *formula*.</span></span>
