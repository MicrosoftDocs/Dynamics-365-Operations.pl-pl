---
title: Kategorie kosztów używane w kontroli produkcji i rachunkowości zarządczej projektów
description: Niektóre typy działań produkcyjnych mogą mieć zastosowanie do szacowania i raportowania czasu trwania projektu. Ten artykuł zawiera informacje o kategoriach kosztów, które należy zdefiniować dla tego typu działań produkcyjnych na potrzeby produkcji i projektu.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCategory
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78253
ms.assetid: cfdd58a0-8afa-4a6f-a208-a76e2c162429
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 540d020820222b024f838f8156aaef823605e950
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228714"
---
# <a name="cost-categories-used-in-production-control-and-project-management-accounting"></a><span data-ttu-id="a9f96-104">Kategorie kosztów używane w kontroli produkcji i rachunkowości zarządczej projektów</span><span class="sxs-lookup"><span data-stu-id="a9f96-104">Cost categories used in Production control and Project management accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9f96-105">Niektóre typy działań produkcyjnych mogą mieć zastosowanie do szacowania i raportowania czasu trwania projektu.</span><span class="sxs-lookup"><span data-stu-id="a9f96-105">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="a9f96-106">Ten artykuł zawiera informacje o kategoriach kosztów, które należy zdefiniować dla tego typu działań produkcyjnych na potrzeby produkcji i projektu.</span><span class="sxs-lookup"><span data-stu-id="a9f96-106">This article provides information about the cost categories that you must define for these types of production work for production and project purposes.</span></span>

<span data-ttu-id="a9f96-107">Niektóre typy działań produkcyjnych mogą mieć zastosowanie do szacowania i raportowania czasu trwania projektu.</span><span class="sxs-lookup"><span data-stu-id="a9f96-107">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="a9f96-108">W takim przypadku kategoria kosztów jest wymagana na potrzeby produkcji i projektu.</span><span class="sxs-lookup"><span data-stu-id="a9f96-108">In this case, a cost category is required for production and project purposes.</span></span> <span data-ttu-id="a9f96-109">Jeśli kategoria kosztów jest używana w produkcji i projektach, należy zdefiniować dodatkowe informacje związane z projektem.</span><span class="sxs-lookup"><span data-stu-id="a9f96-109">When a cost category is used in production and projects, additional project-related information must be defined.</span></span> <span data-ttu-id="a9f96-110">Na przykład koszty godzinowe skojarzone z projektami mogą się różnić od kosztów godzinowych skojarzonych z produkcją.</span><span class="sxs-lookup"><span data-stu-id="a9f96-110">For example, the hourly costs that are associated with projects can differ from the hourly costs that are associated with production.</span></span> <span data-ttu-id="a9f96-111">Można użyć strony **Kategorie kosztu**, aby zdefiniować kategorię kosztów, która będzie używana w modułach kontroli produkcji i rachunkowości zarządczej projektów.</span><span class="sxs-lookup"><span data-stu-id="a9f96-111">You can use the **Cost categories** page to define a cost category that is used in Production control and Project management accounting.</span></span> 

<span data-ttu-id="a9f96-112">**Uwaga:** Moduł Rachunek kosztów zawiera stronę **Kategorie projektu**, ale nie ma ona żadnego związku z funkcjami opisywanymi w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="a9f96-112">**Note:** Cost accounting has a **Project categories** page, but this page has no relationship to the functionality that is described in this topic.</span></span> <span data-ttu-id="a9f96-113">Gdy używasz kategorii kosztów w projektach, strona **Kategorie kosztu** zawiera dodatkowe karty, na których są wyświetlane dodatkowe informacje związane z projektem.</span><span class="sxs-lookup"><span data-stu-id="a9f96-113">When you use a cost category in projects, the **Cost categories** page has additional tabs that show additional project-related information.</span></span> <span data-ttu-id="a9f96-114">Informacje te obejmują grupę kategorii, właściwość wiersza oraz konta księgowe przypisane do kategorii kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f96-114">This information includes the category group, a line property, and ledger accounts that are assigned to the cost category.</span></span>

-   <span data-ttu-id="a9f96-115">Kategoria kosztów musi być przypisana do grupy kategorii obsługującej typ transakcji **Godziny**.</span><span class="sxs-lookup"><span data-stu-id="a9f96-115">The cost category must be assigned to a category group that supports a transaction type of **Hours**.</span></span>
-   <span data-ttu-id="a9f96-116">Właściwość wiersza wskazuje domyślny sposób zaliczania zgłaszanego czasu w ciężar projektu.</span><span class="sxs-lookup"><span data-stu-id="a9f96-116">The line property indicates default information about how reported time can be charged to a project.</span></span>
-   <span data-ttu-id="a9f96-117">Na ogół konta księgowe związane z kosztami i sprzedażą są definiowane dla grupy kategorii przypisanej do kategorii kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f96-117">Typically, the ledger accounts that are related to costs and sales are defined for the category group that is assigned to the cost category.</span></span> <span data-ttu-id="a9f96-118">Jednak dla konkretnej kategorii kosztów można zdefiniować określone konta.</span><span class="sxs-lookup"><span data-stu-id="a9f96-118">However, specific accounts can be defined for an individual cost category.</span></span>

<span data-ttu-id="a9f96-119">Dodatkowe przyciski na stronie **Kategorie kosztu** umożliwiają dostęp do informacji projektowych o wybranej kategorii kosztów.</span><span class="sxs-lookup"><span data-stu-id="a9f96-119">Additional buttons on the **Cost categories** page let you access project-related information about a selected cost category.</span></span> <span data-ttu-id="a9f96-120">Można na przykład wyświetlić transakcje związane z projektem, zdefiniować pracowników lub projekty, zdefiniować koszty godzinowe i ceny sprzedaży oraz obejrzeć raporty.</span><span class="sxs-lookup"><span data-stu-id="a9f96-120">For example, you can view project-related transactions, define employees or projects, define hourly costs and sales prices, and view reports.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]