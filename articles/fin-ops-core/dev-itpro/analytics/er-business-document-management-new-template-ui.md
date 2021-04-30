---
title: Nowy interfejs użytkownika w stylu Microsoft Office dokumentu w zarządzaniu dokumentami biznesowymi
description: W tym temacie wyjaśniono, jak używać nowego interfejsu użytkownika w funkcji zarządzania dokumentami biznesowymi struktury raportowania elektronicznego (ER).
author: v-anamir
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881043"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a><span data-ttu-id="0c879-103">Nowy interfejs użytkownika w stylu Microsoft Office dokumentu w zarządzaniu dokumentami biznesowymi</span><span class="sxs-lookup"><span data-stu-id="0c879-103">Microsoft Office-style user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0c879-104">Zarządzanie dokumentami biznesowymi pozwala użytkownikom korzystać z usługi Microsoft 365 lub odpowiedniej aplikacji komputerowej Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="0c879-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="0c879-105">Edycja może obejmować zmiany projektu lub nowe wdrożenia albo użytkownicy mogą dodawać symbole zastępcze w celu dołączenia dodatkowych danych bez konieczności zmieniania kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="0c879-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="0c879-106">Aby uzyskać więcej informacji na temat pracy z zarządzaniem dokumentami biznesowymi, zapoznaj się z [Omówieniem zarządzania dokumentami biznesowymi](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="0c879-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="0c879-107">Nowy interfejs użytkownika (UI) jest wyraźniejszy i wygodniejszy do używania.</span><span class="sxs-lookup"><span data-stu-id="0c879-107">The new user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="0c879-108">W obszarze **Dokument biznesowy** są wyświetlane tylko szablony dostępne dla bieżącego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="0c879-108">The **Business document** area shows only the templates that are available for the current provider.</span></span> <span data-ttu-id="0c879-109">W poprzednim interfejsie użytkownika na karcie **Szablon** zostały wyświetlone wszystkie szablony dostępne dla dowolnego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="0c879-109">In the previous UI, the **Template** tab listed all the templates that were available for any providers.</span></span> <span data-ttu-id="0c879-110">Pokazał również wszystkie szablony, które zostały utworzone i edytowane przez dowolnego użytkownika, który pełnił tę samą rolę.</span><span class="sxs-lookup"><span data-stu-id="0c879-110">It also showed all the templates that were created and edited by any user who had the same role.</span></span>

<span data-ttu-id="0c879-111">Można użyć przycisku **Nowy dokument** , który umożliwia użytkownikom tworzenie i edytowanie szablonu w konfiguracji formatu sprawozdawczości elektronicznej (ER) dostarczonej przez innego dostawcę.</span><span class="sxs-lookup"><span data-stu-id="0c879-111">You can use the **New document** button to create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="0c879-112">W przykładzie przedstawionym w tym temacie dostawcą jest Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c879-112">In the example in this topic, the provider is Microsoft.</span></span> <span data-ttu-id="0c879-113">Szablon można również utworzyć, przesyłając własny szablon w formacie programu Excel.</span><span class="sxs-lookup"><span data-stu-id="0c879-113">Alternatively, you can create a template by uploading your own template in Excel format.</span></span>


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

<span data-ttu-id="0c879-114">Film [Utwórz nowy dokument biznesowy za pomocą funkcji Zarządzanie dokumentami biznesowymi](https://youtu.be/gAIYl-mM_pw) (pokazany powyżej) jest dołączony do [Listy odtwarzania Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na stronie YouTube.</span><span class="sxs-lookup"><span data-stu-id="0c879-114">The [Create a new business document using Business document management](https://youtu.be/gAIYl-mM_pw) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="0c879-115">Udostępnij interfejs użytkownika nowego dokumentu w zarządzaniu dokumentami biznesowymi</span><span class="sxs-lookup"><span data-stu-id="0c879-115">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="0c879-116">Aby rozpocząć korzystanie z interfejsu użytkownika nowego dokumentu w module Zarządzanie dokumentami biznesowymi, należy uruchomić funkcję **wyglądającą jak interfejs użytkownika Office do zarządzania dokumentami biznesowymi** w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="0c879-116">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="0c879-117">Aby włączyć tę funkcję dla wszystkich firm, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0c879-117">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="0c879-118">W obszarze roboczym **Zarządzanie funkcjami** na karcie **Wszystkie** wybierz pozycję **Wyglądający jak Office interfejs użytkownika na potrzeby zarządzania dokumentami** biznesowymi na liście.</span><span class="sxs-lookup"><span data-stu-id="0c879-118">In the **Feature management** workspace, on the **All** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="0c879-119">Wybierz opcję **Włącz teraz**, aby włączyć wybraną funkcję.</span><span class="sxs-lookup"><span data-stu-id="0c879-119">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="0c879-120">Odśwież stronę, aby uzyskać dostęp do nowej funkcji.</span><span class="sxs-lookup"><span data-stu-id="0c879-120">Refresh the page to access the new feature.</span></span>

## <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="0c879-121">Edytuj szablony należące do innych dostawców</span><span class="sxs-lookup"><span data-stu-id="0c879-121">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="0c879-122">W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.</span><span class="sxs-lookup"><span data-stu-id="0c879-122">In the **Business document management** workspace, select **New document**.</span></span>

    ![Strona obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="0c879-124">Na karcie **Wybierz** wybierz dokument, który ma być używany jako szablon, a następnie wybierz opcję **Utwórz dokument**.</span><span class="sxs-lookup"><span data-stu-id="0c879-124">On the **Select** tab, select the document to use as a template, and then select **Create document**.</span></span>

    ![Dokumenty biznesowe, okno dialogowe](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="0c879-126">W nowym oknie dialogowym, w polu **Tytuł**, zmień tytuł zgodnie z potrzebą.</span><span class="sxs-lookup"><span data-stu-id="0c879-126">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="0c879-127">Tekst będzie używany do napełniania nowej nazwy tworzonej automatycznie konfiguracji formatu ER.</span><span class="sxs-lookup"><span data-stu-id="0c879-127">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="0c879-128">Wersja robocza tej konfiguracji (**Raport o fakturach niezależnych dla odbiorców (GER) - Kopia**) będzie zawierać edytowany szablon i zostanie automatycznie oznaczona do uruchomienia tego formatu ER dla bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0c879-128">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="0c879-129">Niezmodyfikowany oryginalny szablon z podstawowej konfiguracji formatu źródłowego będzie używany do uruchamiania tego formatu ER dla każdego innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0c879-129">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="0c879-130">W polu **Nazwa** zmień nazwę pierwszej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.</span><span class="sxs-lookup"><span data-stu-id="0c879-130">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="0c879-131">W polu **Komentarz** zaktualizuj uwagę dla automatycznie wygenerowanej poprawki edytowalnego szablonu, która zostanie utworzona automatycznie.</span><span class="sxs-lookup"><span data-stu-id="0c879-131">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="0c879-132">Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.</span><span class="sxs-lookup"><span data-stu-id="0c879-132">Select **OK** to confirm the start of the editing process.</span></span>

    ![Tworzenie dokumentu, okno dialogowe](./media/BDM_overview_new_template3.png)

<span data-ttu-id="0c879-134">Przycisk **Nowy dokument** umożliwia użytkownikom tworzenie i edytowanie szablonu w konfiguracji formatu sprawozdawczości elektronicznej (ER) dostarczonej przez innego dostawcę.</span><span class="sxs-lookup"><span data-stu-id="0c879-134">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="0c879-135">W przykładzie przedstawionym w tym temacie dostawcą jest Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c879-135">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="0c879-136">Kliknięcie przycisku **Nowy dokument** powoduje wyświetlenie wszystkich szablonów należących do bieżącego i innych dostawców.</span><span class="sxs-lookup"><span data-stu-id="0c879-136">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="0c879-137">Po wybraniu szablonu, zostanie on otwarty do edycji.</span><span class="sxs-lookup"><span data-stu-id="0c879-137">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="0c879-138">Edytowany szablon zostanie następnie zapisany w nowej konfiguracji formatu, która jest generowana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="0c879-138">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a><span data-ttu-id="0c879-139">Przekaż szablon, który używa istniejącego formatu programu Excel</span><span class="sxs-lookup"><span data-stu-id="0c879-139">Upload a template that uses an existing Excel format</span></span>
<span data-ttu-id="0c879-140">Przed przekazaniem szablonu należy podać wymagane informacje jak opisano w poniższych krokach.</span><span class="sxs-lookup"><span data-stu-id="0c879-140">Follow these steps to provide required information before you upload a template.</span></span>

1. <span data-ttu-id="0c879-141">W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.</span><span class="sxs-lookup"><span data-stu-id="0c879-141">In the **Business document management** workspace, select **New document**.</span></span>

    ![Strona obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM_overview_new_template1.png)
    
2. <span data-ttu-id="0c879-143">Na stronie **Tworzenie nowego szablonu**, na karcie **Przekaż**, na karcie **Szablon** wybierz pozycję **Przeglądaj**, aby znaleźć i wybrać plik programu Excel, który ma być szablonem.</span><span class="sxs-lookup"><span data-stu-id="0c879-143">On the **Create a new template** page, on the **Upload** tab, on the **Template** tab, select **Browse** to find and select the Excel file that you want to use as a template.</span></span> <span data-ttu-id="0c879-144">W sekcji **Szablon** pola **Tytuł** i **Opis** są wypełniane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="0c879-144">In the **Template** section, the **Title** and **Description** fields are automatically filled in.</span></span> <span data-ttu-id="0c879-145">Określają nazwę i opis nowej konfiguracji formatu ER, która jest tworzona automatycznie.</span><span class="sxs-lookup"><span data-stu-id="0c879-145">They specify the name and description of the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="0c879-146">Możesz edytować te pola według potrzeb.</span><span class="sxs-lookup"><span data-stu-id="0c879-146">You can edit these fields as you require.</span></span>
3. <span data-ttu-id="0c879-147">W sekcji **Typ dokumentu**, w polu **Nazwa** określ typ dokumentu biznesowego.</span><span class="sxs-lookup"><span data-stu-id="0c879-147">In the **Document Type** section, in the **Name** field, specify the type of business document.</span></span> <span data-ttu-id="0c879-148">Ta wartość będzie używana do wyszukiwania poprawnego źródła danych (to znaczy konfiguracji modelu ER).</span><span class="sxs-lookup"><span data-stu-id="0c879-148">This value will be used to search the correct data source (that is, the ER model configuration).</span></span>

    ![Karta szablonu](./media/BDM_overview_new_UI_import_21.jpg)

4. <span data-ttu-id="0c879-150">Na karcie **Źródło danych** na skróconej karcie **Filtruj** wybierz pozycję **Zastosuj filtr**.</span><span class="sxs-lookup"><span data-stu-id="0c879-150">On the **Data source** tab, on the **Filter** FastTab, select **Apply filter**.</span></span> <span data-ttu-id="0c879-151">W sekcji **Źródło danych** pole **Nazwa** jest wypełniane automatycznie lub można ręcznie wybrać wartość.</span><span class="sxs-lookup"><span data-stu-id="0c879-151">In the **Data source** section, the **Name** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="0c879-152">Filtr umożliwia wyszukiwanie odpowiedniej nazwy źródła danych według nazwy, opisu, kodu kraju/regionu i typu dokumentu biznesowego.</span><span class="sxs-lookup"><span data-stu-id="0c879-152">You can use the filter to search for the appropriate data source name by name, description, country/region code, and business document type.</span></span>

    ![Karta Źródło danych](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > <span data-ttu-id="0c879-154">Skrócona karta **Filtruj** będzie używana do wyszukiwania poprawnego źródła danych (to znaczy konfiguracji modelu ER).</span><span class="sxs-lookup"><span data-stu-id="0c879-154">The **Filter** FastTab is used to search the correct data source (that is, the ER model configuration).</span></span> <span data-ttu-id="0c879-155">Możesz edytować wszystkie pola filtrów, aby znaleźć najbardziej odpowiednie źródło danych dla przesyłanego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="0c879-155">You can edit all filter fields to find the most appropriate data source for the document that you're uploading.</span></span>
    > 
    > <span data-ttu-id="0c879-156">Warunki na skróconej karcie **Filtruj** są używane jako warunki **OR**.</span><span class="sxs-lookup"><span data-stu-id="0c879-156">The conditions on the **Filter** FastTab are used as **OR** conditions.</span></span>
    
5. <span data-ttu-id="0c879-157">Na karcie **mapowanie** wybierz opcję **Automatyczne wykrywanie**.</span><span class="sxs-lookup"><span data-stu-id="0c879-157">On the **Mapping** tab, select **Auto detect**.</span></span> <span data-ttu-id="0c879-158">Pole **Definicja źródłowa** jest wypełniane automatycznie lub można ręcznie wybrać wartość.</span><span class="sxs-lookup"><span data-stu-id="0c879-158">The **Root definition** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="0c879-159">Na tej karcie jest przedstawiane końcowe mapowanie elementów z szablonu i modelu.</span><span class="sxs-lookup"><span data-stu-id="0c879-159">This tab shows the end mapping for the elements from the template and the model.</span></span>

    ![Karta Mapowanie](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > <span data-ttu-id="0c879-161">Mapowanie w sekcji **Struktura szablonu** korzysta z pełnego dopasowania etykiet lub opisów w źródle danych w języku użytkownika i w nazwie komórki w szablonie.</span><span class="sxs-lookup"><span data-stu-id="0c879-161">The mapping in the **Template structure** section uses the full match of the labels or descriptions in the data source in the user's language, and in the cell name in the template.</span></span>

6. <span data-ttu-id="0c879-162">Wybierz pozycję **Utwórz dokument**, aby potwierdzić, że chcesz utworzyć szablon i rozpocząć proces edycji.</span><span class="sxs-lookup"><span data-stu-id="0c879-162">Select **Create document** to confirm that you want to create a template and start the editing process.</span></span>

<span data-ttu-id="0c879-163">Aby uzyskać więcej informacji, zajrzyj do omówienia [Zarządzania dokumentami biznesowymi](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="0c879-163">For more information, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="0c879-164">Jeśli w raportowaniu elektronicznym nie ma dostawcy, można go utworzyć.</span><span class="sxs-lookup"><span data-stu-id="0c879-164">If there isn't a provider in Electronic reporting, you can create one.</span></span> <span data-ttu-id="0c879-165">Jeśli nie ma aktywnego dostawcy, możesz go aktywować.</span><span class="sxs-lookup"><span data-stu-id="0c879-165">If there's no active provider, you can select to activate one.</span></span>

- <span data-ttu-id="0c879-166">Aby utworzyć dostawcę, zmień nazwę dostawcy w polu **Nazwa**, zaktualizuj adres internetowy nowego dostawcy w polu **Adresu internetowego** i wybierz przycisk **OK**, aby potwierdzić.</span><span class="sxs-lookup"><span data-stu-id="0c879-166">To create a provider, change the name of the provider in the **Name** field, update the internet address of the new provider in the **Internet address** field, and select **OK** to confirm.</span></span>

    ![Utwórz nowego dostawcę w BDM](./media/bdm_create_provider.png)
    
- <span data-ttu-id="0c879-168">Aby uaktywnić istniejącego dostawcę, wybierz nazwę dostawcy w polu **Dostawca konfiguracji** i wybierz przycisk **OK**, aby ustawić dostawcę jako aktywnego.</span><span class="sxs-lookup"><span data-stu-id="0c879-168">To activate existing provider, choose the name of the provider in the **Configuration provider** field, and select **OK** to set provider as active.</span></span>

    ![Aktywuj dostawcę w BDM](./media/bdm_choose_provider.png)

> [!NOTE]
> <span data-ttu-id="0c879-170">Każdy szablon BDM odnosi się do dostawcy jako autora konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="0c879-170">Each BDM template refers to the provider as the author of the configuration.</span></span> <span data-ttu-id="0c879-171">Z tego względu dla szablonu jest wymagany aktywny dostawca.</span><span class="sxs-lookup"><span data-stu-id="0c879-171">This is why an active provider is required for the template.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
