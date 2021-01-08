---
title: Użytkownicy usługi Attract nie mogą ubiegać się o pracę z portalu kariery
description: W tym temacie wyjaśniono sposób rozwiązania problemu polegającego na tym, że przyciąganie użytkowników nie może być stosowane do zadań z portalu kariery.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462199"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a><span data-ttu-id="31108-103">Użytkownicy usługi Attract nie mogą ubiegać się o pracę z portalu kariery</span><span class="sxs-lookup"><span data-stu-id="31108-103">Attract users can't apply for jobs from career portal</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="31108-104">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="31108-104">Issue</span></span>

<span data-ttu-id="31108-105">Użytkownicy usługi Attract nie mogą ubiegać się o pracę z portalu kariery.</span><span class="sxs-lookup"><span data-stu-id="31108-105">Attract users can't apply for jobs from the career portal.</span></span> <span data-ttu-id="31108-106">Przy próbie zastosowania się do zadania, które zostało utworzone w systemie Dynamics 365 Talent: Attract, przeglądarka ładuje stronę w sposób ciągły i nie powoduje wykonania tej akcji.</span><span class="sxs-lookup"><span data-stu-id="31108-106">When they try to apply for a job that was created in Dynamics 365 Talent: Attract, the browser loads the page continuously and doesn't complete the action.</span></span>

## <a name="cause"></a><span data-ttu-id="31108-107">Powód</span><span class="sxs-lookup"><span data-stu-id="31108-107">Cause</span></span>

<span data-ttu-id="31108-108">Ten problem występuje, gdy zespół relacji talentów nie ma roli użytkownika talentów.</span><span class="sxs-lookup"><span data-stu-id="31108-108">This problem occurs when the Talent Relationship Team doesn't have the Talent user role.</span></span>

## <a name="resolution"></a><span data-ttu-id="31108-109">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="31108-109">Resolution</span></span>

<span data-ttu-id="31108-110">Przypisz rolę użytkownika talentów do zespołu relacji talentów.</span><span class="sxs-lookup"><span data-stu-id="31108-110">Assign the Talent user role to the Talent Relationship Team.</span></span>

1. <span data-ttu-id="31108-111">Zaloguj się do [Centrum administracyjnego Power Platform](https://admin.powerplatform.microsoft.com)z dowolnego z następujących poświadczeń administratora:</span><span class="sxs-lookup"><span data-stu-id="31108-111">Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com) with any of the following admin credentials:</span></span>

   - <span data-ttu-id="31108-112">administrator Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="31108-112">Dynamics 365 admin</span></span>
   - <span data-ttu-id="31108-113">Administrator globalny</span><span class="sxs-lookup"><span data-stu-id="31108-113">Global admin</span></span>
   - <span data-ttu-id="31108-114">Administrator Power Platform</span><span class="sxs-lookup"><span data-stu-id="31108-114">Power Platform admin</span></span>

2. <span data-ttu-id="31108-115">W okienku nawigacji wybierz opcję **Środowiska**, a następnie wybierz środowisko, w którym chcesz przypisać rolę użytkownika talentów do zespołu relacji talentów.</span><span class="sxs-lookup"><span data-stu-id="31108-115">In the navigation pane, select **Environments**, and then select the environment in which to assign the Talent user role to the Talent Relationship Team.</span></span>

   ![Wybierz środowisko](./media/attract-troubleshoot-career-portal-select-environment.png)

3. <span data-ttu-id="31108-117">W **okienku środowiska** wybierz **adres URL środowiska** i zaloguj się do portalu administracyjnego środowiska (na przykład https: <orgname>. crm.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="31108-117">In the **Environments** pane, select the **Environment URL** and sign in to the environment's admin portal (for example, https:<orgname>.crm.dynamics.com).</span></span>

4. <span data-ttu-id="31108-118">Wybierz **Ustawienia**, wybierz opcję **System**, a następnie wybierz opcję **Zabezpieczenia**.</span><span class="sxs-lookup"><span data-stu-id="31108-118">Select **Settings**, select **System**, and then select **Security**.</span></span>

   ![Przejdź do sekcji Zabezpieczenia](./media/attract-troubleshoot-career-portal-security.png)

5. <span data-ttu-id="31108-120">Wybierz pozycję **Zespoły**.</span><span class="sxs-lookup"><span data-stu-id="31108-120">Select **Teams**.</span></span>

   ![Wybierz pozycję Zespoły](./media/attract-troubleshoot-career-portal-security-teams.png)

6. <span data-ttu-id="31108-122">Wyszukaj **Zespół relacji talentów** w polu wyszukiwania, a następnie wybierz zespół z wyników wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="31108-122">Search for **Talent Relationship Team** in the search box, and then select the team from the search results.</span></span>

7. <span data-ttu-id="31108-123">Wybierz opcję **ZARZĄDZAJ ROLAMI** ze wstążki.</span><span class="sxs-lookup"><span data-stu-id="31108-123">Select **MANAGE ROLES** from the ribbon.</span></span>

8. <span data-ttu-id="31108-124">W oknie dialogowym **Zarządzanie rolami zespołu** wybierz **Użytkownik talentów** z listy dostępnych ról opcję talentów użytkownika, a następnie kliknij przycisk **OK**, aby zastosować rolę.</span><span class="sxs-lookup"><span data-stu-id="31108-124">In the **Manage Team Roles** dialog, select **Talent user** from the list of available roles, and then select **OK** to apply the role.</span></span>

   ![Zastosuj rolę](./media/attract-troubleshoot-career-portal-apply-role.png)

9. <span data-ttu-id="31108-126">Przetestuj zmiany:</span><span class="sxs-lookup"><span data-stu-id="31108-126">Test your changes:</span></span>

   1. <span data-ttu-id="31108-127">Zaloguj się do portalu kariery w nowym oknie przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="31108-127">Sign in to the career portal from a new browser window.</span></span>
   2. <span data-ttu-id="31108-128">Zastosuj do zadania z portalu kariery.</span><span class="sxs-lookup"><span data-stu-id="31108-128">Apply for the job from the career portal.</span></span> 