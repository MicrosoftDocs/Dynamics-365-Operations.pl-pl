---
title: Definiowanie opłat od płatności dostawcy
description: Skonfiguruj opłaty od płatności dla dostawcy.
author: abruer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e0871e0889b078c08e4bcbd86bf749bcfe39463
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837278"
---
# <a name="define-vendor-payment-fees"></a><span data-ttu-id="bd289-103">Definiowanie opłat od płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="bd289-103">Define vendor payment fees</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bd289-104">Skonfiguruj opłaty od płatności dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="bd289-104">Set up vendor payment fees.</span></span> <span data-ttu-id="bd289-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="bd289-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="bd289-106">Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Opłata.</span><span class="sxs-lookup"><span data-stu-id="bd289-106">Go to Accounts payable > Payment setup > Payment fee.</span></span>
2. <span data-ttu-id="bd289-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="bd289-107">Click New.</span></span>
3. <span data-ttu-id="bd289-108">W polu Identyfikator opłaty wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bd289-108">In the Fee ID field, type a value.</span></span>
    * <span data-ttu-id="bd289-109">Identyfikator opłaty powinien wskazywać, kiedy opłata będzie używana, np. „Opłata_EFT”.</span><span class="sxs-lookup"><span data-stu-id="bd289-109">The Fee ID should describe when this fee will be used, such as "EFT_Fee".</span></span>  
4. <span data-ttu-id="bd289-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bd289-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="bd289-111">W polu Opis opłaty wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bd289-111">In the Fee description field, type a value.</span></span>
    * <span data-ttu-id="bd289-112">Dodaj opis, który bardziej szczegółowo wyjaśnia, kiedy opłata jest naliczana.</span><span class="sxs-lookup"><span data-stu-id="bd289-112">Add a description to provide more detail on when the fee is assessed.</span></span>  
6. <span data-ttu-id="bd289-113">W polu Opłata zaznacz opcję Dostawca lub Księga.</span><span class="sxs-lookup"><span data-stu-id="bd289-113">In the Charge field, select either Vendor or Ledger.</span></span>
    * <span data-ttu-id="bd289-114">Jeśli opłaty będą zaliczane w koszty firmy, jest używana opcja Księga.</span><span class="sxs-lookup"><span data-stu-id="bd289-114">Ledger is used when the fee will be expensed to your organization.</span></span>  <span data-ttu-id="bd289-115">Opcja Dostawca jest używany, jeśli opłata będzie naliczana dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="bd289-115">Vendor is used when the fee will be assessed to the vendor.</span></span>  
7. <span data-ttu-id="bd289-116">Wprowadź konto główne, na którym opłata będzie naliczane w ciężar kosztów.</span><span class="sxs-lookup"><span data-stu-id="bd289-116">Enter a main account for where the fee will be expensed.</span></span>
    * <span data-ttu-id="bd289-117">Ta opcja jest dostępna tylko wtedy, gdy w polu Opłata wybrano opcję Księga.</span><span class="sxs-lookup"><span data-stu-id="bd289-117">This option is only available when selecting Ledger as the Charge option.</span></span>  
8. <span data-ttu-id="bd289-118">Wybierz arkusz, w którym można używać tej opłaty.</span><span class="sxs-lookup"><span data-stu-id="bd289-118">Select the journal on which this fee can be used.</span></span> 
    * <span data-ttu-id="bd289-119">W przypadku opłaty od płatności dostawcy należy wybrać arkusz „Wypłaty dla dostawców”.</span><span class="sxs-lookup"><span data-stu-id="bd289-119">For a vendor payment fee, you would select the journal 'Vendor disbursement.'</span></span>  
9. <span data-ttu-id="bd289-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="bd289-120">Click Save.</span></span>
10. <span data-ttu-id="bd289-121">Kliknij opcję Ustawienia opłat.</span><span class="sxs-lookup"><span data-stu-id="bd289-121">Click Payment fee setup.</span></span>
    * <span data-ttu-id="bd289-122">Przejdź do okna Ustawienia opłat i wskaż, kiedy opłata ma być domyślnie stosowana do wybranego arkusza.</span><span class="sxs-lookup"><span data-stu-id="bd289-122">Continue to the Payment fee setup to define when the fee should default onto the journal you selected.</span></span>  
