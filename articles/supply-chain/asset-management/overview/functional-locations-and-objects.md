---
title: Lokalizacje czynności konserwacyjnych i składniki majątku
description: W tym temacie opisano lokalizacje funkcjonalne i składniki majątku w Zarządzaniu składnikami majątku. Zarządzanie składnikami majątku to zaawansowany moduł do zarządzania zasobami i zadaniami konserwacyjnymi w Dynamics 365 Supply Chain Management.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f93a68f19b0b952eb2964b404bb957865c625cd
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018053"
---
# <a name="functional-locations-and-assets"></a><span data-ttu-id="33e7d-104">Lokalizacje czynności konserwacyjnych i składniki majątku</span><span class="sxs-lookup"><span data-stu-id="33e7d-104">Functional locations and assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="33e7d-105">W tym temacie opisano lokalizacje funkcjonalne i składniki majątku w Zarządzaniu składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="33e7d-105">This topic describes functional locations and assets in Asset Management.</span></span> <span data-ttu-id="33e7d-106">Zarządzanie składnikami majątku to zaawansowany moduł do zarządzania zasobami i zadaniami konserwacyjnymi w Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33e7d-106">Asset Management is an advanced module for managing assets and maintenance jobs in Dynamics 365 Supply Chain Management.</span></span>

## <a name="overview"></a><span data-ttu-id="33e7d-107">Przegląd</span><span class="sxs-lookup"><span data-stu-id="33e7d-107">Overview</span></span>

<span data-ttu-id="33e7d-108">Moduł Zarządzanie składnikami majątku jest bezproblemowo integrowany z kilkoma modułami w innych aplikacjach Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33e7d-108">Asset Management is integrated seamlessly with several modules with other Finance and Operations apps.</span></span> <span data-ttu-id="33e7d-109">Na poniższej ilustracji przedstawiono interfejsy z innymi modułami.</span><span class="sxs-lookup"><span data-stu-id="33e7d-109">The following illustration shows the interfaces with other modules.</span></span>

![Diagram przedstawiający sposób współdziałania modułu Zarządzanie składnikami majątku z innymi modułami](media/01-overview-image.png)

<span data-ttu-id="33e7d-111">Zarządzanie składnikami majątku umożliwia efektywne zarządzanie i wykonywanie wszystkich zadań związanych z zarządzaniem i obsługą wielu typów urządzeń w firmie.</span><span class="sxs-lookup"><span data-stu-id="33e7d-111">Asset Management lets you efficiently manage and perform all tasks that are related to managing and servicing many types of equipment in your company.</span></span> <span data-ttu-id="33e7d-112">Te urządzenia obejmują maszyny, urządzenia produkcyjne i pojazdy.</span><span class="sxs-lookup"><span data-stu-id="33e7d-112">This equipment includes machines, production equipment, and vehicles.</span></span> <span data-ttu-id="33e7d-113">Zarządzanie składnikami majątku również wspiera rozwiązania w wielu branżach.</span><span class="sxs-lookup"><span data-stu-id="33e7d-113">Asset Management also supports solutions across numerous industries.</span></span>

<span data-ttu-id="33e7d-114">Poniższa ilustracja przedstawia omówienie głównych funkcji dostępnych w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="33e7d-114">The following illustration shows an overview of the main functionality that is covered by Asset Management.</span></span>

