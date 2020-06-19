---
title: Utwórz i zastosuj warunki zatrzymania płatności u dostawcy
description: Ten temat zawiera informacje dotyczące konfigurowania i obsługiwania warunków zatrzymania płatności dostawcy.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410257"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a><span data-ttu-id="5a469-103">Utwórz i zastosuj warunki zatrzymania płatności u dostawcy</span><span class="sxs-lookup"><span data-stu-id="5a469-103">Create and apply vendor payment retention terms</span></span>

[!include [banner](../includes/banner.md)] 

<span data-ttu-id="5a469-104">Ustawienie warunków zatrzymania płatności dla dostawcy dla projektu jest przydatne, gdy organizacja chce zachować część płatności dokonanych dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5a469-104">Setting up vendor payment retention terms for a project is useful when your organization wants to retain part of the payments made to a vendor.</span></span> <span data-ttu-id="5a469-105">Na przykład, jeśli chcesz wstrzymać płatność do dostawcy, dopóki dostarczone produkty nie spełnią oczekiwań użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5a469-105">For example, when you want to hold payment to a vendor until the products delivered meet your expectations.</span></span> <span data-ttu-id="5a469-106">Warunki zatrzymania płatności dostawcy można określić podczas negocjacji umowy z dostawcą.</span><span class="sxs-lookup"><span data-stu-id="5a469-106">Vendor payment retention terms can be specified when you negotiate a vendor contract.</span></span>

## <a name="create-vendor-payment-retention-terms"></a><span data-ttu-id="5a469-107">Utwórz warunki zatrzymania płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="5a469-107">Create vendor payment retention terms</span></span>

<span data-ttu-id="5a469-108">Można wprowadzić procent płatności dla dostawcy, jaki ma być zatrzymany oraz procent poprzednio zatrzymanych kwot, jakie mają być zwolnione.</span><span class="sxs-lookup"><span data-stu-id="5a469-108">You can enter the percentage of vendor payment for retention and the percentage of the previously retained amounts to be released.</span></span> <span data-ttu-id="5a469-109">Stosowne kwoty zostają automatycznie zatrzymane na fakturach dostawcy, dopóki umowa nie zostanie wykonana w stopniu określonym w umowie.</span><span class="sxs-lookup"><span data-stu-id="5a469-109">Amounts are automatically retained on vendor invoices until the contract reaches the specified state of completion.</span></span> <span data-ttu-id="5a469-110">Po skonfigurowaniu warunków przechowywania możesz je zastosować w dowolnym projekcie dla tego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5a469-110">After you set up the retention terms, you can apply them to any project for that vendor.</span></span>

<span data-ttu-id="5a469-111">Należy wykonać następujące kroki, aby skonfigurować i obsługiwać warunki zatrzymania płatności dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5a469-111">Use the following steps to set up and maintain retention terms for vendor payments.</span></span> 

1. <span data-ttu-id="5a469-112">Przejdź do **Zarządzanie projektami i ich księgowanie** > **Zatrzymanie** > **Warunki zatrzymania płatności u dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="5a469-112">Go to **Project management and accounting** > **Retention** > **Vendor payment retention terms**.</span></span>
2. <span data-ttu-id="5a469-113">Wybierz **Nowy**, aby dodać nowy warunek zatrzymania płatności dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5a469-113">Select **New** to add a new vendor retention term.</span></span> <span data-ttu-id="5a469-114">Wartość stanowiąca **Identyfikator reguły** dla nowego warunku zostanie wprowadzona automatycznie.</span><span class="sxs-lookup"><span data-stu-id="5a469-114">The **Rule ID** value for the new term is automatically entered.</span></span> 
3. <span data-ttu-id="5a469-115">Wprowadź krótki opis w polu **Opis**, a następnie na skróconej karcie **Warunki** wybierz opcję **Dodaj wiersz**, aby wprowadzić wartości warunków dla następujących:</span><span class="sxs-lookup"><span data-stu-id="5a469-115">Enter a brief description in the **Description** field, and on the **Terms** FastTab, select **Add line** to enter term values for the following:</span></span>

   - <span data-ttu-id="5a469-116">**Procent dostarczonych jednostek**: Wprowadź procent ukończenia dla warunku.</span><span class="sxs-lookup"><span data-stu-id="5a469-116">**Percentage of units delivered**: Enter a percentage of completion for the term.</span></span> <span data-ttu-id="5a469-117">Stosowne kwoty zostają automatycznie zatrzymane na fakturach od dostawcy do czasu ukończenia etapu projektu odpowiadającego określonej wartości procentowej.</span><span class="sxs-lookup"><span data-stu-id="5a469-117">Amounts are automatically retained on vendor invoices until the project stage of completion is equal to the specified percentage.</span></span> <span data-ttu-id="5a469-118">Na przykład, jeśli wprowadzi się wartość 50.00, kwoty zostaną zatrzymywane dopóty, dopóki projekt nie zostanie ukończony w 50 procentach.</span><span class="sxs-lookup"><span data-stu-id="5a469-118">For example, if you enter 50.00, amounts are retained until the project is 50 percent completed.</span></span>
   - <span data-ttu-id="5a469-119">**Procent do zatrzymania**: Wprowadź procent kwoty z faktury dostawcy, jaki ma być zatrzymany.</span><span class="sxs-lookup"><span data-stu-id="5a469-119">**Percentage to retain**: Enter a percentage of the vendor invoice amount to be retained.</span></span> <span data-ttu-id="5a469-120">Na przykład, jeśli zostanie wprowadzona wartość 10,00, to zatrzymywaniu będzie podlegało 10 procent kwoty na fakturze od dostawcy do momentu, gdy projekt nie osiągnie etapu ukończenia określonego w polu **Procent dostarczonych jednostek**.</span><span class="sxs-lookup"><span data-stu-id="5a469-120">For example, if you enter 10.00, then 10 percent of the amount on a vendor invoice is retained until the project reaches the percentage of completion as set in the **Percentage of units delivered field**.</span></span>
   - <span data-ttu-id="5a469-121">**Procent do zwolnienia**: Wybierz **Dodaj wiersz** i wprowadź procent jakichkolwiek wcześniej zatrzymanych kwot, jaki ma być zwolniony po osiągnięciu określonego poziomu ukończenia projektu.</span><span class="sxs-lookup"><span data-stu-id="5a469-121">**Percentage to release**: Select **Add line** to enter a percentage of any previously retained amounts to be released for the selected level of project completion.</span></span>

