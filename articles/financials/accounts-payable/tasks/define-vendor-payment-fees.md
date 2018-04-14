--- 
title: "Definiowanie opłat od płatności dostawcy"
description: "Skonfiguruj opłaty od płatności dla dostawcy."
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a12bdb1532527fff7c3ce0d2b1e34b61b73e8fbc
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="define-vendor-payment-fees"></a><span data-ttu-id="34899-103">Definiowanie opłat od płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="34899-103">Define vendor payment fees</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="34899-104">Skonfiguruj opłaty od płatności dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="34899-104">Set up vendor payment fees.</span></span> <span data-ttu-id="34899-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="34899-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="34899-106">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Opłata.</span><span class="sxs-lookup"><span data-stu-id="34899-106">Go to Accounts payable > Payment setup > Payment fee.</span></span>
2. <span data-ttu-id="34899-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="34899-107">Click New.</span></span>
3. <span data-ttu-id="34899-108">W polu Identyfikator opłaty wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="34899-108">In the Fee ID field, type a value.</span></span>
    * <span data-ttu-id="34899-109">Identyfikator opłaty powinien wskazywać, kiedy opłata będzie używana, np. „Opłata_EFT”.</span><span class="sxs-lookup"><span data-stu-id="34899-109">The Fee ID should describe when this fee will be used, such as "EFT_Fee".</span></span>  
4. <span data-ttu-id="34899-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="34899-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="34899-111">W polu Opis opłaty wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="34899-111">In the Fee description field, type a value.</span></span>
    * <span data-ttu-id="34899-112">Dodaj opis, który bardziej szczegółowo wyjaśnia, kiedy opłata jest naliczana.</span><span class="sxs-lookup"><span data-stu-id="34899-112">Add a description to provide more detail on when the fee is assessed.</span></span>  
6. <span data-ttu-id="34899-113">W polu Opłata zaznacz opcję Dostawca lub Księga.</span><span class="sxs-lookup"><span data-stu-id="34899-113">In the Charge field, select either Vendor or Ledger.</span></span>
    * <span data-ttu-id="34899-114">Jeśli opłaty będą zaliczane w koszty firmy, jest używana opcja Księga.</span><span class="sxs-lookup"><span data-stu-id="34899-114">Ledger is used when the fee will be expensed to your organization.</span></span>  <span data-ttu-id="34899-115">Opcja Dostawca jest używany, jeśli opłata będzie naliczana dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="34899-115">Vendor is used when the fee will be assessed to the vendor.</span></span>  
7. <span data-ttu-id="34899-116">Wprowadź konto główne, na którym opłata będzie naliczane w ciężar kosztów.</span><span class="sxs-lookup"><span data-stu-id="34899-116">Enter a main account for where the fee will be expensed.</span></span>
    * <span data-ttu-id="34899-117">Ta opcja jest dostępna tylko wtedy, gdy w polu Opłata wybrano opcję Księga.</span><span class="sxs-lookup"><span data-stu-id="34899-117">This option is only available when selecting Ledger as the Charge option.</span></span>  
8. <span data-ttu-id="34899-118">Wybierz arkusz, w którym można używać tej opłaty.</span><span class="sxs-lookup"><span data-stu-id="34899-118">Select the journal on which this fee can be used.</span></span> 
    * <span data-ttu-id="34899-119">W przypadku opłaty od płatności dostawcy należy wybrać arkusz „Wypłaty dla dostawców”.</span><span class="sxs-lookup"><span data-stu-id="34899-119">For a vendor payment fee, you would select the journal 'Vendor disbursement.'</span></span>  
9. <span data-ttu-id="34899-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="34899-120">Click Save.</span></span>
10. <span data-ttu-id="34899-121">Kliknij opcję Ustawienia opłat.</span><span class="sxs-lookup"><span data-stu-id="34899-121">Click Payment fee setup.</span></span>
    * <span data-ttu-id="34899-122">Przejdź do okna Ustawienia opłat i wskaż, kiedy opłata ma być domyślnie stosowana do wybranego arkusza.</span><span class="sxs-lookup"><span data-stu-id="34899-122">Continue to the Payment fee setup to define when the fee should default onto the journal you selected.</span></span>  
