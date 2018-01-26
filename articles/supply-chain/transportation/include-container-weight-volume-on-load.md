---
title: "Uwzględnianie wagi i objętości kontenera w ładunku"
description: "W tym temacie opisano jak skonfigurować i zastosować funkcje w celu dodania wagę i objętość kontenera do ładunków."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3c43a42822f291607fbc9708dd07ebf99b9d7ec4
ms.openlocfilehash: 00f7afab0bd65519f9f05773d935c9384c583332
ms.contentlocale: pl-pl
ms.lasthandoff: 01/26/2018

---

# <a name="include-container-weight-and-volume-on-load"></a><span data-ttu-id="cf29e-103">Uwzględnianie wagi i objętości kontenera w ładunku</span><span class="sxs-lookup"><span data-stu-id="cf29e-103">Include container weight and volume on load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cf29e-104">Funkcja dodawania wagi i objętości do ładunku umożliwia uzyskanie przejrzystych informacji o całkowitej wadze i objętości kontenerów i towarów zawartych w ładunku.</span><span class="sxs-lookup"><span data-stu-id="cf29e-104">The functionality for including the container weight and volume on a load gives a clear representation of the total weight and volume of containers and items that are going on a load.</span></span>

<span data-ttu-id="cf29e-105">Ładunek zawiera jedną lub wiele wysyłek, a te wysyłki mogą zawierać osobne towary należące do jednego lub kilku zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cf29e-105">A load contains a single shipment or multiple shipments, and these shipments contain distinct items that belong to a single sales order or multiple sales orders.</span></span> <span data-ttu-id="cf29e-106">Towary są przechowywane w kontenerze, a kontenery ładowane w ramach ładunku.</span><span class="sxs-lookup"><span data-stu-id="cf29e-106">The items are stored inside a container, and containers are loaded on a load.</span></span> <span data-ttu-id="cf29e-107">Towary poza kontenerem także mogą być częścią ładunku.</span><span class="sxs-lookup"><span data-stu-id="cf29e-107">Items that are outside a container can also be part of a load.</span></span> <span data-ttu-id="cf29e-108">Na podstawie tych warunków system oblicza wartości wagi i objętości ładunku, uwzględniając wagę i objętość kontenerów oraz towarów.</span><span class="sxs-lookup"><span data-stu-id="cf29e-108">Based on these conditions, the system calculates values for the weight and volume on the load by considering the weight and volume of both containers and items.</span></span>

<span data-ttu-id="cf29e-109">Jeżeli obliczone wartości są niedokładne, można je dostosować wprowadzając rzeczywiste wartości wagi i objętości ładunku.</span><span class="sxs-lookup"><span data-stu-id="cf29e-109">If the calculated values aren’t precise, you can adjust them by entering the actual values for the weight and volume on the load.</span></span> <span data-ttu-id="cf29e-110">Te wartości wagi i objętości są używane w procesach zarządzania transportem.</span><span class="sxs-lookup"><span data-stu-id="cf29e-110">The values for the weight and volume are used in transportation management processes.</span></span> <span data-ttu-id="cf29e-111">Wartości są na przykład używane w pulpicie ustalania stawek i wyznaczania tras, gdzie ułatwiają zdefiniowanie stawki i trasy ładunków i są także używane dla metod płatności za transport i ewidencjonowanie kierowców.</span><span class="sxs-lookup"><span data-stu-id="cf29e-111">For example, the values are used in the rate route workbench, where they help define the rate and route for loads, and they are also used for transportation tenders and driver check-in.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="cf29e-112">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="cf29e-112">Where it applies</span></span>

<span data-ttu-id="cf29e-113">Funkcja uwzględniania wagi i objętości kontenera w ładunku ma zastosowanie w procesach zarządzania transportem, takich jak pulpit ustalania stawek i wyznaczania tras, metody płatności za transport i ewidencjonowanie kierowców.</span><span class="sxs-lookup"><span data-stu-id="cf29e-113">The functionality for including the container weight and volume on a load applies in transportation management processes, such as the rate route workbench, transportation tenders, and driver check-in.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="cf29e-114">Sposób konfiguracji</span><span class="sxs-lookup"><span data-stu-id="cf29e-114">How it is set up</span></span>

<span data-ttu-id="cf29e-115">Liczba kontenerów, którą należy uwzględnić dla ładunku jest obliczana na podstawie wagi i objętości kontenera i procentu wykorzystania kontenera.</span><span class="sxs-lookup"><span data-stu-id="cf29e-115">The number of containers that should be considered for a load is calculated based on the weight and volume of the container, and on the percentage of the container is used.</span></span>

-   <span data-ttu-id="cf29e-116">Aby ustawić wagę i objętość dla kontenera kliknij kolejno opcje **Zarządzanie magazynem** \> **Konfiguracja** \> **Kontenery** \> **Typy kontenerów**.</span><span class="sxs-lookup"><span data-stu-id="cf29e-116">To set the weight and volume for a container, click **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>

-   <span data-ttu-id="cf29e-117">Aby ustawić procent wykorzystania kontenerów, kliknij kolejno opcje **Zarządzanie magazynem** \> **Konfiguracja** \> **Kontenery** \> **Grupy kontenerów**, a następnie wprowadź wartość w polu **Procent wykorzystania kontenera**.</span><span class="sxs-lookup"><span data-stu-id="cf29e-117">To set the container utilization percentage, click **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**, and then enter a value in the **Container utilization percentage** field.</span></span>

