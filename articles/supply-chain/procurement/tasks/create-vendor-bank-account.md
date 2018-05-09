--- 
title: Tworzenie konta bankowego dostawcy
description: "W tej procedurze pokazano sposób tworzenia konta bankowego dla dostawcy."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3d4977ae0c1ce613b044e59161c96461027411f2
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-vendor-bank-account"></a><span data-ttu-id="7c01a-103">Tworzenie konta bankowego dostawcy</span><span class="sxs-lookup"><span data-stu-id="7c01a-103">Create a vendor bank account</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7c01a-104">W tej procedurze pokazano sposób tworzenia konta bankowego dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="7c01a-104">This procedure shows you how to create a bank account for a vendor.</span></span> <span data-ttu-id="7c01a-105">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="7c01a-105">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="7c01a-106">Wybierz kolejno opcje Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy.</span><span class="sxs-lookup"><span data-stu-id="7c01a-106">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="7c01a-107">Zaznacz dostawcę, dla którego chcesz utworzyć konto bankowe, a następnie kliknij łącze identyfikatora konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="7c01a-107">Select the vendor that you want to create a bank account for, and then click the link on the Vendor account ID.</span></span>
3. <span data-ttu-id="7c01a-108">W okienku akcji kliknij pozycję Dostawca.</span><span class="sxs-lookup"><span data-stu-id="7c01a-108">On the Action Pane, click Vendor.</span></span>
4. <span data-ttu-id="7c01a-109">Kliknij przycisk konta bankowe</span><span class="sxs-lookup"><span data-stu-id="7c01a-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="7c01a-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7c01a-110">Click New.</span></span>
6. <span data-ttu-id="7c01a-111">W polu Konto bankowe wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-111">In the Bank account field, type a value.</span></span>
    * <span data-ttu-id="7c01a-112">Ten identyfikator będzie używany do identyfikowania konta bankowego w rekordzie dostawcy.</span><span class="sxs-lookup"><span data-stu-id="7c01a-112">This ID will be used to identify the bank account on the vendor record.</span></span>  
7. <span data-ttu-id="7c01a-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="7c01a-114">W polu Grupy bankowe wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-114">In the Bank groups field, enter or select a value.</span></span>
9. <span data-ttu-id="7c01a-115">W polu Typ kodu banku wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="7c01a-115">In the Routing number type field, select an option.</span></span>
    * <span data-ttu-id="7c01a-116">Jest to typ numeru rozliczeniowego używanego w płatnościach międzynarodowych.</span><span class="sxs-lookup"><span data-stu-id="7c01a-116">This is the type of routing number that’s used for international payments.</span></span>  
10. <span data-ttu-id="7c01a-117">W polu Numer konta bankowego wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-117">In the Bank account number field, type a value.</span></span>
11. <span data-ttu-id="7c01a-118">W polu Kod SWIFT wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-118">In the SWIFT code field, type a value.</span></span>
12. <span data-ttu-id="7c01a-119">W polu IBAN wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-119">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="7c01a-120">Numer IBAN musi mieć poprawny format.</span><span class="sxs-lookup"><span data-stu-id="7c01a-120">The IBAN number must be in the correct format.</span></span> <span data-ttu-id="7c01a-121">Na przykład można użyć DE89370400440532013000.</span><span class="sxs-lookup"><span data-stu-id="7c01a-121">For example, you could use DE89370400440532013000.</span></span>  
    * <span data-ttu-id="7c01a-122">Konto bankowe ma stan Aktywny, jeśli osiągnięto datę aktywacji, a nie przekroczono data ważności.</span><span class="sxs-lookup"><span data-stu-id="7c01a-122">The status of the bank account is Active if the Active date has been reached, and the Expiration date has not been exceeded.</span></span> <span data-ttu-id="7c01a-123">Konto jest również aktywne, gdy oba pola — Data aktywacji i Data ważności — są puste.</span><span class="sxs-lookup"><span data-stu-id="7c01a-123">It’s also active if both the Active date and Expiration date fields are blank.</span></span> <span data-ttu-id="7c01a-124">Jeśli daty w obu polach Data aktywacji i Data ważności wypadają w przyszłości, płatności elektroniczne są niedostępne.</span><span class="sxs-lookup"><span data-stu-id="7c01a-124">If the dates in both the Active date and Expiration date fields are in the future electronic payments are not available.</span></span> <span data-ttu-id="7c01a-125">Inne typy płatności są dostępne i konto bankowe jest aktywne.</span><span class="sxs-lookup"><span data-stu-id="7c01a-125">Other payment types are available and the bank account is active.</span></span>  
