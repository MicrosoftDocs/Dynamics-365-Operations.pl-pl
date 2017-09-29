---
title: "Tworzenie zleceń produkcyjnych"
description: "Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru. Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia. Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 58213d4d6e8c29ab6605eb7aa5c6cb9ca6ba4a10
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="create-production-orders"></a><span data-ttu-id="51b29-105">Tworzenie zleceń produkcyjnych</span><span class="sxs-lookup"><span data-stu-id="51b29-105">Create production orders</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="51b29-106">Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru.</span><span class="sxs-lookup"><span data-stu-id="51b29-106">When a production order is created, a request is initiated to start producing an item.</span></span> <span data-ttu-id="51b29-107">Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia.</span><span class="sxs-lookup"><span data-stu-id="51b29-107">The production order contains information about what will be produced, the quantity to produce, and the planned finish date.</span></span> <span data-ttu-id="51b29-108">Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji.</span><span class="sxs-lookup"><span data-stu-id="51b29-108">It also contains information about which materials to consume and which process to follow to produce the item.</span></span>

<span data-ttu-id="51b29-109">Zlecenie produkcyjne przechodzą przez kolejne etapy cyklu produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="51b29-109">A production order passes through stages of the production life cycle.</span></span> <span data-ttu-id="51b29-110">Po utworzeniu zlecenie otrzymuje stan **Utworzone**.</span><span class="sxs-lookup"><span data-stu-id="51b29-110">When an order is created, it is assigned the status **Created**.</span></span> <span data-ttu-id="51b29-111">Po zakończeniu zlecenie otrzymuje stan **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="51b29-111">When an order is finished, it is assigned the status **Ended**.</span></span> <span data-ttu-id="51b29-112">Ustawienia parametru na każdym etapie umożliwia użytkownikowi konfigurowanie każdego kroku.</span><span class="sxs-lookup"><span data-stu-id="51b29-112">A parameter setting in each stage allows a user to configure each step.</span></span> <span data-ttu-id="51b29-113">Ustawienie można skonfigurować dla pojedynczego użytkownika lub dla wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="51b29-113">The setting can be set up for a single user or for all users.</span></span>

<span data-ttu-id="51b29-114">Lista składowa (BOM) produkcji i marszruta produkcji są głównymi elementami zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="51b29-114">The production bill of material and the production route are the main entities of the production order.</span></span> <span data-ttu-id="51b29-115">Są one kopiowane do zlecenia produkcyjnego na podstawie wybranego towaru i ilości zaplanowanej do produkcji.</span><span class="sxs-lookup"><span data-stu-id="51b29-115">They are copied to the production order based on the selected item and quantity that are going to be produced.</span></span> <span data-ttu-id="51b29-116">Przed rozpoczęciem zlecenia produkcyjnego można edytować BOM i marszrutę produkcji.</span><span class="sxs-lookup"><span data-stu-id="51b29-116">Before the production order is started, the production bill of material and route can be edited.</span></span>

<span data-ttu-id="51b29-117">Zlecenie produkcyjne można tworzyć w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="51b29-117">A production order can be created in the following scenarios:</span></span>

-   <span data-ttu-id="51b29-118">Tworzenie przez wykonanie głównego planowania według zapotrzebowania materiałów.</span><span class="sxs-lookup"><span data-stu-id="51b29-118">Created by master planning execution based on material demand.</span></span>
-   <span data-ttu-id="51b29-119">Tworzenie bezpośrednio z wiersza zamówienia sprzedaży lub gdy zlecenie produkcyjne wyższego poziomu zostanie utworzone i oszacowane (ustalona dostawa).</span><span class="sxs-lookup"><span data-stu-id="51b29-119">Created directly from a sales order line or when a higher-level production order is created and estimated (pegged supply).</span></span>
-   <span data-ttu-id="51b29-120">Tworzenie ręczne.</span><span class="sxs-lookup"><span data-stu-id="51b29-120">Created manually.</span></span>