![Diagram przedstawiający główną funkcjonalność modułu Zarządzanie składnikami majątku](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a><span data-ttu-id="33e7d-116">Lokalizacje czynności konserwacyjnych i składniki majątku</span><span class="sxs-lookup"><span data-stu-id="33e7d-116">Functional locations and assets</span></span>

<span data-ttu-id="33e7d-117">Lokalizacje czynności konserwacyjnych służą do zarządzania zasobami w lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="33e7d-117">Functional locations are used to manage assets on locations.</span></span> <span data-ttu-id="33e7d-118">To zarządzanie obejmuje śledzenie kosztów aktywów w lokalizacjach czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="33e7d-118">This management includes tracking of asset costs on functional locations.</span></span> <span data-ttu-id="33e7d-119">Lokalizacje czynności konserwacyjnych są uporządkowane hierarchicznie, a lokalizacje mogą mieć Podlokalizacje.</span><span class="sxs-lookup"><span data-stu-id="33e7d-119">Functional locations are structured hierarchically, and locations can have sub-locations.</span></span> <span data-ttu-id="33e7d-120">Struktura lokalizacji czynności konserwacyjnych jest statyczna.</span><span class="sxs-lookup"><span data-stu-id="33e7d-120">The structure of functional locations is static.</span></span> <span data-ttu-id="33e7d-121">Innymi słowy, lokalizacje nie mogą zmieniać miejsca.</span><span class="sxs-lookup"><span data-stu-id="33e7d-121">In other words, locations can't change place.</span></span> <span data-ttu-id="33e7d-122">Składniki majątku mogą być instalowane w lokalizacjach czynności konserwacyjnych i, zgodnie z wymaganiami, mogą być instalowane później w innych lokalizacjach czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="33e7d-122">Assets can be installed on functional locations and, as required, can be installed on other functional locations later.</span></span>

<span data-ttu-id="33e7d-123">Koszty składników majątku zawsze są zgodne z lokalizacją składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="33e7d-123">Asset costs always follow the location of the asset.</span></span> <span data-ttu-id="33e7d-124">Innymi słowy jeśli zasób jest instalowany w nowej lokalizacji czynności konserwacyjnych, zasób automatycznie używa wymiarów finansowych, które są powiązane z nową lokalizacją czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="33e7d-124">In other words, if you install an asset on a new functional location, the asset automatically uses the financial dimensions that are related to the new functional location.</span></span> <span data-ttu-id="33e7d-125">W związku z tym koszty składnika majątku są zawsze związane z lokalizacją czynności konserwacyjnych, na której jest aktualnie zainstalowany składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="33e7d-125">Therefore, asset costs are always related to the functional location that the asset is  currently installed on.</span></span> <span data-ttu-id="33e7d-126">Ta automatyczna obsługa wymiarów finansowych pomaga zagwarantować całkowite śledzenie kosztów, gdy Twoja firma kontroluje i raportuje lokalizacje czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="33e7d-126">This automatic handling of financial dimensions helps guarantee complete tracking of costs when your company does project controlling and reporting on functional locations.</span></span>

<span data-ttu-id="33e7d-127">Sposób budowania hierarchii lokalizacji czynności konserwacyjnych zależy od wymagań firmy w zakresie utrzymywania wewnętrznego sprzętu lub obsługi sprzętu klienta.</span><span class="sxs-lookup"><span data-stu-id="33e7d-127">The way that you build your hierarchy of functional locations depends on your company's requirements for maintaining internal equipment or servicing customer equipment.</span></span> <span data-ttu-id="33e7d-128">Na poniższej ilustracji przedstawiono przykład lokalizacji czynności konserwacyjnych, które są oparte na lokalizacjach geograficznych.</span><span class="sxs-lookup"><span data-stu-id="33e7d-128">The following figure shows an example of functional locations that are based on geographical locations.</span></span>

![Diagram przedstawiający lokalizacje czynności konserwacyjnych na podstawie lokalizacji geograficznych](media/03-overview-image.png)

<span data-ttu-id="33e7d-130">Na poniższej ilustracji przedstawiono przykład lokalizacji czynności konserwacyjnych, które są oparte na klientach.</span><span class="sxs-lookup"><span data-stu-id="33e7d-130">The following figure shows an example of functional locations that are based on customers.</span></span>

![Diagram przedstawiający lokalizacje czynności konserwacyjnych na podstawie klientów](media/04-overview-image.png)