13. <span data-ttu-id="7c01a-126">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="7c01a-126">Expand the Setup section.</span></span>
14. <span data-ttu-id="7c01a-127">W polu Kod tekstu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-127">In the Text code field, type a value.</span></span>
    * <span data-ttu-id="7c01a-128">To pole zawiera kod, który będzie wyświetlany na wyciągu bankowym odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="7c01a-128">This field specifies a code that will appear on the bank statement of the recipient.</span></span>  
15. <span data-ttu-id="7c01a-129">W polu Komunikat do banku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-129">In the Message to bank field, type a value.</span></span>
16. <span data-ttu-id="7c01a-130">W polu Odwołanie do kursu wymiany wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-130">In the Exchange reference field, type a value.</span></span>
    * <span data-ttu-id="7c01a-131">Jest to numer referencyjny przyszłego lub stałego kursu wymiany.</span><span class="sxs-lookup"><span data-stu-id="7c01a-131">This is the reference number for any forward-term or fixed-term rate of exchange.</span></span>  
17. <span data-ttu-id="7c01a-132">W polu Waluta wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-132">In the Currency field, enter or select a value.</span></span>
    * <span data-ttu-id="7c01a-133">W przypadku wystawiania przelewów testowych ta sekcja zawiera podgląd ich stanu (zatwierdzone lub oczekujące).</span><span class="sxs-lookup"><span data-stu-id="7c01a-133">When prenotes are issued, this section provides an overview of their status (pending or approved).</span></span>  
18. <span data-ttu-id="7c01a-134">Rozwiń sekcję Adres.</span><span class="sxs-lookup"><span data-stu-id="7c01a-134">Expand the Address section.</span></span>
19. <span data-ttu-id="7c01a-135">Rozwiń sekcję Przelewy testowe.</span><span class="sxs-lookup"><span data-stu-id="7c01a-135">Expand the Prenotes section.</span></span>
20. <span data-ttu-id="7c01a-136">Rozwiń sekcję Informacje kontaktowe.</span><span class="sxs-lookup"><span data-stu-id="7c01a-136">Expand the Contact information section.</span></span>
21. <span data-ttu-id="7c01a-137">W polu Numer telefonu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7c01a-137">In the Telephone field, type a value.</span></span>
22. <span data-ttu-id="7c01a-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7c01a-138">Close the page.</span></span>
23. <span data-ttu-id="7c01a-139">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="7c01a-139">Click Edit.</span></span>
24. <span data-ttu-id="7c01a-140">Rozwiń sekcję Płatność.</span><span class="sxs-lookup"><span data-stu-id="7c01a-140">Expand the Payment section.</span></span>
25. <span data-ttu-id="7c01a-141">W polu Konto bankowe zaznacz właśnie utworzone konto.</span><span class="sxs-lookup"><span data-stu-id="7c01a-141">In the Bank  account field, select the account that you’ve just created.</span></span>
26. <span data-ttu-id="7c01a-142">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7c01a-142">Click Save.</span></span>
    * <span data-ttu-id="7c01a-143">Adres może być dziedziczony z grupy bankowej (jeśli został tam określony) albo można go dodać w tym polu.</span><span class="sxs-lookup"><span data-stu-id="7c01a-143">The address may be inherited from the bank group, if one is specified, or you can add it here.</span></span>  


