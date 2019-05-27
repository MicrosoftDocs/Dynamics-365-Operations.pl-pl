---
title: Importowanie konfiguracji polecenia zapłaty ISO20022
description: W tej procedurze przestawiono sposób importowania konfiguracji raportowania elektronicznego płatności od odbiorcy.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1757a1477e46f71e327bb70cf4780767b7509e55
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568730"
---
# <a name="import-iso20022-direct-debit-configuration"></a><span data-ttu-id="dd35a-103">Importowanie konfiguracji polecenia zapłaty ISO20022</span><span class="sxs-lookup"><span data-stu-id="dd35a-103">Import ISO20022 direct debit configuration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dd35a-104">W tej procedurze przestawiono sposób importowania konfiguracji raportowania elektronicznego płatności od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="dd35a-104">This procedure demonstrates how to import a customer payment electronic reporting configuration.</span></span> <span data-ttu-id="dd35a-105">Procedura wykorzystuje format zapłaty polecenia zapłaty ISO 20022 jako przykład.</span><span class="sxs-lookup"><span data-stu-id="dd35a-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> 



<span data-ttu-id="dd35a-106">Procedura została utworzona przy użyciu danych firmy demonstracyjnej DEMF, ale do tego celu można użyć danych dowolnej firmy demonstracyjnej.</span><span class="sxs-lookup"><span data-stu-id="dd35a-106">This procedure was created using the demo data company DEMF but you can use any demo data company for this purpose.</span></span>



<span data-ttu-id="dd35a-107">Jest to pierwsza z pięciu procedur, które razem przedstawiają proces płatności od odbiorców przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="dd35a-107">This is the first of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="dd35a-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="dd35a-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="dd35a-109">Na liście dostępnych dostawców konfiguracji zaznacz pozycję Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dd35a-109">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="dd35a-110">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="dd35a-110">Click Set active.</span></span>
4. <span data-ttu-id="dd35a-111">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="dd35a-111">Click Repositories.</span></span>
5. <span data-ttu-id="dd35a-112">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="dd35a-112">Click Open.</span></span>
6. <span data-ttu-id="dd35a-113">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="dd35a-113">Click Show filters.</span></span>
7. <span data-ttu-id="dd35a-114">Zastosuj następujące filtry: w polu „Nazwa konfiguracji” wprowadź wartość filtru „Polecenie zapłaty ISO20022 (Niemcy)”, używając operatora filtru „zaczyna się od”.</span><span class="sxs-lookup"><span data-stu-id="dd35a-114">Apply the following filters: Enter a filter value of "ISO20022 Direct debit (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="dd35a-115">Opcjonalnie można odszukać konfigurację na liście, zaznaczyć ją i pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="dd35a-115">Optionally, you can find the configuration in the list, select it, and skip this step.</span></span>  
8. <span data-ttu-id="dd35a-116">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="dd35a-116">Click Import.</span></span>
    * <span data-ttu-id="dd35a-117">Jeśli przycisk Importuj nie jest dostępny, oznacza to, że konfiguracja została już zaimportowana.</span><span class="sxs-lookup"><span data-stu-id="dd35a-117">If the Import button is not available, it means that the configuration has been imported already.</span></span>  
9. <span data-ttu-id="dd35a-118">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="dd35a-118">Click Yes.</span></span>

