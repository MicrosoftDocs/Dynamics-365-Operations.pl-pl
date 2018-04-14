---
title: "Księgowanie raportu z wydatków"
description: "W tym temacie opisano, jak zaksięgować raport z wydatków w księdze głównej."
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4c0975cf36d87125b8184a7be8a6a8696eef2d3e
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="post-an-expense-report"></a><span data-ttu-id="9b9e4-103">Księgowanie raportu z wydatków</span><span class="sxs-lookup"><span data-stu-id="9b9e4-103">Post an expense report</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="9b9e4-104">Po zatwierdzeniu i przekazaniu do arkusza finansowego raport z wydatków można zaksięgować w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="9b9e4-104">After an expense report has been approved and transferred to the general journal, it can be posted to the general ledger.</span></span> <span data-ttu-id="9b9e4-105">Podczas księgowania raportu z wydatków są identyfikowane wydatki, które kwalifikują się do zwrotu podatku od towarów i usług (VAT).</span><span class="sxs-lookup"><span data-stu-id="9b9e4-105">When you post an expense report, expenses that are eligible for recovery of value-added tax (VAT) are identified.</span></span> <span data-ttu-id="9b9e4-106">Zadanie sprawdzenia poprawności i odzyskania zapłaconego podatku VAT jest przypisywane pracownikowi, który odpowiada za weryfikowanie raportu z wydatków.</span><span class="sxs-lookup"><span data-stu-id="9b9e4-106">The task of verifying and recovering VAT payments is assigned to the employee who is responsible for verifying the expense report.</span></span>

<span data-ttu-id="9b9e4-107">Jeśli wydatki w raporcie z wydatków obciążają firmę inną niż firma zatrudniająca pracownika, należy zweryfikować obie firmy — wierzyciela i dłużnika.</span><span class="sxs-lookup"><span data-stu-id="9b9e4-107">If expenses on an expense report are charged to a company other than the company that employs the employee, you must verify the company that those expenses are owed to and the company that the expenses are owed from.</span></span> <span data-ttu-id="9b9e4-108">Na przykład pracownik, który przesłał raport z wydatków, pracuje dla firmy DAT, ale obciążył wydatkami firmę DIR.</span><span class="sxs-lookup"><span data-stu-id="9b9e4-108">For example, the employee who submitted an expense report works for the DAT company but charged an expense to the DIR company.</span></span> <span data-ttu-id="9b9e4-109">W takim przypadku firma DAT jest wierzycielem, a firma DIR dłużnikiem.</span><span class="sxs-lookup"><span data-stu-id="9b9e4-109">In this case, DAT is the company that the expense is owed to, and DIR is the company that the expense is owed from.</span></span> <span data-ttu-id="9b9e4-110">Po zweryfikowaniu tych wierszy arkusza można księgować wiersze wydatku w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="9b9e4-110">After you verify these journal lines, you can post the expense lines to the general ledger.</span></span>

<span data-ttu-id="9b9e4-111">Aby zaksięgować raport z wydatków, na stronie **Zatwierdzone raporty z wydatków** zaznacz raport z wydatków, a następnie w okienku akcji wybierz opcję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="9b9e4-111">To post an expense report, on the **Approved expense reports** page, select the expense report, and then, on the Action Pane, select **Post**.</span></span>

<span data-ttu-id="9b9e4-112">Można też zaksięgować wszystkie raporty z wydatków figurujące na liście w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="9b9e4-112">You can also post all the expense reports in the list at the same time.</span></span> <span data-ttu-id="9b9e4-113">Zaznacz wszystkie raporty z wydatków, a następnie wybierz opcję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="9b9e4-113">Select all the expense reports, and then select **Post**.</span></span>

