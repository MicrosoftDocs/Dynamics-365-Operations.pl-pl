---
title: Aktualizacja kosztów standardowych w środowisku produkcyjnym
description: Ten artykuł zawiera wskazówki dotyczące aktualizowania kosztów standardowych w środowisku produkcyjnym.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66d08888e426c55fc775a1f2505772bca45e7802
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842136"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a><span data-ttu-id="5b516-103">Aktualizacja kosztów standardowych w środowisku produkcyjnym</span><span class="sxs-lookup"><span data-stu-id="5b516-103">Update standard costs in a manufacturing environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b516-104">Ten artykuł zawiera wskazówki dotyczące aktualizowania kosztów standardowych w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="5b516-104">This article provides guidance about how to update standard costs in a manufacturing environment.</span></span> 

<span data-ttu-id="5b516-105">Aktualizacje mogą odzwierciedlać nowe towary, kategorie kosztów lub wzory obliczania kosztów pośrednich.</span><span class="sxs-lookup"><span data-stu-id="5b516-105">Updates can reflect new items, cost categories, or indirect cost calculation formulas.</span></span> <span data-ttu-id="5b516-106">Mogą także wynikać z korekt i zmian kosztów.</span><span class="sxs-lookup"><span data-stu-id="5b516-106">They can also reflect corrections and cost changes.</span></span> <span data-ttu-id="5b516-107">Typ aktualizacji wpływa na czynności, jakie trzeba wykonać w celu aktualizacji kosztów standardowych, co przedstawiono w poniższych przypadkach:</span><span class="sxs-lookup"><span data-stu-id="5b516-107">The type of update affects the steps that you must complete to update standard costs, as illustrated in the following cases:</span></span>

-   <span data-ttu-id="5b516-108">Wprowadzenie oczekiwanych zmian kosztów standardowych dla kupowanych towarów, a następnie w odpowiednim dniu zmiana stanu rekordów kosztów tych towarów na **Aktywne**.</span><span class="sxs-lookup"><span data-stu-id="5b516-108">Enter expected standard cost changes for purchased items, and then change the status of the item cost records to **Active** on the appropriate date.</span></span> <span data-ttu-id="5b516-109">Nie obliczono jednak ponownie kosztów wytwarzanych towarów, które zużywają kupowane towary.</span><span class="sxs-lookup"><span data-stu-id="5b516-109">However, don't recalculate the costs of manufactured items that use the purchased items.</span></span>
-   <span data-ttu-id="5b516-110">Wprowadzenie kosztów standardowych dla nowo kupowanych towarów bez ponownego obliczenia kosztów produkowanych towarów mających wersję listy składowej (BOM), w której nowo kupowane towary są składnikami.</span><span class="sxs-lookup"><span data-stu-id="5b516-110">Enter standard costs for a new purchased item, but don't recalculate the costs of manufactured items that have a bill of materials (BOM) version that contains the new purchased item as a component.</span></span>
-   <span data-ttu-id="5b516-111">Korekta lub zmiana kosztu kupowanego towaru albo zmiana grupy kosztów przypisanej do kupowanego towaru, a następnie obliczenie kosztu wszystkich produkowanych towarów mających wersję BOM, w której kupowany towar jest składnikiem.</span><span class="sxs-lookup"><span data-stu-id="5b516-111">Correct or change the cost of a purchased item, or change the cost group that is assigned to a purchased item, and calculate the cost for all manufactured items that have a BOM version that contains the purchased item as a component.</span></span>
-   <span data-ttu-id="5b516-112">Zmiana kosztu lub kategorii kosztu, a następnie obliczenie kosztu wszystkich produkowanych towarów mających wersję marszruty z operacjami marszruty wykorzystującymi kategorię kosztów.</span><span class="sxs-lookup"><span data-stu-id="5b516-112">Change the cost for a cost category, and calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="5b516-113">Zmiana kategorii kosztów przypisanych do operacji marszruty albo grupy kosztów przypisanej do kategorii kosztów.</span><span class="sxs-lookup"><span data-stu-id="5b516-113">Change the cost categories that are assigned to routing operations or the cost group that is assigned to cost categories.</span></span> <span data-ttu-id="5b516-114">Następnie obliczono koszt wszystkich produkowanych towarów mających wersję marszruty z operacjami marszruty wykorzystującymi kategorię kosztów.</span><span class="sxs-lookup"><span data-stu-id="5b516-114">Then calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="5b516-115">Zmiana wzoru obliczania kosztów pośrednich i obliczenie kosztu wszystkich wyprodukowanych towarów, na które wpłynęła zmiana.</span><span class="sxs-lookup"><span data-stu-id="5b516-115">Change an indirect cost calculation formula, and calculate the cost for all manufactured items that are affected by the change.</span></span>
-   <span data-ttu-id="5b516-116">Zmiana lub dodanie oddziału, w którym wytworzono towar, i obliczenie kosztu wytworzenia dla określonego oddziału.</span><span class="sxs-lookup"><span data-stu-id="5b516-116">Change or add a manufacturing site for a manufactured item, and calculate the item's manufactured cost for the site.</span></span>
-   <span data-ttu-id="5b516-117">Obliczenie (lub ponowne obliczenie) kosztu produkowanego towaru, a następnie ponowne obliczenie kosztu wszystkich produkowanych towarów mających wersję BOM, w której kupowany towar jest składnikiem.</span><span class="sxs-lookup"><span data-stu-id="5b516-117">Calculate, or recalculate, the cost for a manufactured item, and recalculate the cost for all manufactured items that have a BOM version that contains the manufactured item as a component.</span></span>
-   <span data-ttu-id="5b516-118">Obliczenie kosztów nowo produkowanego towaru na podstawie zdefiniowanej, zatwierdzonej i aktywnej listy BOM oraz informacji o marszrucie.</span><span class="sxs-lookup"><span data-stu-id="5b516-118">Calculate costs for a new manufactured item, based on its defined, approved, and active BOM and route information.</span></span>

<span data-ttu-id="5b516-119">Każdy przykład wymaga specyficznego sposobu aktualizacji kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="5b516-119">Each case requires careful consideration about how to update standard costs.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]