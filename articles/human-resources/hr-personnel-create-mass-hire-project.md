---
title: Tworzenie projektu zatrudnienia grupowego
description: Ta procedura prowadzi przez proces konfigurowania projektu zatrudnienia grupowego.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject,  HRMMassHireLineCreate, HcmJobLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6d553c5762dcb456bd7178858c09129bc154349
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467056"
---
# <a name="create-a-mass-hire-project"></a><span data-ttu-id="67ae9-103">Tworzenie projektu zatrudnienia grupowego</span><span class="sxs-lookup"><span data-stu-id="67ae9-103">Create a mass hire project</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="67ae9-104">Ta procedura prowadzi przez proces konfigurowania projektu zatrudnienia grupowego.</span><span class="sxs-lookup"><span data-stu-id="67ae9-104">This procedure walks through the process of setting up a mass hire project.</span></span> <span data-ttu-id="67ae9-105">Osoba rekrutująca może używać projektów zatrudnienia grupowego, aby łatwo tworzyć wiele stanowisk i zatrudniać na nie wielu pracowników.</span><span class="sxs-lookup"><span data-stu-id="67ae9-105">A recruiter can use mass hire projects to easily create multiple positions and hire a number of workers into those positions.</span></span> <span data-ttu-id="67ae9-106">Aby rozpocząć tę procedurę, wybierz kolejno opcje Zasoby ludzkie > Rekrutacja > Projekty zatrudnienia grupowego.</span><span class="sxs-lookup"><span data-stu-id="67ae9-106">To begin this procedure, go to Human resources > Recruitment > Mass hire projects.</span></span> <span data-ttu-id="67ae9-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="67ae9-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="67ae9-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="67ae9-108">Click New.</span></span>
2. <span data-ttu-id="67ae9-109">W polu Projekt zatrudnienia grupowego wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="67ae9-109">In the Mass hire project field, type a value.</span></span>
3. <span data-ttu-id="67ae9-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="67ae9-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="67ae9-111">W polu Początek projektu wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="67ae9-111">In the Project start field, enter a date.</span></span>
5. <span data-ttu-id="67ae9-112">W polu Koniec projektu wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="67ae9-112">In the Project end field, enter a date.</span></span>
6. <span data-ttu-id="67ae9-113">Kliknij przycisk Otwórz projekt.</span><span class="sxs-lookup"><span data-stu-id="67ae9-113">Click Open project.</span></span>
7. <span data-ttu-id="67ae9-114">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="67ae9-114">Click Yes.</span></span>
8. <span data-ttu-id="67ae9-115">Kliknij przycisk Utwórz stanowiska.</span><span class="sxs-lookup"><span data-stu-id="67ae9-115">Click Create positions.</span></span>
9. <span data-ttu-id="67ae9-116">W polu Ilość wprowadź liczbę stanowisk, jaką chcesz utworzyć.</span><span class="sxs-lookup"><span data-stu-id="67ae9-116">In the Quantity field, enter the number of positions that you want to create</span></span>
    * <span data-ttu-id="67ae9-117">Data początkowa będzie datą zatrudnienia dla nowych pracowników.</span><span class="sxs-lookup"><span data-stu-id="67ae9-117">The Start date will become the Hire date for the new workers.</span></span>  
    * <span data-ttu-id="67ae9-118">Data końcowa będzie datą zakończenia zatrudnienia dla nowych pracowników.</span><span class="sxs-lookup"><span data-stu-id="67ae9-118">The End date will be the Termination date for the new workers.</span></span>  
    * <span data-ttu-id="67ae9-119">Określ, czy nowi pracownicy będą pracownikami czy zleceniobiorcami.</span><span class="sxs-lookup"><span data-stu-id="67ae9-119">Specify whether the new workers will be Employees or Contractors.</span></span>  
10. <span data-ttu-id="67ae9-120">W polu Zadanie kliknij przycisk rozwijany i wybierz zadanie, dla którego chcesz utworzyć stanowiska.</span><span class="sxs-lookup"><span data-stu-id="67ae9-120">In the Job field, click the drop-down button to select the job to create the positions for.</span></span>
11. <span data-ttu-id="67ae9-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="67ae9-121">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="67ae9-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="67ae9-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="67ae9-123">Domyślna wartość równoważnika pełnego etatu będzie pochodziła z wybranego zadania.</span><span class="sxs-lookup"><span data-stu-id="67ae9-123">The default full-time equivalent value will come from the selected job.</span></span> <span data-ttu-id="67ae9-124">W razie potrzeby można to zmienić.</span><span class="sxs-lookup"><span data-stu-id="67ae9-124">You can change this if needed.</span></span>  
    * <span data-ttu-id="67ae9-125">Opcjonalnie wybierz dział dla nowych stanowisk.</span><span class="sxs-lookup"><span data-stu-id="67ae9-125">Optionally, select the Department for the new positions.</span></span>  
13. <span data-ttu-id="67ae9-126">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="67ae9-126">Click OK.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]