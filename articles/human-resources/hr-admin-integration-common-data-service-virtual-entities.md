---
title: Konfigurowanie jednostek wirtualnych usługi Common Data Service
description: W tym temacie przedstawiono sposób konfigurowania jednostek wirtualnych dla systemu Dynamics 365 Human Resources. Generuj i aktualizuj istniejące jednostki wirtualne oraz analizuj wygenerowane i dostępne jednostki.
author: andreabichsel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0848b7556100fba38fcab0aa2a1a109e2e055fc9
ms.sourcegitcommit: b89baab13e530b5b1f079231619c628309a4742d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/05/2020
ms.locfileid: "3959582"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="35db9-104">Konfigurowanie jednostek wirtualnych usługi Common Data Service</span><span class="sxs-lookup"><span data-stu-id="35db9-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="35db9-105">Dynamics 365 Human Resources jest wirtualnym źródłem danych w usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="35db9-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="35db9-106">Obsługuje on pełne operacje tworzenia, odczytu, aktualizacji i usuwania (CRUD) z Common Data Service i Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="35db9-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="35db9-107">Dane dla jednostek wirtualnych nie są przechowywane w usłudze Common Data Service, ale w bazie danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="35db9-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="35db9-108">Aby włączyć operacje CRUD dla jednostek zasobów ludzkich z usługi Common Data Service, należy udostępnić jednostki jako jednostki wirtualne w usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="35db9-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="35db9-109">Pozwala to na wykonywanie operacji CRUD z usługi Common Data Service i Microsoft Power Platform na danych znajdujących się w module Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="35db9-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="35db9-110">Operacje te obsługują również pełne sprawdzanie poprawności logiki biznesowej w celu zapewnienia integralności danych podczas zapisywania danych w jednostkach.</span><span class="sxs-lookup"><span data-stu-id="35db9-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="35db9-111">Dostępne jednostki wirtualne dla modułu Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="35db9-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="35db9-112">Wszystkie jednostki protokołu OData (Open Data Protocol) w module Zasoby ludzkie są dostępne jako jednostki wirtualne w usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="35db9-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="35db9-113">Są one również dostępne w programie Power Platform.</span><span class="sxs-lookup"><span data-stu-id="35db9-113">They're also available in Power Platform.</span></span> <span data-ttu-id="35db9-114">Teraz możesz tworzyć aplikacje i środowiska z danymi bezpośrednio z modułu Zasoby ludzkie z pełnymi funkcjami CRUD bez kopiowania lub synchronizowania danych do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="35db9-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="35db9-115">Portale Power Apps umożliwiają tworzenie zewnętrznych stron internetowych, które pozwalają realizować scenariusze współpracy w zakresie procesów biznesowych w module Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="35db9-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="35db9-116">Można wyświetlić listę jednostek wirtualnych włączonych w środowisku i rozpocząć pracę z jednostkami w [Power Apps](https://make.powerapps.com) w rozwiązaniu **Dynamics 365 HR jednostek miarowych**.</span><span class="sxs-lookup"><span data-stu-id="35db9-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Jednostki wirtualne HR Dynamics 365 w Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="35db9-118">Jednostki wirtualne a jednostki naturalne</span><span class="sxs-lookup"><span data-stu-id="35db9-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="35db9-119">Jednostki wirtualne dla modułu Zasoby ludzkie nie są takie same jak jednostki naturalne Common Data Service utworzone dla modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="35db9-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="35db9-120">Jednostki naturalne dla modułu Zasoby ludzkie są generowane oddzielnie i utrzymywane w rozwiązaniu HCM Common w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="35db9-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="35db9-121">W przypadku jednostek naturalnych dane są przechowywane w usłudze Common Data Service i wymagają synchronizacji z bazą danych aplikacji Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="35db9-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="35db9-122">Aby uzyskać listę jednostek naturalnych usługi Common Data Service dla modułu Zasoby ludzkie, zobacz temat [Jednostki usługi Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="35db9-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="35db9-123">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="35db9-123">Setup</span></span>

<span data-ttu-id="35db9-124">Wykonaj te kroki konfiguracji, aby włączyć jednostki wirtualne w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="35db9-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="35db9-125">Rejestracja aplikacji w usłudze Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="35db9-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="35db9-126">Najpierw należy zarejestrować aplikację w portalu Azure, dzięki czemu platforma tożsamości firmy Microsoft może udostępniać usługi uwierzytelniania i autoryzacji aplikacjom i użytkowników.</span><span class="sxs-lookup"><span data-stu-id="35db9-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="35db9-127">Aby uzyskać więcej informacji o rejestrowaniu aplikacji na platformie Azure, zobacz temat [Szybki Start: rejestracja aplikacji na platformie tożsamości Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="35db9-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="35db9-128">Otwórz portal [Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="35db9-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="35db9-129">Na liście usług Azure wybierz pozycję **Rejestracje aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="35db9-129">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="35db9-130">Wybierz opcję**Nowa rejestracja**.</span><span class="sxs-lookup"><span data-stu-id="35db9-130">Select **New registration**.</span></span>

4. <span data-ttu-id="35db9-131">W polu **Nazwa** wprowadź opisową nazwę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="35db9-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="35db9-132">Na przykład **Encje wirtualne Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="35db9-132">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="35db9-133">W polu **Identyfikator URI przekierowania** wprowadź adres URL obszaru nazw wystąpienia moduły Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="35db9-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="35db9-134">Wybierz opcję **Zarejestruj**.</span><span class="sxs-lookup"><span data-stu-id="35db9-134">Select **Register**.</span></span>

7. <span data-ttu-id="35db9-135">Po zakończeniu rejestracji w module Azure Portal zostanie wyświetlone okienko **Przegląd** rejestracji aplikacji , które zawiera **Identyfikator aplikacji (klienta)**.</span><span class="sxs-lookup"><span data-stu-id="35db9-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="35db9-136">Zapisz teraz **identyfikator aplikacji (klienta)**.</span><span class="sxs-lookup"><span data-stu-id="35db9-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="35db9-137">Te informacje wprowadzisz podczas [konfigurowania źródła danych jednostki wirtualnej](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="35db9-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="35db9-138">W lewym okienku nawigacji wybierz opcję **Certyfikaty i klucze tajne**.</span><span class="sxs-lookup"><span data-stu-id="35db9-138">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="35db9-139">W sekcji **Klucze tajne klienta** strony wybierz opcję **Nowy klucz tajny klienta**.</span><span class="sxs-lookup"><span data-stu-id="35db9-139">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="35db9-140">Podaj opis, wybierz czas trwania i wybierz przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="35db9-140">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="35db9-141">Zapisz wartość klucza tajnego.</span><span class="sxs-lookup"><span data-stu-id="35db9-141">Record the secret's value.</span></span> <span data-ttu-id="35db9-142">Te informacje wprowadzisz podczas [konfigurowania źródła danych jednostki wirtualnej](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="35db9-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="35db9-143">Pamiętaj, aby w tym momencie zapisać wartość klucza tajnego.</span><span class="sxs-lookup"><span data-stu-id="35db9-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="35db9-144">Klucz tajny nie jest nigdy wyświetlany ponownie po opuszczeniu tej strony.</span><span class="sxs-lookup"><span data-stu-id="35db9-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="35db9-145">Instalacja aplikacji Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="35db9-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="35db9-146">Zainstaluj aplikację Dynamics 365 HR Virtual Entity w środowisku Power Apps, aby wdrożyć pakiet rozwiązania jednostek wirtualnych w usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="35db9-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="35db9-147">Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="35db9-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="35db9-148">Na liście **Środowiska** wybierz środowisko Power Apps skojarzone z wystąpieniem modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="35db9-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="35db9-149">W sekcji **Zasoby** wybierz pozycję **Aplikacje Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="35db9-149">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="35db9-150">Wybierz akcję **Zainstaluj aplikację**.</span><span class="sxs-lookup"><span data-stu-id="35db9-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="35db9-151">Wybierz **Dynamics 365 HR Virtual Entity** i kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="35db9-151">Select **Dynamics 365 HR Virtual Entity**, and select **Next**.</span></span>

6. <span data-ttu-id="35db9-152">Przejrzyj i zaznacz pole wyboru, aby wyrazić zgodę na warunki użytkowania usługi.</span><span class="sxs-lookup"><span data-stu-id="35db9-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="35db9-153">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="35db9-153">Select **Install**.</span></span>

<span data-ttu-id="35db9-154">Instalacja potrwa kilka minut.</span><span class="sxs-lookup"><span data-stu-id="35db9-154">The install takes a few minutes.</span></span> <span data-ttu-id="35db9-155">Po zakończeniu przejdź do kolejnych kroków.</span><span class="sxs-lookup"><span data-stu-id="35db9-155">When it completes, continue to the next steps.</span></span>

![Instalacja aplikacji Dynamics 365 HR Virtual Entity z centrum administracyjnego Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="35db9-157">Konfiguracja źródła danych jednostki wirtualnej</span><span class="sxs-lookup"><span data-stu-id="35db9-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="35db9-158">Następnym krokiem jest skonfigurowanie źródła danych jednostki wirtualnej w środowisku Power Apps.</span><span class="sxs-lookup"><span data-stu-id="35db9-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="35db9-159">Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="35db9-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="35db9-160">Na liście **Środowiska** wybierz środowisko Power Apps skojarzone z wystąpieniem modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="35db9-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="35db9-161">Wybierz **Adres URL środowiska** w sekcji **Szczegóły** strony.</span><span class="sxs-lookup"><span data-stu-id="35db9-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="35db9-162">W oknie **Centrum kondycji rozwiązania** wybierz ikonę **Wyszukiwanie zaawansowane** w prawym górnym rogu strony aplikacji.</span><span class="sxs-lookup"><span data-stu-id="35db9-162">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="35db9-163">Na stronie **Wyszukiwanie zaawansowane**, z listy rozwijanej **Wyszukaj** wybierz pozycję **Konfiguracje wirtualnego źródła danych Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="35db9-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="35db9-164">Wybierz opcję **Wyniki**.</span><span class="sxs-lookup"><span data-stu-id="35db9-164">Select **Results**.</span></span>

7. <span data-ttu-id="35db9-165">Wybierz rekord **Microsoft HR Data Source**.</span><span class="sxs-lookup"><span data-stu-id="35db9-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="35db9-166">Wprowadź wymagane informacje dotyczące konfiguracji źródła danych.</span><span class="sxs-lookup"><span data-stu-id="35db9-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="35db9-167">**Docelowy adres URL**: adres URL obszaru nazw modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="35db9-167">**Target URL**: The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="35db9-168">**Identyfikator dzierżawcy**: identyfikator dzierżawcy Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="35db9-168">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="35db9-169">**Identyfikator aplikacji w usłudze AAD**: identyfikator aplikacji (klienta) utworzony dla aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="35db9-169">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="35db9-170">Te informacje uzyskano wcześniej w tym kroku [Rejestracja aplikacji w Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="35db9-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="35db9-171">**Wpis tajny aplikacji w usłudze AAD**: wpis tajny utworzony dla aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="35db9-171">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="35db9-172">Te informacje uzyskano wcześniej w tym kroku [Rejestracja aplikacji w Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="35db9-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="35db9-173">Wybierz opcję **Zapisz i zamknij**.</span><span class="sxs-lookup"><span data-stu-id="35db9-173">Select **Save & Close**.</span></span>

   ![Źródło danych Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="35db9-175">Udzielanie uprawnień aplikacji w module Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="35db9-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="35db9-176">Udziel uprawnień dwóm aplikacjom Azure AD w module zasoby ludzkie:</span><span class="sxs-lookup"><span data-stu-id="35db9-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="35db9-177">Aplikacji utworzonej dla Twojej dzierżawy w portalu Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="35db9-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="35db9-178">Aplikacji Dynamics 365 HR Virtual Entity zainstalowanej w środowisku Power Apps</span><span class="sxs-lookup"><span data-stu-id="35db9-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="35db9-179">W module Zasoby ludzkie otwórz stronę **Aplikacje Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="35db9-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="35db9-180">Wybierz pozycję **Nowy**, aby utworzyć nowy rekord aplikacji:</span><span class="sxs-lookup"><span data-stu-id="35db9-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="35db9-181">W polu **Identyfikator klienta** wprowadź identyfikator klienta aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="35db9-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="35db9-182">W polu **Nazwa** wprowadź nazwę aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="35db9-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="35db9-183">W polu **Identyfikator użytkownika** wybierz identyfikator użytkownika z uprawnieniami administratora w module Zasoby ludzkie i środowisku Power Apps.</span><span class="sxs-lookup"><span data-stu-id="35db9-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="35db9-184">Wybierz pozycję **Nowy**, aby utworzyć drugi rekord aplikacji:</span><span class="sxs-lookup"><span data-stu-id="35db9-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="35db9-185">**Identyfikator klienta**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="35db9-185">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="35db9-186">**Nazwa**: Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="35db9-186">**Name**: Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="35db9-187">W polu **Identyfikator użytkownika** wybierz identyfikator użytkownika z uprawnieniami administratora w module Zasoby ludzkie i środowisku Power Apps.</span><span class="sxs-lookup"><span data-stu-id="35db9-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="35db9-188">Generowanie jednostek wirtualnych</span><span class="sxs-lookup"><span data-stu-id="35db9-188">Generate virtual entities</span></span>

<span data-ttu-id="35db9-189">Po zakończeniu pracy Instalatora można wybrać jednostki wirtualne, które mają zostać wygenerowane i włączone w instancji usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="35db9-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="35db9-190">Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="35db9-190">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="35db9-191">Na liście **Środowiska** wybierz środowisko Power Apps skojarzone z wystąpieniem modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="35db9-191">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="35db9-192">Wybierz **Adres URL środowiska** w sekcji **Szczegóły** strony.</span><span class="sxs-lookup"><span data-stu-id="35db9-192">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="35db9-193">W oknie **Centrum kondycji rozwiązania** wybierz ikonę **Wyszukiwanie zaawansowane** w prawym górnym rogu strony.</span><span class="sxs-lookup"><span data-stu-id="35db9-193">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the page.</span></span>

5. <span data-ttu-id="35db9-194">Na stronie **Wyszukiwanie zaawansowane**, z listy rozwijanej **Wyszukaj** wybierz pozycję **Dostępne jednostki HR**.</span><span class="sxs-lookup"><span data-stu-id="35db9-194">On the **Advanced Find** page, in the **Look for** dropdown list, select **Available HR Entities**.</span></span>

6. <span data-ttu-id="35db9-195">Korzystając z opcji filtrowania, znajdź jednostki, które chcesz włączyć.</span><span class="sxs-lookup"><span data-stu-id="35db9-195">Use the filter options to find the entity or entities you want to enable.</span></span>

7. <span data-ttu-id="35db9-196">Wybierz jednostkę z listy.</span><span class="sxs-lookup"><span data-stu-id="35db9-196">Select an entity from the list.</span></span>

8. <span data-ttu-id="35db9-197">Na stronie jednostki zmień właściwość **Wygenerowano** na **Tak** dla jednostki.</span><span class="sxs-lookup"><span data-stu-id="35db9-197">On the entity page, change the **Has Been Generated** property to **Yes** for the entity.</span></span>

9. <span data-ttu-id="35db9-198">Zapisz i zamknij stronę jednostki.</span><span class="sxs-lookup"><span data-stu-id="35db9-198">Save and close the entity page.</span></span>

> [!NOTE]
> <span data-ttu-id="35db9-199">Można wygenerować wiele jednostek wirtualnych jednocześnie, korzystając ze strony **Zmień wiele rekordów**.</span><span class="sxs-lookup"><span data-stu-id="35db9-199">You can generate multiple virtual entities at once by using the **Change Multiple Records** page.</span></span> <span data-ttu-id="35db9-200">Zaznacz wiele rekordów na stronie i wybierz opcję **Edytuj** na wstążce.</span><span class="sxs-lookup"><span data-stu-id="35db9-200">Select multiple records on the page, and select **Edit** on the ribbon.</span></span> <span data-ttu-id="35db9-201">Następnie możesz zmienić właściwość **Wygenerowano** dla wszystkich zaznaczonych rekordów.</span><span class="sxs-lookup"><span data-stu-id="35db9-201">You can then change the **Has Been Generated** property for all selected records.</span></span>

![Dostępne jednostki HR](./media/hr-admin-integration-virtual-entities-available.jpg)

> [!NOTE]
> <span data-ttu-id="35db9-203">Aby usprawnić proces generowania jednostek wirtualnych w przyszłych wersjach, proces ten następuje na stronie w module Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="35db9-203">To streamline the process of generating virtual entities in future releases, the process will occur in a page in Human Resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="35db9-204">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="35db9-204">See also</span></span>

[<span data-ttu-id="35db9-205">Co to jest usługa Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="35db9-205">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="35db9-206">Przegląd jednostki</span><span class="sxs-lookup"><span data-stu-id="35db9-206">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="35db9-207">Omówienie relacji jednostek</span><span class="sxs-lookup"><span data-stu-id="35db9-207">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="35db9-208">Tworzenie i edytowanie jednostek wirtualnych zawierających dane z zewnętrznego źródła danych</span><span class="sxs-lookup"><span data-stu-id="35db9-208">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="35db9-209">Co to są portale Power Apps?</span><span class="sxs-lookup"><span data-stu-id="35db9-209">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="35db9-210">Omówienie tworzenia aplikacji w Power Apps</span><span class="sxs-lookup"><span data-stu-id="35db9-210">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
