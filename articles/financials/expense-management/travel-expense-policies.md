---
title: "Definiowanie zasad dotyczących wydatków"
description: "Można zdefiniować zasady dotyczące wydatków, których pracownicy muszą przestrzegać przy wprowadzaniu i wysyłaniu raportów z wydatków i wniosków wyjazdowych w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: saraschi2
manager: AnnBe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 940d6f8c3d878c2c12806ad04a092856df2acb33
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="expense-policies"></a><span data-ttu-id="6bb0b-103">Zasady dotyczące wydatków</span><span class="sxs-lookup"><span data-stu-id="6bb0b-103">Expense policies</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6bb0b-104">Można zdefiniować zasady, których pracownicy muszą przestrzegać podczas wprowadzania i przesyłania raportów z wydatków i wniosków wyjazdowych.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span> <span data-ttu-id="6bb0b-105">Wdrożenie zasad dotyczących wydatków może się przyczynić do efektywniejszego zarządzania wydatkami.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-105">Implementing expense policies can help you manage expenses effectively.</span></span> 

<span data-ttu-id="6bb0b-106">Można na przykład określić zasadę dotyczącą wydatków na zakwaterowanie w Nowym Jorku, która stanowi, że wydatki nie mogą przekroczyć 250 zł za noc.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span> <span data-ttu-id="6bb0b-107">Jeśli pracownik prześle raport z wydatków lub wniosek wyjazdowy, w którym ta kwota będzie przekroczona, system powiadomi pracownika, że została przekroczona kwota wydatków określona w zasadach.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="6bb0b-108">Podczas definiowania zasady można skonfigurować wiadomość, jaką otrzyma pracownik.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-108">You can configure the message that the worker will receive when you define the policy.</span></span> 

<span data-ttu-id="6bb0b-109">Można zdefiniować trzy typy zasad:</span><span class="sxs-lookup"><span data-stu-id="6bb0b-109">You can define three types of policies:</span></span> 

 - <span data-ttu-id="6bb0b-110">Ostrzeżenie — umożliwia pracownikowi przesłanie raportu z wydatków lub wniosku wyjazdowego, ale wydatek zostanie oznaczony dla wszystkich osób zatwierdzających i</span><span class="sxs-lookup"><span data-stu-id="6bb0b-110">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>  
 <span data-ttu-id="6bb0b-111">do późniejszego raportowania.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-111">for later reporting.</span></span> 
 - <span data-ttu-id="6bb0b-112">Błąd — wymaga, aby pracownik zmienił wydatek na zgodny z zasadami przed przesłaniem raportu z wydatków lub wniosku wyjazdowego.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-112">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span> 
 - <span data-ttu-id="6bb0b-113">Uzasadnienie — wymaga, aby pracownik lub menedżer wprowadził uzasadnienie przekroczenia kwoty w zasadach przed przesłaniem raportu z wydatków lub wniosku wyjazdowego.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-113">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span> 

<span data-ttu-id="6bb0b-114">Można również skonfigurować zakres dat, dla którego obowiązują zasady dotyczące wydatków.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-114">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="6bb0b-115">Na przykład bilety na loty między Warszawą a Kopenhagą mogą być drogie w sezonie turystycznym.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-115">For example, airline fares for flights between Denmark and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="6bb0b-116">Można określić regułę dotyczącą wydatków na bilety lotnicze, która ogranicza koszty przelotu do Kopenhagi do 500 zł, i można określić, że ta reguła obowiązuje między 15 marca a 15 września.</span><span class="sxs-lookup"><span data-stu-id="6bb0b-116">You can define a flight expense rule that restricts the cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and September 15.</span></span> 

