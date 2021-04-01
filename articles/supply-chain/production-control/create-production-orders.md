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
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68758f4ddf39b4b8f7f0758f9e59e17c3411723a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246316"
---
# <a name="production-order-lifecycle-overview"></a><span data-ttu-id="0290f-105">Omówienie cyklu życia zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="0290f-105">Production order lifecycle overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0290f-106">Po utworzeniu zlecenia produkcyjnego jest inicjowane żądanie rozpoczęcia produkcji towaru.</span><span class="sxs-lookup"><span data-stu-id="0290f-106">When a production order is created, a request is initiated to start producing an item.</span></span> <span data-ttu-id="0290f-107">Zlecenie produkcyjne zawiera informacje o produkowanym towarze, ilości do wyprodukowania i planowanej dacie zakończenia.</span><span class="sxs-lookup"><span data-stu-id="0290f-107">The production order contains information about what will be produced, the quantity to produce, and the planned finish date.</span></span> <span data-ttu-id="0290f-108">Znajdują się w nim również informacje o materiałach, które będą zużywane, i procesach, jakie należy stosować w produkcji.</span><span class="sxs-lookup"><span data-stu-id="0290f-108">It also contains information about which materials to consume and which process to follow to produce the item.</span></span>

<span data-ttu-id="0290f-109">Zlecenie produkcyjne przechodzą przez kolejne etapy cyklu produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="0290f-109">A production order passes through stages of the production life cycle.</span></span> <span data-ttu-id="0290f-110">Po utworzeniu zlecenie otrzymuje stan **Utworzone**.</span><span class="sxs-lookup"><span data-stu-id="0290f-110">When an order is created, it is assigned the status **Created**.</span></span> <span data-ttu-id="0290f-111">Po zakończeniu zlecenie otrzymuje stan **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="0290f-111">When an order is finished, it is assigned the status **Ended**.</span></span> <span data-ttu-id="0290f-112">Ustawienia parametru na każdym etapie umożliwia użytkownikowi konfigurowanie każdego kroku.</span><span class="sxs-lookup"><span data-stu-id="0290f-112">A parameter setting in each stage allows a user to configure each step.</span></span> <span data-ttu-id="0290f-113">Ustawienie można skonfigurować dla pojedynczego użytkownika lub dla wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="0290f-113">The setting can be set up for a single user or for all users.</span></span>

<span data-ttu-id="0290f-114">Lista składowa (BOM) produkcji i marszruta produkcji są głównymi elementami zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="0290f-114">The production bill of material and the production route are the main entities of the production order.</span></span> <span data-ttu-id="0290f-115">Są one kopiowane do zlecenia produkcyjnego na podstawie wybranego towaru i ilości zaplanowanej do produkcji.</span><span class="sxs-lookup"><span data-stu-id="0290f-115">They are copied to the production order based on the selected item and quantity that are going to be produced.</span></span> <span data-ttu-id="0290f-116">Przed rozpoczęciem zlecenia produkcyjnego można edytować BOM i marszrutę produkcji.</span><span class="sxs-lookup"><span data-stu-id="0290f-116">Before the production order is started, the production bill of material and route can be edited.</span></span>

<span data-ttu-id="0290f-117">Zlecenie produkcyjne można tworzyć w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="0290f-117">A production order can be created in the following scenarios:</span></span>

-   <span data-ttu-id="0290f-118">Tworzenie przez wykonanie głównego planowania według zapotrzebowania materiałów.</span><span class="sxs-lookup"><span data-stu-id="0290f-118">Created by master planning execution based on material demand.</span></span>
-   <span data-ttu-id="0290f-119">Tworzenie bezpośrednio z wiersza zamówienia sprzedaży lub gdy zlecenie produkcyjne wyższego poziomu zostanie utworzone i oszacowane (ustalona dostawa).</span><span class="sxs-lookup"><span data-stu-id="0290f-119">Created directly from a sales order line or when a higher-level production order is created and estimated (pegged supply).</span></span>
-   <span data-ttu-id="0290f-120">Tworzenie ręczne.</span><span class="sxs-lookup"><span data-stu-id="0290f-120">Created manually.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]