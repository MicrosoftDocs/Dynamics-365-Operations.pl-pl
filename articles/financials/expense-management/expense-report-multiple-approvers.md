---
title: "Raporty z wydatków i wiele osób zatwierdzających"
description: "Ten temat zawiera informacje dotyczące raportów z wydatków, które wymagają zatwierdzenia przez więcej niż jedną osobę."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 1483de5405895d60f0cb302ab622758b2b05d2ca
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="expense-reports-and-multiple-approvers"></a><span data-ttu-id="4426a-103">Raporty z wydatków i wiele osób zatwierdzających</span><span class="sxs-lookup"><span data-stu-id="4426a-103">Expense reports and multiple approvers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4426a-104">W zależności od zasad zatwierdzania wydatków w organizacji kilka osób może być zobowiązanych do zatwierdzania raportu z wydatków przesłanego przez pracownika.</span><span class="sxs-lookup"><span data-stu-id="4426a-104">Depending on your organization's expense approval policies, more than one person might have to approve an expense report that is submitted by an employee.</span></span> <span data-ttu-id="4426a-105">Podczas konfigurowania procesu przepływu pracy dla zatwierdzania raportów z wydatków można dodać elementy przepływu pracy, które zawierają zadania lub kroki dla jednej lub więcej osób mających zatwierdzać raporty z wydatków.</span><span class="sxs-lookup"><span data-stu-id="4426a-105">When you set up the workflow process for expense report approval, you can add workflow elements that include tasks or steps for one or more expense report approvers.</span></span> <span data-ttu-id="4426a-106">Na przykład może istnieć wymóg, aby wszystkie raporty z wydatków były najpierw zatwierdzane przez przełożonego pracownika, który złożył raport, a następnie przez koordynatora rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="4426a-106">For example, you might require that all expense reports be approved first by the manager of the employee who submitted the report and then by the Accounts payable coordinator.</span></span>

<span data-ttu-id="4426a-107">Jeśli zdecydujesz wprowadzić konieczność istnienia wielu osób zatwierdzających raporty z wydatków, można dodać elementy przepływu pracy na jeden z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="4426a-107">If you decide to require multiple expense report approvers, you can add the workflow elements in any of the following ways:</span></span>

- <span data-ttu-id="4426a-108">Dodanie jednego elementu zatwierdzania, który ma jeden krok.</span><span class="sxs-lookup"><span data-stu-id="4426a-108">Add one approval element that has one step.</span></span> <span data-ttu-id="4426a-109">Na przykład krok może wymagać, aby raport z wydatków został przypisany do grupy użytkowników oraz został zaaprobowany przez 50 członków grupy użytkowników.</span><span class="sxs-lookup"><span data-stu-id="4426a-109">For example, the step might require that an expense report be assigned to a user group, and that it be approved by 50 percent of the user group's members.</span></span>
- <span data-ttu-id="4426a-110">Dodanie jednego elementu zatwierdzania, który ma wiele kroków.</span><span class="sxs-lookup"><span data-stu-id="4426a-110">Add one approval element that has multiple steps.</span></span> <span data-ttu-id="4426a-111">Na przykład element zatwierdzania może zawierać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="4426a-111">For example, the approval element might have the following steps:</span></span>

    1. <span data-ttu-id="4426a-112">Przełożony pracownika, który złożył raport z wydatków, zatwierdza raport.</span><span class="sxs-lookup"><span data-stu-id="4426a-112">The manager of the employee who submitted the expense report approves it.</span></span>
    2. <span data-ttu-id="4426a-113">Pracownik ds. rozrachunków z dostawcami weryfikuje paragony i pozycje raportu z wydatków.</span><span class="sxs-lookup"><span data-stu-id="4426a-113">The Accounts payable clerk verifies the receipts and the expense report items.</span></span>
    3. <span data-ttu-id="4426a-114">Właściciel budżetu zatwierdza raport z wydatków.</span><span class="sxs-lookup"><span data-stu-id="4426a-114">The budget owner approves the expense report.</span></span>

- <span data-ttu-id="4426a-115">Dodanie wielu elementów zatwierdzenia, z których każdy ma jeden krok.</span><span class="sxs-lookup"><span data-stu-id="4426a-115">Add multiple approval elements, each of which has one step.</span></span> <span data-ttu-id="4426a-116">Na przykład można dodać oddzielny element zatwierdzania dla każdego z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="4426a-116">For example, you might add a separate approval element for each of the following steps:</span></span>

    1. <span data-ttu-id="4426a-117">Przełożony pracownika zatwierdza raport z wydatków.</span><span class="sxs-lookup"><span data-stu-id="4426a-117">The employee's manager approves the expense report.</span></span>
    2. <span data-ttu-id="4426a-118">Właściciel budżetu zatwierdza raport z wydatków.</span><span class="sxs-lookup"><span data-stu-id="4426a-118">The budget owner approves the expense report.</span></span>

