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
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5d4256b155d3e06d63e425fab63b4025ef2577f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140025"
---
# <a name="import-iso20022-direct-debit-configuration"></a><span data-ttu-id="f8560-103">Importowanie konfiguracji polecenia zapłaty ISO20022</span><span class="sxs-lookup"><span data-stu-id="f8560-103">Import ISO20022 direct debit configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f8560-104">W tej procedurze przestawiono sposób importowania konfiguracji raportowania elektronicznego płatności od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f8560-104">This procedure demonstrates how to import a customer payment electronic reporting configuration.</span></span> <span data-ttu-id="f8560-105">Procedura wykorzystuje format zapłaty polecenia zapłaty ISO 20022 jako przykład.</span><span class="sxs-lookup"><span data-stu-id="f8560-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> 



<span data-ttu-id="f8560-106">Procedura została utworzona przy użyciu danych firmy demonstracyjnej DEMF, ale do tego celu można użyć danych dowolnej firmy demonstracyjnej.</span><span class="sxs-lookup"><span data-stu-id="f8560-106">This procedure was created using the demo data company DEMF but you can use any demo data company for this purpose.</span></span>



<span data-ttu-id="f8560-107">Jest to pierwsza z pięciu procedur, które razem przedstawiają proces płatności od odbiorców przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="f8560-107">This is the first of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="f8560-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="f8560-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="f8560-109">Na liście dostępnych dostawców konfiguracji zaznacz pozycję Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8560-109">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="f8560-110">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="f8560-110">Click Set active.</span></span>
4. <span data-ttu-id="f8560-111">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="f8560-111">Click Repositories.</span></span>
5. <span data-ttu-id="f8560-112">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="f8560-112">Click Open.</span></span>
6. <span data-ttu-id="f8560-113">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="f8560-113">Click Show filters.</span></span>
7. <span data-ttu-id="f8560-114">Zastosuj następujące filtry: w polu „Nazwa konfiguracji” wprowadź wartość filtru „Polecenie zapłaty ISO20022 (Niemcy)”, używając operatora filtru „zaczyna się od”.</span><span class="sxs-lookup"><span data-stu-id="f8560-114">Apply the following filters: Enter a filter value of "ISO20022 Direct debit (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="f8560-115">Opcjonalnie można odszukać konfigurację na liście, zaznaczyć ją i pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="f8560-115">Optionally, you can find the configuration in the list, select it, and skip this step.</span></span>  
8. <span data-ttu-id="f8560-116">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="f8560-116">Click Import.</span></span>
    * <span data-ttu-id="f8560-117">Jeśli przycisk Importuj nie jest dostępny, oznacza to, że konfiguracja została już zaimportowana.</span><span class="sxs-lookup"><span data-stu-id="f8560-117">If the Import button is not available, it means that the configuration has been imported already.</span></span>  
9. <span data-ttu-id="f8560-118">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="f8560-118">Click Yes.</span></span>

