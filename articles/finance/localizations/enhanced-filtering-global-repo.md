---
title: Rozszerzone filtrowania RCS w repozytorium RCS/globalnym
description: W tym temacie opisano ulepszone możliwości filtrowania w repozytorium globalnym RCS, które zostało udoskonalone w celu uwzględnienia dodatkowych filtrów.
author: JaneA07
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1913b661c46af5e34da1a2939cb2a5d5b4e46411
ms.sourcegitcommit: 7df49a85de484d013518217ba8ada6c61da4b6e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/24/2020
ms.locfileid: "3287946"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a><span data-ttu-id="7d17e-103">Rozszerzone z RCS opcje filtrowania służące do wyszukiwania konfiguracji w RCS/repozytorium globalnym</span><span class="sxs-lookup"><span data-stu-id="7d17e-103">RCS enhanced filtering options for finding configurations in the RCS/Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d17e-104">W tym temacie opisano ulepszone możliwości filtrowania w repozytorium globalnym Regulatory Configuration Services (RCS), które zostało udoskonalone w celu uwzględnienia możliwości filtrowania następujących kryteriów:</span><span class="sxs-lookup"><span data-stu-id="7d17e-104">This topic describes enhanced filtering capabilities for Regulatory Configuration Services (RCS) Global repository, which have been improved to include the ability to filter with the following criteria:</span></span> 
- <span data-ttu-id="7d17e-105">**Kraj/region** — Na podstawie kodów krajów ISO</span><span class="sxs-lookup"><span data-stu-id="7d17e-105">**Country/region** - Based on ISO country codes</span></span>  
- <span data-ttu-id="7d17e-106">Typy **Znaczników** dla:</span><span class="sxs-lookup"><span data-stu-id="7d17e-106">**Tags** types for:</span></span>
  - <span data-ttu-id="7d17e-107">Obszar funkcjonalny</span><span class="sxs-lookup"><span data-stu-id="7d17e-107">Functional area</span></span>
  - <span data-ttu-id="7d17e-108">Obszar funkcji</span><span class="sxs-lookup"><span data-stu-id="7d17e-108">Feature area</span></span>
  - <span data-ttu-id="7d17e-109">Branża</span><span class="sxs-lookup"><span data-stu-id="7d17e-109">Industry</span></span> 
  - <span data-ttu-id="7d17e-110">Dokument biznesowy</span><span class="sxs-lookup"><span data-stu-id="7d17e-110">Business document</span></span> 

<span data-ttu-id="7d17e-111">Aby ułatwić odkrywanie określonych lub powiązanych konfiguracji, można zastosować filtry, pojedynczo lub jako grupę.</span><span class="sxs-lookup"><span data-stu-id="7d17e-111">To make it easier to discover specific or related configurations you can apply filters, either individually or as a group.</span></span> <span data-ttu-id="7d17e-112">Aby na przykład znaleźć pojedynczy typ dokumentów biznesowych, które są związane z fakturami od dostawców, można zastosować filtr **Typu dokumentu biznesowego** w celu wyszukania tego typu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="7d17e-112">For example, to find a single type of 'configurable business documents that are related to vendor invoices, you could apply a **Business document type** filter to search for that type of document.</span></span> 

<span data-ttu-id="7d17e-113">[![Sekcja filtru dla repozytorium globalnego](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span><span class="sxs-lookup"><span data-stu-id="7d17e-113">[![Filter section for Global repository](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span></span> 

<span data-ttu-id="7d17e-114">Można dodatkowo uściślić wyszukiwanie, wybierając typ dokumentu, na przykład „faktura od dostawcy”, i klikając przycisk **Zastosuj filtr**.</span><span class="sxs-lookup"><span data-stu-id="7d17e-114">You can further refine the search by selecting document type, for example 'vendor invoice' and clicking **Apply filter**.</span></span> <span data-ttu-id="7d17e-115">W poniższym przykładzie przedstawiono wyniki filtrowania **typu dokumentu biznesowego** z dodanym typem dokumentu.</span><span class="sxs-lookup"><span data-stu-id="7d17e-115">The following example shows the results when filtering on **Business document type** with the document type added.</span></span> 

<span data-ttu-id="7d17e-116">[![Zastosowano filtr i import dla typu dokumentu biznesowego](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span><span class="sxs-lookup"><span data-stu-id="7d17e-116">[![Applied filter and Import for business document type](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span></span> 

<span data-ttu-id="7d17e-117">Przefiltrowane wyniki mogą być importowane do repozytorium RCS lub środowiska Dynamics 365 Finance albo indywidualnie, albo jako zbiór.</span><span class="sxs-lookup"><span data-stu-id="7d17e-117">Filtered results can be imported into a users RCS repository or a Dynamics 365 Finance environment, either individually or as a set.</span></span> <span data-ttu-id="7d17e-118">W tym celu należy wybrać grupę konfiguracji i kliknąć przycisk **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="7d17e-118">To do this, select the group of configurations, and click **Import**.</span></span>
