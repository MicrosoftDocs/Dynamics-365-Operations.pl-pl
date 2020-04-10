---
title: Konfigurowanie przepływów pracy dla Zarządzania wydatkami
description: Można ustawić proces przepływu pracy, który jest używany do sprawdzania i zatwierdzania dokumentów dotyczących podróży i wydatków.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdd4d69cb86da12e4a265f89c021c238d00cad08
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154001"
---
# <a name="set-up-workflows-for-expense-management"></a><span data-ttu-id="dee6b-103">Konfigurowanie przepływów pracy dla Zarządzania wydatkami</span><span class="sxs-lookup"><span data-stu-id="dee6b-103">Set up workflows for Expense management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dee6b-104">Można ustawić proces przepływu pracy, który jest używany do sprawdzania i zatwierdzania dokumentów dotyczących podróży i wydatków.</span><span class="sxs-lookup"><span data-stu-id="dee6b-104">You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="dee6b-105">Dokumenty, dla których można zdefiniować przepływy pracy obejmują raporty z wydatków, wnioski wyjazdowe i wnioski o zaliczkę gotówkową.</span><span class="sxs-lookup"><span data-stu-id="dee6b-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="dee6b-106">Przepływ pracy reprezentuje proces biznesowy.</span><span class="sxs-lookup"><span data-stu-id="dee6b-106">A workflow represents a business process.</span></span> <span data-ttu-id="dee6b-107">Określa sposób przepływu dokumentu przez system i wskazuje osoby, które muszą zakończyć zadanie lub zatwierdzić dokument.</span><span class="sxs-lookup"><span data-stu-id="dee6b-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="dee6b-108">Używanie systemu przepływu pracy w organizacji ma kilka zalet:</span><span class="sxs-lookup"><span data-stu-id="dee6b-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="dee6b-109">**Spójność procesów** — Możesz zdefiniować proces zatwierdzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków.</span><span class="sxs-lookup"><span data-stu-id="dee6b-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="dee6b-110">Używanie systemu przepływu pracy pomaga zapewnić, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.</span><span class="sxs-lookup"><span data-stu-id="dee6b-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="dee6b-111">Widoczność procesu — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="dee6b-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="dee6b-112">Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.</span><span class="sxs-lookup"><span data-stu-id="dee6b-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="dee6b-113">Scentralizowana lista prac — Użytkownicy mogą wyświetlić scentralizowaną listę prac, aby przeglądać przypisane do nich zadania i zatwierdzenia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="dee6b-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="dee6b-114">**Dostępne typy przepływów pracy**</span><span class="sxs-lookup"><span data-stu-id="dee6b-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="dee6b-115">W poniższej tabeli wymieniono typy przepływów pracy, które można tworzyć w module **Wydatek**.</span><span class="sxs-lookup"><span data-stu-id="dee6b-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>


|              <span data-ttu-id="dee6b-116"><strong>Typ</strong></span><span class="sxs-lookup"><span data-stu-id="dee6b-116"><strong>Type</strong></span></span>              |                   <span data-ttu-id="dee6b-117"><strong>Ten typ służy do następujących zadań</strong></span><span class="sxs-lookup"><span data-stu-id="dee6b-117"><strong>Use this type to</strong></span></span>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <span data-ttu-id="dee6b-118"><strong>Raport o wydatkach</strong></span><span class="sxs-lookup"><span data-stu-id="dee6b-118"><strong>Expense report</strong></span></span>         |            <span data-ttu-id="dee6b-119">Utwórz przepływy pracy zatwierdzania dla raportu z wydatków.</span><span class="sxs-lookup"><span data-stu-id="dee6b-119">Create approval workflows for expense reports.</span></span>             |
|  <span data-ttu-id="dee6b-120"><strong>Automatyczne księgowani raportu wydatków</strong></span><span class="sxs-lookup"><span data-stu-id="dee6b-120"><strong>Expense report auto posting</strong></span></span>   |        <span data-ttu-id="dee6b-121">Utwórz przepływy pracy automatycznego księgowania w raportach z wydatków.</span><span class="sxs-lookup"><span data-stu-id="dee6b-121">Create automatic posting workflows for expense reports.</span></span>        |
|       <span data-ttu-id="dee6b-122"><strong>Pozycja w wierszu wydatku</strong></span><span class="sxs-lookup"><span data-stu-id="dee6b-122"><strong>Expense line item</strong></span></span>        |     <span data-ttu-id="dee6b-123">Utwórz przepływy pracy zatwierdzania dla pozycji w wierszu w raportach z wydatków.</span><span class="sxs-lookup"><span data-stu-id="dee6b-123">Create approval workflows for line items on expense reports.</span></span>      |
| <span data-ttu-id="dee6b-124"><strong>Automatyczne księgowanie pozycji wiersza wydatków</strong></span><span class="sxs-lookup"><span data-stu-id="dee6b-124"><strong>Expense line item auto posting</strong></span></span> | <span data-ttu-id="dee6b-125">Utwórz przepływy pracy automatycznego księgowania dla pozycji w wierszu w raportach z wydatków.</span><span class="sxs-lookup"><span data-stu-id="dee6b-125">Create automatic posting workflows for line items on expense reports.</span></span> |
|       <span data-ttu-id="dee6b-126"><strong>Wniosek wyjazdowy</strong></span><span class="sxs-lookup"><span data-stu-id="dee6b-126"><strong>Travel requisition</strong></span></span>       |          <span data-ttu-id="dee6b-127">Utwórz przepływy pracy zatwierdzania dla wniosków wyjazdowych.</span><span class="sxs-lookup"><span data-stu-id="dee6b-127">Create approval workflows for travel requisitions.</span></span>           |
|      <span data-ttu-id="dee6b-128"><strong>Wniosek o zaliczkę gotówkową</strong></span><span class="sxs-lookup"><span data-stu-id="dee6b-128"><strong>Cash advance request</strong></span></span>      |         <span data-ttu-id="dee6b-129">Utwórz przepływy pracy zatwierdzania wniosków o zaliczkę gotówkową.</span><span class="sxs-lookup"><span data-stu-id="dee6b-129">Create approval workflows for cash advance requests.</span></span>          |
|        <span data-ttu-id="dee6b-130"><strong>Zwrot podatku VAT</strong></span><span class="sxs-lookup"><span data-stu-id="dee6b-130"><strong>VAT tax recovery</strong></span></span>        | <span data-ttu-id="dee6b-131">Utwórz przepływy pracy zatwierdzania dla podatku od wartości dodanej (VAT).</span><span class="sxs-lookup"><span data-stu-id="dee6b-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span>  |

