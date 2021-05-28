---
title: Obsługa Microsoft Teams z Dynamics 365 Commerce
description: W tym temacie opisano sposób inicjowania Microsoft Teams przy użyciu danych organizacyjnych z systemu Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1cb28fb50bdc972d1dae6d03a45f70a2f3a63357
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022453"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a><span data-ttu-id="3fe82-103">Obsługa Microsoft Teams z Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3fe82-103">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3fe82-104">W tym temacie opisano sposób inicjowania Microsoft Teams przy użyciu danych organizacyjnych z systemu Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3fe82-104">This topic describes how to provision Microsoft Teams by using organizational data from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3fe82-105">Dynamics 365 Commerce oferuje łatwy sposób udostępniania zespołów, jeśli jeszcze nie skonfigurowałeś tam zespołów dla swoich sklepów detalicznych.</span><span class="sxs-lookup"><span data-stu-id="3fe82-105">Dynamics 365 Commerce offers an easy way to provision Teams if you haven't yet set up teams for your retail stores there.</span></span> <span data-ttu-id="3fe82-106">Korzystając z dobrze zdefiniowanych informacji z Commerce, które chcesz używać w Teams, możesz pomóc pracownikom sklepu rozpocząć pracę w Teams.</span><span class="sxs-lookup"><span data-stu-id="3fe82-106">By taking advantage of well-defined information from Commerce that you want to use in Teams, you can help your store employees get started in Teams.</span></span> <span data-ttu-id="3fe82-107">Te informacje obejmują hierarchię organizacyjną, nazwy sklepów, informacje o pracownikach oraz konta Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3fe82-107">This information includes the organizational hierarchy, store names, employee information, and Azure Active Directory (Azure AD) accounts.</span></span> 

<span data-ttu-id="3fe82-108">Proces inicjowania obsługi Teams ma dwa główne kroki:</span><span class="sxs-lookup"><span data-stu-id="3fe82-108">The process of provisioning Teams has two main steps:</span></span>

1. <span data-ttu-id="3fe82-109">W Teams utwórz zespół dla każdego sklepu detalicznego i dodaj pracowników sklepu jako członków odpowiedniego zespołu.</span><span class="sxs-lookup"><span data-stu-id="3fe82-109">In Teams, create a team for each retail store, and add store workers as members of the appropriate team.</span></span> <span data-ttu-id="3fe82-110">Jeśli pracownik jest skojarzony z więcej niż jednym sklepem detalicznym, przynależność do zespołu odzwierciedla ten fakt.</span><span class="sxs-lookup"><span data-stu-id="3fe82-110">If an employee is associated with more than one retail store, team membership will reflect that fact.</span></span> <span data-ttu-id="3fe82-111">Zostanie utworzony zespół komunikacji, który obejmuje menedżerów regionalnych jako członków, aby ułatwić publikowanie zadań z Teams.</span><span class="sxs-lookup"><span data-stu-id="3fe82-111">A communications team that includes regional managers as members will be created to help publish tasks from Teams.</span></span>
1. <span data-ttu-id="3fe82-112">Przekaż hierarchię organizacyjną z usług Commerce do Teams.</span><span class="sxs-lookup"><span data-stu-id="3fe82-112">Upload your organizational hierarchy from Commerce to Teams.</span></span>

## <a name="provision-teams-in-commerce-headquarters"></a><span data-ttu-id="3fe82-113">Inicjowanie obsługi Teams w Commerce headquarters</span><span class="sxs-lookup"><span data-stu-id="3fe82-113">Provision Teams in Commerce headquarters</span></span>

<span data-ttu-id="3fe82-114">Przed dostarczeniem Microsoft Teams należy wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="3fe82-114">Before you provision Microsoft Teams, complete these tasks:</span></span>

- <span data-ttu-id="3fe82-115">Potwierdź, że wszyscy menedżerowie regionalni są menedżerami ds. komunikacji.</span><span class="sxs-lookup"><span data-stu-id="3fe82-115">Confirm that all regional managers have been made communications managers.</span></span>
- <span data-ttu-id="3fe82-116">Potwierdź, że konto Azure każdego menedżera sklepu i pracownika zostało skojarzone z rekordem tego menedżera lub pracownika w programie Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="3fe82-116">Confirm that the Azure account of every store manager and worker has been associated with that manager's or worker's worker record in Commerce headquarters.</span></span>

