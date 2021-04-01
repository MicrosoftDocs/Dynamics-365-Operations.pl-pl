---
title: Konfigurowanie przetwarzania karty kredytowej
description: Ta procedura zawiera instruktaż wyświetlania listy dostawców płatności i konfigurowania konta płatności dla rozrachunków z odbiorcami.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d365dfce8e8fbd332111d96eeb2a431151d7a342
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234228"
---
# <a name="configure-credit-card-processing"></a><span data-ttu-id="1ee53-103">Konfigurowanie przetwarzania karty kredytowej</span><span class="sxs-lookup"><span data-stu-id="1ee53-103">Configure credit card processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ee53-104">Ta procedura zawiera instruktaż wyświetlania listy dostawców płatności i konfigurowania konta płatności dla rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="1ee53-104">This procedure walks through how to view the list of payment providers and how to configure a payment account for accounts receivable.</span></span> <span data-ttu-id="1ee53-105">Procedura używa danych firmy demonstracyjnej USRT i jest przeznaczona dla administratorów oraz specjalistów IT.</span><span class="sxs-lookup"><span data-stu-id="1ee53-105">This procedure uses the USRT company in demo data and is intended for Administrators and IT Professionals.</span></span>


## <a name="view-a-list-of-payment-providers"></a><span data-ttu-id="1ee53-106">Wyświetlanie listy dostawców płatności</span><span class="sxs-lookup"><span data-stu-id="1ee53-106">View a list of payment providers</span></span>
1. <span data-ttu-id="1ee53-107">Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Usługi płatności.</span><span class="sxs-lookup"><span data-stu-id="1ee53-107">Go to Accounts receivable > Payments setup > Payment services.</span></span>
2. <span data-ttu-id="1ee53-108">Kliknij opcję Wyświetl dostępnych dostawców.</span><span class="sxs-lookup"><span data-stu-id="1ee53-108">Click View available providers.</span></span>

## <a name="configure-payment-account"></a><span data-ttu-id="1ee53-109">Konfigurowanie konta płatności</span><span class="sxs-lookup"><span data-stu-id="1ee53-109">Configure payment account</span></span>
1. <span data-ttu-id="1ee53-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1ee53-110">Click New.</span></span>
2. <span data-ttu-id="1ee53-111">W polu Usługa płatności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1ee53-111">In the Payment service field, type a value.</span></span>
3. <span data-ttu-id="1ee53-112">W polu Łącznik płatności wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="1ee53-112">In the Payment connector field, select an option.</span></span>
4. <span data-ttu-id="1ee53-113">Przełącz rozwinięcie sekcji Konto usługi płatności.</span><span class="sxs-lookup"><span data-stu-id="1ee53-113">Toggle the expansion of the Payment service account section.</span></span>
5. <span data-ttu-id="1ee53-114">W polu Środowisko: wpisz „PROD”.</span><span class="sxs-lookup"><span data-stu-id="1ee53-114">In the Environment: field, type 'PROD'.</span></span>
6. <span data-ttu-id="1ee53-115">Kliknij opcję Typy kart kredytowych.</span><span class="sxs-lookup"><span data-stu-id="1ee53-115">Click Credit card types.</span></span>
7. <span data-ttu-id="1ee53-116">W polu Arkusz płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1ee53-116">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="1ee53-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1ee53-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="1ee53-118">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1ee53-118">Click Add.</span></span>
10. <span data-ttu-id="1ee53-119">W polu Waluta wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1ee53-119">In the Currency field, type a value.</span></span>
11. <span data-ttu-id="1ee53-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1ee53-120">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="1ee53-121">W polu Arkusz płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1ee53-121">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="1ee53-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1ee53-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="1ee53-123">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1ee53-123">Click Add.</span></span>
15. <span data-ttu-id="1ee53-124">W polu Waluta wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1ee53-124">In the Currency field, type a value.</span></span>
16. <span data-ttu-id="1ee53-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1ee53-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1ee53-126">Te kroki można powtórzyć dla typu typów kart, ile jest potrzebnych.</span><span class="sxs-lookup"><span data-stu-id="1ee53-126">You can repeat these steps for as many card types as you need.</span></span>  
17. <span data-ttu-id="1ee53-127">W polu Arkusz płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1ee53-127">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="1ee53-128">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1ee53-128">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="1ee53-129">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1ee53-129">Click Add.</span></span>
20. <span data-ttu-id="1ee53-130">W polu Waluta wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1ee53-130">In the Currency field, type a value.</span></span>
21. <span data-ttu-id="1ee53-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1ee53-131">Click Save.</span></span>
22. <span data-ttu-id="1ee53-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1ee53-132">Close the page.</span></span>
23. <span data-ttu-id="1ee53-133">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="1ee53-133">Click Validate.</span></span>
24. <span data-ttu-id="1ee53-134">Zaznacz pole wyboru Domyślny agent rozliczeniowy dla nowych kart kredytowych.</span><span class="sxs-lookup"><span data-stu-id="1ee53-134">Click the Default processor for new credit cards checkbox.</span></span>
25. <span data-ttu-id="1ee53-135">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1ee53-135">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]