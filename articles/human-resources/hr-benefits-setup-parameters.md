---
title: Konfigurowanie parametrów zarządzania świadczeniami i samoobsługi pracownika etatowego dla wszystkich firm
description: Konfigurowanie parametrów zarządzania świadczeniami i samoobsługi pracownika etatowego w Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 10f5310ba4feba4a196d02c406ff3217637e447e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791492"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a><span data-ttu-id="5f9e5-103">Konfigurowanie parametrów zarządzania świadczeniami i samoobsługi pracownika etatowego dla wszystkich firm</span><span class="sxs-lookup"><span data-stu-id="5f9e5-103">Set Benefits management and Employee self-service parameters for all companies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="5f9e5-104">Zanim będzie można konfigurować plany świadczeń w module Microsoft Dynamics 365 Human Resources, należy skonfigurować parametry obszaru roboczego Zarządzanie świadczeniami.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-104">Before you can set up benefit plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="5f9e5-105">Te parametry służą do ustawiania wartości domyślnych, kodów przyczyny i innych opcji.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-105">These parameters set default values, reason codes, and other options.</span></span> 

## <a name="configure-general-parameters"></a><span data-ttu-id="5f9e5-106">Konfigurowanie parametrów ogólnych</span><span class="sxs-lookup"><span data-stu-id="5f9e5-106">Configure general parameters</span></span>

1. <span data-ttu-id="5f9e5-107">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Udostępniane parametry Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-107">In the **Benefits management** workspace, under **Setup**, select **Human Resources Shared Parameters**.</span></span>

