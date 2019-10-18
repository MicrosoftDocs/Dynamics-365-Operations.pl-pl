---
title: ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1 — Tworzenie formatu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2a3b3997b8d366f92192ff765dbcff9b68844ba
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182400"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1-create-format"></a><span data-ttu-id="c15fc-103">ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1: Tworzenie formatu)</span><span class="sxs-lookup"><span data-stu-id="c15fc-103">ER Configure format to do counting and summing (Part 1: Create format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c15fc-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="c15fc-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="c15fc-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="c15fc-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="c15fc-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="c15fc-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="c15fc-107">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="c15fc-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="c15fc-108">Uzyskiwanie dostępu do listy konfiguracji dostarczanej przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="c15fc-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="c15fc-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="c15fc-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="c15fc-110">Upewnij się, że dostawca „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="c15fc-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="c15fc-111">jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="c15fc-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="c15fc-112">Zaznacz dostawcę „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="c15fc-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="c15fc-113"> </span><span class="sxs-lookup"><span data-stu-id="c15fc-113">provider.</span></span>
3. <span data-ttu-id="c15fc-114">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="c15fc-114">Click Repositories.</span></span>
    * <span data-ttu-id="c15fc-115">Jeśli repozytorium typu „Zasoby operacyjne” już istnieje, należy pominąć pozostałe kroki bieżącego zadania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="c15fc-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="c15fc-116">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c15fc-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="c15fc-117">W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.</span><span class="sxs-lookup"><span data-stu-id="c15fc-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="c15fc-118">Kliknij opcję Utwórz repozytorium.</span><span class="sxs-lookup"><span data-stu-id="c15fc-118">Click Create repository.</span></span>
7. <span data-ttu-id="c15fc-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c15fc-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="c15fc-120">Pobieranie konfiguracji Intrastat dostarczanych przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="c15fc-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="c15fc-121">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="c15fc-121">Click Open.</span></span>
2. <span data-ttu-id="c15fc-122">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="c15fc-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="c15fc-123">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="c15fc-123">Click Import.</span></span>
    * <span data-ttu-id="c15fc-124">Kliknij przycisk Importuj dla wersji 1.1 wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c15fc-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="c15fc-125">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="c15fc-125">Click Yes.</span></span>
5. <span data-ttu-id="c15fc-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c15fc-126">Close the page.</span></span>
6. <span data-ttu-id="c15fc-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c15fc-127">Close the page.</span></span>
7. <span data-ttu-id="c15fc-128">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="c15fc-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="c15fc-129">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="c15fc-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="c15fc-130">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="c15fc-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>

