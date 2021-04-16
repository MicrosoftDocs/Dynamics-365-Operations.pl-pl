---
title: Konfigurowanie udostępniania danych finansowych między firmami
description: W tej procedurze pokazano sposób konfigurowania, włączania, sprawdzania poprawności i rozwiązywania konfliktów podczas udostępniania danych między firmami.
author: aprilolson
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportRnr, DMFExecutionHistoryWorkspace, DMFExecutionHistorySummary, DMFExecutionHistoryEntities,  SysDataSharingConfiguration, SysDataSharingDiscrepencies
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35ec8fc809841c0830224646fb57b0e4e4d40ef4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752299"
---
# <a name="configure-financial-cross-company-data-sharing"></a><span data-ttu-id="a8712-103">Konfigurowanie udostępniania danych finansowych między firmami</span><span class="sxs-lookup"><span data-stu-id="a8712-103">Configure financial cross-company data sharing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a8712-104">W tej procedurze pokazano sposób konfigurowania, włączania, sprawdzania poprawności i rozwiązywania konfliktów podczas udostępniania danych między firmami.</span><span class="sxs-lookup"><span data-stu-id="a8712-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="a8712-105">Procedura wykorzystuje firmę USMF i szablon udostępniania danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="a8712-105">It uses the USMF company and the Financial data sharing template.</span></span>

<span data-ttu-id="a8712-106">Ten przewodnik po zadaniach wymaga platformy Dynamics AX w wersji 7.1 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="a8712-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="a8712-107">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Obszary robocze > Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="a8712-107">Go to **Navigation pane > Modules > System administration > Workspaces > Data management**.</span></span>
2. <span data-ttu-id="a8712-108">Kliknij **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="a8712-108">Click **Import**.</span></span>
3. <span data-ttu-id="a8712-109">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a8712-109">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="a8712-110">W polu **Format danych źródłowych** wybierz typ „Paczki”.</span><span class="sxs-lookup"><span data-stu-id="a8712-110">In the **Source data format** field, select the 'Package' type.</span></span> <span data-ttu-id="a8712-111">Kliknij przycisk **Przekaż**.</span><span class="sxs-lookup"><span data-stu-id="a8712-111">Click **Upload**.</span></span> <span data-ttu-id="a8712-112">Przejdź do lokalizacji pliku pakietu szablonu udostępniania danych finansowych i wybierz ten plik.</span><span class="sxs-lookup"><span data-stu-id="a8712-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>
5. <span data-ttu-id="a8712-113">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a8712-113">Click **Save**.</span></span>
6. <span data-ttu-id="a8712-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="a8712-114">In the list, mark the selected row.</span></span> <span data-ttu-id="a8712-115">Zaznacz utworzoną właśnie zasadę udostępniania danych.</span><span class="sxs-lookup"><span data-stu-id="a8712-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="a8712-116">Kliknij **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="a8712-116">Click **Import**.</span></span>
8. <span data-ttu-id="a8712-117">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="a8712-117">Click **Close**.</span></span>
9. <span data-ttu-id="a8712-118">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="a8712-118">Refresh the page.</span></span>
10. <span data-ttu-id="a8712-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a8712-119">Close the page.</span></span>
11. <span data-ttu-id="a8712-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a8712-120">Close the page.</span></span>
12. <span data-ttu-id="a8712-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a8712-121">Close the page.</span></span>
13. <span data-ttu-id="a8712-122">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Administracja systemu > Ustawienia > Konfiguruj udostępnianie danych między firmami**.</span><span class="sxs-lookup"><span data-stu-id="a8712-122">Go to **Navigation pane > Modules > System administration > Setup > Configure cross-company data sharing**.</span></span>
14. <span data-ttu-id="a8712-123">Na liście znajdź i zaznacz **Dni płatności**.</span><span class="sxs-lookup"><span data-stu-id="a8712-123">In the list, find and select **Payment days**.</span></span>
15. <span data-ttu-id="a8712-124">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="a8712-124">Click **Add**.</span></span>
16. <span data-ttu-id="a8712-125">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="a8712-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="a8712-126">W polu **Firma** wpisz wartość „USSI”.</span><span class="sxs-lookup"><span data-stu-id="a8712-126">In the **Company** field, type 'USSI'.</span></span>
18. <span data-ttu-id="a8712-127">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="a8712-127">Click **Add**.</span></span>
19. <span data-ttu-id="a8712-128">W polu **Firma** wpisz wartość „USMF”.</span><span class="sxs-lookup"><span data-stu-id="a8712-128">In the **Company** field, type 'USMF'.</span></span>
20. <span data-ttu-id="a8712-129">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a8712-129">Click **Save**.</span></span>
21. <span data-ttu-id="a8712-130">Kliknij przycisk **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="a8712-130">Click **Enable**.</span></span>
22. <span data-ttu-id="a8712-131">Kliknij przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a8712-131">Click **Yes**.</span></span>
23. <span data-ttu-id="a8712-132">Kliknij opcję **Znajdź problemy z udostępnianiem**.</span><span class="sxs-lookup"><span data-stu-id="a8712-132">Click **Find sharing issues**.</span></span>
24. <span data-ttu-id="a8712-133">Kliknij przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a8712-133">Click **Yes**.</span></span>
25. <span data-ttu-id="a8712-134">Kliknij opcję **Aktualizuj wartość pola**.</span><span class="sxs-lookup"><span data-stu-id="a8712-134">Click **Update field value**.</span></span>
26. <span data-ttu-id="a8712-135">Kliknij opcję **Użyj wartości z firmy 1**.</span><span class="sxs-lookup"><span data-stu-id="a8712-135">Click **Use value from company 1**.</span></span>
27. <span data-ttu-id="a8712-136">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="a8712-136">Refresh the page.</span></span>
28. <span data-ttu-id="a8712-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a8712-137">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]