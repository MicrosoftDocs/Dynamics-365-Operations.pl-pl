---
title: Ustawianie parametrów obszaru roboczego Zarządzanie świadczeniami
description: Tu opisano konfigurowanie parametrów obszaru roboczego Zarządzanie świadczeniami dostępnego w programie Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 9d6d463df08b9ae68047f09316f19e98740a8441
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229770"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="bb81c-103">Ustawianie parametrów zarządzania świadczeniami</span><span class="sxs-lookup"><span data-stu-id="bb81c-103">Set Benefits management parameters</span></span>

<span data-ttu-id="bb81c-104">Zanim będzie można konfigurować plany urlopów w module Microsoft Dynamics 365 Human Resources, należy skonfigurować parametry obszaru roboczego Zarządzanie świadczeniami.</span><span class="sxs-lookup"><span data-stu-id="bb81c-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="bb81c-105">Te parametry służą do ustawiania wartości domyślnych, kodów przyczyny i innych opcji.</span><span class="sxs-lookup"><span data-stu-id="bb81c-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="bb81c-106">Konfigurowanie parametrów ogólnych</span><span class="sxs-lookup"><span data-stu-id="bb81c-106">Configure general parameters</span></span>

1. <span data-ttu-id="bb81c-107">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="bb81c-107">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="bb81c-108">Na karcie **Ogólne** wprowadź wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="bb81c-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="bb81c-109">Pole</span><span class="sxs-lookup"><span data-stu-id="bb81c-109">Field</span></span> | <span data-ttu-id="bb81c-110">Opis</span><span class="sxs-lookup"><span data-stu-id="bb81c-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="bb81c-111">**Kraj/region**</span><span class="sxs-lookup"><span data-stu-id="bb81c-111">**Country/region**</span></span> | <span data-ttu-id="bb81c-112">Pole **Kraj/region** określa kolejność wyświetlania kodów pocztowych/jednostek administracyjnych.</span><span class="sxs-lookup"><span data-stu-id="bb81c-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="bb81c-113">Wybrany kraj jest wyświetlany jako pierwszy na liście rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="bb81c-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="bb81c-114">**Kod przyczyny rejestracji**</span><span class="sxs-lookup"><span data-stu-id="bb81c-114">**Enrollment reason code**</span></span> | <span data-ttu-id="bb81c-115">Umożliwia wybór domyślnego kodu przyczyny, który będzie używany podczas tworzenia planów dla pracowników etatowych w trakcie przetwarzania otwartej rejestracji.</span><span class="sxs-lookup"><span data-stu-id="bb81c-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="bb81c-116">**Kod powodu anulowania**</span><span class="sxs-lookup"><span data-stu-id="bb81c-116">**Cancellation reason code**</span></span> | <span data-ttu-id="bb81c-117">Kod przyczyny, który ma być używany podczas anulowania planu świadczeń pracowniczych.</span><span class="sxs-lookup"><span data-stu-id="bb81c-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="bb81c-118">Jest wyświetlany w oknie dialogowym podczas procesu anulowania.</span><span class="sxs-lookup"><span data-stu-id="bb81c-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="bb81c-119">W razie potrzeby użytkownicy mogą go zmienić w polu **Kody powodu anulowania**.</span><span class="sxs-lookup"><span data-stu-id="bb81c-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="bb81c-120">**Kod przyczyny ponownego otwarcia**</span><span class="sxs-lookup"><span data-stu-id="bb81c-120">**Reopen reason code**</span></span> | <span data-ttu-id="bb81c-121">Kod przyczyny, który ma być używany podczas ponownego otwarcia planu świadczeń pracowniczych.</span><span class="sxs-lookup"><span data-stu-id="bb81c-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="bb81c-122">Jest wyświetlany w oknie dialogowym podczas procesu anulowania.</span><span class="sxs-lookup"><span data-stu-id="bb81c-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="bb81c-123">W razie potrzeby użytkownicy mogą go zmienić w polu **Kody przyczyny ponownego otwarcia**.</span><span class="sxs-lookup"><span data-stu-id="bb81c-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="bb81c-124">**Kod przyczyny zdarzenia zmiany sytuacji życiowej**</span><span class="sxs-lookup"><span data-stu-id="bb81c-124">**Life event reason code**</span></span> | <span data-ttu-id="bb81c-125">Kod przyczyny, który ma być używany w razie zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="bb81c-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="bb81c-126">**Kod przyczyny zmiany stawki**</span><span class="sxs-lookup"><span data-stu-id="bb81c-126">**Rate change reason code**</span></span> | <span data-ttu-id="bb81c-127">Kod przyczyny, który ma być używany podczas anulowania i ponownego otwierania planu świadczeń pracowniczych w trakcie procesu aktualizacji zmiany stawki.</span><span class="sxs-lookup"><span data-stu-id="bb81c-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="bb81c-128">Wskazuje, które rekordy zostały zmienione przez proces aktualizacji zmiany stawki.</span><span class="sxs-lookup"><span data-stu-id="bb81c-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="bb81c-129">**Nowo zatrudniona osoba kwalifikuje się**</span><span class="sxs-lookup"><span data-stu-id="bb81c-129">**New hire eligible**</span></span> | <span data-ttu-id="bb81c-130">Określa, czy nowo zatrudnione osoby kwalifikują się do planu.</span><span class="sxs-lookup"><span data-stu-id="bb81c-130">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="bb81c-131">**Okres rejestracji nowo zatrudnionej osoby**</span><span class="sxs-lookup"><span data-stu-id="bb81c-131">**New hire enrollment period**</span></span> | <span data-ttu-id="bb81c-132">Okres, w którym jest dozwolone rejestrowanie nowo zatrudnionej osoby.</span><span class="sxs-lookup"><span data-stu-id="bb81c-132">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="bb81c-133">**Uwaga**: to ustawienie zastępuje każdy okres rejestracji nowo zatrudnionej osoby ustawiony w regule uprawnienia do planu.</span><span class="sxs-lookup"><span data-stu-id="bb81c-133">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> | 
   | <span data-ttu-id="bb81c-134">**Zdarzenia zmiany sytuacji życiowej zostały włączone**</span><span class="sxs-lookup"><span data-stu-id="bb81c-134">**Life events enabled**</span></span> | <span data-ttu-id="bb81c-135">Włącza obsługę zmian sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="bb81c-135">Enables life events.</span></span> |
   | <span data-ttu-id="bb81c-136">**Ukryj starsze formularze świadczeń**</span><span class="sxs-lookup"><span data-stu-id="bb81c-136">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="bb81c-137">Umożliwia ukrycie starszych formularzy świadczeń.</span><span class="sxs-lookup"><span data-stu-id="bb81c-137">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="bb81c-138">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bb81c-138">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="bb81c-139">Konfigurowanie parametrów obszaru Samoobsługa pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="bb81c-139">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="bb81c-140">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="bb81c-140">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="bb81c-141">Na karcie **Samoobsługa pracownika etatowego** wprowadź wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="bb81c-141">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="bb81c-142">Pole</span><span class="sxs-lookup"><span data-stu-id="bb81c-142">Field</span></span> | <span data-ttu-id="bb81c-143">Opis</span><span class="sxs-lookup"><span data-stu-id="bb81c-143">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="bb81c-144">**Weryfikacja świadczenia**</span><span class="sxs-lookup"><span data-stu-id="bb81c-144">**Benefit verification**</span></span> | <span data-ttu-id="bb81c-145">Tekst weryfikacyjny używany podczas realizacji świadczeń w samoobsłudze.</span><span class="sxs-lookup"><span data-stu-id="bb81c-145">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="bb81c-146">**Automatyczny wybór osób wyznaczonych**</span><span class="sxs-lookup"><span data-stu-id="bb81c-146">**Auto select designees**</span></span> | <span data-ttu-id="bb81c-147">Określa, czy osoby na utrzymaniu i beneficjenci mają być automatycznie wybierane na podstawie ich uprawnień do opcji planu.</span><span class="sxs-lookup"><span data-stu-id="bb81c-147">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="bb81c-148">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bb81c-148">Select **Save**.</span></span>
