---
title: Metodologia amortyzacji półrocznej
description: W tym temacie opisano metodę, dzięki której środki trwałe wykorzystywane do obliczania amortyzacji przy użyciu półrocznej konwencji, która oblicza sześć miesięcy amortyzacji w pierwszym i ostatnim roku eksploatacji środka trwałego.
author: moaamer
manager: Ann Beebe
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 55fb03cf08d8ec042aa8fb37fd1fb858d98279b1
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977246"
---
# <a name="half-year-depreciation-convention-methodology"></a><span data-ttu-id="15be9-103">Metodologia amortyzacji półrocznej</span><span class="sxs-lookup"><span data-stu-id="15be9-103">Half-year depreciation convention methodology</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="15be9-104">W tym temacie opisano metodę używaną w podczas obliczania amortyzacji środków trwałych przy użyciu konwencji półrocznej.</span><span class="sxs-lookup"><span data-stu-id="15be9-104">This topic describes the method that is used in fixed assets to calculate depreciation using the half-year convention.</span></span> <span data-ttu-id="15be9-105">Konwencja półroczna oblicza sześć miesięcy amortyzacji podczas pierwszego i ostatniego roku pracy środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="15be9-105">The half-year convention calculates six months of depreciation during an asset’s first and last year of service.</span></span> <span data-ttu-id="15be9-106">Aby uzyskać więcej informacji na temat konwencji amortyzacji, zobacz [Metody i konwencje amortyzacji środka trwałego](Fixed-asset-depreciation-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="15be9-106">For more information about depreciation conventions, see [Depreciation methods and conventions](Fixed-asset-depreciation-conventions.md).</span></span> 

<span data-ttu-id="15be9-107">W przypadku korzystania z półrocznej konwencji amortyzacji, system korzysta z roku nabycia lub roku, w którym środek trwały wszedł do użycia, oblicza pięć lat amortyzacji od tego momentu, a następnie dodaje sześć miesięcy.</span><span class="sxs-lookup"><span data-stu-id="15be9-107">When you use the six-month depreciation convention, the system uses the acquisition year or the year that the asset was placed in service, then calculates five years of depreciation from that year, and then adds six months.</span></span> <span data-ttu-id="15be9-108">Aby zilustrować ten proces, weźmy przykładowy składnik aktywów nabyty za cenę 50 000 i wprowadźmy go do użycia w kwietniu 2020 roku.</span><span class="sxs-lookup"><span data-stu-id="15be9-108">To illustrate this process, consider an asset that was acquired for the price of 50,000, and placed in service in April 2020.</span></span> <span data-ttu-id="15be9-109">Załóżmy również, że środek trwały ma pięcioletni okres użytkowania.</span><span class="sxs-lookup"><span data-stu-id="15be9-109">Also assume that the asset has a five-year service life.</span></span>

<span data-ttu-id="15be9-110">Pierwszy rok służby minie w grudniu 2020 roku, co oznacza, że koniec pięcioletniego okresu użytkowania aktywa minie w grudniu 2024 roku.</span><span class="sxs-lookup"><span data-stu-id="15be9-110">The first year of service will conclude in December 2020, which means the end of the asset’s five-year service life will be December 2024.</span></span> <span data-ttu-id="15be9-111">Półroczna konwencja amortyzacji doda sześć miesięcy do okresu użytkowania składnika aktywów, co oznacza, że jego okres użytkowania zakończy się w czerwcu 2025 roku.</span><span class="sxs-lookup"><span data-stu-id="15be9-111">The half-year depreciation convention will add six months to the asset’s life, which means its service life will end in June 2025.</span></span> 

> <span data-ttu-id="15be9-112">Amortyzacja roczna 50 000/5 = 10 000 miesięczna amortyzacja 10 000/12 = 833,33</span><span class="sxs-lookup"><span data-stu-id="15be9-112">Yearly depreciation 50,000/5 = 10,000 monthly depreciation 10,000/12 = 833.33</span></span> <br>
> <span data-ttu-id="15be9-113">Amortyzacja w pierwszym roku 10 000/2 = 5000 i późniejsza Amortyzacja miesięczna 5000/9 = 555,56</span><span class="sxs-lookup"><span data-stu-id="15be9-113">First year depreciation 10,000/2 = 5,000  and the subsequent monthly depreciation 5,000/9 = 555.56</span></span>

   <span data-ttu-id="15be9-114">[![Plan amortyzacji dla konwencji amortyzacji półrocznej](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span><span class="sxs-lookup"><span data-stu-id="15be9-114">[![Depreciation schedule for half-year depreciation convention](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span></span>

<span data-ttu-id="15be9-115">Rozszerzone okresy amortyzacji dodane przez konwencję półroczną zapewniają bardziej precyzyjną alokację amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="15be9-115">The extended depreciation periods that are added by the half-year convention provide more accurate allocation of depreciation.</span></span> <span data-ttu-id="15be9-116">Konwencja półroczna reprezentuje wydatki na amortyzację w bardziej równomierny sposób, co jest przydatne przy raportowaniu zestawienia zysków i strat.</span><span class="sxs-lookup"><span data-stu-id="15be9-116">The six-month convention represents depreciation expenses more equally, which is useful for reporting on the profit and loss statement.</span></span>
