---
title: Konfigurowanie opcji uprawnień kontaktów osobistych
description: W programie Microsoft Dynamics 365 Human Resources można skonfigurować opcje uprawnień dla kontaktów osobistych. Kontakty osobiste mogą być beneficjentami lub osobami na utrzymaniu.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a50c5e54d224a2f8607284eb105381ffb6ef7ad9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010225"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="88ebd-104">Konfigurowanie opcji uprawnień kontaktów osobistych</span><span class="sxs-lookup"><span data-stu-id="88ebd-104">Configure personal contact eligibility options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="88ebd-105">W tym artykule przedstawiono sposób konfigurowania typów kontaktów osobistych do używania w świadczeniach w programie Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="88ebd-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="88ebd-106">Kontakty osobiste mogą być beneficjentami lub osobami na utrzymaniu.</span><span class="sxs-lookup"><span data-stu-id="88ebd-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="88ebd-107">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Opcje uprawnień kontaktów osobistych**.</span><span class="sxs-lookup"><span data-stu-id="88ebd-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="88ebd-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="88ebd-108">Select **New**.</span></span>

3. <span data-ttu-id="88ebd-109">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="88ebd-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="88ebd-110">Pole</span><span class="sxs-lookup"><span data-stu-id="88ebd-110">Field</span></span> | <span data-ttu-id="88ebd-111">Opis</span><span class="sxs-lookup"><span data-stu-id="88ebd-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="88ebd-112">**Opcja uprawnienia**</span><span class="sxs-lookup"><span data-stu-id="88ebd-112">**Eligibility option**</span></span> | <span data-ttu-id="88ebd-113">Unikatowa nazwa lub kod opcji uprawienia służący do identyfikacji opcji uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="88ebd-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="88ebd-114">**Opis**</span><span class="sxs-lookup"><span data-stu-id="88ebd-114">**Description**</span></span> | <span data-ttu-id="88ebd-115">Krótki opis opcji uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="88ebd-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="88ebd-116">**Kod uprawnienia osoby kontaktowej**</span><span class="sxs-lookup"><span data-stu-id="88ebd-116">**Contact eligibility code**</span></span> | <span data-ttu-id="88ebd-117">Kod systemowy, który najlepiej opisuje opcję osobistego uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="88ebd-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="88ebd-118">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="88ebd-118">You can choose from:</span></span> <ul><li><span data-ttu-id="88ebd-119">Pokrewieństwo</span><span class="sxs-lookup"><span data-stu-id="88ebd-119">Relationship</span></span></li><li><span data-ttu-id="88ebd-120">Uczeń lub student</span><span class="sxs-lookup"><span data-stu-id="88ebd-120">Student</span></span></li><li><span data-ttu-id="88ebd-121">Osoba na utrzymaniu przekraczająca granicę wieku</span><span class="sxs-lookup"><span data-stu-id="88ebd-121">Overage dependent</span></span></li><li><span data-ttu-id="88ebd-122">Niepełnosprawna osoba na utrzymaniu przekraczająca granicę wieku</span><span class="sxs-lookup"><span data-stu-id="88ebd-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="88ebd-123">**Stan**</span><span class="sxs-lookup"><span data-stu-id="88ebd-123">**Status**</span></span> | <span data-ttu-id="88ebd-124">Stan opcji uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="88ebd-124">The status of the eligibility option.</span></span> <span data-ttu-id="88ebd-125">Jeśli stan opcji uprawnienia jest ustawiony jako nieaktywny, nie można wybierać tej opcji uprawnienia kontaktu osobistego dla kontaktów osobistych.</span><span class="sxs-lookup"><span data-stu-id="88ebd-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="88ebd-126">**Pokrewieństwo**</span><span class="sxs-lookup"><span data-stu-id="88ebd-126">**Relationship**</span></span> | <span data-ttu-id="88ebd-127">Określa relację między kontaktem osobistym a pracownikiem etatowym.</span><span class="sxs-lookup"><span data-stu-id="88ebd-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="88ebd-128">To pole jest aktywne tylko wtedy, gdy kod uprawnienia kontaktu jest ustawiony jako Relacja.</span><span class="sxs-lookup"><span data-stu-id="88ebd-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="88ebd-129">**Wiek**</span><span class="sxs-lookup"><span data-stu-id="88ebd-129">**Age**</span></span> | <span data-ttu-id="88ebd-130">Maksymalny wiek uprawnionego kontaktu osobistego w planie świadczeń.</span><span class="sxs-lookup"><span data-stu-id="88ebd-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="88ebd-131">To pole jest aktywne tylko po wybraniu relacji.</span><span class="sxs-lookup"><span data-stu-id="88ebd-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="88ebd-132">Ten wiek jest porównywany z obliczonym wiekiem kontaktu osobistego.</span><span class="sxs-lookup"><span data-stu-id="88ebd-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="88ebd-133">Obliczony wiek to: (Data objęcia świadczeniem - data urodzenia kontaktu osobistego / 365)</span><span class="sxs-lookup"><span data-stu-id="88ebd-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="88ebd-134">Ta liczba jest zawsze liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="88ebd-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="88ebd-135">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="88ebd-135">Select **Save**.</span></span> 