<span data-ttu-id="3fe82-117">Aby obsługiwać Teams w centrali Commerce, wykonaj kroki opisane poniżej.</span><span class="sxs-lookup"><span data-stu-id="3fe82-117">To provision Teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="3fe82-118">Przejdź do opcji **Retail i Commerce \> Konfiguracja kanału \> Grupy realizacji Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="3fe82-118">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="3fe82-119">Na okienku akcji wybierz opcję **Obsługa teams**.</span><span class="sxs-lookup"><span data-stu-id="3fe82-119">On the Action Pane, select **Provision teams**.</span></span> <span data-ttu-id="3fe82-120">Zostanie utworzone zadanie wsadowe o nazwie **Tworzenie zespołów**.</span><span class="sxs-lookup"><span data-stu-id="3fe82-120">A batch job that is named **Teams provision** is created.</span></span>
1. <span data-ttu-id="3fe82-121">Przejdź do **Administracja systemu \> Zapytania \> Zadania wsadowe** i znajdź ostatnie zadanie z opisem Inicjowanie **Obsługa Teams**.</span><span class="sxs-lookup"><span data-stu-id="3fe82-121">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="3fe82-122">Czekaj, aż to zadanie zakończy się.</span><span class="sxs-lookup"><span data-stu-id="3fe82-122">Wait until this job has finished running.</span></span>

> [!TIP]
> <span data-ttu-id="3fe82-123">Jeśli żaden z menedżerów regionalnych, kierowników sklepów i pracowników sklepu nie został skojarzony z licencją zespołu, może zostać wyświetlony następujący komunikat o błędzie: „Nie można pobrać kategorii SKU odpowiedzialnych za aplikacje dla użytkownika”</span><span class="sxs-lookup"><span data-stu-id="3fe82-123">If none of your regional managers, store managers, and store workers have been associated with a Teams license, you might receive the following error message: "Failed to retrieve appliable Sku categories for the user."</span></span> <span data-ttu-id="3fe82-124">Aby rozwiązać ten problem, wybierz **Synchronizacja zespołów i członków** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="3fe82-124">To correct the issue, select **Sync teams and members** on the Action Pane.</span></span>

