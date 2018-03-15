--- 
title: "Konfigurowanie rekomendacji produktów przy użyciu uczenia maszynowego"
description: "Ta procedura odświeża listę danych w magazynie jednostek używanym przez system uczenia maszynowego dostarczający rekomendacji produktów, a następnie umożliwia rekomendowanie produktów na urządzeniach klienckich w punkcie sprzedaży."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 277ffb879b80fe57deeaa2b52c1543baaf820274
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---
# <a name="configure-machine-learning-powered-product-recommendations"></a><span data-ttu-id="4b92e-103">Konfigurowanie rekomendacji produktów przy użyciu uczenia maszynowego</span><span class="sxs-lookup"><span data-stu-id="4b92e-103">Configure machine learning-powered product recommendations</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="4b92e-104">Ta procedura odświeża listę danych w magazynie jednostek używanym przez system uczenia maszynowego dostarczający rekomendacji produktów, a następnie umożliwia rekomendowanie produktów na urządzeniach klienckich w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4b92e-104">This procedure refreshes the data in the Entity store that is used by the machine learning system that powers product recommendations, and then enables product recommendations on POS clients.</span></span> <span data-ttu-id="4b92e-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="4b92e-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="4b92e-106">Wybierz kolejno opcje Administrowanie systemem > Ustawienia > Magazyn jednostek.</span><span class="sxs-lookup"><span data-stu-id="4b92e-106">Go to System administration > Setup > Entity Store.</span></span>
2. <span data-ttu-id="4b92e-107">Na liście znajdź i zaznacz rekord „RetailSales”.</span><span class="sxs-lookup"><span data-stu-id="4b92e-107">In the list, find and select the record 'RetailSales'.</span></span>
3. <span data-ttu-id="4b92e-108">Kliknij przycisk Odśwież.</span><span class="sxs-lookup"><span data-stu-id="4b92e-108">Click Refresh.</span></span>
4. <span data-ttu-id="4b92e-109">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4b92e-109">Click OK.</span></span>
5. <span data-ttu-id="4b92e-110">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4b92e-110">Close the page.</span></span>
6. <span data-ttu-id="4b92e-111">Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia centrali > Parametry > Parametry sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4b92e-111">Go to Retail and commerce > Headquarters setup > Parameters > Retail parameters.</span></span>
7. <span data-ttu-id="4b92e-112">Kliknij kartę Uczenie maszynowe.</span><span class="sxs-lookup"><span data-stu-id="4b92e-112">Click the Machine learning tab.</span></span>
8. <span data-ttu-id="4b92e-113">W polu Włącz rekomendacje produktów zaznacz opcję „Tak”.</span><span class="sxs-lookup"><span data-stu-id="4b92e-113">Select 'Yes' in the Enable product recommendations field.</span></span>
    * <span data-ttu-id="4b92e-114">Jeśli zostanie wyświetlony komunikat „Nie można pobrać modeli rekomendacji”, wynika to z faktu, że magazyn jednostek był odświeżany bardzo niedawno i system mógł jeszcze nie ukończyć przyswajania nowych danych.</span><span class="sxs-lookup"><span data-stu-id="4b92e-114">If you receive the message "The recommendation models couldn't be retrieved", it’s because you refreshed the Entity Store very recently and the system may not have finished assimilating the new data.</span></span> <span data-ttu-id="4b92e-115">Odczekaj 2-3 godziny i spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="4b92e-115">Wait 2-3 hours and try again.</span></span>  
9. <span data-ttu-id="4b92e-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="4b92e-116">Click Save.</span></span>
10. <span data-ttu-id="4b92e-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4b92e-117">Close the page.</span></span>


