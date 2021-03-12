---
title: Średnia ruchoma sekwencji kosztu rezerwowego
description: Ten temat zawiera informacje dotyczące sekwencji kosztów rezerwowych dla obliczeń średniej ruchomej w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
manager: tfehr
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 541b7ecca5c1c36999f573d6d0f2dc0c9e901631
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967590"
---
# <a name="moving-average-fallback-cost-sequence"></a><span data-ttu-id="27499-103">Średnia ruchoma sekwencji kosztu rezerwowego</span><span class="sxs-lookup"><span data-stu-id="27499-103">Moving average fallback cost sequence</span></span>

<span data-ttu-id="27499-104">Jednym ze sposobów obliczania kosztów zapasów jest użycie _średniej ruchomej_.</span><span class="sxs-lookup"><span data-stu-id="27499-104">One way that you can calculate the cost of your inventory is by using a _moving average_.</span></span> <span data-ttu-id="27499-105">Z każdym towarem magazynowym można skojarzyć maksymalnie trzy wartości kosztów:</span><span class="sxs-lookup"><span data-stu-id="27499-105">Up to three cost values can be associated with each inventory item:</span></span>

- <span data-ttu-id="27499-106">**Ostatni problem** — ostatni koszt rozchód przypisany przed stanem zapasów był ujemny</span><span class="sxs-lookup"><span data-stu-id="27499-106">**Last issue** – The last issue cost that was assigned before inventory went negative</span></span>
- <span data-ttu-id="27499-107">**Aktywny koszt** — ostatni koszt uaktywniony w wersji wyceny</span><span class="sxs-lookup"><span data-stu-id="27499-107">**Active cost** – The latest cost that was activated in a costing version</span></span>
- <span data-ttu-id="27499-108">**Cena towaru** — koszt określony dla zwolnionego produktu</span><span class="sxs-lookup"><span data-stu-id="27499-108">**Item price** – The cost that is specified for the released product</span></span>

<span data-ttu-id="27499-109">Aby określić, które z tych wartości kosztów powinny być używane w obliczeniach średniej ruchomej, system używa _sekwencji kosztu rezerwowego_ do określenia kolejności preferencji dla wartości.</span><span class="sxs-lookup"><span data-stu-id="27499-109">To determine which of these cost values should be used in moving average calculations, the system uses a _fallback cost sequence_ to establish the order of preference for the values.</span></span> <span data-ttu-id="27499-110">Jeśli preferowana wartość kosztu jest niedostępna, system używa wartości kolejnego uprzywilejowania i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="27499-110">If the preferred cost value isn't available, the system uses the next-preferred value, and so on.</span></span>

<span data-ttu-id="27499-111">W poprzednich wersjach Microsoft Dynamics 365 Supply Chain Management, system używał stałej sekwencji kosztów rezerwowych (_Ostatni problem — Koszt aktywny – Cena towaru_).</span><span class="sxs-lookup"><span data-stu-id="27499-111">In previous versions of Microsoft Dynamics 365 Supply Chain Management, the system used a fixed fallback cost sequence (_Last issue – Active cost – Item price_).</span></span> <span data-ttu-id="27499-112">W wersji 10.0.11 ta sekwencja nadal jest sekwencją domyślną.</span><span class="sxs-lookup"><span data-stu-id="27499-112">In version 10.0.11, this sequence is still the default sequence.</span></span> <span data-ttu-id="27499-113">Można jednak również włączyć funkcję umożliwiającą wybranie spośród trzech dostępnych sekwencji kosztów rezerwowych.</span><span class="sxs-lookup"><span data-stu-id="27499-113">However, you can also turn on a feature that lets you select among three available fallback cost sequences.</span></span> <span data-ttu-id="27499-114">Ta funkcja może być szczególnie przydatna w organizacjach, które regularnie korzystają z ujemnych wartości zapasów.</span><span class="sxs-lookup"><span data-stu-id="27499-114">This feature can be especially useful for organizations that regularly use negative inventory values.</span></span>

<span data-ttu-id="27499-115">Aby można było korzystać z selektora kosztu rezerwowego, użytkownik (lub administrator) musi skorzystać z [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) w celu włączenia funkcji, która ma nazwę _Średnia ruchoma sekwencji kosztu rezerwowego_.</span><span class="sxs-lookup"><span data-stu-id="27499-115">To make the selector for the fallback cost sequence available, you (or an admin) must use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named _Moving average fallback cost sequence_.</span></span>

<span data-ttu-id="27499-116">Aby wybrać sekwencję kosztów rezerwowych dla obliczeń średniej ruchomej, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="27499-116">To select the fallback cost sequence for moving average calculations, follow these steps.</span></span>

1. <span data-ttu-id="27499-117">Otwórz stronę **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="27499-117">Open the **Parameters** page.</span></span>
2. <span data-ttu-id="27499-118">Na karcie **Księgowanie zapasów** w sekcji **Średnia ruchoma** określ wartość w polu **Sekwencji kosztu rezerwowego** na jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="27499-118">On the **Inventory accounting** tab, in the **Moving average** section, set the **Fallback cost sequence** field to one of the following values:</span></span>

    - <span data-ttu-id="27499-119">**Ostatni problem — Koszt aktywny — Cena towaru** — ta sekwencja jest sekwencją domyślną.</span><span class="sxs-lookup"><span data-stu-id="27499-119">**Last issue – Active cost – Item price** – This sequence is the default sequence.</span></span> <span data-ttu-id="27499-120">Jest to ta sama sekwencja, która jest używana, jeśli funkcja _Średnia ruchoma sekwencji kosztu rezerwowego_ nie jest włączona.</span><span class="sxs-lookup"><span data-stu-id="27499-120">It's the same sequence that is used if the _Moving average fallback cost sequence_ feature isn't turned on.</span></span>
    - <span data-ttu-id="27499-121">**Aktywny koszt — Ostatni problem**</span><span class="sxs-lookup"><span data-stu-id="27499-121">**Active cost – Last issue**</span></span>
    - <span data-ttu-id="27499-122">**Koszt aktywny — cena towaru** — w organizacjach mogą występować problemy z wydajnością, jeśli są one używane w procesach biznesowych, w których zapasy są zwykle ujemne, a jednocześnie objętość transakcji jest wysoka.</span><span class="sxs-lookup"><span data-stu-id="27499-122">**Active cost – Item price** – Organizations might experience performance issues if they use business processes where inventory regularly goes negative and, at the same time, the transaction volume is high.</span></span> <span data-ttu-id="27499-123">To ustawienie pomaga złagodzić te problemy z wydajnością.</span><span class="sxs-lookup"><span data-stu-id="27499-123">This setting can help mitigate those performance issues.</span></span>

<span data-ttu-id="27499-124">![Parametry księgowania zapasów](media/inventory-accounting-parameters.png "Parametry księgowania zapasów")</span><span class="sxs-lookup"><span data-stu-id="27499-124">![Inventory accounting parameters](media/inventory-accounting-parameters.png "Inventory accounting parameters")</span></span>
