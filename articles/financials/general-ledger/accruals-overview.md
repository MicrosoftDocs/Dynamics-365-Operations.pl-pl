---
title: "Przegląd naliczeń"
description: "W tym artykule opisano koncepcję naliczeń oraz sposób ich konfigurowania i tworzenia transakcji."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fb120715090638bf7c6c3833822d942cb6dda8c5
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="accruals-overview"></a><span data-ttu-id="2742e-103">Przegląd naliczeń</span><span class="sxs-lookup"><span data-stu-id="2742e-103">Accruals overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2742e-104">W tym artykule opisano koncepcję naliczeń oraz sposób ich konfigurowania i tworzenia transakcji.</span><span class="sxs-lookup"><span data-stu-id="2742e-104">This article describes accruals, and provides information about how to set them up and create transactions.</span></span>

<span data-ttu-id="2742e-105">Naliczenia są używane w księgowości memoriałowej do śledzenia przychodu rozpoznawanego w okresie, w którym został zarobiony, a nie w momencie otrzymania płatności, oraz do śledzenia wydatków (kosztów), które są rozpoznawane, gdy się pojawiają, a nie kiedy zostanie zrealizowana płatność.</span><span class="sxs-lookup"><span data-stu-id="2742e-105">Accruals are used in accrual accounting to track revenue that is recognized in the period that it's earned in, not when payment is received, and to track expenses (costs) that are recognized when they occur, not when payment is made.</span></span>

## <a name="accrual-schemes"></a><span data-ttu-id="2742e-106">Schematy naliczania</span><span class="sxs-lookup"><span data-stu-id="2742e-106">Accrual schemes</span></span>
<span data-ttu-id="2742e-107">Schematy naliczania są używane do ustawiania odroczonych przychodów i kosztów, a ten sam schemat można wykorzystywać i do kosztów i do przychodów.</span><span class="sxs-lookup"><span data-stu-id="2742e-107">Accrual schemes are used to set up the deferred revenue and costs, and the same accrual scheme can be used for both revenue and costs.</span></span> <span data-ttu-id="2742e-108">Naliczenia finansowe umożliwiają ponowne rozdzielenie kosztów lub przychodów wiersza arkusza, tak aby były rozpoznawane w odpowiednich okresach.</span><span class="sxs-lookup"><span data-stu-id="2742e-108">Ledger accruals redistribute the costs or revenue of a journal line so that the costs and revenues are recognized in the appropriate periods.</span></span> <span data-ttu-id="2742e-109">Na stronie **schematu naliczania** można określić konta debetowe i kredytowe, które będą używane po zastosowaniu schematu naliczania.</span><span class="sxs-lookup"><span data-stu-id="2742e-109">On the **Accrual scheme** page, you specify the debit and the credit accounts that will be used when the accrual scheme is applied.</span></span>

-   <span data-ttu-id="2742e-110">**Debetowe** — zdefiniowane konto główne zostanie zastąpione kontem głównym strony debetowej w wierszu załącznika arkusza.</span><span class="sxs-lookup"><span data-stu-id="2742e-110">**Debit** – The main account that you define will replace the debit main account on the journal voucher line.</span></span> <span data-ttu-id="2742e-111">To konto będzie używane także do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.</span><span class="sxs-lookup"><span data-stu-id="2742e-111">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>
-   <span data-ttu-id="2742e-112">**Kredytowe** — zdefiniowane konto główne zostanie zastąpione kontem głównym strony kredytowej w wierszu załącznika arkusza.</span><span class="sxs-lookup"><span data-stu-id="2742e-112">**Credit** – the main account that you define will replace the credit main account on the journal voucher line.</span></span> <span data-ttu-id="2742e-113">To konto będzie używane także do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.</span><span class="sxs-lookup"><span data-stu-id="2742e-113">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>

<span data-ttu-id="2742e-114">Po ustaleniu, które konta należy zastosować, można określić sposób tworzenia numeru załącznika podczas tworzenia transakcji naliczania.</span><span class="sxs-lookup"><span data-stu-id="2742e-114">After you determine which accounts to use, you can specify how the voucher number is created when accrual transactions are created.</span></span> <span data-ttu-id="2742e-115">Można również określić, jak często występują transakcje, ile razy transakcje są tworzone i kiedy są księgowane.</span><span class="sxs-lookup"><span data-stu-id="2742e-115">You can also specify how often the transactions occur, the number of times that the transactions are created, and when the transactions are posted.</span></span> <span data-ttu-id="2742e-116">Po utworzeniu schematu naliczania, można go używać w niektórych arkuszach, stosując funkcję Naliczenia finansowe.</span><span class="sxs-lookup"><span data-stu-id="2742e-116">After the accrual scheme has been created, you can use it in some of the journals by using the Ledger accruals function.</span></span>

