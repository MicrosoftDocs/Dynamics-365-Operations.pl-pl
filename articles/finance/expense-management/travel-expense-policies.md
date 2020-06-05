---
title: Definiowanie zasad dotyczących wydatków
description: Można zdefiniować zasady dotyczące wydatków, których pracownicy muszą przestrzegać przy wprowadzaniu i wysyłaniu raportów z wydatków i wniosków wyjazdowych w Microsoft Dynamics 365 Finance.
author: suvaidya
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22504e0e26c025d117f29dee3b59b41d508e7724
ms.sourcegitcommit: 4f90b9ddedf312e75a714e0ec7f7ee5fd43cac6a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/21/2020
ms.locfileid: "3389722"
---
# <a name="define-expense-policies"></a><span data-ttu-id="bea0a-103">Definiowanie zasad dotyczących wydatków</span><span class="sxs-lookup"><span data-stu-id="bea0a-103">Define expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bea0a-104">Można zdefiniować zasady, których pracownicy muszą przestrzegać podczas wprowadzania i przesyłania raportów z wydatków i wniosków wyjazdowych.</span><span class="sxs-lookup"><span data-stu-id="bea0a-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="bea0a-105">Wdrożenie zasad dotyczących wydatków może się przyczynić do efektywniejszego zarządzania wydatkami.</span><span class="sxs-lookup"><span data-stu-id="bea0a-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="bea0a-106">Można na przykład określić zasadę dotyczącą wydatków na zakwaterowanie w Nowym Jorku, która stanowi, że wydatki nie mogą przekroczyć 250 zł za noc.</span><span class="sxs-lookup"><span data-stu-id="bea0a-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="bea0a-107">Jeśli pracownik prześle raport z wydatków lub wniosek wyjazdowy, w którym ta kwota będzie przekroczona, system powiadomi pracownika,</span><span class="sxs-lookup"><span data-stu-id="bea0a-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="bea0a-108">że została przekroczona kwota wydatków określona w zasadach.</span><span class="sxs-lookup"><span data-stu-id="bea0a-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="bea0a-109">Podczas definiowania zasady można skonfigurować wiadomość,</span><span class="sxs-lookup"><span data-stu-id="bea0a-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="bea0a-110">jaką otrzyma pracownik.</span><span class="sxs-lookup"><span data-stu-id="bea0a-110">define the policy.</span></span>      
        
<span data-ttu-id="bea0a-111">Można zdefiniować trzy typy zasad:</span><span class="sxs-lookup"><span data-stu-id="bea0a-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="bea0a-112">Ostrzeżenie — umożliwia pracownikowi przesłanie raportu z wydatków lub wniosku wyjazdowego, ale wydatek zostanie oznaczony dla wszystkich osób zatwierdzających i</span><span class="sxs-lookup"><span data-stu-id="bea0a-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="bea0a-113">do późniejszego raportowania.</span><span class="sxs-lookup"><span data-stu-id="bea0a-113">for later reporting.</span></span>        

- <span data-ttu-id="bea0a-114">Błąd — wymaga, aby pracownik zmienił wydatek na zgodny z zasadami przed przesłaniem raportu z wydatków lub wniosku wyjazdowego.</span><span class="sxs-lookup"><span data-stu-id="bea0a-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
 - <span data-ttu-id="bea0a-115">Uzasadnienie — wymaga, aby pracownik lub menedżer wprowadził uzasadnienie przekroczenia kwoty w zasadach przed przesłaniem raportu z wydatków lub wniosku wyjazdowego.</span><span class="sxs-lookup"><span data-stu-id="bea0a-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        

