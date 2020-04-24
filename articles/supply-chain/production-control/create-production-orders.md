---
title: Omówienie cyklu życia zlecenia produkcyjnego
description: Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru. Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia. Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji.
author: johanhoffmann
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80031737ab0d0c4ab1e4dbd5646ad91f1a010cd5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211613"
---
# <a name="production-order-lifecycle-overview"></a><span data-ttu-id="75c97-105">Omówienie cyklu życia zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="75c97-105">Production order lifecycle overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75c97-106">Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru.</span><span class="sxs-lookup"><span data-stu-id="75c97-106">When a production order is created, a request is initiated to start producing an item.</span></span> <span data-ttu-id="75c97-107">Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia.</span><span class="sxs-lookup"><span data-stu-id="75c97-107">The production order contains information about what will be produced, the quantity to produce, and the planned finish date.</span></span> <span data-ttu-id="75c97-108">Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji.</span><span class="sxs-lookup"><span data-stu-id="75c97-108">It also contains information about which materials to consume and which process to follow to produce the item.</span></span>

<span data-ttu-id="75c97-109">Zlecenie produkcyjne przechodzą przez kolejne etapy cyklu produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="75c97-109">A production order passes through stages of the production life cycle.</span></span> <span data-ttu-id="75c97-110">Po utworzeniu zlecenie otrzymuje stan **Utworzone**.</span><span class="sxs-lookup"><span data-stu-id="75c97-110">When an order is created, it is assigned the status **Created**.</span></span> <span data-ttu-id="75c97-111">Po zakończeniu zlecenie otrzymuje stan **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="75c97-111">When an order is finished, it is assigned the status **Ended**.</span></span> <span data-ttu-id="75c97-112">Ustawienia parametru na każdym etapie umożliwia użytkownikowi konfigurowanie każdego kroku.</span><span class="sxs-lookup"><span data-stu-id="75c97-112">A parameter setting in each stage allows a user to configure each step.</span></span> <span data-ttu-id="75c97-113">Ustawienie można skonfigurować dla pojedynczego użytkownika lub dla wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="75c97-113">The setting can be set up for a single user or for all users.</span></span>

<span data-ttu-id="75c97-114">Lista składowa (BOM) produkcji i marszruta produkcji są głównymi elementami zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="75c97-114">The production bill of material and the production route are the main entities of the production order.</span></span> <span data-ttu-id="75c97-115">Są one kopiowane do zlecenia produkcyjnego na podstawie wybranego towaru i ilości zaplanowanej do produkcji.</span><span class="sxs-lookup"><span data-stu-id="75c97-115">They are copied to the production order based on the selected item and quantity that are going to be produced.</span></span> <span data-ttu-id="75c97-116">Przed rozpoczęciem zlecenia produkcyjnego można edytować BOM i marszrutę produkcji.</span><span class="sxs-lookup"><span data-stu-id="75c97-116">Before the production order is started, the production bill of material and route can be edited.</span></span>

<span data-ttu-id="75c97-117">Zlecenie produkcyjne można tworzyć w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="75c97-117">A production order can be created in the following scenarios:</span></span>

-   <span data-ttu-id="75c97-118">Tworzenie przez wykonanie głównego planowania według zapotrzebowania materiałów.</span><span class="sxs-lookup"><span data-stu-id="75c97-118">Created by master planning execution based on material demand.</span></span>
-   <span data-ttu-id="75c97-119">Tworzenie bezpośrednio z wiersza zamówienia sprzedaży lub gdy zlecenie produkcyjne wyższego poziomu zostanie utworzone i oszacowane (ustalona dostawa).</span><span class="sxs-lookup"><span data-stu-id="75c97-119">Created directly from a sales order line or when a higher-level production order is created and estimated (pegged supply).</span></span>
-   <span data-ttu-id="75c97-120">Tworzenie ręczne.</span><span class="sxs-lookup"><span data-stu-id="75c97-120">Created manually.</span></span>




