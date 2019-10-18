---
title: Rejestrowanie i księgowanie czeku postdatowanego dla dostawcy
description: Za pomocą załącznika arkusza można zarejestrować szczegóły czeku postdatowanego przed wysłaniem go dostawcy.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe29e106055177dbd12c39ee3fc9de609059f73b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179421"
---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a><span data-ttu-id="0427d-103">Rejestrowanie i księgowanie czeku postdatowanego dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="0427d-103">Register and post a postdated check for a vendor</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0427d-104">Za pomocą załącznika arkusza można zarejestrować szczegóły czeku postdatowanego przed wysłaniem go dostawcy.</span><span class="sxs-lookup"><span data-stu-id="0427d-104">You can register the details of a postdated check before you issue the check to a vendor by using the journal voucher.</span></span> <span data-ttu-id="0427d-105">Można także zaksięgować postdatowany czek i wygenerować transakcje finansowe.</span><span class="sxs-lookup"><span data-stu-id="0427d-105">You can also post the postdated check and generate financial transactions.</span></span> <span data-ttu-id="0427d-106">Przed zarejestrowaniem i zaksięgowaniem postdatowanego czeku od dostawcy należy wykonać następujące zadanie:</span><span class="sxs-lookup"><span data-stu-id="0427d-106">Before you register and post a postdated check from a vendor, complete the following task:</span></span> 

<span data-ttu-id="0427d-107">Konfigurowanie czeków postdatowanych na stronie Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="0427d-107">Set up postdated checks in the Cash and bank management page.</span></span> 



<span data-ttu-id="0427d-108">Rolą w tym przewodniku po zadaniach jest Skarbnik.</span><span class="sxs-lookup"><span data-stu-id="0427d-108">The role of this task guides is Treasurer.</span></span> <span data-ttu-id="0427d-109">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="0427d-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="0427d-110">Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="0427d-110">Go to Acounts payable > Payments > Payment journal</span></span>
2. <span data-ttu-id="0427d-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0427d-111">Click New.</span></span>
3. <span data-ttu-id="0427d-112">W polu Nazwa wpisz „VendPay”.</span><span class="sxs-lookup"><span data-stu-id="0427d-112">In the Name field, type 'VendPay'.</span></span>
4. <span data-ttu-id="0427d-113">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="0427d-113">Click Lines.</span></span>
5. <span data-ttu-id="0427d-114">W polu Konto podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="0427d-114">In the Account field, specify the desired values.</span></span>
6. <span data-ttu-id="0427d-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="0427d-115">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="0427d-116">W polu Debet wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="0427d-116">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="0427d-117">W polu Metoda płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0427d-117">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="0427d-118">Wybierz metodę płatności dla czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="0427d-118">Select the method of payment for the postdated check</span></span>  
9. <span data-ttu-id="0427d-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="0427d-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="0427d-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0427d-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="0427d-121">Kliknij kartę Czeki postdatowane.</span><span class="sxs-lookup"><span data-stu-id="0427d-121">Click the Postdated checks tab.</span></span>
12. <span data-ttu-id="0427d-122">W polu Numer czeku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0427d-122">In the Check number field, type a value.</span></span>
    * <span data-ttu-id="0427d-123">Wprowadź lub zmodyfikuj numer czeku postdatowanego.</span><span class="sxs-lookup"><span data-stu-id="0427d-123">Enter or modify the number of the postdated check.</span></span>  
13. <span data-ttu-id="0427d-124">W polu Nazwa banku wystawiającego wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0427d-124">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="0427d-125">Wprowadź dane banku wystawcy.</span><span class="sxs-lookup"><span data-stu-id="0427d-125">enter the bank details for the issuing bank.</span></span>  
14. <span data-ttu-id="0427d-126">Kliknij kartę Lista.</span><span class="sxs-lookup"><span data-stu-id="0427d-126">Click the List tab.</span></span>
15. <span data-ttu-id="0427d-127">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="0427d-127">Click Post.</span></span>
16. <span data-ttu-id="0427d-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0427d-128">Close the page.</span></span>
17. <span data-ttu-id="0427d-129">Kliknij kartę Czeki postdatowane.</span><span class="sxs-lookup"><span data-stu-id="0427d-129">Click the Postdated checks tab.</span></span>

