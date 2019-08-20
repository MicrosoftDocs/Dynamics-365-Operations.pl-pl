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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d008ef8dd55550431fbb9e329cd7d9428a08831
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/30/2019
ms.locfileid: "1794963"
---
# <a name="post-an-expense-report"></a><span data-ttu-id="8628f-103">Księgowanie raportu z wydatków</span><span class="sxs-lookup"><span data-stu-id="8628f-103">Post an expense report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8628f-104">Po zatwierdzeniu i przekazaniu do arkusza finansowego raport z wydatków można zaksięgować w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="8628f-104">After an expense report has been approved and transferred to the general journal, it can be posted to the general ledger.</span></span> <span data-ttu-id="8628f-105">Podczas księgowania raportu z wydatków są identyfikowane wydatki, które kwalifikują się do zwrotu podatku od towarów i usług (VAT).</span><span class="sxs-lookup"><span data-stu-id="8628f-105">When you post an expense report, expenses that are eligible for recovery of value-added tax (VAT) are identified.</span></span> <span data-ttu-id="8628f-106">Zadanie sprawdzenia poprawności i odzyskania zapłaconego podatku VAT jest przypisywane pracownikowi, który odpowiada za weryfikowanie raportu z wydatków.</span><span class="sxs-lookup"><span data-stu-id="8628f-106">The task of verifying and recovering VAT payments is assigned to the employee who is responsible for verifying the expense report.</span></span>

<span data-ttu-id="8628f-107">Jeśli wydatki w raporcie z wydatków obciążają firmę inną niż firma zatrudniająca pracownika, należy zweryfikować obie firmy — wierzyciela i dłużnika.</span><span class="sxs-lookup"><span data-stu-id="8628f-107">If expenses on an expense report are charged to a company other than the company that employs the employee, you must verify the company that those expenses are owed to and the company that the expenses are owed from.</span></span> <span data-ttu-id="8628f-108">Na przykład pracownik, który przesłał raport z wydatków, pracuje dla firmy DAT, ale obciążył wydatkami firmę DIR.</span><span class="sxs-lookup"><span data-stu-id="8628f-108">For example, the employee who submitted an expense report works for the DAT company but charged an expense to the DIR company.</span></span> <span data-ttu-id="8628f-109">W takim przypadku firma DAT jest wierzycielem, a firma DIR dłużnikiem.</span><span class="sxs-lookup"><span data-stu-id="8628f-109">In this case, DAT is the company that the expense is owed to, and DIR is the company that the expense is owed from.</span></span> <span data-ttu-id="8628f-110">Po zweryfikowaniu tych wierszy arkusza można księgować wiersze wydatku w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="8628f-110">After you verify these journal lines, you can post the expense lines to the general ledger.</span></span>

<span data-ttu-id="8628f-111">Aby zaksięgować raport z wydatków, na stronie **Zatwierdzone raporty z wydatków** zaznacz raport z wydatków, a następnie w okienku akcji wybierz opcję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="8628f-111">To post an expense report, on the **Approved expense reports** page, select the expense report, and then, on the Action Pane, select **Post**.</span></span>

<span data-ttu-id="8628f-112">Można też zaksięgować wszystkie raporty z wydatków figurujące na liście w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="8628f-112">You can also post all the expense reports in the list at the same time.</span></span> <span data-ttu-id="8628f-113">Zaznacz wszystkie raporty z wydatków, a następnie wybierz opcję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="8628f-113">Select all the expense reports, and then select **Post**.</span></span>
