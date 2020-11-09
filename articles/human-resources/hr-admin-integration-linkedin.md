---
title: Integracja z usługą LinkedIn Talent Hub
description: W tym temacie opisano sposób konfigurowania pul integracji Microsoft Dynamics 365 Human Resources i LinkedIn Talent Hub.
author: jaredha
manager: tfehr
ms.date: 10/20/2020
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
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e82b79858060f31a6310cc5abdb2faf87db2d6c2
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "4056104"
---
# <a name="integrate-with-linkedin-talent-hub"></a><span data-ttu-id="18878-103">Integracja z usługą LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="18878-103">Integrate with LinkedIn Talent Hub</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="18878-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) jest platformą systemu śledzenia kandydatów (ATS).</span><span class="sxs-lookup"><span data-stu-id="18878-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) is an applicant tracking system (ATS) platform.</span></span> <span data-ttu-id="18878-105">Umożliwia on źródło, zarządzanie i zatrudnianie pracowników w jednym miejscu.</span><span class="sxs-lookup"><span data-stu-id="18878-105">It lets you source, manage, and hire employees all in one place.</span></span> <span data-ttu-id="18878-106">Integrując Microsoft Dynamics 365 Human Resources z LinkedIn Talent Hub, można łatwo utworzyć rekordy pracowników w Human Resources dla kandydatów, którzy zostali zatrudnieni na stanowiskach.</span><span class="sxs-lookup"><span data-stu-id="18878-106">By integrating Microsoft Dynamics 365 Human Resources with LinkedIn Talent Hub, you can easily create employee records in Human Resources for applicants who have been hired for a position.</span></span>

## <a name="setup"></a><span data-ttu-id="18878-107">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="18878-107">Setup</span></span>

<span data-ttu-id="18878-108">Administrator systemu musi wykonać zadania konfiguracyjne, aby włączyć integrację z LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="18878-108">A system administrator must complete setup tasks to enable integration with LinkedIn Talent Hub.</span></span> <span data-ttu-id="18878-109">Najpierw w środowisku Power Apps należy skonfigurować użytkownika i rolę zabezpieczeń, aby LinkedIn Talent Hub odpowiednich uprawnień do zapisywania danych w Human Resources.</span><span class="sxs-lookup"><span data-stu-id="18878-109">First, in the Power Apps environment, you must set up a user and security role to grant LinkedIn Talent Hub the appropriate permissions to write data into Human Resources.</span></span>

### <a name="link-your-environment-to-linkedin-talent-hub"></a><span data-ttu-id="18878-110">Połącz środowisko z LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="18878-110">Link your environment to LinkedIn Talent Hub</span></span>

