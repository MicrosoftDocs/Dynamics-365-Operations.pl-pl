---
title: Przedmioty serwisu
description: "Przedmioty serwisu to aktywa i produkty klienta, dla których można wykonać usługi."
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0f7b63393085858c5ff4c64ebdf5d64b3c3ccdef
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="service-objects"></a><span data-ttu-id="ff4d9-103">Przedmioty serwisu</span><span class="sxs-lookup"><span data-stu-id="ff4d9-103">Service objects</span></span> 

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="ff4d9-104">Przedmioty serwisu to aktywa i produkty klienta, dla których można wykonać usługi.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-104">Service objects are a customer’s assets and products for which you can perform a service.</span></span> <span data-ttu-id="ff4d9-105">W zależności od typu oferowanej usługi przedmioty dzielą się na materialne i niematerialne:</span><span class="sxs-lookup"><span data-stu-id="ff4d9-105">Depending on the type of service you provide, objects can be tangible or intangible:</span></span>

-  <span data-ttu-id="ff4d9-106">przedmioty materialne są to obiekty, na przykład maszyny lub budynki, które można poddać fizycznym działaniom serwisowym,</span><span class="sxs-lookup"><span data-stu-id="ff4d9-106">Tangible objects are things, such as a machine or a building, on which you can perform a physical service task.</span></span>

    <span data-ttu-id="ff4d9-107">Materialny przedmiot serwisu może też być pozycją magazynową utworzoną w formularzu Szczegóły zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-107">A tangible service object can also be an inventory item that you create in the Released product details form.</span></span> <span data-ttu-id="ff4d9-108">W zależności od tego, którą grupą wymiarów magazynowych można oznaczyć dany towar, przedmiot serwisu można utworzyć nawet na poziomie numeru seryjnego towaru.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-108">Depending on the inventory dimension group that you attach to the item, you can create a service object to a level of detail that includes the item serial number.</span></span> <span data-ttu-id="ff4d9-109">Jest to użyteczne wtedy, gdy trzeba śledzić określony towar reprezentowany przez przedmiot serwisu.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-109">This is useful when you must keep track of the exact item that the service object represents.</span></span>

    <span data-ttu-id="ff4d9-110">Materialnym przedmiotem serwisu może być jednak coś niezwiązanego bezpośrednio z produkcją firmy lub jej łańcuchem dostaw.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-110">A tangible service object can also be an item that is not directly related to a company's direct production or supply chain.</span></span> <span data-ttu-id="ff4d9-111">Na przykład zestaw narzędzi używany do napraw w ramach zlecenia serwisowego może być przedmiotem serwisu nie uwzględnionym w zapasach.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-111">For example, a tool kit that is used for repairs in a service order can be a service object that is not included in inventory.</span></span> <span data-ttu-id="ff4d9-112">W takim przypadku nie można go zarejestrować jako pozycji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-112">In this case, you don’t register it as an inventory item.</span></span>

-  <span data-ttu-id="ff4d9-113">Przedmioty niematerialne są to abstrakcyjne elementy, na przykład zbiór kont lub oficjalny dokument, na podstawie których można wykonać działania serwisowe.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-113">Intangible objects are nonphysical things, such as a set of accounts or a legal document, on which you can perform a service task.</span></span>

## <a name="example-of-an-intangible-service-object"></a><span data-ttu-id="ff4d9-114">Przykład niematerialnego przedmiotu serwisu</span><span class="sxs-lookup"><span data-stu-id="ff4d9-114">Example of an intangible service object</span></span>

<span data-ttu-id="ff4d9-115">Firma A obsługuje rekordy finansowe dla kilku małych firm.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-115">Company A maintains the financial records for several small companies.</span></span> <span data-ttu-id="ff4d9-116">Jednym z klientów firmy A jest lokalna drużyna piłkarska, dla której A wykonuje co tydzień usługi księgowe i coroczny audyt kont klubu.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-116">One of Company A's clients is the local football team, for which Company A does the weekly bookkeeping and annual audit of the club's accounts.</span></span> <span data-ttu-id="ff4d9-117">Konta klubu są konfigurowane w formularzu Przedmioty serwisu i określane jako obiekt w umowie serwisowej.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-117">The club's accounts are set up in the Service objects form and specified as the object in the service agreement.</span></span> <span data-ttu-id="ff4d9-118">Istnieją dwa wiersze umowy serwisowej dla obiektu.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-118">There are two service agreement lines for the object.</span></span> <span data-ttu-id="ff4d9-119">Wiersz 1 to cotygodniowa księgowość, a wiersz 2 to coroczny audyt.</span><span class="sxs-lookup"><span data-stu-id="ff4d9-119">Line 1 is weekly bookkeeping with a weekly interval assigned to the line, and line 2 is the annual audit with a yearly interval assigned to it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ff4d9-120">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="ff4d9-120">Related topics</span></span>

[<span data-ttu-id="ff4d9-121">Tworzenie przedmiotów serwisu</span><span class="sxs-lookup"><span data-stu-id="ff4d9-121">Create service objects</span></span>](create-service-objects.md)


