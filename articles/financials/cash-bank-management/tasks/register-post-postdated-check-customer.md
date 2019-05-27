---
title: Rejestrowanie i księgowanie czeku postdatowanego dla odbiorcy
description: Można rejestrować szczegóły czeku postdatowanego otrzymanego od odbiorcy.
author: kweekley
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 131e4f364c62d03b95fb4b77f472828b9483d5e1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566094"
---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="b6ba2-103">Rejestrowanie i księgowanie czeku postdatowanego dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="b6ba2-103">Register and post a postdated check for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b6ba2-104">Można rejestrować szczegóły czeku postdatowanego otrzymanego od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-104">You can register details of a postdated check received from a customer.</span></span> <span data-ttu-id="b6ba2-105">Można także zaksięgować postdatowany czek i wygenerować transakcje finansowe.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-105">You can also post the postdated check and generate financial transactions.</span></span>   <span data-ttu-id="b6ba2-106">Przed zarejestrowaniem i zaksięgowaniem postdatowanego czeku otrzymanego od odbiorcy należy wykonać następujące zadania:   • Konfigurowanie czeku postdatowanego na stronie Zarządzanie gotówką i bankami • Konfigurowanie metody płatności dla czeków postdatowanych   Rolą w tej procedurze jest Skarbnik.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-106">Complete the following tasks before you register and post a postdated check received from a customer:   • Set up postdated check in the Cash and bank management page • Set up a method of payment for postdated checks   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="b6ba2-107">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="b6ba2-108">Wybierz kolejno opcje Rozrachunki z odbiorcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="b6ba2-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-109">Click New.</span></span>
3. <span data-ttu-id="b6ba2-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="b6ba2-111">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-111">Click Lines.</span></span>
5. <span data-ttu-id="b6ba2-112">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="b6ba2-113">W polu Konto podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="b6ba2-114">W polu Kredyt wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="b6ba2-115">Wprowadź kwotę określoną w czeku postdatowanym.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-115">Enter the amount specified in the postdated check.</span></span>  
8. <span data-ttu-id="b6ba2-116">Kliknij kartę Płatność.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="b6ba2-117">W polu Metoda płatności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="b6ba2-118">Wybierz metodę płatności dla czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-118">Select the method of payment for the postdated check.</span></span>  
10. <span data-ttu-id="b6ba2-119">Kliknij kartę Czeki postdatowane.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="b6ba2-120">W polu Data terminu płatności wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="b6ba2-121">Wprowadź datę należności czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-121">Enter the date when the postdated check is due for payment.</span></span>  
12. <span data-ttu-id="b6ba2-122">W polu Oddział banku wystawiającego wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="b6ba2-123">Wprowadź informacje bankowe czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-123">Enter the bank details of the postdated check.</span></span>  
13. <span data-ttu-id="b6ba2-124">W polu Numer czeku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-124">In the check number field, type a value.</span></span>
14. <span data-ttu-id="b6ba2-125">W polu Nazwa banku wystawiającego wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="b6ba2-126">Wprowadź informacje bankowe czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="b6ba2-127">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-127">Click Post.</span></span>
16. <span data-ttu-id="b6ba2-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b6ba2-128">Close the page.</span></span>

