---
title: Sekwencja numerów zarządzania transportem
description: W tym temacie opisano, jak skonfigurować sekwencje numerów do zarządzania transportem.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2c3f087ac76412cd2dce93dcb31b796ce2cb3bc4
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "4435687"
---
# <a name="transportation-management-number-sequence"></a><span data-ttu-id="c3815-103">Sekwencja numerów zarządzania transportem</span><span class="sxs-lookup"><span data-stu-id="c3815-103">Transportation management number sequence</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3815-104">Strona **Sekwencje numerów** w module zarządzania transportem umożliwia konfigurowanie różnych numerów pro.</span><span class="sxs-lookup"><span data-stu-id="c3815-104">Use the **Number sequences** page in the transportation management module to set up various pro numbers.</span></span> <span data-ttu-id="c3815-105">Numery pro są używane przez przewoźników do organizowania i śledzenia postępu każdej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="c3815-105">Pro numbers are used by carriers to organize and track the progress of each shipment.</span></span>

## <a name="create-a-number-sequence-for-a-pro-number"></a><span data-ttu-id="c3815-106">Utwórz sekwencję liczb dla numeru pro</span><span class="sxs-lookup"><span data-stu-id="c3815-106">Create a number sequence for a pro number</span></span>

<span data-ttu-id="c3815-107">Aby utworzyć sekwencję numerów dla numeru pro, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="c3815-107">To create a number sequence for a pro number, do the following:</span></span>

1. <span data-ttu-id="c3815-108">Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Numery kolejne**.</span><span class="sxs-lookup"><span data-stu-id="c3815-108">Go to **Transportation management \> Setup \> Carriers \> Number sequences**.</span></span>
1. <span data-ttu-id="c3815-109">Wybierz pozycję **Nowy**, aby utworzyć nową sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="c3815-109">Select **New** to create a new number sequence.</span></span>
1. <span data-ttu-id="c3815-110">Wprowadź unikatowy identyfikator i opisową nazwę sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="c3815-110">Enter a unique ID and descriptive name for the number sequence.</span></span>
1. <span data-ttu-id="c3815-111">W polu **Typ sekwencji numerów** jedyną opcją jest *numer pro*.</span><span class="sxs-lookup"><span data-stu-id="c3815-111">In the **Number sequence type** field, *Pro number* is the only option.</span></span>
1. <span data-ttu-id="c3815-112">W polu **Cyfra kontrolna**, *Cyfra kontrolna* jest jedyną opcją i skonfigurowano ją jako aparat ogólny.</span><span class="sxs-lookup"><span data-stu-id="c3815-112">In the **Check digit** field, *Check digit* is the only option and is set up as a generic engine.</span></span>
1. <span data-ttu-id="c3815-113">Na skróconej karcie **Sekwencja** podaj informacje o sekwencji.</span><span class="sxs-lookup"><span data-stu-id="c3815-113">On the **Sequence** FastTab, provide information about the sequence.</span></span>
1. <span data-ttu-id="c3815-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c3815-114">Close the page.</span></span>

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a><span data-ttu-id="c3815-115">Łączenie sekwencji numerów z przewoźnikiem</span><span class="sxs-lookup"><span data-stu-id="c3815-115">Link a number sequence to a shipping carrier</span></span>

<span data-ttu-id="c3815-116">Aby połączyć sekwencję numerów z przewoźnikiem, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="c3815-116">To link a number sequence to a carrier, do the following:</span></span>

1. <span data-ttu-id="c3815-117">Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Firmy przewozowe**.</span><span class="sxs-lookup"><span data-stu-id="c3815-117">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="c3815-118">Wybierz przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="c3815-118">Select a shipping carrier.</span></span>
1. <span data-ttu-id="c3815-119">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="c3815-119">Select **Edit**.</span></span>
1. <span data-ttu-id="c3815-120">Na skróconej karcie **Omówienie** wybierz opcję w polu **Sekwencja numerów produktów**.</span><span class="sxs-lookup"><span data-stu-id="c3815-120">On the **Overview** FastTab, select an option in the **Pro number sequence** field.</span></span>
1. <span data-ttu-id="c3815-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c3815-121">Close the page.</span></span>