1. <span data-ttu-id="18878-111">Otwórz [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span><span class="sxs-lookup"><span data-stu-id="18878-111">Open [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span></span>

2. <span data-ttu-id="18878-112">W menu rozwijanym użytkownik Wybierz opcję **Ustawienia produktu**.</span><span class="sxs-lookup"><span data-stu-id="18878-112">On the user drop-down menu, select **Product Settings**.</span></span>

3. <span data-ttu-id="18878-113">W lewym okienku nawigacji w sekcji **Zaawansowane** wybierz opcję **Integracje**.</span><span class="sxs-lookup"><span data-stu-id="18878-113">In the left navigation pane, in the **Advanced** section, select **Integrations**.</span></span>

4. <span data-ttu-id="18878-114">Wybierz **Autoryzację** dla integracji rozwiązania Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="18878-114">Select **Authorize** for the Microsoft Dynamics 365 Human Resources integration.</span></span>

5. <span data-ttu-id="18878-115">Na stronie **Dynamics 365 Human Resources** wybierz środowisko, którego ma dotyczyć łącze do LinkedIn Talent Hub, a następnie wybierz **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="18878-115">On the **Dynamics 365 Human Resources** page, select the environment to link LinkedIn Talent Hub to, and then select **Link**.</span></span>

    ![Przygotowywanie LinkedIn Talent Hub](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > <span data-ttu-id="18878-117">Możesz łączyć tylko ze środowiskami, w których konto użytkownika ma dostęp administratora zarówno do środowiska Human Resources, jak i skojarzonego środowiska Power Apps.</span><span class="sxs-lookup"><span data-stu-id="18878-117">You can link only to environments where your user account has administrator access to both the Human Resources environment and the associated Power Apps environment.</span></span> <span data-ttu-id="18878-118">Jeśli na stronie łączy Human Resources nie ma żadnych środowisk, upewnij się, że masz licencjonowane środowiska Human Resources w dzierżawie, a użytkownik, który zalogował się na stronie łącza, ma uprawnienia administratora zarówno dla środowiska Human Resources, jak i środowiska Power Apps.</span><span class="sxs-lookup"><span data-stu-id="18878-118">If no environments are listed on the Human Resources link page, make sure that you have licensed Human Resources environments on the tenant, and that the user that you signed in to the link page as has administrator permissions to both the Human Resources environment and the Power Apps environment.</span></span>

### <a name="create-a-power-apps-security-role"></a><span data-ttu-id="18878-119">Tworzenie roli zabezpieczeń Power Apps</span><span class="sxs-lookup"><span data-stu-id="18878-119">Create a Power Apps security role</span></span>

1. <span data-ttu-id="18878-120">Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="18878-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="18878-121">Na liście **Środowiska** wybierz środowisko skojarzone ze środowiskiem Human Resources, które chcesz połączyć z Twoim wystąpieniem LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="18878-121">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="18878-122">Wybierz **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="18878-122">Select **Settings**.</span></span>

4. <span data-ttu-id="18878-123">Rozwiń węzeł **Użytkownicy + uprawnienia** i wybierz pozycję **Role zabezpieczeń**.</span><span class="sxs-lookup"><span data-stu-id="18878-123">Expand the **Users + Permissions** node, and select **Security Roles**.</span></span>

5. <span data-ttu-id="18878-124">Na stronie **Role zabezpieczeń** na pasku narzędzi wybierz opcję **Nowa rola**.</span><span class="sxs-lookup"><span data-stu-id="18878-124">On the **Security Roles** page, on the toolbar, select **New role**.</span></span>

6. <span data-ttu-id="18878-125">Na karcie **Szczegóły** wprowadź nazwę roli, na przykład **Integracja LinkedIn Talent Hub HRIS**.</span><span class="sxs-lookup"><span data-stu-id="18878-125">On the **Details** tab, enter a name for the role, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>

7. <span data-ttu-id="18878-126">Na karcie **Dostosowywanie** wybierz uprawnienia do **Odczytu** na poziomie organizacji dla następujących jednostek:</span><span class="sxs-lookup"><span data-stu-id="18878-126">On the **Customization** tab, select organization-level **Read** permission for the following entities:</span></span>

    - <span data-ttu-id="18878-127">Jednostka</span><span class="sxs-lookup"><span data-stu-id="18878-127">Entity</span></span>
    - <span data-ttu-id="18878-128">Pole</span><span class="sxs-lookup"><span data-stu-id="18878-128">Field</span></span>
    - <span data-ttu-id="18878-129">Pokrewieństwo</span><span class="sxs-lookup"><span data-stu-id="18878-129">Relationship</span></span>

8. <span data-ttu-id="18878-130">Zapisz i zamknij rolę zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="18878-130">Save and close the security role.</span></span>

### <a name="create-a-power-apps-application-user"></a><span data-ttu-id="18878-131">Utwórz użytkownika aplikacji Power Apps</span><span class="sxs-lookup"><span data-stu-id="18878-131">Create a Power Apps application user</span></span>

<span data-ttu-id="18878-132">Należy utworzyć użytkownika aplikacji dla adaptera LinkedIn Talent Hub, aby nadać adapterowi uprawnienia do zapisywania rekordów kandydatów w środowisku Power Apps.</span><span class="sxs-lookup"><span data-stu-id="18878-132">An application user must be created for the LinkedIn Talent Hub adapter to grant permissions to the adapter to write candidate records into the Power Apps environment.</span></span>

1. <span data-ttu-id="18878-133">Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="18878-133">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="18878-134">Na liście **Środowiska** wybierz środowisko skojarzone ze środowiskiem Human Resources, które chcesz połączyć z Twoim wystąpieniem LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="18878-134">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="18878-135">Wybierz **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="18878-135">Select **Settings**.</span></span>

4. <span data-ttu-id="18878-136">Rozwiń węzeł **Użytkownicy + uprawnienia** i wybierz pozycję **Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="18878-136">Expand the **Users + Permissions** node, and select **Users**.</span></span>

5. <span data-ttu-id="18878-137">Wybierz opcję **Zarządzaj użytkownikami w systemie Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="18878-137">Select **Manage users in Dynamics 365**.</span></span>

6. <span data-ttu-id="18878-138">Skorzystaj z menu rozwijanego powyżej listy, aby zmienić widok z domyślnego widoku **Włączeni użytkownicy** na **Użytkowników aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="18878-138">Use the drop-down menu above the list to change the view from the default **Enabled Users** view to **Application Users**.</span></span>

    ![Widok Użytkownicy aplikacji](./media/hr-admin-integration-power-apps-application-users.jpg)

7. <span data-ttu-id="18878-140">Na pasku narzędzi wybierz **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="18878-140">On the toolbar, select **New**.</span></span>

8. <span data-ttu-id="18878-141">Na stronie **Nowy użytkownik** wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="18878-141">On the **New user** page, follow these steps:</span></span>

    1. <span data-ttu-id="18878-142">Zmień wartość w polu **Tryb użytkownika** na **Użytkownik aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="18878-142">Change the value of the **User type** field to **Application User**.</span></span>
    2. <span data-ttu-id="18878-143">W polu **Nazwa użytkownika** określ **Integracja Dynamics365 LinkedIn HRIS**.</span><span class="sxs-lookup"><span data-stu-id="18878-143">Set the **User Name** field to **Dynamics365 HR LinkedIn HRIS Integration**.</span></span>
    3. <span data-ttu-id="18878-144">Ustaw wartość w polu **Identyfikator aplikacji** na **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="18878-144">Set the **Application ID** field to **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    4. <span data-ttu-id="18878-145">Wprowadź dowolną wartość w polach **Imię** , **Nazwisko** i **Podstawowy adres e-mail**.</span><span class="sxs-lookup"><span data-stu-id="18878-145">Enter any value in the **First Name** , **Last Name** , and **Primary Email** fields.</span></span>
    5. <span data-ttu-id="18878-146">Wybierz **Zapisz \& Zamknij** na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="18878-146">On the toolbar, select **Save \& Close**.</span></span>

### <a name="assign-a-security-role-to-the-new-user"></a><span data-ttu-id="18878-147">Przypisz rolę zabezpieczeń do nowego użytkownika</span><span class="sxs-lookup"><span data-stu-id="18878-147">Assign a security role to the new user</span></span>

<span data-ttu-id="18878-148">Po zapisaniu i zamknięciu nowego użytkownika aplikacji w poprzedniej sekcji wrócisz do strony **Listy użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="18878-148">After you save and close the new application user in the previous section, you're returned to the **Users list** page.</span></span>

1. <span data-ttu-id="18878-149">Na stronie **Listy użytkowników** zmień widok na **Użytkowników aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="18878-149">On the **Users list** page, change the view to **Application Users**.</span></span>

2. <span data-ttu-id="18878-150">Wybierz użytkownika aplikacji, który został utworzony w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="18878-150">Select the application user that you created in the previous section.</span></span>

3. <span data-ttu-id="18878-151">Na pasku narzędzi wybierz opcję **Zarządzaj rolami**.</span><span class="sxs-lookup"><span data-stu-id="18878-151">On the toolbar, select **Manage Roles**.</span></span>

4. <span data-ttu-id="18878-152">Wybierz utworzoną wcześniej rolę zabezpieczeń dla integracji.</span><span class="sxs-lookup"><span data-stu-id="18878-152">Select the security role that you created earlier for the integration.</span></span>

5. <span data-ttu-id="18878-153">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="18878-153">Select **OK**.</span></span>

### <a name="add-an-azure-active-directory-app-in-human-resources"></a><span data-ttu-id="18878-154">Dodaj aplikację Azure Active Directory w Human Resources</span><span class="sxs-lookup"><span data-stu-id="18878-154">Add an Azure Active Directory app in Human Resources</span></span>

1. <span data-ttu-id="18878-155">W Dynamics 365 Human Resources otwórz stronę **Aplikacje Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="18878-155">In Dynamics 365 Human Resources, open the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="18878-156">Dodaj nowy rekord do listy i ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="18878-156">Add a new record to the list, and set the following fields:</span></span>

    - <span data-ttu-id="18878-157">**Identyfikator klienta** : Wpisz **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="18878-157">**Client ID** : Enter **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    - <span data-ttu-id="18878-158">**Nazwa** : należy wprowadzić nazwę utworzonej wcześniej roli zabezpieczeń Power Apps, na przykład **Integracja LinkedIn Talent Hub HRIS**.</span><span class="sxs-lookup"><span data-stu-id="18878-158">**Name** : Enter the name of the Power Apps security role that you created earlier, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>
    - <span data-ttu-id="18878-159">**Identyfikator użytkownika** : Wybierz użytkownika, który ma uprawnienia do zapisywania danych w zarządzaniu personelem.</span><span class="sxs-lookup"><span data-stu-id="18878-159">**User ID** : Select a user who has permissions to write data in Personnel Management.</span></span>

### <a name="create-the-entity-in-common-data-service"></a><span data-ttu-id="18878-160">Utwórz jednostkę w Common Data Service</span><span class="sxs-lookup"><span data-stu-id="18878-160">Create the entity in Common Data Service</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18878-161">Integracja z LinkedIn Talent Hub zależy od jednostek wirtualnych w module Common Data Service dla Human Resources.</span><span class="sxs-lookup"><span data-stu-id="18878-161">The integration with LinkedIn Talent Hub depends on virtual entities in Common Data Service for Human Resources.</span></span> <span data-ttu-id="18878-162">Jako warunek wstępny dla tego kroku w konfiguracji należy skonfigurować jednostki wirtualne.</span><span class="sxs-lookup"><span data-stu-id="18878-162">As a prerequisite for this step in the setup, you must configure virtual entities.</span></span> <span data-ttu-id="18878-163">Aby uzyskać informacje o konfigurowaniu jednostek wirtualnych, zajrzyj do [Konfiguracja jednostek wirtualnych Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="18878-163">For information about how to configure virtual entities, see [Configure Common Data Service virtual entities](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

1. <span data-ttu-id="18878-164">W module Zasoby ludzkie otwórz stronę **Integracja Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="18878-164">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="18878-165">Wybierz kartę **Jednostki wirtualne**.</span><span class="sxs-lookup"><span data-stu-id="18878-165">Select the **Virtual entities** tab.</span></span>

3. <span data-ttu-id="18878-166">Filtruj listę jednostek według etykiety jednostki, aby odnaleźć **Kandydata wyeksportowanego z serwisu LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="18878-166">Filter the entity list by entity label to find **LinkedIn exported candidate**.</span></span>

4. <span data-ttu-id="18878-167">Wybierz jednostkę i wybierz przycisk **Generuj/odśwież**.</span><span class="sxs-lookup"><span data-stu-id="18878-167">Select the entity, and then select **Generate/refresh**.</span></span>

## <a name="exporting-candidate-records"></a><span data-ttu-id="18878-168">Eksportowanie rekordów kandydatów</span><span class="sxs-lookup"><span data-stu-id="18878-168">Exporting candidate records</span></span>

<span data-ttu-id="18878-169">Po zakończeniu instalacji pracownicy działu informatyki i specjaliści do zasobów ludzkich mogą skorzystać z funkcji **Eksportu do HRIS** w LinkedIn Talent Hub, aby wyeksportować zarejestrowane rekordy kandydatów z LinkedIn Talent Hub do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="18878-169">After the setup is completed, recruiters and Human resources (HR) professionals can use the **Export to HRIS** function in LinkedIn Talent Hub to export hired candidate records from LinkedIn Talent Hub to Human Resources.</span></span>

### <a name="export-records-from-linkedin-talent-hub"></a><span data-ttu-id="18878-170">Eksportuj rekordy z LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="18878-170">Export records from LinkedIn Talent Hub</span></span>

<span data-ttu-id="18878-171">Po przeniesieniu kandydata do procesu rekrutacji i po jego zatrudnieniu można wyeksportować rekord kandydata z LinkedIn Talent Hub do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="18878-171">After a candidate has moved through the recruiting process and has been hired, you can export the candidate record from LinkedIn Talent Hub to Human Resources.</span></span>

1. <span data-ttu-id="18878-172">W LinkedIn Talent Hub otwórz projekt, dla którego został zatrudniony nowy pracownik etatowy.</span><span class="sxs-lookup"><span data-stu-id="18878-172">In LinkedIn Talent Hub, open the project that you hired the new employee for.</span></span>

2. <span data-ttu-id="18878-173">Wybierz rekord kandydata.</span><span class="sxs-lookup"><span data-stu-id="18878-173">Select a candidate record.</span></span>

3. <span data-ttu-id="18878-174">Wybierz pozycję **Zmień etap** , a następnie wybierz opcję **Zatrudniono**.</span><span class="sxs-lookup"><span data-stu-id="18878-174">Select **Change stage** , and then select **Hired**.</span></span>

4. <span data-ttu-id="18878-175">W menu wielokropka ( **...** ) dla kandydata wybierz **Eksportuj do HRIS**.</span><span class="sxs-lookup"><span data-stu-id="18878-175">On the ellipsis menu ( **...** ) for the candidate, select **Export to HRIS**.</span></span>

5. <span data-ttu-id="18878-176">W okienku **Eksportuj do HRIS** wprowadź informacje, które muszą zostać wyeksportowane:</span><span class="sxs-lookup"><span data-stu-id="18878-176">In the **Export to HRIS** pane, enter the information that must be exported:</span></span>

    - <span data-ttu-id="18878-177">W polu **Dostawca HRIS** wybierz pozycję **Microsoft Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="18878-177">In the **HRIS provider** field, select **Microsoft Dynamics 365 Human Resources**.</span></span>
    - <span data-ttu-id="18878-178">W polu **Data rozpoczęcia** wybierz wartość dla nowego pracownika.</span><span class="sxs-lookup"><span data-stu-id="18878-178">In the **Start date** field, select a value for the new employee.</span></span>
    - <span data-ttu-id="18878-179">W polu **Stanowisko** wprowadź stanowisko nowego pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="18878-179">In the **Job title** field, enter a job title for the new employee's job.</span></span>
    - <span data-ttu-id="18878-180">W polu **Lokalizacja** wprowadź lokalizację, w której ma być oparty dany pracownik etatowy.</span><span class="sxs-lookup"><span data-stu-id="18878-180">In the **Location** field, enter the location where the employee will be based.</span></span>
    - <span data-ttu-id="18878-181">Wprowadź lub Sprawdź adres e-mail pracownika.</span><span class="sxs-lookup"><span data-stu-id="18878-181">Enter or verify the employee's email address.</span></span>

![Eksportowanie do okienka HRIS w LinkedIn Talent Hub](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a><span data-ttu-id="18878-183">Dokończ dołączanie do Human Resources</span><span class="sxs-lookup"><span data-stu-id="18878-183">Complete onboarding in Human Resources</span></span>

<span data-ttu-id="18878-184">Rekordy kandydatów eksportowane z LinkedIn Talent Hub do Human Resources znajdują się w sekcji **Kandydaci do zatrudnienia** na stronie **Zarządzanie personelem**.</span><span class="sxs-lookup"><span data-stu-id="18878-184">Candidate records that are exported from LinkedIn Talent Hub to Human Resources appear in the **Candidates to hire** section of the **Personnel management** page.</span></span>

1. <span data-ttu-id="18878-185">W module Human Resources otwórz stronę listy **Zarządzanie personelem**.</span><span class="sxs-lookup"><span data-stu-id="18878-185">In Human Resources, open the **Personnel management** page.</span></span>

2. <span data-ttu-id="18878-186">W sekcji **Kandydaci do zatrudnienia** wybierz opcję **Zatrudnij** dla wybranego kandydata.</span><span class="sxs-lookup"><span data-stu-id="18878-186">In the **Candidates to hire** section, select **Hire** for the selected candidate.</span></span>

3. <span data-ttu-id="18878-187">W oknie dialogowym **Zatrudnij nowego pracownika** przejrzyj rekord i dodaj wszystkie wymagane informacje.</span><span class="sxs-lookup"><span data-stu-id="18878-187">In the **Hire new worker** dialog box, review the record, and add any required information.</span></span> <span data-ttu-id="18878-188">Możesz również wybrać numer stanowiska, na które kandydat został zatrudniony.</span><span class="sxs-lookup"><span data-stu-id="18878-188">You can also select the position number that the candidate has been hired for.</span></span>

<span data-ttu-id="18878-189">Po wprowadzeniu wymaganych informacji można kontynuować procesy standardowe służące do tworzenia rekordów pracowników i dołączania pracowników.</span><span class="sxs-lookup"><span data-stu-id="18878-189">After the required information has been entered, you can continue with your standard processes for creating employee records and onboarding employees.</span></span>

<span data-ttu-id="18878-190">Następujące szczegóły są importowane i uwzględniane w nowym rekordzie pracownika etatowego:</span><span class="sxs-lookup"><span data-stu-id="18878-190">The following details are imported and included on the new employee record:</span></span>

- <span data-ttu-id="18878-191">Imię</span><span class="sxs-lookup"><span data-stu-id="18878-191">First name</span></span>
- <span data-ttu-id="18878-192">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="18878-192">Last name</span></span>
- <span data-ttu-id="18878-193">Data rozpoczęcia zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="18878-193">Employment start date</span></span>
- <span data-ttu-id="18878-194">Adres e-mail</span><span class="sxs-lookup"><span data-stu-id="18878-194">Email address</span></span>
- <span data-ttu-id="18878-195">Numer telefonu</span><span class="sxs-lookup"><span data-stu-id="18878-195">Phone number</span></span>

## <a name="see-also"></a><span data-ttu-id="18878-196">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="18878-196">See also</span></span>

[<span data-ttu-id="18878-197">Konfigurowanie jednostek wirtualnych usługi Common Data Service</span><span class="sxs-lookup"><span data-stu-id="18878-197">Configure Common Data Service virtual entities</span></span>](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="18878-198">Co to jest usługa Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="18878-198">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
