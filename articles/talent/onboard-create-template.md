---
title: Tworzenie szablonu wdrażania do pracy w Dynamics 365 Talent - Onboard
description: W tym temacie wyjaśniono użycie Dynamics 365 Talent - Onboard do utworzenia szablonu dla przewodnika wdrażania do pracy dla nowych pracowników. To zadanie jest podstawowym pierwszym krokiem w zarządzaniu kapitałem ludzkim (HCM) zatrudniania do wycofania strategii.
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 55853418eacd179b7bb50b7e4385300bdcb27abe
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812909"
---
# <a name="create-an-onboarding-template-by-using-dynamics-365-talent---onboard"></a><span data-ttu-id="13122-104">Tworzenie szablonu wdrażania do pracy w Dynamics 365 Talent - Onboard</span><span class="sxs-lookup"><span data-stu-id="13122-104">Create an onboarding template by using Dynamics 365 Talent - Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="13122-105">Microsoft Dynamics 365 Talent: Onboard udostępnia różne szablony, które mogą pomóc Ci utworzyć przewodnik wdrażania do pracy tak szybko, jak to możliwe.</span><span class="sxs-lookup"><span data-stu-id="13122-105">Microsoft Dynamics 365 Talent: Onboard provides various templates that can help you create an onboarding guide as quickly as possible.</span></span> <span data-ttu-id="13122-106">Można użyć jednego lub więcej z tych szablonów, lub można tworzyć własne szablony.</span><span class="sxs-lookup"><span data-stu-id="13122-106">You can use one or more of these templates, or you can create your own templates.</span></span> <span data-ttu-id="13122-107">Onboard zawiera przykładowy tekst, który można użyć podczas tworzenia własnych szablonów.</span><span class="sxs-lookup"><span data-stu-id="13122-107">Onboard provides sample text that you can use when you create your own templates.</span></span> <span data-ttu-id="13122-108">W związku z tym proces jest łatwy, nawet jeśli zaczniesz od zera.</span><span class="sxs-lookup"><span data-stu-id="13122-108">Therefore, the process is easy even if you start from scratch.</span></span>

## <a name="create-an-onboarding-template-from-an-existing-template"></a><span data-ttu-id="13122-109">Tworzenie szablonu wdrażania do pracy z istniejącego szablonu</span><span class="sxs-lookup"><span data-stu-id="13122-109">Create an onboarding template from an existing template</span></span>

1. <span data-ttu-id="13122-110">W menu po lewej stronie wybierz **Szablony**.</span><span class="sxs-lookup"><span data-stu-id="13122-110">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="13122-111">W obszarze **Popularne szablony z galerii** lub **Moje szablony** wybierz szablon.</span><span class="sxs-lookup"><span data-stu-id="13122-111">Under **Popular templates from the gallery** or **My templates**, select a template.</span></span> <span data-ttu-id="13122-112">Aby wyświetlić więcej szablonów, wybierz **Więcej w galerii szablonów**.</span><span class="sxs-lookup"><span data-stu-id="13122-112">To view more templates, select **More in template gallery**.</span></span>
3. <span data-ttu-id="13122-113">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="13122-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="13122-114">Jeśli szablon znajduje się w galerii, wybierz opcję **Zapisz jako mój szablon**, wprowadź nową nazwę szablonu i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="13122-114">If the template is from the gallery, select **Save as my template**, enter a new name for the template, and select **Save**.</span></span>
    - <span data-ttu-id="13122-115">Jeśli szablon znajduje się w **Moje szablony**, wybierz opcję **Zapisz jako szablon**, wprowadź nową nazwę szablonu i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="13122-115">If the template is from **My templates**, select **Save as template**, enter a new name for the template, and select **Save**.</span></span>

    <span data-ttu-id="13122-116">[![Tworzenie szablonu z istniejącego szablonu](./media/onboard-save-template.png)](./media/onboard-save-template.png)</span><span class="sxs-lookup"><span data-stu-id="13122-116">[![Creating a template from an existing template](./media/onboard-save-template.png)](./media/onboard-save-template.png)</span></span>

## <a name="create-a-new-onboarding-template"></a><span data-ttu-id="13122-117">Tworzenie nowego szablonu wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="13122-117">Create a new onboarding template</span></span>

1. <span data-ttu-id="13122-118">W menu po lewej stronie wybierz **Szablony**.</span><span class="sxs-lookup"><span data-stu-id="13122-118">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="13122-119">W obszarze **Moje szablony** wybierz kafelek **Dodaj** (znak plus \[**+**\]).</span><span class="sxs-lookup"><span data-stu-id="13122-119">Under **My templates**, select the **Add** (plus sign \[**+**\]) tile.</span></span>

    <span data-ttu-id="13122-120">[![Tworzenie nowego szablonu](./media/onboard-create-new-template.png)](./media/onboard-create-new-template.png)</span><span class="sxs-lookup"><span data-stu-id="13122-120">[![Creating a new template](./media/onboard-create-new-template.png)](./media/onboard-create-new-template.png)</span></span>

3. <span data-ttu-id="13122-121">W okienku dialogowym **Stwórz szablon przewodnika** nadaj szablonowi nazwę, a następnie kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="13122-121">In the **Create a guide template** dialog box, enter a name for the template, and then select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="13122-122">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="13122-122">Next steps</span></span>

- [<span data-ttu-id="13122-123">Edytowanie przewodników i szablonów wdrażania do pracy</span><span class="sxs-lookup"><span data-stu-id="13122-123">Edit onboarding guides and templates</span></span>](./onboard-edit-guides-templates.md)
- [<span data-ttu-id="13122-124">Udostępnianie zawartości innym współautorom</span><span class="sxs-lookup"><span data-stu-id="13122-124">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="13122-125">Wyświetlanie stanu zadań i dołączania pracowników</span><span class="sxs-lookup"><span data-stu-id="13122-125">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="13122-126">Tworzenie zespołów rekrutacyjnych w Onboard</span><span class="sxs-lookup"><span data-stu-id="13122-126">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="13122-127">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="13122-127">See also</span></span>

- [<span data-ttu-id="13122-128">Wypróbuj lub kup aplikację Onboard</span><span class="sxs-lookup"><span data-stu-id="13122-128">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="13122-129">Nowości i zmiany w Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="13122-129">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="13122-130">Plany wydań</span><span class="sxs-lookup"><span data-stu-id="13122-130">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="13122-131">Uzyskiwanie pomocy technicznej dotyczącej rozwiązania Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="13122-131">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
