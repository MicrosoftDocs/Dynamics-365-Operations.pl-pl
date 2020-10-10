---
title: Zaawansowanego uzgodnienia konta bankowego — omówienie
description: W tym artykule opisano przebieg procesu zaawansowanego uzgadniania konta bankowego. Funkcja zaawansowanego uzgadniania konta bankowego umożliwia importowanie wyciągów bankowych, a następnie ich automatyczne uzgadnianie z poziomu transakcji bankowych.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b26b6e1e50e5a9b53ca6b5315de760f5bcec4769
ms.sourcegitcommit: 74b10104338222a945684d841d60ab4b8e570168
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2020
ms.locfileid: "3899404"
---
# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="6c551-104">Zaawansowanego uzgodnienia konta bankowego — omówienie</span><span class="sxs-lookup"><span data-stu-id="6c551-104">Advanced bank reconciliation overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c551-105">W tym artykule opisano przebieg procesu zaawansowanego uzgadniania konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="6c551-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="6c551-106">Funkcja zaawansowanego uzgadniania konta bankowego umożliwia importowanie wyciągów bankowych, a następnie ich automatyczne uzgadnianie z poziomu transakcji bankowych.</span><span class="sxs-lookup"><span data-stu-id="6c551-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="6c551-107">Funkcja zaawansowanego uzgodnienia konta bankowego pozwala importować wyciągi bankowe.</span><span class="sxs-lookup"><span data-stu-id="6c551-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="6c551-108">Zaimportowany wyciąg z konta można następnie automatycznie uzgodnić z poziomu transakcji bankowych.</span><span class="sxs-lookup"><span data-stu-id="6c551-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="6c551-109">Poniżej przedstawiono kroki w procesie zaawansowanego uzgadniania konta bankowego</span><span class="sxs-lookup"><span data-stu-id="6c551-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="6c551-110">Konfigurowanie importu wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="6c551-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="6c551-111">Importowanie wyciągów bankowych za pośrednictwem struktury danych jednostki.</span><span class="sxs-lookup"><span data-stu-id="6c551-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="6c551-112">Trzy typowe formaty wyciągów bankowych są wbudowane: ISO20022, BAI2, i MT940.</span><span class="sxs-lookup"><span data-stu-id="6c551-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="6c551-113">Funkcję można rozszerzyć na dowolny format.</span><span class="sxs-lookup"><span data-stu-id="6c551-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="6c551-114">Należy ustawić kolejność na potrzeby zaawansowanego uzgadniania konta bankowego i zdefiniować reguł uzgadniania wyciągów bankowych.</span><span class="sxs-lookup"><span data-stu-id="6c551-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="6c551-115">Reguły uzgadniania wyciągów to zestaw kryteriów, które są używane do filtrowania podczas procesu uzgadniania wierszy wyciągu bankowego z wierszami transakcji bankowych w Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="6c551-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 Finance bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="6c551-116">W zależności od praktyk biznesowych klienta można skonfigurować więcej niż jedną regułę uzgadniania i zautomatyzować oraz zoptymalizować proces uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="6c551-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="6c551-117">Uzgadnianie wyciągów bankowych z transakcjami bankowymi w programie Finance.</span><span class="sxs-lookup"><span data-stu-id="6c551-117">Reconcile bank statements with Finance bank transactions.</span></span>
    -   <span data-ttu-id="6c551-118">Automatyczne dopasowywanie i tworzenie arkuszy uzgadniania konta.</span><span class="sxs-lookup"><span data-stu-id="6c551-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="6c551-119">Bezpośrednie porównywanie wyciągów bankowych z transakcjami bankowymi w aplikacji Finance.</span><span class="sxs-lookup"><span data-stu-id="6c551-119">View bank statements and Finance bank transactions side by side.</span></span>
    -   <span data-ttu-id="6c551-120">Automatyczne księgowanie transakcji bankowych w Finance, jeśli pojawiają się na wyciągu bankowym, ale nie ma ich w aplikacji Finance.</span><span class="sxs-lookup"><span data-stu-id="6c551-120">Automatically post Finance bank transactions if they appear on a bank statement but don't appear in the Finance app.</span></span>
    -   <span data-ttu-id="6c551-121">Generowanie wyciągu uzgodnienia.</span><span class="sxs-lookup"><span data-stu-id="6c551-121">Generate a reconciliation statement.</span></span>





