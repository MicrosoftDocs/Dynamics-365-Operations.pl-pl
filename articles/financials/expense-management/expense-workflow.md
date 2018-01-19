---
title: "Przepływ pracy dotyczący wydatków"
description: "W tym temacie wyjaśniono, jak korzystać z systemu przepływu pracy w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, w celu skonfigurowania procesu kontroli dla raportu wydatków w funkcji Zarządzanie wydatkami."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 25fc9b5bac4a63cdf24cca10ef3a683a3b02b527
ms.contentlocale: pl-pl
ms.lasthandoff: 01/19/2018

---

# <a name="expense-workflow"></a><span data-ttu-id="3571b-103">Przepływ pracy dotyczący wydatków</span><span class="sxs-lookup"><span data-stu-id="3571b-103">Expense workflow</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3571b-104">Systemu przepływu pracy w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, można użyć w celu skonfigurowania procesu kontroli dla raportu wydatków w funkcji Zarządzanie wydatkami.</span><span class="sxs-lookup"><span data-stu-id="3571b-104">You can use the workflow system in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to set up a review process for expense reports in Expense management.</span></span> <span data-ttu-id="3571b-105">Można skonfigurować przepływ pracy, który używa następujących kryteriów do określenia osoby zatwierdzającej raporty wydatków:</span><span class="sxs-lookup"><span data-stu-id="3571b-105">You can set up a workflow that uses the following criteria to determine who approves expense reports:</span></span>

- <span data-ttu-id="3571b-106">Hierarchia raportowania pracownika i wstępnie zdefiniowane limity zatwierdzenia</span><span class="sxs-lookup"><span data-stu-id="3571b-106">The employee reporting hierarchy and predefined approval limits</span></span>
- <span data-ttu-id="3571b-107">Wielopoziomowe zatwierdzanie, które obsługuje osoby zatwierdzające tymczasowo i osobę ostatecznie zatwierdzającą</span><span class="sxs-lookup"><span data-stu-id="3571b-107">Multi-level approval that supports interim approvers and a final approver</span></span>
- <span data-ttu-id="3571b-108">Wymiary finansowe i odpowiedzialność za projekt</span><span class="sxs-lookup"><span data-stu-id="3571b-108">Financial dimensions and project responsibility</span></span>
- <span data-ttu-id="3571b-109">Przypisanie do określonych użytkowników lub grup użytkowników</span><span class="sxs-lookup"><span data-stu-id="3571b-109">Assignment to specific users or user groups</span></span>

<span data-ttu-id="3571b-110">Zatwierdzenia przepływu pracy można utworzyć dla raportów z wydatków, wniosków wyjazdowych, zaliczek gotówkowych i zwrotu podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="3571b-110">Workflow approvals can be created for expense reports, travel requisitions, cash advances, and value-added tax (VAT) recovery.</span></span>

<span data-ttu-id="3571b-111">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="3571b-111">**Example**</span></span>

<span data-ttu-id="3571b-112">Poniżej przedstawiono przykładowy przepływ pracy zarządzania wydatkami w odniesieniu do raportu z wydatków.</span><span class="sxs-lookup"><span data-stu-id="3571b-112">The following process is an example of the expense management workflow for an expense report.</span></span>

1. <span data-ttu-id="3571b-113">Pracownik tworzy i zapisuje raport z wydatków.</span><span class="sxs-lookup"><span data-stu-id="3571b-113">An employee creates and saves an expense report.</span></span>
2. <span data-ttu-id="3571b-114">Pracownik przesyła raport z wydatku do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="3571b-114">The employee submits the expense report for approval.</span></span> <span data-ttu-id="3571b-115">Osoba zatwierdzająca jest identyfikowana na podstawie zasad zdefiniowanych podczas konfigurowania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="3571b-115">The approver is identified based on the rules that were defined when the workflow was set up.</span></span>
3. <span data-ttu-id="3571b-116">Osoba zatwierdzająca otrzymuje powiadomienie, że raport z wydatków jest gotowy do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="3571b-116">The approver receives a notification that an expense report is ready for approval.</span></span> <span data-ttu-id="3571b-117">Osoba zatwierdzająca sprawdza raport z wydatków i weryfikuje spełnienie następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="3571b-117">The approver reviews the expense report and verifies that the following conditions are met:</span></span>

    - <span data-ttu-id="3571b-118">Wydatki nie są niezgodne z zasadami dotyczącymi wydatków.</span><span class="sxs-lookup"><span data-stu-id="3571b-118">The expenses don't violate any expense policies.</span></span> <span data-ttu-id="3571b-119">Jeżeli wydatek narusza zasady, osoba zatwierdzająca sprawdza, czy raport z wydatków zawiera prawidłowe uzasadnienie biznesowe.</span><span class="sxs-lookup"><span data-stu-id="3571b-119">If an expense violates a policy, the approver verifies that the expense report includes a valid business justification.</span></span>
    - <span data-ttu-id="3571b-120">Do raportu z wydatków są dołączone pokwitowania elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="3571b-120">Electronic receipts are attached to the expense report.</span></span>

4. <span data-ttu-id="3571b-121">Osoba zatwierdzająca zatwierdza raport z wydatków.</span><span class="sxs-lookup"><span data-stu-id="3571b-121">The approver approves the expense report.</span></span>
5. <span data-ttu-id="3571b-122">Raport z wydatków zostaje przypisany do osoby odpowiedzialnej za rozrachunki z dostawcami w celu zaksięgowania.</span><span class="sxs-lookup"><span data-stu-id="3571b-122">The expense report is assigned to the Accounts payable coordinator for posting.</span></span>
6. <span data-ttu-id="3571b-123">W zależności od tego, czy skonfigurowano automatyczne księgowanie, wykonywany jest jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="3571b-123">One of the following steps occurs, depending on whether automatic posting is configured:</span></span>

    - <span data-ttu-id="3571b-124">Jeżeli skonfigurowano automatyczne księgowanie, raport z wydatków jest przetwarzany w celu płatności, a stan raportu z wydatków jest aktualizowany.</span><span class="sxs-lookup"><span data-stu-id="3571b-124">If automatic posting is configured, the expense report is processed for payment, and the status of the expense report is updated.</span></span>
    - <span data-ttu-id="3571b-125">Jeżeli automatyczne księgowanie nie jest skonfigurowane, osoba odpowiedzialna za rozrachunki z dostawcami sprawdza, czy wszystkie oryginalne pokwitowania zostały przesłane i są zgodne z wydatkami w raporcie.</span><span class="sxs-lookup"><span data-stu-id="3571b-125">If automatic posting isn't configured, the Accounts payable coordinator verifies that all original receipts have been submitted, and that the receipts are aligned with the expenses on the expense report.</span></span> <span data-ttu-id="3571b-126">Wszystkie kody podatków wprowadzone w raporcie z wydatków także muszą zostać zweryfikowane jako prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="3571b-126">All tax codes that are entered on the expense report must also be verified as correct.</span></span>

<span data-ttu-id="3571b-127">Po zweryfikowaniu tych wymagań raport z wydatków jest księgowany.</span><span class="sxs-lookup"><span data-stu-id="3571b-127">After these requirements are verified, the expense report is posted.</span></span>

<span data-ttu-id="3571b-128">Po zaksięgowaniu raportu z wydatków płatność jest autoryzowana dla raportu z wydatków, a pracownik otrzymuje zwrot.</span><span class="sxs-lookup"><span data-stu-id="3571b-128">After the expense report is posted, payment is authorized for the expense report, and the employee is reimbursed.</span></span>

