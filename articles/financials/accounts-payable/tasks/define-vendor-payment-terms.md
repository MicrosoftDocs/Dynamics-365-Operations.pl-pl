---
title: Definiowanie warunków płatności dla dostawcy
description: W tym temacie opisano sposób konfigurowania warunków płatności dla faktur od dostawcy.
author: abruer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6432d04aa821e76d67e2c430e514f4b9056d8228
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843201"
---
# <a name="define-vendor-payment-terms"></a><span data-ttu-id="f3d25-103">Definiowanie warunków płatności dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="f3d25-103">Define vendor payment terms</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f3d25-104">W tym temacie opisano sposób konfigurowania warunków płatności dla faktur od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="f3d25-104">This topic explains how to set up payment terms for vendor invoices.</span></span> <span data-ttu-id="f3d25-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="f3d25-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f3d25-106">Wybierz kolejno **okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia płatności > Warunki płatności**.</span><span class="sxs-lookup"><span data-stu-id="f3d25-106">Go to **Navigation pane > Modules > Accounts payable > Payment setup > Terms of payment**.</span></span>
2. <span data-ttu-id="f3d25-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3d25-107">Select **New**.</span></span> <span data-ttu-id="f3d25-108">Strona Warunki płatności służy do definiowania sposobu obliczania terminu płatności.</span><span class="sxs-lookup"><span data-stu-id="f3d25-108">The Terms of payment page is used to define how the due date will be calculated.</span></span> <span data-ttu-id="f3d25-109">Nie jest używana do definiowania sposobu obliczania daty rabatu gotówkowego.</span><span class="sxs-lookup"><span data-stu-id="f3d25-109">It is not used to define how the cash discount date will be calculated.</span></span>  
3. <span data-ttu-id="f3d25-110">W polu **Warunki płatności** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f3d25-110">In the **Terms of payment** field, type a value.</span></span>
4. <span data-ttu-id="f3d25-111">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f3d25-111">In the **Description field**, type a value.</span></span>
5. <span data-ttu-id="f3d25-112">W polu **Dni** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f3d25-112">In the **Days** field, enter a number.</span></span> <span data-ttu-id="f3d25-113">Liczba wprowadzona w tym polu zostanie użyta w celu dodania czasu do terminu płatności lub do końca okresu zidentyfikowanego w metodzie płatności.</span><span class="sxs-lookup"><span data-stu-id="f3d25-113">The number entered here will be used to add to the due date, or to the end of the period identified in the Payment method.</span></span> <span data-ttu-id="f3d25-114">Na przykład wybranie opcji **Netto** spowoduje dodanie czasu do terminu płatności.</span><span class="sxs-lookup"><span data-stu-id="f3d25-114">For example, if you select **Net**, the number will be added to the due date.</span></span> <span data-ttu-id="f3d25-115">Jeśli zaznaczysz opcję **Bieżący miesiąc**, w celu obliczenia terminu płatności czas zostanie dodany do ostatniego dnia bieżącego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="f3d25-115">If you select **Current month**, it will add the number to the last day of the current month to calculate the due date.</span></span>  
6. <span data-ttu-id="f3d25-116">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3d25-116">Select **Save**.</span></span>
7. <span data-ttu-id="f3d25-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f3d25-117">Close the page.</span></span>
8. <span data-ttu-id="f3d25-118">Wybierz kolejno opcje **Rozrachunki z dostawcami > Ustawienia płatności > Rabaty gotówkowe**.</span><span class="sxs-lookup"><span data-stu-id="f3d25-118">Go to **Accounts payable > Payment setup > Cash discounts**.</span></span>
9. <span data-ttu-id="f3d25-119">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3d25-119">Select **New**.</span></span>
10. <span data-ttu-id="f3d25-120">W polu **Rabat gotówkowy** wprowadź identyfikator.</span><span class="sxs-lookup"><span data-stu-id="f3d25-120">In the **Cash discount** field, enter an ID.</span></span>
11. <span data-ttu-id="f3d25-121">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f3d25-121">In the **Description** field, type a value.</span></span>
12. <span data-ttu-id="f3d25-122">Jeśli dostawca oferuje rabat warstwowy, zaznacz następny rabat gotówkowy, który będzie stosowany po upływie terminu bieżącego rabatu.</span><span class="sxs-lookup"><span data-stu-id="f3d25-122">If the vendor offers a tiered discount, select the next cash discount after the current one is expired.</span></span>
13. <span data-ttu-id="f3d25-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f3d25-123">Close the page.</span></span>
14. <span data-ttu-id="f3d25-124">W polu **Dni** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f3d25-124">In the **Days** field, enter a number.</span></span> <span data-ttu-id="f3d25-125">Ilość wprowadzona w polu **Dni** będzie używana do obliczania daty rabatu gotówkowego w oparciu o opcję wybraną w polu **Netto/Bieżące**.</span><span class="sxs-lookup"><span data-stu-id="f3d25-125">The quantity entered in the **Days** field will be used to calculate the Cash discount date, based on what option was selected in the **Net/Current** field.</span></span> <span data-ttu-id="f3d25-126">Jeśli wybrano opcję **Netto**, w celu wyznaczenia daty rabatu gotówkowego ilość zostanie dodana do daty faktury.</span><span class="sxs-lookup"><span data-stu-id="f3d25-126">If **Net** was selected, the quantity will be added to the invoice date to determine the cash discount date.</span></span> <span data-ttu-id="f3d25-127">Jeśli wybrano opcję **Bieżący miesiąc**, w celu wyznaczenia daty rabatu gotówkowego ilość zostanie dodana na końcu bieżącego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="f3d25-127">If **Current month** was selected, the quantity will be added to the end of the currency month to determine the cash discount date.</span></span>  
15. <span data-ttu-id="f3d25-128">W polu **Rabat** wprowadź wartość procentową rabatu gotówkowego.</span><span class="sxs-lookup"><span data-stu-id="f3d25-128">Enter the percentage of the cash discount in the **Discount** field.</span></span> 
16. <span data-ttu-id="f3d25-129">Wprowadź konto główne, do którego zostanie zaksięgowany rabat gotówkowy dla faktur odbiorcy, a następnie wprowadź konto główne, do którego zostanie zaksięgowany rabat gotówkowy dla faktur od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="f3d25-129">Enter the main account to which the cash discount will be posted for customer invoices, then enter the main account to which the cash discount will be posted for vendor invoices.</span></span> <span data-ttu-id="f3d25-130">Jeśli w polu **Konta przeciwstawne rabatów** jest ustawiona opcja **Użyj konta głównego dla rabaty dostawcy**, będzie używane konto główne.</span><span class="sxs-lookup"><span data-stu-id="f3d25-130">If **Discount offset accounts** is set to **Use main account for vendor discount**, then the Main account will be used.</span></span> <span data-ttu-id="f3d25-131">Jeśli wybierzesz opcję **Konta w wierszach faktury**, rabat gotówkowy będzie księgowany na kontach środków trwałych/wydatków z wierszy faktury.</span><span class="sxs-lookup"><span data-stu-id="f3d25-131">If the option is set to **Accounts on the invoice lines**, the cash discount will be posted to the asset/expense accounts on the invoice's lines.</span></span>  
17. <span data-ttu-id="f3d25-132">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3d25-132">Select **Save**.</span></span>

