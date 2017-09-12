---
title: "Używanie katalogów zewnętrznych dla rozwiązania PunchOut eProcurement"
description: "W tym temacie wyjaśniono sposób używania zewnętrznych katalogów do tworzenia i przesyłania zapotrzebowań."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 035c5d15e5508c78dd66a349defd534bfecc96bb
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="use-external-catalogs-for-punchout-eprocurement"></a><span data-ttu-id="b303d-103">Używanie katalogów zewnętrznych dla rozwiązania PunchOut eProcurement</span><span class="sxs-lookup"><span data-stu-id="b303d-103">Use external catalogs for PunchOut eProcurement</span></span>
<span data-ttu-id="b303d-104">Używając zewnętrznych katalogów w elektronicznym systemie zaopatrzenia z dynamicznie dostępnym katalogiem dostawcy, nie trzeba przechowywać informacji o produktach dostawców we własnych danych użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b303d-104">By using external catalogs for PunchOut e-procurement, you don't have to maintain information about your vendors' products in your own master data.</span></span> <span data-ttu-id="b303d-105">Zamiast tego koszyk w witrynie internetowej dostawcy jest konwertowany na wiersze zapotrzebowania zawierające poprawne informacje o produktach.</span><span class="sxs-lookup"><span data-stu-id="b303d-105">Instead, the shopping cart on a vendor's website is converted to requisition lines that have the correct product information.</span></span> 

<span data-ttu-id="b303d-106">Należy unikać utrzymywania opisów i cen produktów dostawców wśród własnych danych głównych produktów.</span><span class="sxs-lookup"><span data-stu-id="b303d-106">You should avoid maintaining the descriptions and prices of your vendors’ products in your own product master data.</span></span> <span data-ttu-id="b303d-107">Zamiast tego należy używać zewnętrznych katalogów w scenariuszu elektronicznego systemu zaopatrzenia z dynamicznie dostępnym katalogiem dostawcy.</span><span class="sxs-lookup"><span data-stu-id="b303d-107">Instead, use external catalogs for PunchOut e-procurement.</span></span> <span data-ttu-id="b303d-108">Wtedy gdy pracownicy tworzą zapotrzebowania, mogą dynamicznie sięgnąć do witryny katalogu zewnętrznego dostawcy (innymi słowy opuszczają własny system i przechodzą do witryny dostawcy).</span><span class="sxs-lookup"><span data-stu-id="b303d-108">Then, when employees create requisitions, they can “punch out” to a vendor’s external catalog site (in other words, they leave your system and go to the vendor’s site).</span></span> <span data-ttu-id="b303d-109">Produkty dodane do koszyka w witrynie internetowej dostawcy mogą być następnie konwertowane na wiersze zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="b303d-109">The products that are added to the shopping cart on the vendor’s website can then be converted to requisition lines.</span></span> <span data-ttu-id="b303d-110">W związku z tym otrzymujesz poprawne informacje o produktach: identyfikator produktu, nazwę, cenę itd.</span><span class="sxs-lookup"><span data-stu-id="b303d-110">Therefore, you get the correct product information: product ID, name, price, and so on.</span></span>

<span data-ttu-id="b303d-111">Aby korzystać z zewnętrznych katalogów, pracownik musi utworzyć zapotrzebowania na stronie **Moje zapotrzebowania na zakup**.</span><span class="sxs-lookup"><span data-stu-id="b303d-111">To use external catalogs, an employee must create a requisition on the **My purchase requisitions** page.</span></span>

<span data-ttu-id="b303d-112">Pracownik, który utworzył zapotrzebowanie, jest nazywany wystawcą zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="b303d-112">The employee who creates a requisition is referred to as the preparer of the requisition.</span></span> <span data-ttu-id="b303d-113">Wystawca może wykonywać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="b303d-113">As a preparer, you can complete the following tasks.</span></span>

<span data-ttu-id="b303d-114">Używanie akcji wiersza **Katalogi zewnętrzne** w celu otwarcia strony zawierającej wszystkie katalogi zewnętrzne dostępne dla określonego zleceniodawcy, kupującej firmy i przyjmującej jednostki operacyjnej.</span><span class="sxs-lookup"><span data-stu-id="b303d-114">Use the **External catalogs** line action to open a page that includes all external catalogs that are available for the specified requester, buying legal entity, and receiving operating unit.</span></span>

