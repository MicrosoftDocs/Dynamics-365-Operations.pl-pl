---
title: Konfigurowanie produktów, które mogą być produkowane lub zamawiane
description: Produkty można pozyskiwać na różne sposoby — mogą być produkowane (wytwarzane) lub zamawiane (kupowane). W tym artykule opisano niektóre typowe kwestie do rozważenia podczas konfigurowania dla produktów obsługi pozyskiwania z wielu źródeł.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9b5ba58703e636308d83a94ecc2e27e44812c49
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435275"
---
# <a name="set-up-products-that-can-be-produced-or-procured"></a><span data-ttu-id="92824-104">Konfigurowanie produktów, które mogą być produkowane lub zamawiane</span><span class="sxs-lookup"><span data-stu-id="92824-104">Set up products that can be produced or procured</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92824-105">Produkty można pozyskiwać na różne sposoby — mogą być produkowane (wytwarzane) lub zamawiane (kupowane).</span><span class="sxs-lookup"><span data-stu-id="92824-105">Products can be sourced in various ways -  they can be produced (manufactured) or procured (purchased).</span></span> <span data-ttu-id="92824-106">W tym artykule opisano niektóre typowe kwestie do rozważenia podczas konfigurowania dla produktów obsługi pozyskiwania z wielu źródeł.</span><span class="sxs-lookup"><span data-stu-id="92824-106">This article describes some typical points to consider when you configure products to support multi-sourcing.</span></span> 

<span data-ttu-id="92824-107">Model wielu źródeł jest zwykle używany do kupowania towarów, które są wytwarzane od czasu do czasu, lub gdy jakiś towar, który był głównie towarem wytwarzanym, zmienił się i teraz jest głównie towarem kupowanym.</span><span class="sxs-lookup"><span data-stu-id="92824-107">Multi-sourcing is typically used for a purchased item that is occasionally manufactured, or when an item that was primarily a manufactured item is changed so that it's now primarily a purchased item.</span></span> <span data-ttu-id="92824-108">Towar jest początkowo określany jako towar wytwarzany w celu zdefiniowania informacji o BOM i marszrucie oraz umożliwienia tworzenia zleceń produkcyjnych dla tego towaru.</span><span class="sxs-lookup"><span data-stu-id="92824-108">The item is first designated as a manufactured item, so that bill of materials (BOM) and route information can be defined, and to support production orders for the item.</span></span> <span data-ttu-id="92824-109">Typ produkcji powinien być ustawiony na **BOM** (lub dla procesu wytwarzania na **Formuła** lub **Produkt towarzyszący**).</span><span class="sxs-lookup"><span data-stu-id="92824-109">The production type should be set to **BOM** (or, for process manufacturing, **Formula** or **Co-Product**).</span></span>

<span data-ttu-id="92824-110">Jeśli używasz kosztu standardowego, rekord kosztu towaru można obliczyć dla towaru wytwarzanego.</span><span class="sxs-lookup"><span data-stu-id="92824-110">When you use standard cost, the item cost record can be calculated for the manufactured item.</span></span> <span data-ttu-id="92824-111">Jednak rekord kosztu towaru nie może pokrywać się z kosztem standardowym, który ma być stosowany dla celów zakupów.</span><span class="sxs-lookup"><span data-stu-id="92824-111">However, the item cost record might not match the standard cost that you want for purchasing purposes.</span></span> <span data-ttu-id="92824-112">W takim przypadku koszt standardowy należy wprowadzić i aktywować dla rekordu kosztu towaru.</span><span class="sxs-lookup"><span data-stu-id="92824-112">In this case, the standard cost must be manually entered and activated for the item cost record.</span></span> <span data-ttu-id="92824-113">Do obliczania kosztów należy wziąć pod uwagę specjalną listę BOM i marszrutę, odzwierciedlające kombinację dostaw produktu w okresie obrachunkowym, aby zminimalizować odchylenia w czasie.</span><span class="sxs-lookup"><span data-stu-id="92824-113">For the cost calculation, consider using a special BOM and route that represent the supply mix of the product over the course of a fiscal period, to minimize the variances over time.</span></span> <span data-ttu-id="92824-114">Ponadto towar wytwarzany w jednym oddziale może zostać przeniesiony do innego oddziału.</span><span class="sxs-lookup"><span data-stu-id="92824-114">Additionally, a manufactured item at one site can be transferred to another site.</span></span> <span data-ttu-id="92824-115">W związku z tym koszt towaru musi być ręcznie wprowadzony i aktywowany dla oddziału, do którego jest przenoszony.</span><span class="sxs-lookup"><span data-stu-id="92824-115">Therefore, the item's cost must be manually entered and activated for the site that the item is transferred to.</span></span> <span data-ttu-id="92824-116">Jeśli towar wytwarzany jest składnikiem produktu wyższego poziomu, koszt składnika powinien być traktowany jak koszt towaru kupowanego.</span><span class="sxs-lookup"><span data-stu-id="92824-116">When you use the manufactured item as a component in higher-level products, the component's costs should be treated as a purchased item.</span></span> <span data-ttu-id="92824-117">Niniejsze wytyczne obowiązują niezależnie od tego, czy koszty składników zostały obliczone czy wprowadzone ręcznie.</span><span class="sxs-lookup"><span data-stu-id="92824-117">This guideline applies, regardless of whether the component’s costs were calculated or manually entered.</span></span> <span data-ttu-id="92824-118">Innymi słowy, w przypadku obliczania BOM koszty towaru powinny być traktowane jako koszty składnika kupowanego, zamiast używać informacji dotyczących BOM i marszruty dla towaru w celu obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="92824-118">In other words, a BOM calculation should treat the item's costs as a purchased component instead of using the item's BOM and route information to calculate costs.</span></span> 

<span data-ttu-id="92824-119">Aby zablokować takie obliczenia, wybierz flagę **Zatrzymanie rozłożenia** znajdującą się w grupie obliczania BOM przypisanej do towaru.</span><span class="sxs-lookup"><span data-stu-id="92824-119">To prevent the calculation from occurring, select the **Stop explosion** flag that is embedded in the BOM calculation group that is assigned to the item.</span></span> <span data-ttu-id="92824-120">Aby w przypadku obliczeń w procesie planowania głównego uniemożliwić rozłożenie kosztów towaru, ustaw horyzont rozłożenia na 0 (zero) dni w zapotrzebowaniu na towary lub w grupie zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="92824-120">To prevent master scheduling calculations from exploding requirements through the item, set the explosion fence to 0 (zero) days in item coverage or in the coverage group.</span></span> <span data-ttu-id="92824-121">W obliczaniu planowania głównego towar będzie traktowany jako kupowany i nie zostaną przeprowadzone dodatkowe obliczenia dla informacji dotyczących BOM i marszruty towaru.</span><span class="sxs-lookup"><span data-stu-id="92824-121">The master scheduling calculation will then treat the item as a purchased item and won't perform more calculations for the item's BOM and route information.</span></span>





