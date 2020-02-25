---
title: Przetwarzanie wybranych zmian sytuacji życiowej
description: W programie Microsoft Dynamics 365 Human Resources można przetwarzać zmiany sytuacji życiowej.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f9bce9394a361bbecfcc0531c5d7ebe9302c8f11
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010215"
---
# <a name="process-life-event-changes"></a><span data-ttu-id="e4e99-103">Przetwarzanie wybranych zmian sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="e4e99-103">Process life event changes</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="e4e99-104">W programie Microsoft Dynamics 365 Human Resources można przetwarzać dwa rodzaje zmian sytuacji życiowej:</span><span class="sxs-lookup"><span data-stu-id="e4e99-104">Process life event changes in Microsoft Dynamics 365 Human Resources for two life event changes:</span></span>

- <span data-ttu-id="e4e99-105">Zmiany związane z narodzinami</span><span class="sxs-lookup"><span data-stu-id="e4e99-105">Birthday changes</span></span>
- <span data-ttu-id="e4e99-106">Zmiany wygaśnięcia zastąpienia reguły uprawnienia</span><span class="sxs-lookup"><span data-stu-id="e4e99-106">Eligibility rule override expiration changes</span></span> 

1. <span data-ttu-id="e4e99-107">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Przetwarzanie zmian zdarzeń sytuacji życiowej**.</span><span class="sxs-lookup"><span data-stu-id="e4e99-107">In the **Benefits management** workspace, under **Processing**, select **Life event change processing**.</span></span>

2. <span data-ttu-id="e4e99-108">W oknie dialogowym **Uruchom proces zmian zdarzenia zmiany sytuacji życiowej** określ wartości następujących pól:</span><span class="sxs-lookup"><span data-stu-id="e4e99-108">In the **Run life event change process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="e4e99-109">Pole</span><span class="sxs-lookup"><span data-stu-id="e4e99-109">Field</span></span> | <span data-ttu-id="e4e99-110">Opis</span><span class="sxs-lookup"><span data-stu-id="e4e99-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="e4e99-111">Okres rejestracji</span><span class="sxs-lookup"><span data-stu-id="e4e99-111">Enrollment period</span></span> | <span data-ttu-id="e4e99-112">Okres rejestracji, dla którego mają być przetwarzane zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="e4e99-112">The enrollment period to process life event changes for.</span></span> |
   | <span data-ttu-id="e4e99-113">Firma</span><span class="sxs-lookup"><span data-stu-id="e4e99-113">Legal entity</span></span> | <span data-ttu-id="e4e99-114">Firma, dla której mają być przetwarzane zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="e4e99-114">The legal entity to process life event changes for.</span></span> |

3. <span data-ttu-id="e4e99-115">Jeśli chcesz uruchomić ten proces w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="e4e99-115">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="e4e99-116">Umożliwia wprowadzanie informacji o przetwarzaniu.</span><span class="sxs-lookup"><span data-stu-id="e4e99-116">Enter information for the process.</span></span>

   2. <span data-ttu-id="e4e99-117">Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4e99-117">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="e4e99-118">Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4e99-118">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="e4e99-119">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4e99-119">Select **OK**.</span></span> <span data-ttu-id="e4e99-120">Proces będzie uruchamiany z parametrami określonymi przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e4e99-120">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="e4e99-121">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4e99-121">Select **OK**.</span></span>
