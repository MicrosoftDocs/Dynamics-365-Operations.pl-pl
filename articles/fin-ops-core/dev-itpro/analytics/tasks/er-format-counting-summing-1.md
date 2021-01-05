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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1742582057cc912d8e6f90eb14e9e4cdcd193608
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684722"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a><span data-ttu-id="75720-103">ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1 — Tworzenie formatu)</span><span class="sxs-lookup"><span data-stu-id="75720-103">ER Configure format to do counting and summing (Part 1 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="75720-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="75720-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="75720-105">Kroki można wykonać na danych dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="75720-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="75720-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="75720-106">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="75720-107">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="75720-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="75720-108">Uzyskiwanie dostępu do listy konfiguracji dostarczanej przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="75720-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="75720-109">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="75720-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="75720-110">Upewnij się, że dostawca „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="75720-110">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="75720-111">jest dostępny i oznaczony jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="75720-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="75720-112">Wybierz dostawcę „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="75720-112">Select the "Litware, Inc."</span></span> <span data-ttu-id="75720-113"> </span><span class="sxs-lookup"><span data-stu-id="75720-113">provider.</span></span>
3. <span data-ttu-id="75720-114">Kliknij Repozytoria.</span><span class="sxs-lookup"><span data-stu-id="75720-114">Click Repositories.</span></span>
    * <span data-ttu-id="75720-115">Jeśli repozytorium typu „Zasoby operacyjne” już istnieje, należy pominąć pozostałe kroki bieżącego zadania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="75720-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="75720-116">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="75720-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="75720-117">W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.</span><span class="sxs-lookup"><span data-stu-id="75720-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="75720-118">Kliknij opcję Utwórz repozytorium.</span><span class="sxs-lookup"><span data-stu-id="75720-118">Click Create repository.</span></span>
7. <span data-ttu-id="75720-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="75720-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="75720-120">Pobieranie konfiguracji Intrastat dostarczanych przez firmę Microsoft</span><span class="sxs-lookup"><span data-stu-id="75720-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="75720-121">Kliknij przycisk Otwórz.</span><span class="sxs-lookup"><span data-stu-id="75720-121">Click Open.</span></span>
2. <span data-ttu-id="75720-122">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="75720-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="75720-123">Kliknij przycisk Importuj.</span><span class="sxs-lookup"><span data-stu-id="75720-123">Click Import.</span></span>
    * <span data-ttu-id="75720-124">Kliknij przycisk Importuj dla wersji 1.1 wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="75720-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="75720-125">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="75720-125">Click Yes.</span></span>
5. <span data-ttu-id="75720-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="75720-126">Close the page.</span></span>
6. <span data-ttu-id="75720-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="75720-127">Close the page.</span></span>
7. <span data-ttu-id="75720-128">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="75720-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="75720-129">W drzewie rozwiń węzeł „Model Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="75720-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="75720-130">W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.</span><span class="sxs-lookup"><span data-stu-id="75720-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>

