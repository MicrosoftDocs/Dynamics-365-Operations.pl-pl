---
title: "Ustawianie przepływów pracy dla wydatków"
description: "Można ustawić proces przepływu pracy, który jest używany do sprawdzania i zatwierdzania dokumentów dotyczących podróży i wydatków."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: ef60fbab0f75ff70206d954e3d098a3866c467b6
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---

# <a name="set-up-workflows-for-expense"></a><span data-ttu-id="194f9-103">Ustawianie przepływów pracy dla wydatków</span><span class="sxs-lookup"><span data-stu-id="194f9-103">Set up workflows for expense</span></span>

[!include[banner](../includes/banner.md)]<span data-ttu-id="194f9-104"> Można ustawić proces przepływu pracy, który jest używany do sprawdzania i zatwierdzania dokumentów dotyczących podróży i wydatków.</span><span class="sxs-lookup"><span data-stu-id="194f9-104"> You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="194f9-105">Dokumenty, dla których można zdefiniować przepływy pracy obejmują raporty z wydatków, wnioski wyjazdowe i wnioski o zaliczkę gotówkową.</span><span class="sxs-lookup"><span data-stu-id="194f9-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="194f9-106">Przepływ pracy reprezentuje proces biznesowy.</span><span class="sxs-lookup"><span data-stu-id="194f9-106">A workflow represents a business process.</span></span> <span data-ttu-id="194f9-107">Określa sposób przepływu dokumentu przez system i wskazuje osoby, które muszą zakończyć zadanie lub zatwierdzić dokument.</span><span class="sxs-lookup"><span data-stu-id="194f9-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="194f9-108">Używanie systemu przepływu pracy w organizacji ma kilka zalet:</span><span class="sxs-lookup"><span data-stu-id="194f9-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="194f9-109">**Spójność procesów** — Możesz zdefiniować proces zatwierdzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków.</span><span class="sxs-lookup"><span data-stu-id="194f9-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="194f9-110">Używanie systemu przepływu pracy pomaga zapewnić, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.</span><span class="sxs-lookup"><span data-stu-id="194f9-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="194f9-111">Widoczność procesu — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="194f9-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="194f9-112">Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.</span><span class="sxs-lookup"><span data-stu-id="194f9-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="194f9-113">Scentralizowana lista prac — Użytkownicy mogą wyświetlić scentralizowaną listę prac, aby przeglądać przypisane do nich zadania i zatwierdzenia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="194f9-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="194f9-114">**Dostępne typy przepływów pracy**</span><span class="sxs-lookup"><span data-stu-id="194f9-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="194f9-115">W poniższej tabeli wymieniono typy przepływów pracy, które można tworzyć w module **Wydatek**.</span><span class="sxs-lookup"><span data-stu-id="194f9-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>

| <span data-ttu-id="194f9-116">**Typ**</span><span class="sxs-lookup"><span data-stu-id="194f9-116">**Type**</span></span>                           | <span data-ttu-id="194f9-117">**Ten typ służy do następujących zadań**</span><span class="sxs-lookup"><span data-stu-id="194f9-117">**Use this type to**</span></span>                                                 |     
|------------------------------------|----------------------------------------------------------------------|
| <span data-ttu-id="194f9-118">**Raport o wydatkach**</span><span class="sxs-lookup"><span data-stu-id="194f9-118">**Expense report**</span></span>                 | <span data-ttu-id="194f9-119">Utwórz przepływy pracy zatwierdzania dla raportu z wydatków.</span><span class="sxs-lookup"><span data-stu-id="194f9-119">Create approval workflows for expense reports.</span></span>                       |      
| <span data-ttu-id="194f9-120">**Automatyczne księgowani raportu wydatków**</span><span class="sxs-lookup"><span data-stu-id="194f9-120">**Expense report auto posting**</span></span>    | <span data-ttu-id="194f9-121">Utwórz przepływy pracy automatycznego księgowania w raportach z wydatków.</span><span class="sxs-lookup"><span data-stu-id="194f9-121">Create automatic posting workflows for expense reports.</span></span>              |     
| <span data-ttu-id="194f9-122">**Pozycja w wierszu wydatku**</span><span class="sxs-lookup"><span data-stu-id="194f9-122">**Expense line item**</span></span>              | <span data-ttu-id="194f9-123">Utwórz przepływy pracy zatwierdzania dla pozycji w wierszu w raportach z wydatków.</span><span class="sxs-lookup"><span data-stu-id="194f9-123">Create approval workflows for line items on expense reports.</span></span>         |     
| <span data-ttu-id="194f9-124">**Automatyczne księgowanie pozycji wiersza wydatków**</span><span class="sxs-lookup"><span data-stu-id="194f9-124">**Expense line item auto posting**</span></span> | <span data-ttu-id="194f9-125">Utwórz przepływy pracy automatycznego księgowania dla pozycji w wierszu w raportach z wydatków.</span><span class="sxs-lookup"><span data-stu-id="194f9-125">Create automatic posting workflows for line items on expense reports.</span></span>|
| <span data-ttu-id="194f9-126">**Wniosek wyjazdowy**</span><span class="sxs-lookup"><span data-stu-id="194f9-126">**Travel requisition**</span></span>             | <span data-ttu-id="194f9-127">Utwórz przepływy pracy zatwierdzania dla wniosków wyjazdowych.</span><span class="sxs-lookup"><span data-stu-id="194f9-127">Create approval workflows for travel requisitions.</span></span>                   |    
| <span data-ttu-id="194f9-128">**Wniosek o zaliczkę gotówkową**</span><span class="sxs-lookup"><span data-stu-id="194f9-128">**Cash advance request**</span></span>           | <span data-ttu-id="194f9-129">Utwórz przepływy pracy zatwierdzania wniosków o zaliczkę gotówkową.</span><span class="sxs-lookup"><span data-stu-id="194f9-129">Create approval workflows for cash advance requests.</span></span>                 |     
| <span data-ttu-id="194f9-130">**Zwrot podatku VAT**</span><span class="sxs-lookup"><span data-stu-id="194f9-130">**VAT tax recovery**</span></span>               | <span data-ttu-id="194f9-131">Utwórz przepływy pracy zatwierdzania dla podatku od wartości dodanej (VAT).</span><span class="sxs-lookup"><span data-stu-id="194f9-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span> |       