<span data-ttu-id="b303d-115">W zależności od posiadanych uprawnień zmiana zleceniodawcy, kupującej firmy i przyjmującej jednostki operacyjnej.</span><span class="sxs-lookup"><span data-stu-id="b303d-115">Depending on your permissions, change the requester, buying legal entity, and receiving operating unit.</span></span> <span data-ttu-id="b303d-116">Zmiana tych wartości może powodować zmianę listy zewnętrznych katalogów dostępnych dla zleceniodawcy.</span><span class="sxs-lookup"><span data-stu-id="b303d-116">A change in those values might change the list of external catalogs that are available to a requester.</span></span> <span data-ttu-id="b303d-117">Dostępne zewnętrzne katalogi zależą od obecnie aktywnych zasad zakupów w kupującej firmie lub przyjmującej jednostce operacyjnej.</span><span class="sxs-lookup"><span data-stu-id="b303d-117">The external catalogs that are available depend on the current active purchasing policies for the buying legal entity or the receiving operating unit.</span></span> <span data-ttu-id="b303d-118">Zasady te mogą przyznawać lub blokować dostęp do określonych kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="b303d-118">These policies can allow or prevent access to specific procurement categories.</span></span> <span data-ttu-id="b303d-119">Może to wpływać na listę zewnętrznych katalogów mapowanych na te kategorie zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="b303d-119">Therefore, the list of external catalogs that are mapped to these procurement categories can be affected.</span></span>

<span data-ttu-id="b303d-120">Aby uzyskać więcej informacji o zasadach, zobacz [Zasady zakupów](../procurement/purchase-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b303d-120">For more information about policies, see [Purchasing policies](../procurement/purchase-policies.md).</span></span>

- <span data-ttu-id="b303d-121">Aby znaleźć zewnętrzne katalogi dla określonych kategorii zaopatrzenia, wpisz tekst w polu wyszukiwania katalogów.</span><span class="sxs-lookup"><span data-stu-id="b303d-121">To find external catalogs for specific procurement categories, enter text in the catalog search field.</span></span>
- <span data-ttu-id="b303d-122">Aby dodać produkty z zewnętrznego katalogu dostawcy w witrynie internetowej dostawcy, kliknij zewnętrzny katalog.</span><span class="sxs-lookup"><span data-stu-id="b303d-122">To add products from a vendor’s external catalog on the vendor’s website, click the external catalog.</span></span> <span data-ttu-id="b303d-123">Następnie dodaj produkty do koszyka i sfinalizuj transakcję.</span><span class="sxs-lookup"><span data-stu-id="b303d-123">Then add products to the shopping cart, and check out.</span></span> <span data-ttu-id="b303d-124">Wiersze koszyka zostaną przeniesione do programu Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b303d-124">The shopping cart lines will be transferred to Microsoft Dynamics 365.</span></span>

<span data-ttu-id="b303d-125">Jeśli istnieje wiele kategorii zaopatrzenia, wybierz odpowiednią kategorię zaopatrzenia przed dodaniem wierszy do zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="b303d-125">If there are multiple options for procurement categories, select the correct procurement category before you add the lines to the requisition.</span></span>
<span data-ttu-id="b303d-126">Gdy wiersze zostaną dodane do zapotrzebowania, można dodać więcej wierszy bez korzystania z zewnętrznych katalogów.</span><span class="sxs-lookup"><span data-stu-id="b303d-126">After lines have been added to a requisition, you can add more lines without using external catalogs.</span></span> <span data-ttu-id="b303d-127">Alternatywnie możesz dodawać wiersze nadal z zewnętrznych katalogów.</span><span class="sxs-lookup"><span data-stu-id="b303d-127">Alternatively, you can continue to use external catalogs to add lines.</span></span>

<span data-ttu-id="b303d-128">Gdy zapotrzebowanie jest gotowe, użyj akcji **Przepływ pracy** > **Prześlij**, aby je wysłać do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="b303d-128">When the requisition is ready, use the **Workflow** > **Submit** action to submit it for approval.</span></span>

