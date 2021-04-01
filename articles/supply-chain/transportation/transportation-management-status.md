---
title: Stany zarządzania transportem
description: W tym temacie opisano sposób tworzenia stanu transportu i mapowania tego stanu na stan przewoźnika.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: fb0d98729046330037f96ab7e13a1bf897e35a1e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233350"
---
# <a name="transportation-management-statuses"></a><span data-ttu-id="abfc4-103">Stany zarządzania transportem</span><span class="sxs-lookup"><span data-stu-id="abfc4-103">Transportation management statuses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="abfc4-104">Ustaw kody główne stanów transportu do zinterpretowania kodów przekazanych przez przewoźników.</span><span class="sxs-lookup"><span data-stu-id="abfc4-104">Set up master codes for transportation statuses to interpret codes that are provided by your shipping carriers.</span></span> <span data-ttu-id="abfc4-105">Pozwala to na integrację z przewoźnikami w celu nadania statusu.</span><span class="sxs-lookup"><span data-stu-id="abfc4-105">This lets you integrate with shipping carriers to provide a status.</span></span> <span data-ttu-id="abfc4-106">Stan transportu podawany dla kodu stanu głównego transportu może ułatwić śledzenie stanu ładunku, wysyłki lub kontenera.</span><span class="sxs-lookup"><span data-stu-id="abfc4-106">The transportation status that you provide for a transportation master status code can help you track the status of a load, shipment, or container.</span></span> <span data-ttu-id="abfc4-107">Określony stan transportu dla ładunku, wysyłki lub kontenera można aktualizować tylko za pośrednictwem integracji danych, a nie ręcznie za pośrednictwem interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="abfc4-107">The specific transportation status for a load, shipment, or container can only be updated through data integration and not manually through the user interface.</span></span>

## <a name="create-a-transportation-status"></a><span data-ttu-id="abfc4-108">Tworzenie stanu transportu</span><span class="sxs-lookup"><span data-stu-id="abfc4-108">Create a transportation status</span></span>

<span data-ttu-id="abfc4-109">Aby utworzyć stan transportu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="abfc4-109">To create a transportation status, follow these steps:</span></span>

1. <span data-ttu-id="abfc4-110">Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Główne stany transportu**.</span><span class="sxs-lookup"><span data-stu-id="abfc4-110">Go to **Transportation management \> Setup \> Transportation status masters**.</span></span>
1. <span data-ttu-id="abfc4-111">Wybierz **Nowy** do utworzenia danych głównych stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="abfc4-111">Select **New** to create a transportation status master.</span></span>
1. <span data-ttu-id="abfc4-112">W polu **Główny stan transportu** wprowadź unikatowy kod dla stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="abfc4-112">In the **Transportation status master** field, enter a unique code for the transportation status.</span></span>
1. <span data-ttu-id="abfc4-113">W polu **Typ transportu** wybierz *Przewoźnik* lub *Centrum* jako typ transportu.</span><span class="sxs-lookup"><span data-stu-id="abfc4-113">In the **Transportation type** field, select either *Shipping carrier* or *Hub* as the type of transportation.</span></span>
1. <span data-ttu-id="abfc4-114">Umożliwia wprowadzenie nazwy i stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="abfc4-114">Enter a name and transportation status.</span></span>
1. <span data-ttu-id="abfc4-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="abfc4-115">Close the page.</span></span>

## <a name="map-a-transportation-status-to-a-carrier-status"></a><span data-ttu-id="abfc4-116">Mapuj stan transportu na stan przewoźnika</span><span class="sxs-lookup"><span data-stu-id="abfc4-116">Map a transportation status to a carrier status</span></span>

<span data-ttu-id="abfc4-117">Aby zamapować stan transportu na stan przewoźnika, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="abfc4-117">To map a transportation status to a carrier status, follow these steps:</span></span>

1. <span data-ttu-id="abfc4-118">Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Stan transportu przewoźnika**.</span><span class="sxs-lookup"><span data-stu-id="abfc4-118">Go to **Transportation management \> Setup \> Carriers \> Carrier transportation status**.</span></span>
1. <span data-ttu-id="abfc4-119">Wybierz **Nowy**, aby zmapować kod od przewoźnika do kodu głównego stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="abfc4-119">Select **New** to map a code from a shipping carrier to a transportation status master code.</span></span>
1. <span data-ttu-id="abfc4-120">Wybierz unikatowy identyfikator dla przewoźnika i usługi przewozowej.</span><span class="sxs-lookup"><span data-stu-id="abfc4-120">Select the unique ID for the shipping carrier and the carrier service.</span></span>
1. <span data-ttu-id="abfc4-121">Wybierz kod stanu transportu, który ma być mapowany do kodu wybranego przewoźnika wysyłki.</span><span class="sxs-lookup"><span data-stu-id="abfc4-121">Select the transportation status code that you want to map to the selected shipping carrier's code.</span></span>
1. <span data-ttu-id="abfc4-122">Wprowadź kod zewnętrzny używany przez przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="abfc4-122">Enter the external code that is used by the shipping carrier.</span></span>
1. <span data-ttu-id="abfc4-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="abfc4-123">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]