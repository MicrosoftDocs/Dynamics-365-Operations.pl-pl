---
title: Definiowanie metody płatności odbiorcy
description: W tym temacie wyjaśniono, jak można utworzyć metodę płatności dla płatności odbiorcy.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b9960c3fdf0d65be19e28dbb41913a310ae7530
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446791"
---
# <a name="establish-customer-method-of-payment"></a><span data-ttu-id="a2349-103">Definiowanie metody płatności odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a2349-103">Establish customer method of payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a2349-104">W tym temacie wyjaśniono, jak można utworzyć metodę płatności dla płatności odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="a2349-104">This topic explains how to create a method of payment for customer payments.</span></span> <span data-ttu-id="a2349-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="a2349-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="a2349-106">W okienku nawigacji przejdź do **Moduły > Rozrachunki z odbiorcami > Ustawienia płatności > Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="a2349-106">In the navigation pane, go to **Modules > Accounts receivable > Payments setup > Methods of payment**.</span></span>
2. <span data-ttu-id="a2349-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a2349-107">Select **New**.</span></span>
3. <span data-ttu-id="a2349-108">W polu **Metody płatności** wprowadź identyfikator metody płatności.</span><span class="sxs-lookup"><span data-stu-id="a2349-108">In the **Method of payment** field, enter an ID for the method of payment.</span></span> <span data-ttu-id="a2349-109">Metoda powiązana z identyfikatorem płatności jest wyświetlana na fakturach i w płatnościach, dlatego musi być na tyle opisowa, aby sugerować, jaki typ płatności jest rejestrowany i dla którego konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="a2349-109">The Method of payment ID is shown on invoices and payments, so make it descriptive enough to understand what type of payment is being recorded, and for what bank account.</span></span>  
4. <span data-ttu-id="a2349-110">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="a2349-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="a2349-111">Wybierz, jaki stan płatności jest wymagany, aby można było księgować płatności.</span><span class="sxs-lookup"><span data-stu-id="a2349-111">Select what payment status is required in order for payments to be posted.</span></span> <span data-ttu-id="a2349-112">Podczas tworzenia płatności od odbiorcy można ją zaksięgować tylko wtedy, gdy stan płatności jest taki sam jak zdefiniowany tutaj.</span><span class="sxs-lookup"><span data-stu-id="a2349-112">When creating a customer payment, it can only be posted when the payment status matches the payment status you define here.</span></span>  
6. <span data-ttu-id="a2349-113">Określ, jak mają być tworzone płatności odbiorców za faktury.</span><span class="sxs-lookup"><span data-stu-id="a2349-113">Select how customers payments should be created for invoices.</span></span> <span data-ttu-id="a2349-114">Ta opcja jest używana tylko przy generowaniu propozycji płatności.</span><span class="sxs-lookup"><span data-stu-id="a2349-114">This option is only used when running a payment proposal.</span></span> <span data-ttu-id="a2349-115">Można używać propozycji płatności dla płatności od odbiorców podczas operacji polecenia zapłaty, aby ściągać środki z rachunków bankowych odbiorców.</span><span class="sxs-lookup"><span data-stu-id="a2349-115">A payment proposal could be used for customer payments when doing direct debits, and pulling the funds from the customers' bank accounts.</span></span>  
7. <span data-ttu-id="a2349-116">Wybierz typ płatności.</span><span class="sxs-lookup"><span data-stu-id="a2349-116">Select the type of payment.</span></span> <span data-ttu-id="a2349-117">Typ płatności może pomóc określić, czy płatność będzie w jakikolwiek sposób weryfikowana.</span><span class="sxs-lookup"><span data-stu-id="a2349-117">The payment type will help determine whether some validation will occur or not on the payment.</span></span>  
8. <span data-ttu-id="a2349-118">Wybierz typ konta, na jakim będą księgowane płatności.</span><span class="sxs-lookup"><span data-stu-id="a2349-118">Select what account type payments will post to.</span></span> <span data-ttu-id="a2349-119">Zazwyczaj w tej opcji wybiera się opcję Bank.</span><span class="sxs-lookup"><span data-stu-id="a2349-119">Typically, Bank would be selected for this option.</span></span>  
9. <span data-ttu-id="a2349-120">Wybierz konto bankowe, na którym ta płatność ma zostać zarejestrowana.</span><span class="sxs-lookup"><span data-stu-id="a2349-120">Select the bank account into which this payment will be recorded.</span></span>
10. <span data-ttu-id="a2349-121">Wprowadź typ transakcji bankowej, aby zidentyfikować typu płatności używany przez bank.</span><span class="sxs-lookup"><span data-stu-id="a2349-121">Enter the Bank transaction type to identify the type of payment used by your bank.</span></span> <span data-ttu-id="a2349-122">Typ transakcji bankowej jest używany w procesie uzgadniania konta bankowego i ułatwia uzgadnianie.</span><span class="sxs-lookup"><span data-stu-id="a2349-122">The bank transaction type is used during the bank reconciliation process, and can make reconciliation easier.</span></span>  
11. <span data-ttu-id="a2349-123">Określ, czy ta płatności będzie tymczasowo księgowana na koncie pomostowym.</span><span class="sxs-lookup"><span data-stu-id="a2349-123">Select whether this payment will temporarily post to a bridging account.</span></span> <span data-ttu-id="a2349-124">Jeśli chcesz wypróbować określony czas obrotu kasowego dla rozliczania płatności przez bank, użyj funkcji transakcji pomostowej.</span><span class="sxs-lookup"><span data-stu-id="a2349-124">If you want to try the float time for a payment to clear the bank, use the Bridging functionality.</span></span> <span data-ttu-id="a2349-125">Płatność tymczasowo zostanie zaksięgowana na koncie księgowym, dopóki bank jej nie rozliczy. Wtedy płatność zostanie przeniesiona na konto bankowe zdefiniowane w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="a2349-125">The payment will temporarily post to a Ledger account until it clears the bank, at which time the payment will move to the bank account you defined here.</span></span>  
12. <span data-ttu-id="a2349-126">Wprowadź konto główne używane dla księgowania pomostowego.</span><span class="sxs-lookup"><span data-stu-id="a2349-126">Enter the main account used for the bridging posting.</span></span> <span data-ttu-id="a2349-127">To jest konto główne, na którym płatność zostanie tymczasowo zaksięgowana, jeśli są używane transakcje pomostowe.</span><span class="sxs-lookup"><span data-stu-id="a2349-127">This is the main account to which the payment will temporarily post if using bridging.</span></span>  
13. <span data-ttu-id="a2349-128">Na karcie **Format pliku** zdefiniuj ustawienia płatności elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="a2349-128">Use the **File format** tab to define setting for electronic payments.</span></span>
14. <span data-ttu-id="a2349-129">Karta **Kontrola płatności** służy do definiowania pól, które są wymagane.</span><span class="sxs-lookup"><span data-stu-id="a2349-129">Use the **Payment control** tab to define fields that are mandatory.</span></span> <span data-ttu-id="a2349-130">Na przykład jeśli wszystkie płatności z tą metodą płatności mają być wpłacane, można zaznaczyć tę opcję na tej karcie.</span><span class="sxs-lookup"><span data-stu-id="a2349-130">For example, if you require all payments with this method of payment to be deposited, you can choose that option on this tab.</span></span>  
15. <span data-ttu-id="a2349-131">Karta **Atrybuty płatności** służy do określania, które atrybuty płatności mają być używane dla tej metody płatności.</span><span class="sxs-lookup"><span data-stu-id="a2349-131">Use the **Payment attributes** tab to define which payment attributes you want to use for this method of payment.</span></span>
16. <span data-ttu-id="a2349-132">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a2349-132">Select **Save**.</span></span>

