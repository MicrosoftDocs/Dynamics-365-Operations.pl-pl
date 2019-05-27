---
title: Księgowanie raportu z wydatków
description: W tym temacie opisano, jak zaksięgować raport z wydatków w księdze głównej.
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1252825848aedcdaf633c04edddddca7dd09d774
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570674"
---
# <a name="post-an-expense-report"></a><span data-ttu-id="e8377-103">Księgowanie raportu z wydatków</span><span class="sxs-lookup"><span data-stu-id="e8377-103">Post an expense report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8377-104">Po zatwierdzeniu i przekazaniu do arkusza finansowego raport z wydatków można zaksięgować w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="e8377-104">After an expense report has been approved and transferred to the general journal, it can be posted to the general ledger.</span></span> <span data-ttu-id="e8377-105">Podczas księgowania raportu z wydatków są identyfikowane wydatki, które kwalifikują się do zwrotu podatku od towarów i usług (VAT).</span><span class="sxs-lookup"><span data-stu-id="e8377-105">When you post an expense report, expenses that are eligible for recovery of value-added tax (VAT) are identified.</span></span> <span data-ttu-id="e8377-106">Zadanie sprawdzenia poprawności i odzyskania zapłaconego podatku VAT jest przypisywane pracownikowi, który odpowiada za weryfikowanie raportu z wydatków.</span><span class="sxs-lookup"><span data-stu-id="e8377-106">The task of verifying and recovering VAT payments is assigned to the employee who is responsible for verifying the expense report.</span></span>

<span data-ttu-id="e8377-107">Jeśli wydatki w raporcie z wydatków obciążają firmę inną niż firma zatrudniająca pracownika, należy zweryfikować obie firmy — wierzyciela i dłużnika.</span><span class="sxs-lookup"><span data-stu-id="e8377-107">If expenses on an expense report are charged to a company other than the company that employs the employee, you must verify the company that those expenses are owed to and the company that the expenses are owed from.</span></span> <span data-ttu-id="e8377-108">Na przykład pracownik, który przesłał raport z wydatków, pracuje dla firmy DAT, ale obciążył wydatkami firmę DIR.</span><span class="sxs-lookup"><span data-stu-id="e8377-108">For example, the employee who submitted an expense report works for the DAT company but charged an expense to the DIR company.</span></span> <span data-ttu-id="e8377-109">W takim przypadku firma DAT jest wierzycielem, a firma DIR dłużnikiem.</span><span class="sxs-lookup"><span data-stu-id="e8377-109">In this case, DAT is the company that the expense is owed to, and DIR is the company that the expense is owed from.</span></span> <span data-ttu-id="e8377-110">Po zweryfikowaniu tych wierszy arkusza można księgować wiersze wydatku w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="e8377-110">After you verify these journal lines, you can post the expense lines to the general ledger.</span></span>

<span data-ttu-id="e8377-111">Aby zaksięgować raport z wydatków, na stronie **Zatwierdzone raporty z wydatków** zaznacz raport z wydatków, a następnie w okienku akcji wybierz opcję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="e8377-111">To post an expense report, on the **Approved expense reports** page, select the expense report, and then, on the Action Pane, select **Post**.</span></span>

<span data-ttu-id="e8377-112">Można też zaksięgować wszystkie raporty z wydatków figurujące na liście w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="e8377-112">You can also post all the expense reports in the list at the same time.</span></span> <span data-ttu-id="e8377-113">Zaznacz wszystkie raporty z wydatków, a następnie wybierz opcję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="e8377-113">Select all the expense reports, and then select **Post**.</span></span>