11. <span data-ttu-id="34899-123">Wybierz opcję Tabela, Grupa lub Wszystko.</span><span class="sxs-lookup"><span data-stu-id="34899-123">Select either Table, Group or All.</span></span>
    * <span data-ttu-id="34899-124">Opcja Tabela służy do wybierania jednego konta bankowego, opcja Grupa służy do wybierania grupy bankowej, a opcja Wszystko powoduje używanie tej konfiguracji opłat dla wszystkich kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="34899-124">Table is used to select a single bank account, Group is used to select a bank group, and All is to use this fee setup for all bank accounts</span></span>  
12. <span data-ttu-id="34899-125">Zaznacz grupę bankową lub konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="34899-125">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="34899-126">Wyszukiwanie spowoduje wyświetlenie grupy bankowej, jeśli została wybrana opcja Grupa, a kont bankowych, jeśli wybrano opcję Tabela.</span><span class="sxs-lookup"><span data-stu-id="34899-126">The lookup will show bank group if you selected Group, and will show bank accounts if you selected Table.</span></span>  
13. <span data-ttu-id="34899-127">Zaznacz metodę płatności, w której opłata będzie naliczana.</span><span class="sxs-lookup"><span data-stu-id="34899-127">Select the method of payment for when this fee will be assessed.</span></span>
14. <span data-ttu-id="34899-128">Wybierz specyfikację płatności dla wybranej metody płatności.</span><span class="sxs-lookup"><span data-stu-id="34899-128">Select the Payment specification for the selected method of payment.</span></span>
    * <span data-ttu-id="34899-129">Specyfikacja płatności jest używana do płatności za pomocą przelewów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="34899-129">The Payment specification is used with electronic fund transfer methods of payment.</span></span>  
15. <span data-ttu-id="34899-130">Określ, czy opłata będzie procentem, kwotą czy interwałem.</span><span class="sxs-lookup"><span data-stu-id="34899-130">Select whether the fee is a percentage, amount or interval.</span></span>
16. <span data-ttu-id="34899-131">Wprowadź procent lub kwotę opłaty.</span><span class="sxs-lookup"><span data-stu-id="34899-131">Enter the percentage or amount of the fee.</span></span>
    * <span data-ttu-id="34899-132">Jeśli w polu Opłata zaznaczono opcję Wartość procentowa, wprowadź wartość procentową.</span><span class="sxs-lookup"><span data-stu-id="34899-132">If the Fee is a percentage, enter the percentage.</span></span> <span data-ttu-id="34899-133">Jeśli w polu Opłata zaznaczono opcję Kwota, wprowadź kwotę opłaty.</span><span class="sxs-lookup"><span data-stu-id="34899-133">If the Fee is an amount, enter the amount of the fee.</span></span> <span data-ttu-id="34899-134">Jeśli w polu Opłata zaznaczono opcję Interwał, na karcie Interwał zdefiniuj opłaty warstwowe.</span><span class="sxs-lookup"><span data-stu-id="34899-134">If the Fee is an interval, use the Interval tab to defined the tiered fees.</span></span>  
17. <span data-ttu-id="34899-135">W polu Waluta opłaty wybierz walutę, w jakiej będzie naliczana opłata.</span><span class="sxs-lookup"><span data-stu-id="34899-135">In the Fee currency field, select the currency in which the fee will be assessed.</span></span>
    * <span data-ttu-id="34899-136">Ta waluta dotyczy opłaty.</span><span class="sxs-lookup"><span data-stu-id="34899-136">This currency is for the fee.</span></span> <span data-ttu-id="34899-137">Waluta płatności jest używana do zdefiniowania, kiedy reguła opłat powinna być stosowana na podstawie waluty płatności.</span><span class="sxs-lookup"><span data-stu-id="34899-137">The payment currency is used to define when the fee rule should be assessed based on the payment's currency.</span></span> <span data-ttu-id="34899-138">Na przykład bank może nakładać opłatę podczas dokonywania płatności w euro, podczas gdy płatności w innych walutach nie są obciążane.</span><span class="sxs-lookup"><span data-stu-id="34899-138">For example, your bank may charge a fee when a payment is made in EUR, but all other payments aren't assessed a fee.</span></span>  
18. <span data-ttu-id="34899-139">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="34899-139">Click Save.</span></span>


