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
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11089584e150a1a302eb969a5fb61cb9d1900901
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141748"
---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="0b12f-103">Rejestrowanie i księgowanie czeku postdatowanego dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="0b12f-103">Register and post a postdated check for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0b12f-104">Można rejestrować szczegóły czeku postdatowanego otrzymanego od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="0b12f-104">You can register details of a postdated check received from a customer.</span></span> <span data-ttu-id="0b12f-105">Można także zaksięgować postdatowany czek i wygenerować transakcje finansowe.</span><span class="sxs-lookup"><span data-stu-id="0b12f-105">You can also post the postdated check and generate financial transactions.</span></span>   <span data-ttu-id="0b12f-106">Przed zarejestrowaniem i zaksięgowaniem postdatowanego czeku otrzymanego od odbiorcy należy wykonać następujące zadania:  \* Konfigurowanie czeku postdatowanego na stronie Zarządzanie gotówką i bankami \* Konfigurowanie metody płatności dla czeków postdatowanych   Rolą w tej procedurze jest Skarbnik.</span><span class="sxs-lookup"><span data-stu-id="0b12f-106">Complete the following tasks before you register and post a postdated check received from a customer:   \* Set up postdated check in the Cash and bank management page \* Set up a method of payment for postdated checks   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="0b12f-107">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="0b12f-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="0b12f-108">Wybierz kolejno opcje Rozrachunki z odbiorcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="0b12f-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="0b12f-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0b12f-109">Click New.</span></span>
3. <span data-ttu-id="0b12f-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0b12f-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="0b12f-111">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="0b12f-111">Click Lines.</span></span>
5. <span data-ttu-id="0b12f-112">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="0b12f-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="0b12f-113">W polu Konto podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="0b12f-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="0b12f-114">W polu Kredyt wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="0b12f-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="0b12f-115">Wprowadź kwotę określoną w czeku postdatowanym.</span><span class="sxs-lookup"><span data-stu-id="0b12f-115">Enter the amount specified in the postdated check.</span></span>  
8. <span data-ttu-id="0b12f-116">Kliknij kartę Płatność.</span><span class="sxs-lookup"><span data-stu-id="0b12f-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="0b12f-117">W polu Metoda płatności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0b12f-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="0b12f-118">Wybierz metodę płatności dla czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="0b12f-118">Select the method of payment for the postdated check.</span></span>  
10. <span data-ttu-id="0b12f-119">Kliknij kartę Czeki postdatowane.</span><span class="sxs-lookup"><span data-stu-id="0b12f-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="0b12f-120">W polu Data terminu płatności wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="0b12f-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="0b12f-121">Wprowadź datę należności czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="0b12f-121">Enter the date when the postdated check is due for payment.</span></span>  
12. <span data-ttu-id="0b12f-122">W polu Oddział banku wystawiającego wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0b12f-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="0b12f-123">Wprowadź informacje bankowe czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="0b12f-123">Enter the bank details of the postdated check.</span></span>  
13. <span data-ttu-id="0b12f-124">W polu Numer czeku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0b12f-124">In the check number field, type a value.</span></span>
14. <span data-ttu-id="0b12f-125">W polu Nazwa banku wystawiającego wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0b12f-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="0b12f-126">Wprowadź informacje bankowe czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="0b12f-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="0b12f-127">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="0b12f-127">Click Post.</span></span>
16. <span data-ttu-id="0b12f-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0b12f-128">Close the page.</span></span>

