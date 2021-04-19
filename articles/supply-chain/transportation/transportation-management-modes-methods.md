---
title: Tryby i metody zarządzania transportem
description: W tym temacie przedstawiono sposób konfigurowania trybów i metod zarządzania transportem.
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
ms.openlocfilehash: 71e37dcd4509813f930906ae3bb3d3b98c9100a0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828315"
---
# <a name="transportation-management-modes-and-methods"></a><span data-ttu-id="159be-103">Tryby i metody zarządzania transportem</span><span class="sxs-lookup"><span data-stu-id="159be-103">Transportation management modes and methods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="159be-104">Tryb zarządzania transportem reprezentuje rodzaj transportu, z którego korzysta przewoźnik przy dostawach towarów, takich jak Less than truckload (LTL), Truckload (TL) lub paczka.</span><span class="sxs-lookup"><span data-stu-id="159be-104">The transportation management  mode represents the type of transport that the carrier uses for freight deliveries, such as less than load (LTL), truckload (TL), or parcel.</span></span> <span data-ttu-id="159be-105">Metoda transportu reprezentuje formę transportu używaną przez przewoźnika do dostaw towarów, na przykład lotniczy, lądowy, morski lub kolejowy.</span><span class="sxs-lookup"><span data-stu-id="159be-105">The transportation method represents the form of transport that the carrier uses for freight deliveries, such as air, ground, ocean, or rail.</span></span>

<span data-ttu-id="159be-106">Tryby i metody transportu są używane w kilku kontekstach.</span><span class="sxs-lookup"><span data-stu-id="159be-106">Modes and transportation methods are used in several contexts.</span></span> <span data-ttu-id="159be-107">W planach tras używane są tylko tryby, natomiast podczas konfigurowania przewoźników i usług przewoźników używane są zarówno tryby, jak i metody transportu.</span><span class="sxs-lookup"><span data-stu-id="159be-107">Only modes are used in route plans, while both modes and transportation methods are used when setting up shipping carriers and carrier services.</span></span> <span data-ttu-id="159be-108">Nie ma wyraźnego związku ani hierarchii między rodzajami transportu i środkami transportu.</span><span class="sxs-lookup"><span data-stu-id="159be-108">No explicit relationship or hierarchy exists between modes and transportation methods.</span></span>

## <a name="create-a-mode"></a><span data-ttu-id="159be-109">Tworzenie trybu</span><span class="sxs-lookup"><span data-stu-id="159be-109">Create a mode</span></span>

<span data-ttu-id="159be-110">Aby utworzyć tryb, należy wykonać poniższe kroki:</span><span class="sxs-lookup"><span data-stu-id="159be-110">To create a mode, follow these steps:</span></span>

1. <span data-ttu-id="159be-111">Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Tryb**.</span><span class="sxs-lookup"><span data-stu-id="159be-111">Go to **Transportation management \> Setup \> Carriers \> Mode**.</span></span>
1. <span data-ttu-id="159be-112">Wybierz pozycję **Nowy**, aby utworzyć nowy tryb.</span><span class="sxs-lookup"><span data-stu-id="159be-112">Select **New** to create a new mode.</span></span>
1. <span data-ttu-id="159be-113">Wprowadź unikatowy identyfikator i opisową nazwę trybu.</span><span class="sxs-lookup"><span data-stu-id="159be-113">Enter a unique ID and a descriptive name for the mode.</span></span>
1. <span data-ttu-id="159be-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="159be-114">Close the page.</span></span>

## <a name="create-a-transportation-method"></a><span data-ttu-id="159be-115">Tworzenie metody transportu</span><span class="sxs-lookup"><span data-stu-id="159be-115">Create a transportation method</span></span>

<span data-ttu-id="159be-116">Aby utworzyć metodę transportu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="159be-116">To create a transportation method, follow these steps:</span></span>

1. <span data-ttu-id="159be-117">Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Metody transportu**.</span><span class="sxs-lookup"><span data-stu-id="159be-117">Go to **Transportation management \> Setup \> Carriers \> Transportation methods**.</span></span>
1. <span data-ttu-id="159be-118">Wybierz **Nowy**, aby utworzyć nową metodę transportu.</span><span class="sxs-lookup"><span data-stu-id="159be-118">Select **New** to create a new transportation method.</span></span>
1. <span data-ttu-id="159be-119">Wprowadź unikatowy identyfikator i opisową nazwę metody transportu.</span><span class="sxs-lookup"><span data-stu-id="159be-119">Enter a unique ID and descriptive name for the transportation method.</span></span>
1. <span data-ttu-id="159be-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="159be-120">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]