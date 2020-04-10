---
title: Importowanie konfiguracji polecenia przelewu ISO20022
description: W tej procedurze pokazano sposób importowania konfiguracji raportowania elektronicznego płatności dla dostawcy.
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
ms.openlocfilehash: 01f44c49b6623cbcc2f08cfd6e4978c9a1676b83
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140048"
---
# <a name="import-iso20022-credit-transfer-configuration"></a><span data-ttu-id="70e7c-103">Importowanie konfiguracji polecenia przelewu ISO20022</span><span class="sxs-lookup"><span data-stu-id="70e7c-103">Import ISO20022 credit transfer configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="70e7c-104">W tej procedurze pokazano sposób importowania konfiguracji raportowania elektronicznego płatności dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="70e7c-104">This procedure shows how to import a vendor payment electronic reporting configuration.</span></span> <span data-ttu-id="70e7c-105">Jako przykładu użyto niemieckiego formatu poleceń przelewu zgodnego z normą ISO 20022.</span><span class="sxs-lookup"><span data-stu-id="70e7c-105">The German ISO 20022 credit transfer format is used as an example.</span></span> <span data-ttu-id="70e7c-106">Procedura może być używana do innych dostępnych formatów raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="70e7c-106">This procedure can be used for other available electronic reporting format.</span></span> 

<span data-ttu-id="70e7c-107">Zadanie zostało utworzone przy użyciu danych firmy demonstracyjnej DEMF, ale do wykonania zadania można użyć danych dowolnej firmy demonstracyjnej.</span><span class="sxs-lookup"><span data-stu-id="70e7c-107">This task was created using the demo data company DEMF but you can use any demo data company to complete this task.</span></span>

<span data-ttu-id="70e7c-108">Jest to pierwsze z pięciu zadań, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="70e7c-108">This is the first of five tasks, that together illustrate the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="70e7c-109">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="70e7c-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="70e7c-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="70e7c-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="70e7c-111">Na liście dostępnych dostawców konfiguracji zaznacz pozycję Microsoft.</span><span class="sxs-lookup"><span data-stu-id="70e7c-111">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="70e7c-112">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="70e7c-112">Click Set active.</span></span>
4. <span data-ttu-id="70e7c-113">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="70e7c-113">Click Repositories.</span></span>
5. <span data-ttu-id="70e7c-114">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="70e7c-114">Click Open.</span></span>
6. <span data-ttu-id="70e7c-115">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="70e7c-115">Click Show filters.</span></span>
7. <span data-ttu-id="70e7c-116">Zastosuj następujące filtry: w polu „Nazwa konfiguracji” wprowadź wartość filtru „Polecenie przelewu ISO20022 (Niemcy)”, używając operatora filtru „zaczyna się od”.</span><span class="sxs-lookup"><span data-stu-id="70e7c-116">Apply the following filters: Enter a filter value of "ISO20022 Credit transfer (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="70e7c-117">Alternatywnie można poszukać konfiguracji na liście, zaznaczyć ją, a następnie przenieść do zadania importu.</span><span class="sxs-lookup"><span data-stu-id="70e7c-117">Alternatively, you can find the configuration in the list, select it, and then move it to the Import task.</span></span>  
8. <span data-ttu-id="70e7c-118">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="70e7c-118">Click Import.</span></span>
    * <span data-ttu-id="70e7c-119">Jeśli przycisk Importuj nie jest dostępny, oznacza to, że konfiguracja została już zaimportowana.</span><span class="sxs-lookup"><span data-stu-id="70e7c-119">If the Import button is not available, it means that the configuration has  already been imported.</span></span>  
9. <span data-ttu-id="70e7c-120">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="70e7c-120">Click Yes.</span></span>

