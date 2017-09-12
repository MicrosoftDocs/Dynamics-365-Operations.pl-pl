--- 
title: "Definiowanie warunków płatności dostawcy"
description: "Konfigurowanie warunków płatności dla faktur od odbiorców."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a00ca73b1bc301960132a86846749d12c39ed3f7
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="define-vendor-payment-terms"></a><span data-ttu-id="a9bdc-103">Definiowanie warunków płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="a9bdc-103">Define vendor payment terms</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a9bdc-104">Konfigurowanie warunków płatności dla faktur od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-104">Set up payment terms for vendor invoices.</span></span> <span data-ttu-id="a9bdc-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="a9bdc-106">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Warunki płatności.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-106">Go to Accounts payable > Payment setup > Terms of payment.</span></span>
2. <span data-ttu-id="a9bdc-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-107">Click New.</span></span>
    * <span data-ttu-id="a9bdc-108">Strona Warunki płatności służy do definiowania sposobu obliczania terminu płatności.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-108">The Terms of payment page is used to define how the due date will be calculated.</span></span> <span data-ttu-id="a9bdc-109">Nie jest używana do definiowania sposobu obliczania daty rabatu gotówkowego.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-109">It is not used to define how the cash discount date will be calculated.</span></span>  
3. <span data-ttu-id="a9bdc-110">W polu Warunki płatności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-110">In the Terms of payment field, type a value.</span></span>
4. <span data-ttu-id="a9bdc-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a9bdc-112">W polu Dni wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-112">In the Days field, enter a number.</span></span>
    * <span data-ttu-id="a9bdc-113">Liczba wprowadzona w tym polu zostanie użyta w celu dodania czasu do terminu płatności lub do końca okresu zidentyfikowanego w metodzie płatności.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-113">The number entered here will be used to add to the due date, or to the end of the period identified in the Payment method.</span></span> <span data-ttu-id="a9bdc-114">Na przykład wybranie opcji Netto spowoduje dodanie czasu do terminu płatności.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-114">For example, if you select Net, the number will be added to the due date.</span></span> <span data-ttu-id="a9bdc-115">Jeśli zaznaczysz opcję Bieżący miesiąc, w celu obliczenia terminu płatności czas zostanie dodany do ostatniego dnia bieżącego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-115">If you select Current month, it will add the number to the last day of the current month to calculate the due date.</span></span>  
6. <span data-ttu-id="a9bdc-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-116">Click Save.</span></span>
7. <span data-ttu-id="a9bdc-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-117">Close the page.</span></span>
8. <span data-ttu-id="a9bdc-118">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Rabaty gotówkowe.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-118">Go to Accounts payable > Payment setup > Cash discounts.</span></span>
9. <span data-ttu-id="a9bdc-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-119">Click New.</span></span>
10. <span data-ttu-id="a9bdc-120">W polu Rabat gotówkowy wprowadź identyfikator.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-120">In the Cash discount field, enter an ID.</span></span>
11. <span data-ttu-id="a9bdc-121">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-121">In the Description field, type a value.</span></span>
12. <span data-ttu-id="a9bdc-122">Jeśli dostawca oferuje rabat warstwowy, zaznacz następny rabat gotówkowy, który będzie stosowany po upływie terminu bieżącego rabatu.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-122">If the vendor offers a tiered discount, select the next cash discount after the current one is expired.</span></span>
13. <span data-ttu-id="a9bdc-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-123">Close the page.</span></span>
14. <span data-ttu-id="a9bdc-124">W polu Dni wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-124">In the Days field, enter a number.</span></span>
    * <span data-ttu-id="a9bdc-125">Ilość wprowadzona w polu Dni będzie używana do obliczania daty rabatu gotówkowego w oparciu o opcję wybraną w polu Netto/Bieżące.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-125">The quantity entered in the Days field will be used to calculate the Cash discount date, based on what option was selected in the Net/Current field.</span></span> <span data-ttu-id="a9bdc-126">Jeśli wybrano opcję Netto, w celu wyznaczenia daty rabatu gotówkowego ilość zostanie dodana do daty faktury.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-126">If Net was selected, the quantity will be added to the invoice date to determine the cash discount date.</span></span> <span data-ttu-id="a9bdc-127">Jeśli wybrano opcję Bieżący miesiąc, w celu wyznaczenia daty rabatu gotówkowego ilość zostanie dodana na końcu bieżącego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-127">If Current month was selected, the quantity will be added to the end of the currency month to determine the cash discount date.</span></span>  
15. <span data-ttu-id="a9bdc-128">W polu Rabat wprowadź wartość procentową rabatu gotówkowego.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-128">Enter the percentage of the cash discount in the Discount field.</span></span> 
16. <span data-ttu-id="a9bdc-129">Wprowadź konto główne, na którym będzie księgowany rabat gotówkowy faktur dla odbiorców.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-129">Enter the main account to which the cash discount will be posted for customer invoices.</span></span>
17. <span data-ttu-id="a9bdc-130">Wprowadź konto główne, na którym będzie księgowany rabat gotówkowy faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-130">Enter the main account to which the cash discount will be posted for vendor invoices.</span></span>
    * <span data-ttu-id="a9bdc-131">Jeśli w polu „Konta przeciwstawne rabatów” jest ustawiona opcja Użyj konta głównego dla rabaty dostawcy, będzie używane konto główne.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-131">If 'Discount offset accounts' is set to Use main account for vendor discount, then the Main account will be used.</span></span>  <span data-ttu-id="a9bdc-132">Jeśli wybierzesz opcję Konta w wierszach faktury, rabat gotówkowy będzie księgowany na kontach środków trwałych/wydatków z wierszy faktury.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-132">If the option is set to Accounts on the invoice lines, the cash discount will be posted to the asset/expense accounts on the invoice's lines.</span></span>  
18. <span data-ttu-id="a9bdc-133">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-133">Click Save.</span></span>


