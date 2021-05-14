---
title: Konfiguruj tabele wirtualne usługi Dataverse
description: W tym temacie przedstawiono sposób konfigurowania tabel wirtualnych dla systemu Dynamics 365 Human Resources. Generuj i aktualizuj istniejące tabele wirtualne oraz analizuj wygenerowane i dostępne tabele.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 04997aba427ae6013c8154593b09ae1a45a580c3
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935760"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="5ec74-104">Konfiguruj tabele wirtualne usługi Dataverse</span><span class="sxs-lookup"><span data-stu-id="5ec74-104">Configure Dataverse virtual tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="5ec74-105">Dynamics 365 Human Resources jest wirtualnym źródłem danych w usłudze Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ec74-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="5ec74-106">Obsługuje on pełne operacje tworzenia, odczytu, aktualizacji i usuwania (CRUD) z Dataverse i Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="5ec74-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="5ec74-107">Dane dla tabel wirtualnych nie są przechowywane w usłudze Dataverse, ale w bazie danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5ec74-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="5ec74-108">Aby włączyć operacje CRUD dla jednostek zasobów ludzkich z usługi Dataverse, należy udostępnić jednostki jako tabele wirtualne w usłudze Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ec74-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="5ec74-109">Pozwala to na wykonywanie operacji CRUD z usługi Dataverse i Microsoft Power Platform na danych znajdujących się w module Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="5ec74-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="5ec74-110">Operacje te obsługują również pełne sprawdzanie poprawności logiki biznesowej w celu zapewnienia integralności danych podczas zapisywania danych w jednostkach.</span><span class="sxs-lookup"><span data-stu-id="5ec74-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="5ec74-111">Jednostki Human Resources odpowiadają tabelom Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ec74-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="5ec74-112">Aby uzyskać więcej informacji o Dataverse (poprzednio Common Data Service) i aktualizacjach terminologii, zobacz [Co to jest Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="5ec74-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="5ec74-113">Dostępne tabele wirtualne dla modułu Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5ec74-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="5ec74-114">Wszystkie jednostki protokołu OData (Open Data Protocol) w module Zasoby ludzkie są dostępne jako tabele wirtualne w usłudze Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ec74-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="5ec74-115">Są one również dostępne w programie Power Platform.</span><span class="sxs-lookup"><span data-stu-id="5ec74-115">They're also available in Power Platform.</span></span> <span data-ttu-id="5ec74-116">Teraz możesz tworzyć aplikacje i środowiska z danymi bezpośrednio z modułu Zasoby ludzkie z pełnymi funkcjami CRUD bez kopiowania lub synchronizowania danych do usługi Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ec74-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="5ec74-117">Portale Power Apps umożliwiają tworzenie zewnętrznych stron internetowych, które pozwalają realizować scenariusze współpracy w zakresie procesów biznesowych w module Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="5ec74-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="5ec74-118">Można wyświetlić listę tabel wirtualnych włączonych w środowisku i rozpocząć pracę z tabelami w [Power Apps](https://make.powerapps.com) w rozwiązaniu **Dynamics 365 HR tabel miarowych**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Tabele wirtualne HR Dynamics 365 w Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="5ec74-120">Tabele wirtualne a tabele macierzyste</span><span class="sxs-lookup"><span data-stu-id="5ec74-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="5ec74-121">Tabele wirtualne dla modułu Zasoby ludzkie nie są takie same jak tabele natywne Dataverse utworzone dla modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="5ec74-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="5ec74-122">Tabele natywne dla modułu Zasoby ludzkie są generowane oddzielnie i utrzymywane w rozwiązaniu HCM Common w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ec74-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="5ec74-123">W przypadku tabel natywnych dane są przechowywane w usłudze Dataverse i wymagają synchronizacji z bazą danych aplikacji Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="5ec74-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="5ec74-124">Aby uzyskać listę tabel natywnych usługi Dataverse dla modułu Zasoby ludzkie, zobacz temat [Tabele usługi Dataverse](./hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="5ec74-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](./hr-developer-entities.md).</span></span>

## <a name="setup"></a><span data-ttu-id="5ec74-125">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="5ec74-125">Setup</span></span>

<span data-ttu-id="5ec74-126">Wykonaj te kroki konfiguracji, aby włączyć tabele wirtualne w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="5ec74-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="5ec74-127">Włącz tabele wirtualne w module Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5ec74-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="5ec74-128">Najpierw musisz włączyć tabele wirtualne w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="5ec74-129">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="5ec74-130">Wybierz kafelek **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="5ec74-131">Wybierz **Obsługę tabel wirtualnych dla HR w Dataverse**, a następnie wybierz opcję **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="5ec74-132">Aby uzyskać więcej informacji na temat włączania i wyłączania funkcji, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="5ec74-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="5ec74-133">Rejestracja aplikacji w usłudze Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="5ec74-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="5ec74-134">Najpierw należy zarejestrować wystąpienie modułu Zasoby ludzkie w witrynie Azure Portal, aby platforma tożsamości Microsoft mogła udostępniać usługi uwierzytelniania i autoryzacji aplikacjom i użytkowników.</span><span class="sxs-lookup"><span data-stu-id="5ec74-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="5ec74-135">Aby uzyskać więcej informacji o rejestrowaniu aplikacji na platformie Azure, zobacz temat [Szybki Start: rejestracja aplikacji na platformie tożsamości Microsoft](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="5ec74-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="5ec74-136">Otwórz portal [Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="5ec74-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="5ec74-137">Na liście usług Azure wybierz pozycję **Rejestracje aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="5ec74-138">Wybierz opcję **Nowa rejestracja**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-138">Select **New registration**.</span></span>

4. <span data-ttu-id="5ec74-139">W polu **Nazwa** wprowadź opisową nazwę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5ec74-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="5ec74-140">Na przykład **Tabele wirtualne Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="5ec74-141">W polu **Identyfikator URI przekierowania** wprowadź adres URL obszaru nazw wystąpienia moduły Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="5ec74-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="5ec74-142">Wybierz opcję **Zarejestruj**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-142">Select **Register**.</span></span>

7. <span data-ttu-id="5ec74-143">Po zakończeniu rejestracji w module Azure Portal zostanie wyświetlone okienko **Przegląd** rejestracji aplikacji , które zawiera **Identyfikator aplikacji (klienta)**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="5ec74-144">Zapisz teraz **identyfikator aplikacji (klienta)**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="5ec74-145">Te informacje wprowadzisz podczas [Konfigurowania źródła danych tabeli wirtualnej](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="5ec74-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="5ec74-146">W lewym okienku nawigacji wybierz opcję **Certyfikaty i klucze tajne**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="5ec74-147">W sekcji **Klucze tajne klienta** strony wybierz opcję **Nowy klucz tajny klienta**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="5ec74-148">Podaj opis, wybierz czas trwania i wybierz przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="5ec74-149">Zanotuj wartość tajnych właściwości tabeli **Wartość**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-149">Record the secret's value from the **Value** property of the table.</span></span> <span data-ttu-id="5ec74-150">Te informacje wprowadzisz podczas [Konfigurowania źródła danych tabeli wirtualnej](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="5ec74-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5ec74-151">Pamiętaj, aby w tym momencie zapisać wartość klucza tajnego.</span><span class="sxs-lookup"><span data-stu-id="5ec74-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="5ec74-152">Klucz tajny nie jest nigdy wyświetlany ponownie po opuszczeniu tej strony.</span><span class="sxs-lookup"><span data-stu-id="5ec74-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="5ec74-153">Instalacja aplikacji Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="5ec74-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="5ec74-154">Zainstaluj aplikację Dynamics 365 HR Virtual Table w środowisku Power Apps, aby wdrożyć pakiet rozwiązania tabel wirtualnych w usłudze Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ec74-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="5ec74-155">W module Zasoby ludzkie otwórz stronę **Integracja Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-155">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="5ec74-156">Wybierz kartę **Tabele wirtualne**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-156">Select the **Virtual tables** tab.</span></span>

3. <span data-ttu-id="5ec74-157">Wybierz opcję **Zainstaluj aplikację tabeli wirtualnej**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-157">Select **Install virtual table app**.</span></span>

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="5ec74-158">Konfiguracja źródła danych tabeli wirtualnej</span><span class="sxs-lookup"><span data-stu-id="5ec74-158">Configure the virtual table data source</span></span>

<span data-ttu-id="5ec74-159">Następnym krokiem jest skonfigurowanie źródła danych tabeli wirtualnej w środowisku Power Apps.</span><span class="sxs-lookup"><span data-stu-id="5ec74-159">The next step is to configure the virtual table data source in the Power Apps environment.</span></span>

1. <span data-ttu-id="5ec74-160">Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5ec74-160">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="5ec74-161">Na liście **Środowiska** wybierz środowisko Power Apps skojarzone z wystąpieniem modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="5ec74-161">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="5ec74-162">Wybierz **Adres URL środowiska** w sekcji **Szczegóły** strony.</span><span class="sxs-lookup"><span data-stu-id="5ec74-162">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="5ec74-163">W oknie **Centrum kondycji rozwiązania** wybierz ikonę **Wyszukiwanie zaawansowane** w prawym górnym rogu strony aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5ec74-163">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="5ec74-164">Na stronie **Wyszukiwanie zaawansowane**, z listy rozwijanej **Wyszukaj** wybierz pozycję **Konfiguracje wirtualnego źródła danych Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-164">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5ec74-165">Instalacja aplikacji tabel wirtualnych z poprzedniego kroku konfiguracji może potrwać kilka minut.</span><span class="sxs-lookup"><span data-stu-id="5ec74-165">The installation of the virtual table app from the previous setup step can take a few minutes.</span></span> <span data-ttu-id="5ec74-166">Jeśli na liście nie opcji **Konfiguracje wirtualnego źródła danych Finance and Operations**, zaczekaj na minutę i odśwież listę.</span><span class="sxs-lookup"><span data-stu-id="5ec74-166">If **Finance and Operations Virtual Data Source Configurations** isn't available in the list, wait for a minute and refresh the list.</span></span>

6. <span data-ttu-id="5ec74-167">Wybierz opcję **Wyniki**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-167">Select **Results**.</span></span>

7. <span data-ttu-id="5ec74-168">Wybierz rekord **Microsoft HR Data Source**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-168">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="5ec74-169">Wprowadź wymagane informacje dotyczące konfiguracji źródła danych:</span><span class="sxs-lookup"><span data-stu-id="5ec74-169">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="5ec74-170">**Docelowy adres URL**: adres URL obszaru nazw modułu Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="5ec74-170">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="5ec74-171">Docelowy adres URL ma format:</span><span class="sxs-lookup"><span data-stu-id="5ec74-171">The format of the target URL is:</span></span>
     
     <span data-ttu-id="5ec74-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="5ec74-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="5ec74-173">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="5ec74-173">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="5ec74-174">Pamiętaj, aby umieścić znak „**/**” na końcu adresu URL, aby uniknąć błędu.</span><span class="sxs-lookup"><span data-stu-id="5ec74-174">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="5ec74-175">**Identyfikator dzierżawcy**: identyfikator dzierżawcy Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="5ec74-175">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="5ec74-176">**Identyfikator aplikacji w usłudze AAD**: identyfikator aplikacji (klienta) utworzony dla aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="5ec74-176">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="5ec74-177">Te informacje uzyskano wcześniej w tym kroku [Rejestracja aplikacji w Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="5ec74-177">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="5ec74-178">**Wpis tajny aplikacji w usłudze AAD**: wpis tajny utworzony dla aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="5ec74-178">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="5ec74-179">Te informacje uzyskano wcześniej w tym kroku [Rejestracja aplikacji w Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="5ec74-179">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Źródło danych Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="5ec74-181">Wybierz opcję **Zapisz i zamknij**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-181">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="5ec74-182">Udzielanie uprawnień aplikacji w module Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="5ec74-182">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="5ec74-183">Udziel uprawnień dwóm aplikacjom Azure AD w module zasoby ludzkie:</span><span class="sxs-lookup"><span data-stu-id="5ec74-183">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="5ec74-184">Aplikacji utworzonej dla Twojej dzierżawy w portalu Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="5ec74-184">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="5ec74-185">Aplikacji Dynamics 365 HR Virtual Table zainstalowanej w środowisku Power Apps</span><span class="sxs-lookup"><span data-stu-id="5ec74-185">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="5ec74-186">W module Zasoby ludzkie otwórz stronę **Aplikacje Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-186">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="5ec74-187">Wybierz pozycję **Nowy**, aby utworzyć nowy rekord aplikacji:</span><span class="sxs-lookup"><span data-stu-id="5ec74-187">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="5ec74-188">W polu **Identyfikator klienta** wprowadź identyfikator klienta aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="5ec74-188">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="5ec74-189">W polu **Nazwa** wprowadź nazwę aplikacji zarejestrowanej w portalu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="5ec74-189">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="5ec74-190">W polu **Identyfikator użytkownika** wybierz identyfikator użytkownika z uprawnieniami administratora w module Zasoby ludzkie i środowisku Power Apps.</span><span class="sxs-lookup"><span data-stu-id="5ec74-190">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="5ec74-191">Wybierz pozycję **Nowy**, aby utworzyć drugi rekord aplikacji:</span><span class="sxs-lookup"><span data-stu-id="5ec74-191">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="5ec74-192">**Identyfikator klienta**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="5ec74-192">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="5ec74-193">**Nazwa**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="5ec74-193">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="5ec74-194">W polu **Identyfikator użytkownika** wybierz identyfikator użytkownika z uprawnieniami administratora w module Zasoby ludzkie i środowisku Power Apps.</span><span class="sxs-lookup"><span data-stu-id="5ec74-194">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="5ec74-195">Generowanie tabel wirtualnych</span><span class="sxs-lookup"><span data-stu-id="5ec74-195">Generate virtual tables</span></span>

<span data-ttu-id="5ec74-196">Po zakończeniu pracy Instalatora można wybrać tabele wirtualne, które mają zostać wygenerowane i włączone w instancji usługi Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ec74-196">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="5ec74-197">W module Zasoby ludzkie otwórz stronę **Integracja Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-197">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="5ec74-198">Wybierz kartę **Tabele wirtualne**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-198">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="5ec74-199">**Włączenie przełączania tabel wirtualnych** będzie automatycznie ustawiane na wartość **Tak**, gdy wszystkie wymagane ustawienia zostaną zakończone.</span><span class="sxs-lookup"><span data-stu-id="5ec74-199">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="5ec74-200">Jeśli przełącznik ma wartość **Nie**, sprawdź kroki w poprzednich sekcjach tego dokumentu, aby upewnić się, że wszystkie ustawienia wymagań wstępnych zostały zakończone.</span><span class="sxs-lookup"><span data-stu-id="5ec74-200">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="5ec74-201">Wybierz tabelę lub tabele, w których chcesz utworzyć w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ec74-201">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="5ec74-202">Wybierz opcję **Generuj/Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-202">Select **Generate/refresh**.</span></span>

![Integracja z usługą Dataverse](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a><span data-ttu-id="5ec74-204">Sprawdź stan generacji tabel</span><span class="sxs-lookup"><span data-stu-id="5ec74-204">Check table generation status</span></span>

<span data-ttu-id="5ec74-205">Tabele wirtualne są generowane w Dataverse w trakcie asynchronicznego procesu w tle.</span><span class="sxs-lookup"><span data-stu-id="5ec74-205">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="5ec74-206">Aktualizacje w procesie są wyświetlane w centrum akcji.</span><span class="sxs-lookup"><span data-stu-id="5ec74-206">Updates on the process display in the action center.</span></span> <span data-ttu-id="5ec74-207">Szczegóły procesu, w tym dzienniki błędów, znajdują się na stronie **Automatyzacja procesów**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-207">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="5ec74-208">W module Human Resources otwórz stronę listy **Automatyzacja procesów**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-208">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="5ec74-209">Wybierz kartę **Procesy w tle**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-209">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="5ec74-210">Wybierz **Proces w tle asynchronicznego sondowania tabeli wirtualnej**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-210">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="5ec74-211">Służy do **Wyświetl ostatnie wyniki**.</span><span class="sxs-lookup"><span data-stu-id="5ec74-211">Select **View most recent results**.</span></span>

<span data-ttu-id="5ec74-212">W okienku slideout wyświetlane są najnowsze wyniki wykonania procesu.</span><span class="sxs-lookup"><span data-stu-id="5ec74-212">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="5ec74-213">Można przejrzeć dziennik procesu, w tym wszystkie błędy zwrócone przez system Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ec74-213">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ec74-214">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="5ec74-214">See also</span></span>

[<span data-ttu-id="5ec74-215">Co to jest usługa Dataverse?</span><span class="sxs-lookup"><span data-stu-id="5ec74-215">What is Dataverse?</span></span>](/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="5ec74-216">Tabele w Dataverse</span><span class="sxs-lookup"><span data-stu-id="5ec74-216">Tables in Dataverse</span></span>](/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="5ec74-217">Omówienie relacji tabel</span><span class="sxs-lookup"><span data-stu-id="5ec74-217">Table relationships overview</span></span>](/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="5ec74-218">Tworzenie i edytowanie tabel wirtualnych zawierających dane z zewnętrznego źródła danych</span><span class="sxs-lookup"><span data-stu-id="5ec74-218">Create and edit virtual tables that contain data from an external data source</span></span>](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="5ec74-219">Co to są portale Power Apps?</span><span class="sxs-lookup"><span data-stu-id="5ec74-219">What is Power Apps portals?</span></span>](/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="5ec74-220">Omówienie tworzenia aplikacji w Power Apps</span><span class="sxs-lookup"><span data-stu-id="5ec74-220">Overview of creating apps in Power Apps</span></span>](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
