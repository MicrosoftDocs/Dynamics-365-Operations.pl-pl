---
title: "Definiowanie zasad dotyczących wydatków"
description: "Można zdefiniować zasady dotyczące wydatków, których pracownicy muszą przestrzegać przy wprowadzaniu i wysyłaniu raportów z wydatków i wniosków wyjazdowych w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 04eaff110fea021ddee32be650be540894eb703b
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="expense-policies"></a><span data-ttu-id="46a67-103">Zasady dotyczące wydatków</span><span class="sxs-lookup"><span data-stu-id="46a67-103">Expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46a67-104">Można zdefiniować zasady, których pracownicy muszą przestrzegać podczas wprowadzania i przesyłania raportów z wydatków i wniosków wyjazdowych.</span><span class="sxs-lookup"><span data-stu-id="46a67-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="46a67-105">Wdrożenie zasad dotyczących wydatków może się przyczynić do efektywniejszego zarządzania wydatkami.</span><span class="sxs-lookup"><span data-stu-id="46a67-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="46a67-106">Można na przykład określić zasadę dotyczącą wydatków na zakwaterowanie w Nowym Jorku, która stanowi, że wydatki nie mogą przekroczyć 250 zł za noc.</span><span class="sxs-lookup"><span data-stu-id="46a67-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="46a67-107">Jeśli pracownik prześle raport z wydatków lub wniosek wyjazdowy, w którym ta kwota będzie przekroczona, system powiadomi pracownika,</span><span class="sxs-lookup"><span data-stu-id="46a67-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="46a67-108">że została przekroczona kwota wydatków określona w zasadach.</span><span class="sxs-lookup"><span data-stu-id="46a67-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="46a67-109">Podczas definiowania zasady można skonfigurować wiadomość,</span><span class="sxs-lookup"><span data-stu-id="46a67-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="46a67-110">jaką otrzyma pracownik.</span><span class="sxs-lookup"><span data-stu-id="46a67-110">define the policy.</span></span>      
        
<span data-ttu-id="46a67-111">Można zdefiniować trzy typy zasad:</span><span class="sxs-lookup"><span data-stu-id="46a67-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="46a67-112">Ostrzeżenie — umożliwia pracownikowi przesłanie raportu z wydatków lub wniosku wyjazdowego, ale wydatek zostanie oznaczony dla wszystkich osób zatwierdzających i</span><span class="sxs-lookup"><span data-stu-id="46a67-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="46a67-113">do późniejszego raportowania.</span><span class="sxs-lookup"><span data-stu-id="46a67-113">for later reporting.</span></span>        

- <span data-ttu-id="46a67-114">Błąd — wymaga, aby pracownik zmienił wydatek na zgodny z zasadami przed przesłaniem raportu z wydatków lub wniosku wyjazdowego.</span><span class="sxs-lookup"><span data-stu-id="46a67-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
  - <span data-ttu-id="46a67-115">Uzasadnienie — wymaga, aby pracownik lub menedżer wprowadził uzasadnienie przekroczenia kwoty w zasadach przed przesłaniem raportu z wydatków lub wniosku wyjazdowego.</span><span class="sxs-lookup"><span data-stu-id="46a67-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        
 
  <span data-ttu-id="46a67-116">Można również skonfigurować zakres dat, dla którego obowiązują zasady dotyczące wydatków.</span><span class="sxs-lookup"><span data-stu-id="46a67-116">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="46a67-117">Na przykład bilety na loty między Warszawą a Kopenhagą</span><span class="sxs-lookup"><span data-stu-id="46a67-117">For example, airline fares for flights between Denmark</span></span>      
  <span data-ttu-id="46a67-118">mogą być drogie w sezonie turystycznym.</span><span class="sxs-lookup"><span data-stu-id="46a67-118">and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="46a67-119">Można określić regułę dotyczącą wydatków na bilety lotnicze,</span><span class="sxs-lookup"><span data-stu-id="46a67-119">You can define a flight expense rule that restricts the</span></span>      
  <span data-ttu-id="46a67-120">która ogranicza koszty przelotu do Kopenhagi do 500 zł, i można określić, że ta reguła obowiązuje między 15 marca a</span><span class="sxs-lookup"><span data-stu-id="46a67-120">cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and</span></span>      
  <span data-ttu-id="46a67-121">15 września.</span><span class="sxs-lookup"><span data-stu-id="46a67-121">September 15.</span></span>