## <a name="ledger-accruals"></a><span data-ttu-id="2742e-117">Naliczenia finansowe</span><span class="sxs-lookup"><span data-stu-id="2742e-117">Ledger accruals</span></span>
<span data-ttu-id="2742e-118">Po wprowadzeniu arkusza można kliknąć opcję **Naliczenia finansowe** w menu **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="2742e-118">When you enter a journal, you can click **Ledger accruals** on the **Functions** menu.</span></span> <span data-ttu-id="2742e-119">Następnie, po wybraniu schematu naliczania, zostanie wyświetlona kwota podstawy z arkusza, która zostanie rozłożona w okresie zgodnie ze schematem naliczania.</span><span class="sxs-lookup"><span data-stu-id="2742e-119">Then, when you select the accrual scheme, you will see the base amount from the journal that will be spread over the period, as determined by the accrual scheme.</span></span> <span data-ttu-id="2742e-120">Na przykład jeśli płacisz ubezpieczenie pracownika za cały rok w styczniu, a kwota ubezpieczenia wynosi 12 000, trzeba wykazać ten wydatek w każdym miesiącu.</span><span class="sxs-lookup"><span data-stu-id="2742e-120">For example, if you pay an employee's insurance for the whole year in January, and the amount is 12,000, you must recognize that expense each month.</span></span> <span data-ttu-id="2742e-121">Można wybrać datę początkową.</span><span class="sxs-lookup"><span data-stu-id="2742e-121">You can select the start date.</span></span> <span data-ttu-id="2742e-122">Można również określić, czy naliczana kwota, jest oparta na koncie lub koncie przeciwstawnym.</span><span class="sxs-lookup"><span data-stu-id="2742e-122">You can also specify whether the amount that is accrued is based on the account or the offset account.</span></span> <span data-ttu-id="2742e-123">Po dokonaniu wyboru kliknij przycisk **Transakcje**, aby wyświetlić wszystkie transakcje utworzone na podstawie schematu naliczania.</span><span class="sxs-lookup"><span data-stu-id="2742e-123">After you make your selections, click **Transactions** to view all the transactions that have been created based on the accrual scheme.</span></span> <span data-ttu-id="2742e-124">Na przykład jeśli podzielisz kwotę ubezpieczenia 12 000 na rok, zobaczysz 1000 w każdym miesiącu.</span><span class="sxs-lookup"><span data-stu-id="2742e-124">For example, if you spread the 12,000 in insurance expenses over the year, you will see 1,000 for each month.</span></span> <span data-ttu-id="2742e-125">Po zaksięgowaniu arkusza można przeglądać transakcje za pomocą strony zapytań **Transakcje na załączniku**.</span><span class="sxs-lookup"><span data-stu-id="2742e-125">After you post the journal, you can view the transactions by using the **Voucher transactions** inquiry page.</span></span> <span data-ttu-id="2742e-126">Jeśli nie można zastosować schematu naliczania (na przykład gdy transakcja dotyczy faktury do zamówienia sprzedaży lub faktury do zamówienia zakupu), można zwrócić przedpłaconą kwotę i potrącić kwotę wydatku.</span><span class="sxs-lookup"><span data-stu-id="2742e-126">If an accrual scheme can't be applied (for example, when a sales order invoice or purchase order invoice is involved), you can credit the prepaid amount and debit the expense amount.</span></span> <span data-ttu-id="2742e-127">Następnie można wybrać **przeciwstawne**, jeśli stosujesz schemat naliczania.</span><span class="sxs-lookup"><span data-stu-id="2742e-127">You can then select **Offset** when you apply the accrual scheme.</span></span>


<span data-ttu-id="2742e-128">Aby uzyskać więcej informacji, zobacz [Tworzenie schematów naliczania](tasks/create-accrual-schemes.md) i [Tworzenie transakcji naliczeń finansowych](tasks/create-ledger-accrual-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="2742e-128">For more information, see [Create accrual schemes](tasks/create-accrual-schemes.md) and [Create ledger accrual transactions](tasks/create-ledger-accrual-transactions.md).</span></span>