11. <span data-ttu-id="bd289-123">Wybierz opcję Tabela, Grupa lub Wszystko.</span><span class="sxs-lookup"><span data-stu-id="bd289-123">Select either Table, Group or All.</span></span>
    * <span data-ttu-id="bd289-124">Opcja Tabela służy do wybierania jednego konta bankowego, opcja Grupa służy do wybierania grupy bankowej, a opcja Wszystko powoduje używanie tej konfiguracji opłat dla wszystkich kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="bd289-124">Table is used to select a single bank account, Group is used to select a bank group, and All is to use this fee setup for all bank accounts</span></span>  
12. <span data-ttu-id="bd289-125">Zaznacz grupę bankową lub konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="bd289-125">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="bd289-126">Wyszukiwanie spowoduje wyświetlenie grupy bankowej, jeśli została wybrana opcja Grupa, a kont bankowych, jeśli wybrano opcję Tabela.</span><span class="sxs-lookup"><span data-stu-id="bd289-126">The lookup will show bank group if you selected Group, and will show bank accounts if you selected Table.</span></span>  
13. <span data-ttu-id="bd289-127">Zaznacz metodę płatności, w której opłata będzie naliczana.</span><span class="sxs-lookup"><span data-stu-id="bd289-127">Select the method of payment for when this fee will be assessed.</span></span>
14. <span data-ttu-id="bd289-128">Wybierz specyfikację płatności dla wybranej metody płatności.</span><span class="sxs-lookup"><span data-stu-id="bd289-128">Select the Payment specification for the selected method of payment.</span></span>
    * <span data-ttu-id="bd289-129">Specyfikacja płatności jest używana do płatności za pomocą przelewów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="bd289-129">The Payment specification is used with electronic fund transfer methods of payment.</span></span>  
15. <span data-ttu-id="bd289-130">Określ, czy opłata będzie procentem, kwotą czy interwałem.</span><span class="sxs-lookup"><span data-stu-id="bd289-130">Select whether the fee is a percentage, amount or interval.</span></span>
16. <span data-ttu-id="bd289-131">Wprowadź procent lub kwotę opłaty.</span><span class="sxs-lookup"><span data-stu-id="bd289-131">Enter the percentage or amount of the fee.</span></span>
    * <span data-ttu-id="bd289-132">Jeśli w polu Opłata zaznaczono opcję Wartość procentowa, wprowadź wartość procentową.</span><span class="sxs-lookup"><span data-stu-id="bd289-132">If the Fee is a percentage, enter the percentage.</span></span> <span data-ttu-id="bd289-133">Jeśli w polu Opłata zaznaczono opcję Kwota, wprowadź kwotę opłaty.</span><span class="sxs-lookup"><span data-stu-id="bd289-133">If the Fee is an amount, enter the amount of the fee.</span></span> <span data-ttu-id="bd289-134">Jeśli w polu Opłata zaznaczono opcję Interwał, na karcie Interwał zdefiniuj opłaty warstwowe.</span><span class="sxs-lookup"><span data-stu-id="bd289-134">If the Fee is an interval, use the Interval tab to defined the tiered fees.</span></span>  
17. <span data-ttu-id="bd289-135">W polu Waluta opłaty wybierz walutę, w jakiej będzie naliczana opłata.</span><span class="sxs-lookup"><span data-stu-id="bd289-135">In the Fee currency field, select the currency in which the fee will be assessed.</span></span>
    * <span data-ttu-id="bd289-136">Ta waluta dotyczy opłaty.</span><span class="sxs-lookup"><span data-stu-id="bd289-136">This currency is for the fee.</span></span> <span data-ttu-id="bd289-137">Waluta płatności jest używana do zdefiniowania, kiedy reguła opłat powinna być stosowana na podstawie waluty płatności.</span><span class="sxs-lookup"><span data-stu-id="bd289-137">The payment currency is used to define when the fee rule should be assessed based on the payment's currency.</span></span> <span data-ttu-id="bd289-138">Na przykład bank może nakładać opłatę podczas dokonywania płatności w euro, podczas gdy płatności w innych walutach nie są obciążane.</span><span class="sxs-lookup"><span data-stu-id="bd289-138">For example, your bank may charge a fee when a payment is made in EUR, but all other payments aren't assessed a fee.</span></span>  
18. <span data-ttu-id="bd289-139">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="bd289-139">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]