---
title: Konfigurowanie jednostek wirtualnych usługi Common Data Service
description: W tym temacie przedstawiono sposób konfigurowania jednostek wirtualnych dla systemu Dynamics 365 Human Resources. Generuj i aktualizuj istniejące jednostki wirtualne oraz analizuj wygenerowane i dostępne jednostki.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
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
ms.openlocfilehash: 2b590faeab600d04c9d5303693ec1e9ac682250d
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645608"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="13b73-104">Konfigurowanie jednostek wirtualnych usługi Common Data Service</span><span class="sxs-lookup"><span data-stu-id="13b73-104">Configure Common Data Service virtual entities</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="13b73-105">Dynamics 365 Human Resources jest wirtualnym źródłem danych w usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13b73-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="13b73-106">Obsługuje on pełne operacje tworzenia, odczytu, aktualizacji i usuwania (CRUD) z Common Data Service i Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="13b73-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="13b73-107">Dane dla jednostek wirtualnych nie są przechowywane w usłudze Common Data Service, ale w bazie danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="13b73-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="13b73-108">Aby włączyć operacje CRUD dla jednostek zasobów ludzkich z usługi Common Data Service, należy udostępnić jednostki jako jednostki wirtualne w usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13b73-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="13b73-109">Pozwala to na wykonywanie operacji CRUD z usługi Common Data Service i Microsoft Power Platform na danych znajdujących się w module Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="13b73-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="13b73-110">Operacje te obsługują również pełne sprawdzanie poprawności logiki biznesowej w celu zapewnienia integralności danych podczas zapisywania danych w jednostkach.</span><span class="sxs-lookup"><span data-stu-id="13b73-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="13b73-111">Dostępne jednostki wirtualne dla modułu Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="13b73-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="13b73-112">Wszystkie jednostki protokołu OData (Open Data Protocol) w module Zasoby ludzkie są dostępne jako jednostki wirtualne w usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13b73-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="13b73-113">Są one również dostępne w programie Power Platform.</span><span class="sxs-lookup"><span data-stu-id="13b73-113">They're also available in Power Platform.</span></span> <span data-ttu-id="13b73-114">Teraz możesz tworzyć aplikacje i środowiska z danymi bezpośrednio z modułu Zasoby ludzkie z pełnymi funkcjami CRUD bez kopiowania lub synchronizowania danych do usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13b73-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="13b73-115">Portale Power Apps umożliwiają tworzenie zewnętrznych stron internetowych, które pozwalają realizować scenariusze współpracy w zakresie procesów biznesowych w module Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="13b73-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="13b73-116">Można wyświetlić listę jednostek wirtualnych włączonych w środowisku i rozpocząć pracę z jednostkami w [Power Apps](https://make.powerapps.com) w rozwiązaniu **Dynamics 365 HR jednostek miarowych**.</span><span class="sxs-lookup"><span data-stu-id="13b73-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Jednostki wirtualne HR Dynamics 365 w Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="13b73-118">Jednostki wirtualne a jednostki naturalne</span><span class="sxs-lookup"><span data-stu-id="13b73-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="13b73-119">Jednostki wirtualne dla modułu Zasoby ludzkie nie są takie same jak jednostki naturalne Common Data Service utworzone dla modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="13b73-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="13b73-120">Jednostki naturalne dla modułu Zasoby ludzkie są generowane oddzielnie i utrzymywane w rozwiązaniu HCM Common w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13b73-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="13b73-121">W przypadku jednostek naturalnych dane są przechowywane w usłudze Common Data Service i wymagają synchronizacji z bazą danych aplikacji Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="13b73-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="13b73-122">Aby uzyskać listę jednostek naturalnych usługi Common Data Service dla modułu Zasoby ludzkie, zobacz temat [Jednostki usługi Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="13b73-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="13b73-123">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="13b73-123">Setup</span></span>

