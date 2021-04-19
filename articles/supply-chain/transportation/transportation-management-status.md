---
title: Stany zarządzania transportem
description: W tym temacie opisano sposób tworzenia stanu transportu i mapowania tego stanu na stan przewoźnika.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: f3a2b9e50dddf0f015cdd3f16d6d93fcc03d464d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807615"
---
# <a name="transportation-management-statuses"></a><span data-ttu-id="3b105-103">Stany zarządzania transportem</span><span class="sxs-lookup"><span data-stu-id="3b105-103">Transportation management statuses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b105-104">Ustaw kody główne stanów transportu do zinterpretowania kodów przekazanych przez przewoźników.</span><span class="sxs-lookup"><span data-stu-id="3b105-104">Set up master codes for transportation statuses to interpret codes that are provided by your shipping carriers.</span></span> <span data-ttu-id="3b105-105">Pozwala to na integrację z przewoźnikami w celu nadania statusu.</span><span class="sxs-lookup"><span data-stu-id="3b105-105">This lets you integrate with shipping carriers to provide a status.</span></span> <span data-ttu-id="3b105-106">Stan transportu podawany dla kodu stanu głównego transportu może ułatwić śledzenie stanu ładunku, wysyłki lub kontenera.</span><span class="sxs-lookup"><span data-stu-id="3b105-106">The transportation status that you provide for a transportation master status code can help you track the status of a load, shipment, or container.</span></span> <span data-ttu-id="3b105-107">Określony stan transportu dla ładunku, wysyłki lub kontenera można aktualizować tylko za pośrednictwem integracji danych, a nie ręcznie za pośrednictwem interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="3b105-107">The specific transportation status for a load, shipment, or container can only be updated through data integration and not manually through the user interface.</span></span>

## <a name="create-a-transportation-status"></a><span data-ttu-id="3b105-108">Tworzenie stanu transportu</span><span class="sxs-lookup"><span data-stu-id="3b105-108">Create a transportation status</span></span>

<span data-ttu-id="3b105-109">Aby utworzyć stan transportu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="3b105-109">To create a transportation status, follow these steps:</span></span>

1. <span data-ttu-id="3b105-110">Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Główne stany transportu**.</span><span class="sxs-lookup"><span data-stu-id="3b105-110">Go to **Transportation management \> Setup \> Transportation status masters**.</span></span>
1. <span data-ttu-id="3b105-111">Wybierz **Nowy** do utworzenia danych głównych stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="3b105-111">Select **New** to create a transportation status master.</span></span>
1. <span data-ttu-id="3b105-112">W polu **Główny stan transportu** wprowadź unikatowy kod dla stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="3b105-112">In the **Transportation status master** field, enter a unique code for the transportation status.</span></span>
1. <span data-ttu-id="3b105-113">W polu **Typ transportu** wybierz *Przewoźnik* lub *Centrum* jako typ transportu.</span><span class="sxs-lookup"><span data-stu-id="3b105-113">In the **Transportation type** field, select either *Shipping carrier* or *Hub* as the type of transportation.</span></span>
1. <span data-ttu-id="3b105-114">Umożliwia wprowadzenie nazwy i stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="3b105-114">Enter a name and transportation status.</span></span>
1. <span data-ttu-id="3b105-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3b105-115">Close the page.</span></span>

## <a name="map-a-transportation-status-to-a-carrier-status"></a><span data-ttu-id="3b105-116">Mapuj stan transportu na stan przewoźnika</span><span class="sxs-lookup"><span data-stu-id="3b105-116">Map a transportation status to a carrier status</span></span>

<span data-ttu-id="3b105-117">Aby zamapować stan transportu na stan przewoźnika, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="3b105-117">To map a transportation status to a carrier status, follow these steps:</span></span>

1. <span data-ttu-id="3b105-118">Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Stan transportu przewoźnika**.</span><span class="sxs-lookup"><span data-stu-id="3b105-118">Go to **Transportation management \> Setup \> Carriers \> Carrier transportation status**.</span></span>
1. <span data-ttu-id="3b105-119">Wybierz **Nowy**, aby zmapować kod od przewoźnika do kodu głównego stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="3b105-119">Select **New** to map a code from a shipping carrier to a transportation status master code.</span></span>
1. <span data-ttu-id="3b105-120">Wybierz unikatowy identyfikator dla przewoźnika i usługi przewozowej.</span><span class="sxs-lookup"><span data-stu-id="3b105-120">Select the unique ID for the shipping carrier and the carrier service.</span></span>
1. <span data-ttu-id="3b105-121">Wybierz kod stanu transportu, który ma być mapowany do kodu wybranego przewoźnika wysyłki.</span><span class="sxs-lookup"><span data-stu-id="3b105-121">Select the transportation status code that you want to map to the selected shipping carrier's code.</span></span>
1. <span data-ttu-id="3b105-122">Wprowadź kod zewnętrzny używany przez przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="3b105-122">Enter the external code that is used by the shipping carrier.</span></span>
1. <span data-ttu-id="3b105-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3b105-123">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]