---
title: Konfigurowanie odbiorców i kont bankowych odbiorców dla poleceń zapłaty ISO20022
description: To zadanie prowadzi Cię przez konfigurowanie konta bankowego odbiorcy i zgody dla odbiorcy na polecenia zapłaty, co jest wymagane do generowania pliku płatności od odbiorcy, np. poleceniem zapłaty ISO20022.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, CustDirectDebitMandate, BankAccountTableLookUp,  LogisticsAddressCityLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 82a8a3eff1f882d0d9b3d4943e352a8f3d1a6ae4
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185734"
---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="2191b-103">Konfigurowanie odbiorców i kont bankowych odbiorców dla poleceń zapłaty ISO20022</span><span class="sxs-lookup"><span data-stu-id="2191b-103">Set up customers and customer bank accounts for ISO20022 direct debits</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2191b-104">To zadanie prowadzi Cię przez konfigurowanie konta bankowego odbiorcy i zgody dla odbiorcy na polecenia zapłaty, co jest wymagane do generowania pliku płatności od odbiorcy, np. poleceniem zapłaty ISO20022.</span><span class="sxs-lookup"><span data-stu-id="2191b-104">This task walks you through setting up a customer bank account and a customer direct debit mandate which are required to generate the customer payment file like ISO20022 direct debit.</span></span> <span data-ttu-id="2191b-105">W zależności od skonfigurowanych formatów płatności od odbiorców mogą być wymagane dodatkowe informacje o odbiorcach lub kontach bankowych odbiorców, nieuwzględnione w tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="2191b-105">Depending on the customer payment formats tha are set up, additional information, not covered in this procedure, might be required for a customer or a customer bank account.</span></span> 

<span data-ttu-id="2191b-106">Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="2191b-106">This task was created using the demo data company DEMF with a legal entity primary address in Germany.</span></span>



<span data-ttu-id="2191b-107">Jest to czwarta z pięciu procedur, które razem przedstawiają proces płatności od odbiorców przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="2191b-107">This is the fourth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-a-customer-bank-account"></a><span data-ttu-id="2191b-108">Konfigurowanie konta bankowego odbiorcy</span><span class="sxs-lookup"><span data-stu-id="2191b-108">Set up a customer bank account</span></span>
1. <span data-ttu-id="2191b-109">Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2191b-109">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="2191b-110">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="2191b-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="2191b-111">Na przykład wyfiltruj według pola Konto z wartością „DE-010”.</span><span class="sxs-lookup"><span data-stu-id="2191b-111">For example, filter on the Account field with a value of 'DE-010 '.</span></span>
3. <span data-ttu-id="2191b-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2191b-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="2191b-113">W okienku akcji kliknij pozycję Odbiorca.</span><span class="sxs-lookup"><span data-stu-id="2191b-113">On the Action Pane, click Customer.</span></span>
5. <span data-ttu-id="2191b-114">Kliknij przycisk konta bankowe</span><span class="sxs-lookup"><span data-stu-id="2191b-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="2191b-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2191b-115">Click New.</span></span>
7. <span data-ttu-id="2191b-116">W polu Konto bankowe wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2191b-116">In the Bank account field, type a value.</span></span>
8. <span data-ttu-id="2191b-117">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2191b-117">In the Name field, type a value.</span></span>
    * <span data-ttu-id="2191b-118">Na przykład wpisz „Bank dla euro”.</span><span class="sxs-lookup"><span data-stu-id="2191b-118">For example, enter 'EUR bank'.</span></span>  
9. <span data-ttu-id="2191b-119">W polu Grupy bankowe wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2191b-119">In the Bank groups field, enter or select a value.</span></span>
10. <span data-ttu-id="2191b-120">W polu IBAN wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2191b-120">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="2191b-121">Na przykład wpisz „DE36200400000628808808”.</span><span class="sxs-lookup"><span data-stu-id="2191b-121">For example, enter 'DE36200400000628808808'.</span></span>  
11. <span data-ttu-id="2191b-122">W polu Kod SWIFT wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2191b-122">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="2191b-123">Na przykład wpisz „COBADEFFXXX”.</span><span class="sxs-lookup"><span data-stu-id="2191b-123">For example: Enter 'COBADEFFXXX'.</span></span>  <span data-ttu-id="2191b-124">Należy zauważyć, że kod SWIFT\BIC nie jest obowiązkowy dla wielu formatów płatności, jednak zaleca się zarejestrowanie go dla konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="2191b-124">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
12. <span data-ttu-id="2191b-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2191b-125">Click Save.</span></span>
13. <span data-ttu-id="2191b-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2191b-126">Close the page.</span></span>
14. <span data-ttu-id="2191b-127">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="2191b-127">Click Edit.</span></span>
15. <span data-ttu-id="2191b-128">Rozwiń sekcję Ustawienia domyślne płatności.</span><span class="sxs-lookup"><span data-stu-id="2191b-128">Expand the Payment defaults section.</span></span>
16. <span data-ttu-id="2191b-129">W polu Konto bankowe wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2191b-129">In the Bank account field, enter or select a value.</span></span>

## <a name="add-a-direct-debit-mandate"></a><span data-ttu-id="2191b-130">Dodawanie zgody na polecenie zapłaty</span><span class="sxs-lookup"><span data-stu-id="2191b-130">Add a direct debit mandate</span></span>
1. <span data-ttu-id="2191b-131">Rozwiń sekcję Pozwolenia na polecenie zapłaty.</span><span class="sxs-lookup"><span data-stu-id="2191b-131">Expand the Direct debit mandates section.</span></span>
2. <span data-ttu-id="2191b-132">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="2191b-132">Click Add.</span></span>
3. <span data-ttu-id="2191b-133">W polu Konto bankowe wierzyciela wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2191b-133">In the Creditor bank account field, enter or select a value.</span></span>
    * <span data-ttu-id="2191b-134">Na przykład zaznacz pozycję DEMF OPER.</span><span class="sxs-lookup"><span data-stu-id="2191b-134">For example, select DEMF OPER.</span></span>  
4. <span data-ttu-id="2191b-135">W polu Data podpisania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="2191b-135">In the Signature date field, enter a date.</span></span>
5. <span data-ttu-id="2191b-136">Kliknij przycisk Tak, aby potwierdzić aktualizację daty.</span><span class="sxs-lookup"><span data-stu-id="2191b-136">Click Yes to confirm the date update.</span></span>
6. <span data-ttu-id="2191b-137">W polu Miejsce podpisania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2191b-137">In the Signature location field, enter or select a value.</span></span>
7. <span data-ttu-id="2191b-138">W polu Przewidywana liczba płatności wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="2191b-138">In the Expected number of payments field, enter a number.</span></span>
8. <span data-ttu-id="2191b-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2191b-139">Click OK.</span></span>
9. <span data-ttu-id="2191b-140">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2191b-140">Click Save.</span></span>

