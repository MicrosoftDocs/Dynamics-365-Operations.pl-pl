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
ms.openlocfilehash: 9d3ed4b73f909b50e97c971a37c548c8c4a9e620
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006473"
---
# <a name="transportation-management-statuses"></a><span data-ttu-id="38a15-103">Stany zarządzania transportem</span><span class="sxs-lookup"><span data-stu-id="38a15-103">Transportation management statuses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="38a15-104">Ustaw kody główne stanów transportu do zinterpretowania kodów przekazanych przez przewoźników.</span><span class="sxs-lookup"><span data-stu-id="38a15-104">Set up master codes for transportation statuses to interpret codes that are provided by your shipping carriers.</span></span> <span data-ttu-id="38a15-105">Pozwala to na integrację z przewoźnikami w celu nadania statusu.</span><span class="sxs-lookup"><span data-stu-id="38a15-105">This lets you integrate with shipping carriers to provide a status.</span></span> <span data-ttu-id="38a15-106">Stan transportu podawany dla kodu stanu głównego transportu może ułatwić śledzenie stanu ładunku, wysyłki lub kontenera.</span><span class="sxs-lookup"><span data-stu-id="38a15-106">The transportation status that you provide for a transportation master status code can help you track the status of a load, shipment, or container.</span></span> <span data-ttu-id="38a15-107">Określony stan transportu dla ładunku, wysyłki lub kontenera można aktualizować tylko za pośrednictwem integracji danych, a nie ręcznie za pośrednictwem interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="38a15-107">The specific transportation status for a load, shipment, or container can only be updated through data integration and not manually through the user interface.</span></span>

## <a name="create-a-transportation-status"></a><span data-ttu-id="38a15-108">Tworzenie stanu transportu</span><span class="sxs-lookup"><span data-stu-id="38a15-108">Create a transportation status</span></span>

<span data-ttu-id="38a15-109">Aby utworzyć stan transportu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="38a15-109">To create a transportation status, follow these steps:</span></span>

1. <span data-ttu-id="38a15-110">Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Główne stany transportu**.</span><span class="sxs-lookup"><span data-stu-id="38a15-110">Go to **Transportation management \> Setup \> Transportation status masters**.</span></span>
1. <span data-ttu-id="38a15-111">Wybierz **Nowy** do utworzenia danych głównych stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="38a15-111">Select **New** to create a transportation status master.</span></span>
1. <span data-ttu-id="38a15-112">W polu **Główny stan transportu** wprowadź unikatowy kod dla stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="38a15-112">In the **Transportation status master** field, enter a unique code for the transportation status.</span></span>
1. <span data-ttu-id="38a15-113">W polu **Typ transportu** wybierz *Przewoźnik* lub *Centrum* jako typ transportu.</span><span class="sxs-lookup"><span data-stu-id="38a15-113">In the **Transportation type** field, select either *Shipping carrier* or *Hub* as the type of transportation.</span></span>
1. <span data-ttu-id="38a15-114">Umożliwia wprowadzenie nazwy i stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="38a15-114">Enter a name and transportation status.</span></span>
1. <span data-ttu-id="38a15-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38a15-115">Close the page.</span></span>

## <a name="map-a-transportation-status-to-a-carrier-status"></a><span data-ttu-id="38a15-116">Mapuj stan transportu na stan przewoźnika</span><span class="sxs-lookup"><span data-stu-id="38a15-116">Map a transportation status to a carrier status</span></span>

<span data-ttu-id="38a15-117">Aby zamapować stan transportu na stan przewoźnika, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="38a15-117">To map a transportation status to a carrier status, follow these steps:</span></span>

1. <span data-ttu-id="38a15-118">Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Stan transportu przewoźnika**.</span><span class="sxs-lookup"><span data-stu-id="38a15-118">Go to **Transportation management \> Setup \> Carriers \> Carrier transportation status**.</span></span>
1. <span data-ttu-id="38a15-119">Wybierz **Nowy**, aby zmapować kod od przewoźnika do kodu głównego stanu transportu.</span><span class="sxs-lookup"><span data-stu-id="38a15-119">Select **New** to map a code from a shipping carrier to a transportation status master code.</span></span>
1. <span data-ttu-id="38a15-120">Wybierz unikatowy identyfikator dla przewoźnika i usługi przewozowej.</span><span class="sxs-lookup"><span data-stu-id="38a15-120">Select the unique ID for the shipping carrier and the carrier service.</span></span>
1. <span data-ttu-id="38a15-121">Wybierz kod stanu transportu, który ma być mapowany do kodu wybranego przewoźnika wysyłki.</span><span class="sxs-lookup"><span data-stu-id="38a15-121">Select the transportation status code that you want to map to the selected shipping carrier's code.</span></span>
1. <span data-ttu-id="38a15-122">Wprowadź kod zewnętrzny używany przez przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="38a15-122">Enter the external code that is used by the shipping carrier.</span></span>
1. <span data-ttu-id="38a15-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="38a15-123">Close the page.</span></span>
