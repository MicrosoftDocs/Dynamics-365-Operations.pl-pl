---
title: Sekwencja numerów zarządzania transportem
description: W tym temacie opisano, jak skonfigurować sekwencje numerów do zarządzania transportem.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: f3da757cbf47e0e1af781b720d17a673e19aeb3b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807687"
---
# <a name="transportation-management-number-sequence"></a><span data-ttu-id="aa206-103">Sekwencja numerów zarządzania transportem</span><span class="sxs-lookup"><span data-stu-id="aa206-103">Transportation management number sequence</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa206-104">Strona **Sekwencje numerów** w module zarządzania transportem umożliwia konfigurowanie różnych numerów pro.</span><span class="sxs-lookup"><span data-stu-id="aa206-104">Use the **Number sequences** page in the transportation management module to set up various pro numbers.</span></span> <span data-ttu-id="aa206-105">Numery pro są używane przez przewoźników do organizowania i śledzenia postępu każdej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="aa206-105">Pro numbers are used by carriers to organize and track the progress of each shipment.</span></span>

## <a name="create-a-number-sequence-for-a-pro-number"></a><span data-ttu-id="aa206-106">Utwórz sekwencję liczb dla numeru pro</span><span class="sxs-lookup"><span data-stu-id="aa206-106">Create a number sequence for a pro number</span></span>

<span data-ttu-id="aa206-107">Aby utworzyć sekwencję numerów dla numeru pro, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="aa206-107">To create a number sequence for a pro number, do the following:</span></span>

1. <span data-ttu-id="aa206-108">Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Numery kolejne**.</span><span class="sxs-lookup"><span data-stu-id="aa206-108">Go to **Transportation management \> Setup \> Carriers \> Number sequences**.</span></span>
1. <span data-ttu-id="aa206-109">Wybierz pozycję **Nowy**, aby utworzyć nową sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="aa206-109">Select **New** to create a new number sequence.</span></span>
1. <span data-ttu-id="aa206-110">Wprowadź unikatowy identyfikator i opisową nazwę sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="aa206-110">Enter a unique ID and descriptive name for the number sequence.</span></span>
1. <span data-ttu-id="aa206-111">W polu **Typ sekwencji numerów** jedyną opcją jest *numer pro*.</span><span class="sxs-lookup"><span data-stu-id="aa206-111">In the **Number sequence type** field, *Pro number* is the only option.</span></span>
1. <span data-ttu-id="aa206-112">W polu **Cyfra kontrolna**, *Cyfra kontrolna* jest jedyną opcją i skonfigurowano ją jako aparat ogólny.</span><span class="sxs-lookup"><span data-stu-id="aa206-112">In the **Check digit** field, *Check digit* is the only option and is set up as a generic engine.</span></span>
1. <span data-ttu-id="aa206-113">Na skróconej karcie **Sekwencja** podaj informacje o sekwencji.</span><span class="sxs-lookup"><span data-stu-id="aa206-113">On the **Sequence** FastTab, provide information about the sequence.</span></span>
1. <span data-ttu-id="aa206-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="aa206-114">Close the page.</span></span>

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a><span data-ttu-id="aa206-115">Łączenie sekwencji numerów z przewoźnikiem</span><span class="sxs-lookup"><span data-stu-id="aa206-115">Link a number sequence to a shipping carrier</span></span>

<span data-ttu-id="aa206-116">Aby połączyć sekwencję numerów z przewoźnikiem, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="aa206-116">To link a number sequence to a carrier, do the following:</span></span>

1. <span data-ttu-id="aa206-117">Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Firmy przewozowe**.</span><span class="sxs-lookup"><span data-stu-id="aa206-117">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="aa206-118">Wybierz przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="aa206-118">Select a shipping carrier.</span></span>
1. <span data-ttu-id="aa206-119">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="aa206-119">Select **Edit**.</span></span>
1. <span data-ttu-id="aa206-120">Na skróconej karcie **Omówienie** wybierz opcję w polu **Sekwencja numerów produktów**.</span><span class="sxs-lookup"><span data-stu-id="aa206-120">On the **Overview** FastTab, select an option in the **Pro number sequence** field.</span></span>
1. <span data-ttu-id="aa206-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="aa206-121">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]