> [!NOTE]
> <span data-ttu-id="5a469-122">Jeśli projekt obejmuje więcej niż jeden kamień milowy dla różnych poziomów ukończenie projektu, wprowadź osobny wiersz warunku zatrzymania płatności dla dostawcy dla każdej reguły zatrzymania.</span><span class="sxs-lookup"><span data-stu-id="5a469-122">If you have more than one milestone for different levels of project completion, enter a separate vendor retention term line for each retention rule.</span></span> <span data-ttu-id="5a469-123">Każdy wiersz może określać inną wartość procentową zatrzymania i inny procent do zwolnienia dla każdego wyznaczonego poziomu ukończenia projektu.</span><span class="sxs-lookup"><span data-stu-id="5a469-123">Each line can specify a different retention percentage and a different release percentage for each designated level of project completion.</span></span>

<span data-ttu-id="5a469-124">Po utworzeniu warunków zatrzymania dostawcy dla dostawcy można zastosować warunki do projektu.</span><span class="sxs-lookup"><span data-stu-id="5a469-124">After you create vendor retention terms for a vendor, you can apply the terms to a project.</span></span>

## <a name="apply-vendor-retention-terms-to-a-project"></a><span data-ttu-id="5a469-125">Zastosuj warunki zatrzymania dostawcy do projektu</span><span class="sxs-lookup"><span data-stu-id="5a469-125">Apply vendor retention terms to a project</span></span>

1. <span data-ttu-id="5a469-126">Przejdź do **Zarządzanie projektami i ich księgowanie** > **Projekty** > **Wszystkie projekty**, a następnie otwórz projekt ze strony Lista projektów.</span><span class="sxs-lookup"><span data-stu-id="5a469-126">Go to **Project management and accounting** > **Projects** > **All projects** and open a project from the project list page.</span></span>
2. <span data-ttu-id="5a469-127">Na skróconej karcie **Umowy z dostawcami**, wybierz **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="5a469-127">On the **Vendor agreements** FastTab, select **Add line**.</span></span>
3. <span data-ttu-id="5a469-128">W **polu Kod konta** wybierz jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="5a469-128">In the **Account code field**, select one of the following options:</span></span> 

   - <span data-ttu-id="5a469-129">**Tabela**: Warunki zatrzymania płatności dla dostawcy mają zastosowanie do jednego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5a469-129">**Table**: The vendor retention terms apply to a single vendor.</span></span>
   - <span data-ttu-id="5a469-130">**Grupa**: Warunki zatrzymania płatności dla dostawcy mają zastosowanie do wszystkich dostawców w wybranej grupie dostawców.</span><span class="sxs-lookup"><span data-stu-id="5a469-130">**Group**: The vendor retention terms apply to all vendors in a vendor group.</span></span>
   - <span data-ttu-id="5a469-131">**Wszystko**: Warunki zatrzymania płatności dla dostawcy mają zastosowanie do wszystkich dostawców.</span><span class="sxs-lookup"><span data-stu-id="5a469-131">**All**: The vendor retention terms apply to all vendors.</span></span>

4. <span data-ttu-id="5a469-132">W **polu Dostawca/grupa dostawców** wybierz dostawcę lub grupę dostawców, do których mają zastosowanie warunki zatrzymania płatności.</span><span class="sxs-lookup"><span data-stu-id="5a469-132">In the **Vendor/Vendor group field**, select the vendor or vendor group to which the vendor retention terms apply.</span></span> <span data-ttu-id="5a469-133">W przypadku wybrania opcji **Wszystkie** w poprzednim kroku, to pole będzie niedostępne.</span><span class="sxs-lookup"><span data-stu-id="5a469-133">If you selected **All** in the previous step, this field is unavailable.</span></span>
5. <span data-ttu-id="5a469-134">W polu **Warunki retencji dostawcy** wybierz warunek zatrzymania utworzony w poprzedniej procedurze.</span><span class="sxs-lookup"><span data-stu-id="5a469-134">In the **Vendor retention terms** field, select the retention terms that you created in the previous procedure.</span></span>
6. <span data-ttu-id="5a469-135">Jeśli w projekcie skonfigurowano również warunki płatności po zapłacie (PWP) dla dostawcy, wprowadź procent progowy dla projektu w polu **Wartość procentową progu PWP**.</span><span class="sxs-lookup"><span data-stu-id="5a469-135">If the project also has pay-when-paid (PWP) terms set up for the vendor, enter the threshold percentage for the project in the **PWP threshold percentage** field.</span></span>

<span data-ttu-id="5a469-136">Warunki zatrzymania płatności dla dostawcy widnieją również na zamówieniach zakupu utworzonych dla danego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5a469-136">The vendor retention terms are also displayed on purchase orders that you create for the vendor.</span></span>