<span data-ttu-id="13b73-124">Wykonaj te kroki konfiguracji, aby włączyć jednostki wirtualne w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="13b73-124">Follow these setup steps to enable virtual entities in your environment.</span></span>

### <a name="enable-virtual-entities-in-human-resources"></a><span data-ttu-id="13b73-125">Włącz jednostki wirtualne w module Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="13b73-125">Enable virtual entities in Human Resources</span></span>

<span data-ttu-id="13b73-126">Najpierw musisz włączyć jednostki wirtualne w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="13b73-126">First, you must enable virtual entities in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="13b73-127">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="13b73-127">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="13b73-128">Wybierz kafelek **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="13b73-128">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="13b73-129">Wybierz **obsługę jednostek wirtualnych w usłudze HR/CDS**, a następnie wybierz opcję **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="13b73-129">Select **Virtual Entity support in HR/CDS**, and then select **Enable**.</span></span>

<span data-ttu-id="13b73-130">Aby uzyskać więcej informacji na temat włączania i wyłączania funkcji, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="13b73-130">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="13b73-131">Rejestracja aplikacji w usłudze Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="13b73-131">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="13b73-132">Najpierw należy zarejestrować wystąpienie modułu Zasoby ludzkie w witrynie Azure Portal, aby platforma tożsamości Microsoft mogła udostępniać usługi uwierzytelniania i autoryzacji aplikacjom i użytkowników.</span><span class="sxs-lookup"><span data-stu-id="13b73-132">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="13b73-133">Aby uzyskać więcej informacji o rejestrowaniu aplikacji na platformie Azure, zobacz temat [Szybki Start: rejestracja aplikacji na platformie tożsamości Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="13b73-133">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="13b73-134">Otwórz portal [Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="13b73-134">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="13b73-135">Na liście usług Azure wybierz pozycję **Rejestracje aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="13b73-135">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="13b73-136">Wybierz opcję **Nowa rejestracja**.</span><span class="sxs-lookup"><span data-stu-id="13b73-136">Select **New registration**.</span></span>

4. <span data-ttu-id="13b73-137">W polu **Nazwa** wprowadź opisową nazwę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="13b73-137">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="13b73-138">Na przykład **Encje wirtualne Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="13b73-138">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="13b73-139">W polu **Identyfikator URI przekierowania** wprowadź adres URL obszaru nazw wystąpienia moduły Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="13b73-139">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="13b73-140">Wybierz opcję **Zarejestruj**.</span><span class="sxs-lookup"><span data-stu-id="13b73-140">Select **Register**.</span></span>

7. <span data-ttu-id="13b73-141">Po zakończeniu rejestracji w module Azure Portal zostanie wyświetlone okienko **Przegląd** rejestracji aplikacji , które zawiera **Identyfikator aplikacji (klienta)**.</span><span class="sxs-lookup"><span data-stu-id="13b73-141">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="13b73-142">Zapisz teraz **identyfikator aplikacji (klienta)**.</span><span class="sxs-lookup"><span data-stu-id="13b73-142">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="13b73-143">Te informacje wprowadzisz podczas [konfigurowania źródła danych jednostki wirtualnej](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="13b73-143">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="13b73-144">W lewym okienku nawigacji wybierz opcję **Certyfikaty i klucze tajne**.</span><span class="sxs-lookup"><span data-stu-id="13b73-144">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="13b73-145">W sekcji **Klucze tajne klienta** strony wybierz opcję **Nowy klucz tajny klienta**.</span><span class="sxs-lookup"><span data-stu-id="13b73-145">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="13b73-146">Podaj opis, wybierz czas trwania i wybierz przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="13b73-146">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="13b73-147">Zapisz wartość klucza tajnego.</span><span class="sxs-lookup"><span data-stu-id="13b73-147">Record the secret's value.</span></span> <span data-ttu-id="13b73-148">Te informacje wprowadzisz podczas [konfigurowania źródła danych jednostki wirtualnej](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="13b73-148">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="13b73-149">Pamiętaj, aby w tym momencie zapisać wartość klucza tajnego.</span><span class="sxs-lookup"><span data-stu-id="13b73-149">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="13b73-150">Klucz tajny nie jest nigdy wyświetlany ponownie po opuszczeniu tej strony.</span><span class="sxs-lookup"><span data-stu-id="13b73-150">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="13b73-151">Instalacja aplikacji Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="13b73-151">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="13b73-152">Zainstaluj aplikację Dynamics 365 HR Virtual Entity w środowisku Power Apps, aby wdrożyć pakiet rozwiązania jednostek wirtualnych w usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13b73-152">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="13b73-153">Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="13b73-153">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="13b73-154">Na liście **Środowiska** wybierz środowisko Power Apps skojarzone z wystąpieniem modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="13b73-154">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="13b73-155">W sekcji **Zasoby** wybierz pozycję **Aplikacje Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="13b73-155">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="13b73-156">Wybierz akcję **Zainstaluj aplikację**.</span><span class="sxs-lookup"><span data-stu-id="13b73-156">Select the **Install app** action.</span></span>

5. <span data-ttu-id="13b73-157">Wybierz **Dynamics 365 HR Virtual Entity** i kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="13b73-157">Select **Dynamics 365 HR Virtual Entity**, and select **Next**.</span></span>

6. <span data-ttu-id="13b73-158">Przejrzyj i zaznacz pole wyboru, aby wyrazić zgodę na warunki użytkowania usługi.</span><span class="sxs-lookup"><span data-stu-id="13b73-158">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="13b73-159">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="13b73-159">Select **Install**.</span></span>

<span data-ttu-id="13b73-160">Instalacja potrwa kilka minut.</span><span class="sxs-lookup"><span data-stu-id="13b73-160">The install takes a few minutes.</span></span> <span data-ttu-id="13b73-161">Po zakończeniu przejdź do kolejnych kroków.</span><span class="sxs-lookup"><span data-stu-id="13b73-161">When it completes, continue to the next steps.</span></span>

![Instalacja aplikacji Dynamics 365 HR Virtual Entity z centrum administracyjnego Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="13b73-163">Konfiguracja źródła danych jednostki wirtualnej</span><span class="sxs-lookup"><span data-stu-id="13b73-163">Configure the virtual entity data source</span></span> 

<span data-ttu-id="13b73-164">Następnym krokiem jest skonfigurowanie źródła danych jednostki wirtualnej w środowisku Power Apps.</span><span class="sxs-lookup"><span data-stu-id="13b73-164">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="13b73-165">Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="13b73-165">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="13b73-166">Na liście **Środowiska** wybierz środowisko Power Apps skojarzone z wystąpieniem modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="13b73-166">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="13b73-167">Wybierz **Adres URL środowiska** w sekcji **Szczegóły** strony.</span><span class="sxs-lookup"><span data-stu-id="13b73-167">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="13b73-168">W oknie **Centrum kondycji rozwiązania** wybierz ikonę **Wyszukiwanie zaawansowane** w prawym górnym rogu strony aplikacji.</span><span class="sxs-lookup"><span data-stu-id="13b73-168">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="13b73-169">Na stronie **Wyszukiwanie zaawansowane**, z listy rozwijanej **Wyszukaj** wybierz pozycję **Konfiguracje wirtualnego źródła danych Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="13b73-169">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="13b73-170">Wybierz opcję **Wyniki**.</span><span class="sxs-lookup"><span data-stu-id="13b73-170">Select **Results**.</span></span>

7. <span data-ttu-id="13b73-171">Wybierz rekord **Microsoft HR Data Source**.</span><span class="sxs-lookup"><span data-stu-id="13b73-171">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="13b73-172">Wprowadź wymagane informacje dotyczące konfiguracji źródła danych:</span><span class="sxs-lookup"><span data-stu-id="13b73-172">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="13b73-173">**Docelowy adres URL**: adres URL obszaru nazw modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="13b73-173">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="13b73-174">Docelowy adres URL ma format:</span><span class="sxs-lookup"><span data-stu-id="13b73-174">The format of the target URL is:</span></span>
     
     <span data-ttu-id="13b73-175">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="13b73-175">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="13b73-176">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="13b73-176">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="13b73-177">Pamiętaj, aby umieścić znak „**/**” na końcu adresu URL, aby uniknąć błędu.</span><span class="sxs-lookup"><span data-stu-id="13b73-177">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="13b73-178">**Identyfikator dzierżawcy**: identyfikator dzierżawcy Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="13b73-178">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="13b73-179">**Identyfikator aplikacji w usłudze AAD**: identyfikator aplikacji (klienta) utworzony dla aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="13b73-179">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="13b73-180">Te informacje uzyskano wcześniej w tym kroku [Rejestracja aplikacji w Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="13b73-180">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="13b73-181">**Wpis tajny aplikacji w usłudze AAD**: wpis tajny utworzony dla aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="13b73-181">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="13b73-182">Te informacje uzyskano wcześniej w tym kroku [Rejestracja aplikacji w Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="13b73-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Źródło danych Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="13b73-184">Wybierz opcję **Zapisz i zamknij**.</span><span class="sxs-lookup"><span data-stu-id="13b73-184">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="13b73-185">Udzielanie uprawnień aplikacji w module Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="13b73-185">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="13b73-186">Udziel uprawnień dwóm aplikacjom Azure AD w module zasoby ludzkie:</span><span class="sxs-lookup"><span data-stu-id="13b73-186">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="13b73-187">Aplikacji utworzonej dla Twojej dzierżawy w portalu Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="13b73-187">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="13b73-188">Aplikacji Dynamics 365 HR Virtual Entity zainstalowanej w środowisku Power Apps</span><span class="sxs-lookup"><span data-stu-id="13b73-188">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="13b73-189">W module Zasoby ludzkie otwórz stronę **Aplikacje Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="13b73-189">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="13b73-190">Wybierz pozycję **Nowy**, aby utworzyć nowy rekord aplikacji:</span><span class="sxs-lookup"><span data-stu-id="13b73-190">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="13b73-191">W polu **Identyfikator klienta** wprowadź identyfikator klienta aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="13b73-191">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="13b73-192">W polu **Nazwa** wprowadź nazwę aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="13b73-192">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="13b73-193">W polu **Identyfikator użytkownika** wybierz identyfikator użytkownika z uprawnieniami administratora w module Zasoby ludzkie i środowisku Power Apps.</span><span class="sxs-lookup"><span data-stu-id="13b73-193">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="13b73-194">Wybierz pozycję **Nowy**, aby utworzyć drugi rekord aplikacji:</span><span class="sxs-lookup"><span data-stu-id="13b73-194">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="13b73-195">**Identyfikator klienta**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="13b73-195">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="13b73-196">**Nazwa**: Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="13b73-196">**Name**: Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="13b73-197">W polu **Identyfikator użytkownika** wybierz identyfikator użytkownika z uprawnieniami administratora w module Zasoby ludzkie i środowisku Power Apps.</span><span class="sxs-lookup"><span data-stu-id="13b73-197">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="13b73-198">Generowanie jednostek wirtualnych</span><span class="sxs-lookup"><span data-stu-id="13b73-198">Generate virtual entities</span></span>

<span data-ttu-id="13b73-199">Po zakończeniu pracy Instalatora można wybrać jednostki wirtualne, które mają zostać wygenerowane i włączone w instancji usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13b73-199">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="13b73-200">W module Zasoby ludzkie otwórz stronę **Integracja Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="13b73-200">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="13b73-201">Wybierz kartę **Jednostki wirtualne**.</span><span class="sxs-lookup"><span data-stu-id="13b73-201">Select the **Virtual entities** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="13b73-202">**Włączenie przełączania jednostek wirtualnych** będzie automatycznie ustawiane na wartość **Tak**, gdy wszystkie wymagane ustawienia zostaną zakończone.</span><span class="sxs-lookup"><span data-stu-id="13b73-202">The **Enable the virtual entity** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="13b73-203">Jeśli przełącznik ma wartość **Nie**, sprawdź kroki w poprzednich sekcjach tego dokumentu, aby upewnić się, że wszystkie ustawienia wymagań wstępnych zostały zakończone.</span><span class="sxs-lookup"><span data-stu-id="13b73-203">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="13b73-204">Wybierz jednostki lub jednostki, w których chcesz utworzyć w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13b73-204">Select the entity or entities you want to generate in Common Data Service.</span></span>

4. <span data-ttu-id="13b73-205">Wybierz opcję **Generuj/Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="13b73-205">Select **Generate/refresh**.</span></span>

![Integracja z usługą Common Data Service](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a><span data-ttu-id="13b73-207">Sprawdź stan generacji jednostki</span><span class="sxs-lookup"><span data-stu-id="13b73-207">Check entity generation status</span></span>

<span data-ttu-id="13b73-208">Jednostki wirtualne są generowane w Common Data Service w trakcie asynchronicznego procesu w tle.</span><span class="sxs-lookup"><span data-stu-id="13b73-208">Virtual entities are generated in Common Data Service through an asynchronous background process.</span></span> <span data-ttu-id="13b73-209">Aktualizacje w procesie są wyświetlane w centrum akcji.</span><span class="sxs-lookup"><span data-stu-id="13b73-209">Updates on the process display in the action center.</span></span> <span data-ttu-id="13b73-210">Szczegóły procesu, w tym dzienniki błędów, znajdują się na stronie **Automatyzacja procesów**.</span><span class="sxs-lookup"><span data-stu-id="13b73-210">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="13b73-211">W module Human Resources otwórz stronę listy **Automatyzacja procesów**.</span><span class="sxs-lookup"><span data-stu-id="13b73-211">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="13b73-212">Wybierz kartę **Procesy w tle**.</span><span class="sxs-lookup"><span data-stu-id="13b73-212">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="13b73-213">Wybierz **Proces w tle asynchronicznego sondowania jednostki wirtualnej**.</span><span class="sxs-lookup"><span data-stu-id="13b73-213">Select **Virtual entity poll async operation background process**.</span></span>

4. <span data-ttu-id="13b73-214">Służy do **Wyświetl ostatnie wyniki**.</span><span class="sxs-lookup"><span data-stu-id="13b73-214">Select **View most recent results**.</span></span>

<span data-ttu-id="13b73-215">W okienku slideout wyświetlane są najnowsze wyniki wykonania procesu.</span><span class="sxs-lookup"><span data-stu-id="13b73-215">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="13b73-216">Można przejrzeć dziennik procesu, w tym wszystkie błędy zwrócone przez system Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13b73-216">You can view the log for the process, including any errors returned from Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="13b73-217">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="13b73-217">See also</span></span>

[<span data-ttu-id="13b73-218">Co to jest usługa Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="13b73-218">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="13b73-219">Przegląd jednostki</span><span class="sxs-lookup"><span data-stu-id="13b73-219">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="13b73-220">Omówienie relacji jednostek</span><span class="sxs-lookup"><span data-stu-id="13b73-220">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="13b73-221">Tworzenie i edytowanie jednostek wirtualnych zawierających dane z zewnętrznego źródła danych</span><span class="sxs-lookup"><span data-stu-id="13b73-221">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="13b73-222">Co to są portale Power Apps?</span><span class="sxs-lookup"><span data-stu-id="13b73-222">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="13b73-223">Omówienie tworzenia aplikacji w Power Apps</span><span class="sxs-lookup"><span data-stu-id="13b73-223">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
