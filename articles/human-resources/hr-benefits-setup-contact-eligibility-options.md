---
title: Konfigurowanie opcji uprawnień kontaktów osobistych
description: W programie Microsoft Dynamics 365 Human Resources można skonfigurować opcje uprawnień dla kontaktów osobistych. Kontakty osobiste mogą być beneficjentami lub osobami na utrzymaniu.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d85677973f67f0c68de6c5ede62c142524939833
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054411"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="b14f8-104">Konfigurowanie opcji uprawnień kontaktów osobistych</span><span class="sxs-lookup"><span data-stu-id="b14f8-104">Configure personal contact eligibility options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b14f8-105">W tym artykule przedstawiono sposób konfigurowania typów kontaktów osobistych do używania w świadczeniach w programie Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b14f8-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b14f8-106">Kontakty osobiste mogą być beneficjentami lub osobami na utrzymaniu.</span><span class="sxs-lookup"><span data-stu-id="b14f8-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="b14f8-107">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Opcje uprawnień kontaktów osobistych**.</span><span class="sxs-lookup"><span data-stu-id="b14f8-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="b14f8-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b14f8-108">Select **New**.</span></span>

3. <span data-ttu-id="b14f8-109">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="b14f8-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="b14f8-110">Pole</span><span class="sxs-lookup"><span data-stu-id="b14f8-110">Field</span></span> | <span data-ttu-id="b14f8-111">Opis</span><span class="sxs-lookup"><span data-stu-id="b14f8-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="b14f8-112">**Opcja uprawnienia**</span><span class="sxs-lookup"><span data-stu-id="b14f8-112">**Eligibility option**</span></span> | <span data-ttu-id="b14f8-113">Unikatowa nazwa lub kod opcji uprawienia służący do identyfikacji opcji uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="b14f8-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="b14f8-114">**Opis**</span><span class="sxs-lookup"><span data-stu-id="b14f8-114">**Description**</span></span> | <span data-ttu-id="b14f8-115">Krótki opis opcji uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="b14f8-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="b14f8-116">**Kod uprawnienia osoby kontaktowej**</span><span class="sxs-lookup"><span data-stu-id="b14f8-116">**Contact eligibility code**</span></span> | <span data-ttu-id="b14f8-117">Kod systemowy, który najlepiej opisuje opcję osobistego uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="b14f8-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="b14f8-118">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="b14f8-118">You can choose from:</span></span> <ul><li><span data-ttu-id="b14f8-119">Pokrewieństwo</span><span class="sxs-lookup"><span data-stu-id="b14f8-119">Relationship</span></span></li><li><span data-ttu-id="b14f8-120">Uczeń lub student</span><span class="sxs-lookup"><span data-stu-id="b14f8-120">Student</span></span></li><li><span data-ttu-id="b14f8-121">Osoba na utrzymaniu przekraczająca granicę wieku</span><span class="sxs-lookup"><span data-stu-id="b14f8-121">Overage dependent</span></span></li><li><span data-ttu-id="b14f8-122">Niepełnosprawna osoba na utrzymaniu przekraczająca granicę wieku</span><span class="sxs-lookup"><span data-stu-id="b14f8-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="b14f8-123">**Stan**</span><span class="sxs-lookup"><span data-stu-id="b14f8-123">**Status**</span></span> | <span data-ttu-id="b14f8-124">Stan opcji uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="b14f8-124">The status of the eligibility option.</span></span> <span data-ttu-id="b14f8-125">Jeśli stan opcji uprawnienia jest ustawiony jako nieaktywny, nie można wybierać tej opcji uprawnienia kontaktu osobistego dla kontaktów osobistych.</span><span class="sxs-lookup"><span data-stu-id="b14f8-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="b14f8-126">**Pokrewieństwo**</span><span class="sxs-lookup"><span data-stu-id="b14f8-126">**Relationship**</span></span> | <span data-ttu-id="b14f8-127">Określa relację między kontaktem osobistym a pracownikiem etatowym.</span><span class="sxs-lookup"><span data-stu-id="b14f8-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="b14f8-128">To pole jest aktywne tylko wtedy, gdy kod uprawnienia kontaktu jest ustawiony jako Relacja.</span><span class="sxs-lookup"><span data-stu-id="b14f8-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="b14f8-129">**Wiek**</span><span class="sxs-lookup"><span data-stu-id="b14f8-129">**Age**</span></span> | <span data-ttu-id="b14f8-130">Maksymalny wiek uprawnionego kontaktu osobistego w planie świadczeń.</span><span class="sxs-lookup"><span data-stu-id="b14f8-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="b14f8-131">To pole jest aktywne tylko po wybraniu relacji.</span><span class="sxs-lookup"><span data-stu-id="b14f8-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="b14f8-132">Ten wiek jest porównywany z obliczonym wiekiem kontaktu osobistego.</span><span class="sxs-lookup"><span data-stu-id="b14f8-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="b14f8-133">Obliczony wiek to: (Data objęcia świadczeniem - data urodzenia kontaktu osobistego / 365)</span><span class="sxs-lookup"><span data-stu-id="b14f8-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="b14f8-134">Ta liczba jest zawsze liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="b14f8-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="b14f8-135">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b14f8-135">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]