## <a name="policy-tips"></a><span data-ttu-id="bea0a-116">Porady dotyczące zasad</span><span class="sxs-lookup"><span data-stu-id="bea0a-116">Policy tips</span></span>
<span data-ttu-id="bea0a-117">Oto kilka sugestii ułatwiających tworzenie nowych zasad zarządzania wydatkami.</span><span class="sxs-lookup"><span data-stu-id="bea0a-117">Here are a few suggestions that can assist you when creating new policies for expense management.</span></span> 
* <span data-ttu-id="bea0a-118">Zasady obowiązują od dnia ich wprowadzenia; nie zaczną obowiązywać, jeśli zasada zostanie utworzona z datą późniejszą niż data wystąpienia wydatku.</span><span class="sxs-lookup"><span data-stu-id="bea0a-118">Policies are date effective and won't take effect if the policy is created with a date after the date that the expense occurred.</span></span> <span data-ttu-id="bea0a-119">Jeśli na przykład nowe zasady są tworzone dzisiaj w celu wymuszenia maksymalnego kosztu posiłku wynoszącego $50, wówczas wszelkie istniejące wydatki wprowadzone z datą wczorajszą nie będą sprawdzane w odniesieniu do tej zasady.</span><span class="sxs-lookup"><span data-stu-id="bea0a-119">For example, if you are creating a new policy today to enforce a maximum meal expense of $50, then any existing expenses entered as of yesterday won't be checked against this policy.</span></span>
* <span data-ttu-id="bea0a-120">Podczas tworzenia zasady dla kategorii wydatków, która może być wyszczególniona, należy rozważyć dodanie warunku dla typu wiersza wydatku.</span><span class="sxs-lookup"><span data-stu-id="bea0a-120">When creating a policy for an expense category that can be itemized, consider adding a condition for expense line type.</span></span> <span data-ttu-id="bea0a-121">Niektóre zasady, takie jak wymaganie przyjęcia paragonu, mogą nie mieć sensu w przypadku wierszy wyszczególnionych i powinny być stosowane tylko do wierszy nagłówka lub wierszy bez pozycji.</span><span class="sxs-lookup"><span data-stu-id="bea0a-121">Some policies such as requiring a receipt may not make sense for itemized lines and should only be applied to the header line or a non-itemized line.</span></span> 
* <span data-ttu-id="bea0a-122">Zasady zarządzania wydatkami są domyślnie wypróbowywane w odniesieniu do jednostki źródłowej.</span><span class="sxs-lookup"><span data-stu-id="bea0a-122">Expense management policies are evaluated against the source entity by default.</span></span> <span data-ttu-id="bea0a-123">W scenariuszach międzyfirmowych można określić, że zasady mają być w zamian wypróbowywane względem jednostki docelowej (jednostka pożyczająca).</span><span class="sxs-lookup"><span data-stu-id="bea0a-123">For intercompany scenarios, you can set the policy to be evaluated against the destination entity (borrowing entity) instead.</span></span> <span data-ttu-id="bea0a-124">Aby uruchomić zasady w odniesieniu do jednostki docelowej, włącz funkcję „wypróbowywania zasad wydatków w odniesieniu do firmy pożyczającej” w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="bea0a-124">To run the policies against the destination entity, turn on the "Evaluate Expense policy against borrowing legal entity" feature in the **Feature Management** workspace.</span></span>

## <a name="when-to-evaluate-policies"></a><span data-ttu-id="bea0a-125">Kiedy oceniać zasady</span><span class="sxs-lookup"><span data-stu-id="bea0a-125">When to evaluate policies</span></span>

<span data-ttu-id="bea0a-126">W parametrach zarządzania wydatkami istnieje możliwość oceny zasad zarządzania wydatkami podczas zapisywania wiersza lub przesyłania raportu z wydatków.</span><span class="sxs-lookup"><span data-stu-id="bea0a-126">In expense management parameters, there is an option to either evaluate expense management policies when a line is saved or when an expense report is submitted.</span></span> <span data-ttu-id="bea0a-127">Jeśli zostanie wybrana opcja oceny, kiedy wiersz zostanie zapisany, użytkownicy będą wcześniej wiedzieli, co muszą zrobić, aby od razu wypełnić cały raporty z wydatków.</span><span class="sxs-lookup"><span data-stu-id="bea0a-127">If you choose to evaluate when a line is saved this ensures that users have earlier visibility into what they need to do to complete their expense report all at once.</span></span> <span data-ttu-id="bea0a-128">W przeciwnym wypadku można opóźnić ocenianie zasad i zaoszczędzić czas, jeśli podczas przesyłania do przepływu pracy następuje weryfikacja.</span><span class="sxs-lookup"><span data-stu-id="bea0a-128">Otherwise, you can delay policy evaluation and save time if you have validation occur at the end, during submission to workflow.</span></span>