<!-- ![Dynamics 365 Commerce - Teams integration configuration](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a><span data-ttu-id="3fe82-125">Sprawdzanie poprawności inicjowania obsługi Teams w centrum administratora Teams</span><span class="sxs-lookup"><span data-stu-id="3fe82-125">Validate Teams provisioning in the Teams admin center</span></span>

<span data-ttu-id="3fe82-126">Aby sprawdzić poprawność inicjowania obsługi Microsoft Teams w centrum administratora Microsoft Teams, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3fe82-126">To validate Microsoft Teams provisioning in the Microsoft Teams admin center, follow these steps.</span></span>
    
1. <span data-ttu-id="3fe82-127">Przejdź do [centrum administracyjnego Teams](https://admin.teams.microsoft.com/) i zaloguj się jako administrator twojej dzierżawy usług e-commerce.</span><span class="sxs-lookup"><span data-stu-id="3fe82-127">Go to the [Teams admin center](https://admin.teams.microsoft.com/), and sign in as the administrator of your e-commerce tenant.</span></span>
1. <span data-ttu-id="3fe82-128">W lewym okienku nawigacji wybierz pozycję **Teams**, aby je rozwinąć, a następnie wybierz pozycję **Zarządzaj zespołami**.</span><span class="sxs-lookup"><span data-stu-id="3fe82-128">In the left navigation pane, select **Teams** to expand it, and then select **Manage teams**.</span></span>
1. <span data-ttu-id="3fe82-129">Potwierdź, że utworzono jeden zespół dla każdego sklepu detalicznego Commerce.</span><span class="sxs-lookup"><span data-stu-id="3fe82-129">Confirm that one team has been created for each Commerce retail store.</span></span>
1. <span data-ttu-id="3fe82-130">Wybierz zespół i potwierdź, że pracownicy sklepu dodano do niego jako członków.</span><span class="sxs-lookup"><span data-stu-id="3fe82-130">Select a team, and confirm that store workers have been added to it as members.</span></span>
1. <span data-ttu-id="3fe82-131">W lewym okienku nawigacji wybierz pozycję **Użytkownicy** i potwierdź, że wszyscy pracownicy sklepu we wszystkich sklepach dodano jako użytkowników.</span><span class="sxs-lookup"><span data-stu-id="3fe82-131">In the left navigation pane, select **Users**, and confirm that all store employees in all stores have been added as users.</span></span>

<span data-ttu-id="3fe82-132">Na poniższej ilustracji pokazano przykład strony **Zarządzanie zespołami** w Centrum administratora Teams.</span><span class="sxs-lookup"><span data-stu-id="3fe82-132">The following illustration shows an example of the **Manage teams** page in the Teams admin center.</span></span>

![Przykład strony Zarządzanie zespołami w centrum administratora Teams](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a><span data-ttu-id="3fe82-134">Przekaż hierarchię organizacyjną z Commerce do Teams</span><span class="sxs-lookup"><span data-stu-id="3fe82-134">Upload a Commerce organizational hierarchy to Teams</span></span>
    
<span data-ttu-id="3fe82-135">Hierarchii organizacyjnej Commerce można używać w Microsoft Teams do publikowania zadań dla wszystkich lub wybranych sklepów, które używają tej samej struktury hierarchii.</span><span class="sxs-lookup"><span data-stu-id="3fe82-135">The Commerce organizational hierarchy can be used in Microsoft Teams to publish tasks to all or selected stores that use the same hierarchy structure.</span></span>

<span data-ttu-id="3fe82-136">Aby przekazać hierarchię organizacyjną Commerce do Teams, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3fe82-136">To upload a Commerce organizational hierarchy to Teams, follow these steps.</span></span>
    
1. <span data-ttu-id="3fe82-137">W Commerce przejdź do **Handel detaliczny i inny \> Ustawienia kanału \> Harmonogram integracji Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="3fe82-137">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="3fe82-138">Wybierz opcję **Pobierz hierarchię określania wartości docelowych**, a następnie wybierz pozycję **Sklepy detaliczne według regionów**, aby pobrać plik z hierarchią organizacyjną z wartościami rozdzielaymi przecinkami (CSV).</span><span class="sxs-lookup"><span data-stu-id="3fe82-138">Select **Download targeting hierarchy**, and then select **Retail Stores by Region** to download a comma-separated values (CSV) file of the organizational hierarchy.</span></span>
1. <span data-ttu-id="3fe82-139">Zainstaluj moduł Microsoft Teams PowerShell, wykonać poniższe kroki w [Instalacja Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="3fe82-139">Install the Microsoft Teams PowerShell module by following the steps in [Install Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).</span></span>
1. <span data-ttu-id="3fe82-140">Po wyświetleniu monitu w oknie programu Teams PowerShell zaloguj się, używając konta administratora twojej dzierżawy Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3fe82-140">When you're prompted in the Teams PowerShell window, sign in by using the administrator account for your Azure AD tenant.</span></span>
1. <span data-ttu-id="3fe82-141">Aby przekazać plik CSV dla hierarchii docelowych, wykonaj kroki w temacie [Konfigurowanie hierarchii określania docelowego dla zespołu](/microsoftteams/set-up-your-team-hierarchy).</span><span class="sxs-lookup"><span data-stu-id="3fe82-141">Follow the steps in [Set up your team targeting hierarchy](/microsoftteams/set-up-your-team-hierarchy) to upload the CSV file for the targeting hierarchy.</span></span>

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a><span data-ttu-id="3fe82-142">Sprawdź, czy hierarchia organizacyjna została przekazane do Teams</span><span class="sxs-lookup"><span data-stu-id="3fe82-142">Verify that the organizational hierarchy was uploaded to Teams</span></span>

<span data-ttu-id="3fe82-143">Aby sprawdzić, czy hierarchia organizacyjna została przekazana do Microsoft Teams, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3fe82-143">To verify that the organizational hierarchy was uploaded to Microsoft Teams, follow these steps.</span></span>

1. <span data-ttu-id="3fe82-144">Zaloguj się do Teams jako kierownik ds. komunikacji.</span><span class="sxs-lookup"><span data-stu-id="3fe82-144">Sign in to Teams as a communications manager.</span></span>
1. <span data-ttu-id="3fe82-145">W lewym okienku nawigacji wybierz pozycję **Zadania według programu Planner**.</span><span class="sxs-lookup"><span data-stu-id="3fe82-145">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="3fe82-146">Na karcie **Listy opublikowane** utwórz nową listę, która ma fikcyjne zadanie.</span><span class="sxs-lookup"><span data-stu-id="3fe82-146">On the **Published lists** tab, create a new list that has a dummy task.</span></span>
1. <span data-ttu-id="3fe82-147">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="3fe82-147">Select **Publish**.</span></span> <span data-ttu-id="3fe82-148">Hierarchia organizacyjna powinna być wyświetlana w polu **Wybór osoby, która ma zostać opublikowana** w oknie dialogowym, tak jak pokazano na przykładzie na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="3fe82-148">The organizational hierarchy should appear in the **Select who to publish to** dialog box, as shown in the example in the following illustration.</span></span>

![Przykład hierarchii organizacyjnej w oknie dialogowym Wybierz osoby, które mają być publikowane](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a><span data-ttu-id="3fe82-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3fe82-150">Additional resources</span></span>

[<span data-ttu-id="3fe82-151">Omówienie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fe82-151">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="3fe82-152">Włączanie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fe82-152">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="3fe82-153">Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="3fe82-153">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="3fe82-154">Zarządzanie rolami użytkowników w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fe82-154">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="3fe82-155">Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fe82-155">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="3fe82-156">Integracja z usługami Dynamics 365 Commerce i Microsoft Teams - FAQ</span><span class="sxs-lookup"><span data-stu-id="3fe82-156">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)