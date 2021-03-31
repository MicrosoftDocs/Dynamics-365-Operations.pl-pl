---
title: Tworzenie kodu odsetek z zakresem
description: Kody odsetek można konfigurować do obliczania różnych kwot odsetek na podstawie zakresu wartości.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 44b98436d6e0c40f0458dc4744b8b1d96baa8b54
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216576"
---
# <a name="create-an-interest-code-with-a-range"></a><span data-ttu-id="ceeaa-103">Tworzenie kodu odsetek z zakresem</span><span class="sxs-lookup"><span data-stu-id="ceeaa-103">Create an interest code with a range</span></span>

[!include [banner](../../includes/banner.md)]
<span data-ttu-id="ceeaa-104">Kody odsetek można konfigurować do obliczania różnych kwot odsetek na podstawie zakresu wartości.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-104">Interest codes can be set up to calculate different interest amounts based on a range of values.</span></span> <span data-ttu-id="ceeaa-105">Ta procedura pokazuje dodawanie kodu odsetek i dodawanie do niego zakresu.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-105">This procedure will show you how to add an interest code and add a range to it.</span></span>

1. <span data-ttu-id="ceeaa-106">Wybierz kolejno opcje Kredyty i windykacja > Odsetki > Skonfiguruj kody odsetek.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-106">Go to Credit and collections > Interest > Set up interest codes.</span></span>
2. <span data-ttu-id="ceeaa-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-107">Click New.</span></span>
3. <span data-ttu-id="ceeaa-108">W polu Kod odsetek wprowadź nazwę kodu odsetek.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-108">In the Interest code field, enter the name of the interest code.</span></span>
4. <span data-ttu-id="ceeaa-109">W polu Opis wprowadź opis kodu odsetek.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-109">In the Description field, enter a description for the interest code.</span></span>
5. <span data-ttu-id="ceeaa-110">Wybierz opcję Miesiąc.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-110">Select Month.</span></span>
6. <span data-ttu-id="ceeaa-111">Rozwiń sekcję Dochody.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-111">Expand the Earnings section.</span></span>
7. <span data-ttu-id="ceeaa-112">Rozwiń sekcję Dochody wg waluty.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-112">Expand the Earnings by currency section.</span></span>
8. <span data-ttu-id="ceeaa-113">W polu Konto księgowania w księdze podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-113">In the Ledger posting account field, specify the desired values.</span></span>
9. <span data-ttu-id="ceeaa-114">W polu Odsetki według zakresu wybierz opcję „Miesiące”.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-114">In the Interest by range field, select 'Months'.</span></span>
10. <span data-ttu-id="ceeaa-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-115">Click Add.</span></span>
11. <span data-ttu-id="ceeaa-116">W polu Opis wprowadź opis tej waluty i zakresu.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-116">In the Description field, enter a description for this currency and range.</span></span>
12. <span data-ttu-id="ceeaa-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-117">Click Save.</span></span>
13. <span data-ttu-id="ceeaa-118">Kliknij opcję Zakresy.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-118">Click Ranges.</span></span>
14. <span data-ttu-id="ceeaa-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-119">Click New.</span></span>
15. <span data-ttu-id="ceeaa-120">Wprowadź wartość początkową 0, a następnie wprowadź miesięczną stopę procentową, która będzie używana do obliczania odsetek.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-120">Enter the From value as 0 and then enter the interest percent per month that will be used to calculate the interest.</span></span> <span data-ttu-id="ceeaa-121">W naszym przykładzie jest to 1,5.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-121">For our example, it is 1.5.</span></span>
16. <span data-ttu-id="ceeaa-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-122">Click New.</span></span>
17. <span data-ttu-id="ceeaa-123">Wprowadź następną wartość początkową jako 4, co odpowiada pierwszemu miesiącowi, kiedy będzie obliczana nowa kwota odsetek.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-123">Enter the next From value as 4, which is the first month that you will be calculating a new interest amount.</span></span>
18. <span data-ttu-id="ceeaa-124">Wprowadź miesięczne oprocentowanie, które posłuży do obliczania odsetek począwszy od miesiąca 4.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-124">Enter the interest percent per month that will be used to calculate the interest starting in month 4.</span></span> <span data-ttu-id="ceeaa-125">W tym przykładzie jest to 2,0.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-125">For this example, it is 2.0.</span></span>
19. <span data-ttu-id="ceeaa-126">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-126">Click New.</span></span>
20. <span data-ttu-id="ceeaa-127">Wprowadź następną wartość początkową jako 7, co odpowiada następnemu miesiącowi, kiedy będzie obliczana nowa kwota odsetek.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-127">Enter the next From value as 7, which is the next month that you will be calculating a new interest amount.</span></span>
21. <span data-ttu-id="ceeaa-128">Wprowadź miesięczne oprocentowanie, które posłuży do obliczania odsetek począwszy od miesiąca 7.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-128">Enter the interest percent per month that will be used to calculate the interest starting in month 7.</span></span> <span data-ttu-id="ceeaa-129">W tym przykładzie jest to 2,5.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-129">For this example, it is 2.5.</span></span>
22. <span data-ttu-id="ceeaa-130">Kliknij przycisk Zamknij, aby zakończyć określanie ustawień.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-130">Click Close to complete the setup.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]