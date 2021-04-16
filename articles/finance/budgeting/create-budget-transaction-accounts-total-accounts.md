---
title: Tworzenie budżetu z kont transakcji i kont sum
description: Ten artykuł zawiera omówienie procesu tworzenia budżetów na podstawie kont sum. Ponadto wyjaśnia, jak włączyć kontrolę budżetu dla kont sum, jeśli kontrola budżetu jest wymagana.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e296118b3b806a5267e29c2b2d4d859c1aea1977
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827393"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a><span data-ttu-id="e89e0-104">Tworzenie budżetu z kont transakcji i kont sum</span><span class="sxs-lookup"><span data-stu-id="e89e0-104">Create a budget from transaction accounts and total accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e89e0-105">Ten artykuł zawiera omówienie procesu tworzenia budżetów na podstawie kont sum.</span><span class="sxs-lookup"><span data-stu-id="e89e0-105">This article provides an overview of the process for creating budgets based on total accounts.</span></span> <span data-ttu-id="e89e0-106">Ponadto wyjaśnia, jak włączyć kontrolę budżetu dla kont sum, jeśli kontrola budżetu jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="e89e0-106">It also explains how to turn on budget control for total accounts, if budget control is required.</span></span>

<span data-ttu-id="e89e0-107">Dokumenty wpisowe zarówno planu budżetu, jak i rejestru budżetu umożliwiają tworzenie budżetu na kontach głównych z typem **Suma**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-107">Both budget plan and budget register entry documents allow for budgeting on main accounts that have a main account type of **Total**.</span></span> <span data-ttu-id="e89e0-108">Wartości rzeczywiste mogą być księgowane tylko na kontach głównych transakcji.</span><span class="sxs-lookup"><span data-stu-id="e89e0-108">Actuals can be posted only to transactional main accounts.</span></span> 

<span data-ttu-id="e89e0-109">Do obsługi okresowego procesu **Generowanie planu budżetu na podstawie księgi głównej** na karcie **Źródło** możesz określić typ konta głównego **Suma** jako kryterium.</span><span class="sxs-lookup"><span data-stu-id="e89e0-109">For the **Generate budget plan from General ledger** periodic process, on the **Source** tab, you can specify the **Total** main account type as a criterion.</span></span> <span data-ttu-id="e89e0-110">W tym przypadku każde konto główne będzie objęte docelowym planem budżetu, a kwota będzie równa łącznej kwocie w zakresie dat dla wybranych kont głównych.</span><span class="sxs-lookup"><span data-stu-id="e89e0-110">In this case, each total main account will be included in the target budget plan, and the amount will equal the total amount of the range of selected main accounts.</span></span> 

<span data-ttu-id="e89e0-111">Można uaktywnić kontrolę budżetu dla kont głównych typu **Suma**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-111">You can activate budget control for main accounts of the **Total** type.</span></span> <span data-ttu-id="e89e0-112">Ta funkcja jest obsługiwana za pomocą grup budżetu.</span><span class="sxs-lookup"><span data-stu-id="e89e0-112">This functionality is supported through the use of budget groups.</span></span> <span data-ttu-id="e89e0-113">Dla każdego konta głównego sum budżet, który ma być kontrolowany w grupie budżetu, musi być utworzony na stronie **Konfiguracja kontroli budżetu**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-113">For each total main account, the budget that should be controlled for a budget group must be created on the \*\*Budget control configuration \*\*page.</span></span> <span data-ttu-id="e89e0-114">Zdefiniowane kryteria muszą obejmować konto główne sum oraz zakres kont.</span><span class="sxs-lookup"><span data-stu-id="e89e0-114">The criteria that you specify must include the total main account and the range of accounts.</span></span> <span data-ttu-id="e89e0-115">Aby przyspieszyć proces tworzenia grup budżetu, użytkownik może skorzystać z jednostki danych grup Kontrola budżetu.</span><span class="sxs-lookup"><span data-stu-id="e89e0-115">To speed up the process of creating budget groups, you can take advantage of the Budget control groups data entity.</span></span> 

<span data-ttu-id="e89e0-116">Jeśli budżet używany jest przy tworzeniu raportów, na przykład w sprawozdaniu finansowym, suma budżetów dla konta sum zawiera następujące kwoty:</span><span class="sxs-lookup"><span data-stu-id="e89e0-116">When a budget is used in reporting, such as on a financial statement, the budget sum for the total account consists of the following amounts:</span></span>

-   <span data-ttu-id="e89e0-117">Budżety utworzone z każdego konta księgowego transakcji w interwale konta sum.</span><span class="sxs-lookup"><span data-stu-id="e89e0-117">The budgets that are created from each transaction ledger account in the interval of the total account.</span></span>
-   <span data-ttu-id="e89e0-118">Kwota budżetu wprowadzona bezpośrednio na koncie sum.</span><span class="sxs-lookup"><span data-stu-id="e89e0-118">The budget amount that is entered directly on the total account.</span></span>

<span data-ttu-id="e89e0-119">Dlatego możliwe jest tworzenie oddzielnych budżetów dla najważniejszych kont transakcji w interwale konta sum i dodawanie pozostałych kwot budżetów do konta sum.</span><span class="sxs-lookup"><span data-stu-id="e89e0-119">Therefore, you can create separate budgets for the most significant transaction accounts in the interval of the total account, and then add the available budget amount to the total account.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]