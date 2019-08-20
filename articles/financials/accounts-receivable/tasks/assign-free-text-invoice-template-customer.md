---
title: Przypisanie szablonu faktury niezależnej do odbiorcy
description: To zadanie przedstawia sposób przypisywania szablonu faktury niezależnej do odbiorcy.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 53bff33083a78c0bb1c7d243fe9965fb264d209e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843056"
---
# <a name="assign-free-text-invoice-template-to-a-customer"></a><span data-ttu-id="d2032-103">Przypisanie szablonu faktury niezależnej do odbiorcy</span><span class="sxs-lookup"><span data-stu-id="d2032-103">Assign free text invoice template to a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2032-104">To zadanie przedstawia sposób przypisywania szablonu faktury niezależnej do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d2032-104">This task demonstrates how to assign a free text invoice template to a customer.</span></span> <span data-ttu-id="d2032-105">To zadanie wykorzystuje firmę demonstracyjną USMF i jest przeznaczone dla użytkownika, który odpowiada za zarządzanie i przetwarzanie faktur dla odbiorców.</span><span class="sxs-lookup"><span data-stu-id="d2032-105">This task uses the USMF demo company and is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="d2032-106">Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d2032-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="d2032-107">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d2032-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d2032-108">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="d2032-108">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="d2032-109">Kliknij opcję Faktury cykliczne.</span><span class="sxs-lookup"><span data-stu-id="d2032-109">Click Recurring invoices.</span></span>
    * <span data-ttu-id="d2032-110">Ta strona służy do przypisania szablonów faktur niezależnych do odbiorców oraz określania, jak często faktury będą wysyłane do odbiorców.</span><span class="sxs-lookup"><span data-stu-id="d2032-110">Use this page to assign free text invoice templates to customers and specify how frequently invoices will be sent to the customer.</span></span>  
5. <span data-ttu-id="d2032-111">Kliknij przycisk Nowy, aby przypisać nowy szablon do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d2032-111">Click New to assign a new template to the customer.</span></span>
6. <span data-ttu-id="d2032-112">Zaznacz szablon faktury niezależnej, który chcesz przypisać odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d2032-112">Select the free text invoice template you want to assign to the customer.</span></span>
7. <span data-ttu-id="d2032-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d2032-113">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="d2032-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d2032-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="d2032-115">Wprowadź datę, kiedy zostanie wygenerowana pierwsza faktura.</span><span class="sxs-lookup"><span data-stu-id="d2032-115">Enter the date when the first invoice will be generated.</span></span>
    * <span data-ttu-id="d2032-116">Wprowadź datę zakończenia cyklu.</span><span class="sxs-lookup"><span data-stu-id="d2032-116">Enter a recurring end date.</span></span>  
    * <span data-ttu-id="d2032-117">Wybierz jedną z następujących opcje: Brak daty zakończenia — Faktury będą generowane bezterminowo do czasu usunięcia szablonu z konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d2032-117">Select one of the following: No end date – Invoices will be generated indefinitely until the template is removed from the customer account.</span></span>  <span data-ttu-id="d2032-118">Data zakończenia fakturowania — Zaznacz tę opcję i wprowadź ostatni dzień, w którym fakturę można wygenerować.</span><span class="sxs-lookup"><span data-stu-id="d2032-118">Billing end date – Select this option and enter the last date that the invoice can be generated.</span></span>  
    * <span data-ttu-id="d2032-119">Maksymalna kwota skumulowana, po której generowanie faktur się zatrzyma.</span><span class="sxs-lookup"><span data-stu-id="d2032-119">Maximum cumulative amount after which invoice generation will stop.</span></span>  
    * <span data-ttu-id="d2032-120">Wprowadź maksymalną kwotę skumulowaną, jaką można osiągnąć za pomocą wybranego szablonu.</span><span class="sxs-lookup"><span data-stu-id="d2032-120">Enter the maximum cumulative amount that can be reached using the selected template.</span></span> <span data-ttu-id="d2032-121">Na przykład wprowadzenie wartości 1 000,00 i generowanie faktur miesięcznych dla każdej kwoty 100,00 spowoduje, że faktury przestaną być generowane po wygenerowaniu dziesiątej faktury.</span><span class="sxs-lookup"><span data-stu-id="d2032-121">For example, if you enter 1,000.00 and generate monthly invoices for 100.00 each, invoices will stop generating after the tenth invoice is generated.</span></span>  
    * <span data-ttu-id="d2032-122">Umożliwia generowanie faktur cyklicznych przy użyciu domyślnych wartości z szablonu faktury niezależnej lub konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d2032-122">Generate recurring invoices by using the default values from either free text invoice template or the customer account.</span></span>  
    * <span data-ttu-id="d2032-123">Umożliwia określenie, czy ma być używany szablon faktury niezależnej czy konto odbiorcy do określania wartości domyślnych języka, profilu księgowania, grupy podatków, grupy podatków towaru, kodu listy, kraju/regionu dostawy, waluty, warunków płatności, metody płatności, specyfikacji płatności, harmonogramu płatności, rabatu gotówkowego, wymiarów finansowych oraz przekazu GIRO podczas tworzenia faktur.</span><span class="sxs-lookup"><span data-stu-id="d2032-123">Select whether to use the free text invoice template or the customer account to determine the default values for the language, posting profile, sales tax group, item sales tax group, list code, country/region for delivery, currency, terms of payment, method of payment, payment specification, payment schedule, cash discount, financial dimensions, and giro money transfer slip when invoices are created.</span></span>  
