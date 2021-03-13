---
title: ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1 — Tworzenie formatu)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego do zliczania i sumowania na podstawie danych już wygenerowanego tekstu wyjściowego. (część 1)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a3639b5ac28f8a571642e983906d658dabf05b1
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093029"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a><span data-ttu-id="ae441-104">ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1 — Tworzenie formatu)</span><span class="sxs-lookup"><span data-stu-id="ae441-104">ER Configure format to do counting and summing (Part 1 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ae441-105">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="ae441-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="ae441-106">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="ae441-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="ae441-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="ae441-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="ae441-108">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="ae441-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="ae441-109">Uzyskiwanie dostępu do listy konfiguracji dostarczanej przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae441-109">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="ae441-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="ae441-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="ae441-111">Upewnij się, że dostawca „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="ae441-111">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="ae441-112">jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="ae441-112">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="ae441-113">Wybierz dostawcę „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="ae441-113">Select the "Litware, Inc."</span></span> <span data-ttu-id="ae441-114"> </span><span class="sxs-lookup"><span data-stu-id="ae441-114">provider.</span></span>
3. <span data-ttu-id="ae441-115">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="ae441-115">Click Repositories.</span></span>
    * <span data-ttu-id="ae441-116">Jeśli repozytorium typu „Zasoby operacyjne” już istnieje, należy pominąć pozostałe kroki bieżącego zadania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="ae441-116">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="ae441-117">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ae441-117">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="ae441-118">W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.</span><span class="sxs-lookup"><span data-stu-id="ae441-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="ae441-119">Kliknij opcję Utwórz repozytorium.</span><span class="sxs-lookup"><span data-stu-id="ae441-119">Click Create repository.</span></span>
7. <span data-ttu-id="ae441-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ae441-120">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="ae441-121">Pobieranie konfiguracji Intrastat dostarczanych przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae441-121">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="ae441-122">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="ae441-122">Click Open.</span></span>
2. <span data-ttu-id="ae441-123">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="ae441-123">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="ae441-124">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="ae441-124">Click Import.</span></span>
    * <span data-ttu-id="ae441-125">Kliknij przycisk Importuj dla wersji 1.1 wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="ae441-125">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="ae441-126">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="ae441-126">Click Yes.</span></span>
5. <span data-ttu-id="ae441-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ae441-127">Close the page.</span></span>
6. <span data-ttu-id="ae441-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ae441-128">Close the page.</span></span>
7. <span data-ttu-id="ae441-129">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="ae441-129">Click Reporting configurations.</span></span>
8. <span data-ttu-id="ae441-130">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="ae441-130">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="ae441-131">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="ae441-131">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>