2. <span data-ttu-id="5f9e5-108">Na karcie **Zarządzanie świadczeniami** wprowadź wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="5f9e5-108">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="5f9e5-109">Pole</span><span class="sxs-lookup"><span data-stu-id="5f9e5-109">Field</span></span> | <span data-ttu-id="5f9e5-110">opis</span><span class="sxs-lookup"><span data-stu-id="5f9e5-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="5f9e5-111">**Kraj/region**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-111">**Country/region**</span></span> | <span data-ttu-id="5f9e5-112">Pole **Kraj/region** określa kolejność wyświetlania kodów pocztowych/jednostek administracyjnych.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="5f9e5-113">Wybrany kraj jest wyświetlany jako pierwszy na liście rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="5f9e5-114">**Kod przyczyny rejestracji**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-114">**Enrollment reason code**</span></span> | <span data-ttu-id="5f9e5-115">Umożliwia wybór domyślnego kodu przyczyny, który będzie używany podczas tworzenia planów dla pracowników etatowych w trakcie przetwarzania otwartej rejestracji.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="5f9e5-116">**Kod powodu anulowania**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-116">**Cancellation reason code**</span></span> | <span data-ttu-id="5f9e5-117">Kod przyczyny, który ma być używany podczas anulowania planu świadczeń pracowniczych.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="5f9e5-118">Jest wyświetlany w oknie dialogowym podczas procesu anulowania.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="5f9e5-119">W razie potrzeby użytkownicy mogą go zmienić w polu **Kody powodu anulowania**.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="5f9e5-120">**Kod przyczyny ponownego otwarcia**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-120">**Reopen reason code**</span></span> | <span data-ttu-id="5f9e5-121">Kod przyczyny, który ma być używany podczas ponownego otwarcia planu świadczeń pracowniczych.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="5f9e5-122">Jest wyświetlany w oknie dialogowym podczas procesu anulowania.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="5f9e5-123">W razie potrzeby użytkownicy mogą go zmienić w polu **Kody przyczyny ponownego otwarcia**.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="5f9e5-124">**Kod przyczyny zdarzenia zmiany sytuacji życiowej**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-124">**Life event reason code**</span></span> | <span data-ttu-id="5f9e5-125">Kod przyczyny, który ma być używany w razie zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="5f9e5-126">**Kod przyczyny zmiany stawki**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-126">**Rate change reason code**</span></span> | <span data-ttu-id="5f9e5-127">Kod przyczyny, który ma być używany podczas anulowania i ponownego otwierania planu świadczeń pracowniczych w trakcie procesu aktualizacji zmiany stawki.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="5f9e5-128">Wskazuje, które rekordy zostały zmienione przez proces aktualizacji zmiany stawki.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="5f9e5-129">**Roczne wynagrodzenie z tytułu świadczenia**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-129">**Benefits annual salary**</span></span> | <span data-ttu-id="5f9e5-130">Umożliwia ustawienie kwoty **Świadczenia do wynagrodzenia rocznego** dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-130">Enables you to set a **Benefits annual salary** amount for an employee.</span></span> <span data-ttu-id="5f9e5-131">Przy ustalaniu kwot pokrycia w Human Resources zamiast kwoty rocznej dla stałej płacy będzie używana kwota **Świadczenia do wynagrodzenia rocznego**.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-131">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> |
   | <span data-ttu-id="5f9e5-132">**Nowo zatrudniona osoba kwalifikuje się**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-132">**New hire eligible**</span></span> | <span data-ttu-id="5f9e5-133">Określa, czy nowo zatrudnione osoby kwalifikują się do planu.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-133">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="5f9e5-134">**Okres rejestracji nowo zatrudnionej osoby**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-134">**New hire enrollment period**</span></span> | <span data-ttu-id="5f9e5-135">Okres, w którym jest dozwolone rejestrowanie nowo zatrudnionej osoby.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-135">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="5f9e5-136">**Uwaga**: to ustawienie zastępuje każdy okres rejestracji nowo zatrudnionej osoby ustawiony w regule uprawnienia do planu.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-136">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> |
   | <span data-ttu-id="5f9e5-137">**Domyślna częstotliwość wypłat**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-137">**Default pay frequency**</span></span> | <span data-ttu-id="5f9e5-138">Domyślna częstotliwość płac, która ma być używana przy dodawaniu nowych pracowników.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-138">The default pay frequency to use when new workers are added.</span></span> |
   | <span data-ttu-id="5f9e5-139">**Zdarzenia zmiany sytuacji życiowej zostały włączone**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-139">**Life events enabled**</span></span> | <span data-ttu-id="5f9e5-140">Włącza obsługę zmian sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-140">Enables life events.</span></span> |
   | <span data-ttu-id="5f9e5-141">**Ukryj starsze formularze świadczeń**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-141">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="5f9e5-142">Umożliwia ukrycie starszych formularzy świadczeń.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-142">Allows you to hide legacy benefit forms.</span></span> |
   | <span data-ttu-id="5f9e5-143">**Weryfikacja świadczenia**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-143">**Benefit verification**</span></span> | <span data-ttu-id="5f9e5-144">Tekst weryfikacyjny używany podczas realizacji świadczeń w samoobsłudze.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-144">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="5f9e5-145">**Automatyczny wybór osób wyznaczonych**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-145">**Auto select designees**</span></span> | <span data-ttu-id="5f9e5-146">Określa, czy osoby na utrzymaniu i beneficjenci mają być automatycznie wybierani na podstawie ich uprawnień do opcji planu.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-146">Specifies whether to automatically select dependents and beneficiaries, based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="5f9e5-147">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-147">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="5f9e5-148">Konfigurowanie parametrów obszaru Samoobsługa pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="5f9e5-148">Configure Employee self-service parameters</span></span>

1. <span data-ttu-id="5f9e5-149">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-149">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="5f9e5-150">Na karcie **Zarządzanie świadczeniami** wprowadź wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="5f9e5-150">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="5f9e5-151">Pole</span><span class="sxs-lookup"><span data-stu-id="5f9e5-151">Field</span></span> | <span data-ttu-id="5f9e5-152">opis</span><span class="sxs-lookup"><span data-stu-id="5f9e5-152">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="5f9e5-153">**Weryfikacja świadczenia**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-153">**Benefit verification**</span></span> | <span data-ttu-id="5f9e5-154">Tekst weryfikacyjny używany podczas realizacji świadczeń w samoobsłudze.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-154">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="5f9e5-155">**Automatyczny wybór osób wyznaczonych**</span><span class="sxs-lookup"><span data-stu-id="5f9e5-155">**Auto select designees**</span></span> | <span data-ttu-id="5f9e5-156">Określa, czy osoby na utrzymaniu i beneficjenci mają być automatycznie wybierane na podstawie ich uprawnień do opcji planu.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-156">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="5f9e5-157">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-157">Select **Save**.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]