10. <span data-ttu-id="d2032-124">Wybierz wzorzec cyklu.</span><span class="sxs-lookup"><span data-stu-id="d2032-124">Select the recurrence pattern.</span></span>
    * <span data-ttu-id="d2032-125">Dziennie — Wybierz tę opcję i podaj liczbę dni w polu Na.</span><span class="sxs-lookup"><span data-stu-id="d2032-125">Daily – Select this option and enter the number of days in the Per field.</span></span> <span data-ttu-id="d2032-126">Na przykład, jeśli zostanie wprowadzona wartość 15, co 15 dni będzie generowana faktura dla tego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d2032-126">For example, if you enter 15, an invoice will be generated every 15 days for this customer.</span></span>  <span data-ttu-id="d2032-127">Tygodniowo — Wybierz tę opcję i podaj liczbę tygodni w polu Na.</span><span class="sxs-lookup"><span data-stu-id="d2032-127">Weekly - Select this option and enter the number of weeks in the Per field.</span></span> <span data-ttu-id="d2032-128">Na przykład, jeśli zostanie wprowadzona wartość 2, co 2 tygodnie będzie generowana faktura dla tego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d2032-128">For example, if you enter 2, an invoice will be generated every two weeks for this customer.</span></span>  <span data-ttu-id="d2032-129">Miesięcznie — Wybierz tę opcję i podaj liczbę miesięcy w polu Na.</span><span class="sxs-lookup"><span data-stu-id="d2032-129">Monthly - Select this option and enter the number of months in the Per field.</span></span> <span data-ttu-id="d2032-130">Na przykład, jeśli zostanie wprowadzona wartość 6, co 6 miesięcy będzie generowana faktura dla tego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d2032-130">For example, if you enter 6, an invoice will be generated every six months for this customer.</span></span>  <span data-ttu-id="d2032-131">Rocznie — Wybierz tę opcję i podaj liczbę lat w polu Na.</span><span class="sxs-lookup"><span data-stu-id="d2032-131">Yearly – Select this option and enter the number of years in the Per field.</span></span> <span data-ttu-id="d2032-132">Na przykład, jeśli zostanie wprowadzona wartość 2, co 2 lata będzie generowana faktura dla tego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d2032-132">For example, if you enter 2, an invoice will be generated every two years for this customer.</span></span>  
11. <span data-ttu-id="d2032-133">W polu Na wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="d2032-133">In the Per field, enter a number.</span></span>

