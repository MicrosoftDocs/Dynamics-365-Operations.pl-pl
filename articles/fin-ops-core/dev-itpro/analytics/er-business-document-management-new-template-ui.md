---
title: Nowy interfejs użytkownika dokumentu w zarządzaniu dokumentami biznesowymi
description: Ten temat zawiera informacje dotyczące korzystania z interfejsu użytkownika nowego dokumentu w funkcji zarządzania dokumentami biznesowymi struktury modułu raportowania elektronicznego.
author: v-anamir
ms.date: 05/12/2019
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
ms.openlocfilehash: 4c430e21e3bf7f1c01c7b60c0bef58fb49c0c601
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748348"
---
# <a name="new-document-user-interface-in-business-document-management"></a><span data-ttu-id="27599-103">Nowy interfejs użytkownika dokumentu w zarządzaniu dokumentami biznesowymi</span><span class="sxs-lookup"><span data-stu-id="27599-103">New document user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="27599-104">Zarządzanie dokumentami biznesowymi pozwala użytkownikom korzystać z usługi Microsoft 365 lub odpowiedniej aplikacji komputerowej Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="27599-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="27599-105">Edycja może obejmować zmiany projektu lub nowe wdrożenia albo użytkownicy mogą dodawać symbole zastępcze w celu dołączenia dodatkowych danych bez konieczności zmieniania kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="27599-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="27599-106">Aby uzyskać więcej informacji na temat pracy z zarządzaniem dokumentami biznesowymi, zapoznaj się z [Omówieniem zarządzania dokumentami biznesowymi](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="27599-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="27599-107">Nowy interfejs użytkownika (UI) nowego dokumentu jest wyraźniejszy i wygodniejszy do używania.</span><span class="sxs-lookup"><span data-stu-id="27599-107">The new document user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="27599-108">W obszarze **Dokument biznesowy** są wyświetlane tylko szablony dostępne dla bieżącego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="27599-108">The **Business document** area shows only the templates that are available for the current provider.</span></span>

<span data-ttu-id="27599-109">Przycisk **Nowy dokument** umożliwia użytkownikom tworzenie i edytowanie szablonu w konfiguracji formatu sprawozdawczości elektronicznej (ER) dostarczonej przez innego dostawcę.</span><span class="sxs-lookup"><span data-stu-id="27599-109">The **New document** button lets users create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="27599-110">W przykładzie przedstawionym w tym temacie dostawcą jest Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27599-110">In the example in this topic, the provider is Microsoft.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="27599-111">Udostępnij interfejs użytkownika nowego dokumentu w zarządzaniu dokumentami biznesowymi</span><span class="sxs-lookup"><span data-stu-id="27599-111">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="27599-112">Aby rozpocząć korzystanie z interfejsu użytkownika nowego dokumentu w module Zarządzanie dokumentami biznesowymi, należy uruchomić funkcję **wyglądającą jak interfejs użytkownika Office do zarządzania dokumentami biznesowymi** w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="27599-112">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="27599-113">Aby włączyć tę funkcję dla wszystkich firm, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="27599-113">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="27599-114">W obszarze roboczym **Zarządzanie funkcjami** na karcie **Nowy** wybierz pozycję **Wyglądający jak Office interfejs użytkownika na potrzeby zarządzania dokumentami** biznesowymi na liście.</span><span class="sxs-lookup"><span data-stu-id="27599-114">In the **Feature management** workspace, on the **New** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="27599-115">Wybierz opcję **Włącz teraz**, aby włączyć wybraną funkcję.</span><span class="sxs-lookup"><span data-stu-id="27599-115">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="27599-116">Odśwież stronę, aby uzyskać dostęp do nowej funkcji.</span><span class="sxs-lookup"><span data-stu-id="27599-116">Refresh the page to access the new feature.</span></span>

### <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="27599-117">Edytuj szablony należące do innych dostawców</span><span class="sxs-lookup"><span data-stu-id="27599-117">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="27599-118">W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.</span><span class="sxs-lookup"><span data-stu-id="27599-118">In the **Business document management** workspace, select **New document**.</span></span>

    ![Strona obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="27599-120">W oknie dialogowym wybierz dokument, który ma być używany jako szablon, a następnie wybierz opcję **Utwórz dokument**.</span><span class="sxs-lookup"><span data-stu-id="27599-120">In the dialog box, select the document to use as a template, and then select **Create document**.</span></span>

    ![Dokumenty biznesowe, okno dialogowe](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="27599-122">W nowym oknie dialogowym, w polu **Tytuł**, zmień tytuł zgodnie z potrzebą.</span><span class="sxs-lookup"><span data-stu-id="27599-122">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="27599-123">Tekst będzie używany do napełniania nowej nazwy tworzonej automatycznie konfiguracji formatu ER.</span><span class="sxs-lookup"><span data-stu-id="27599-123">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="27599-124">Wersja robocza tej konfiguracji (**Raport o fakturach niezależnych dla odbiorców (GER) - Kopia**) będzie zawierać edytowany szablon i zostanie automatycznie oznaczona do uruchomienia tego formatu ER dla bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="27599-124">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="27599-125">Niezmodyfikowany oryginalny szablon z podstawowej konfiguracji formatu źródłowego będzie używany do uruchamiania tego formatu ER dla każdego innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="27599-125">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="27599-126">W polu **Nazwa** zmień nazwę pierwszej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.</span><span class="sxs-lookup"><span data-stu-id="27599-126">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="27599-127">W polu **Komentarz** zaktualizuj uwagę dla automatycznie wygenerowanej poprawki edytowalnego szablonu, która zostanie utworzona automatycznie.</span><span class="sxs-lookup"><span data-stu-id="27599-127">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="27599-128">Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.</span><span class="sxs-lookup"><span data-stu-id="27599-128">Select **OK** to confirm the start of the editing process.</span></span>

    ![Tworzenie dokumentu, okno dialogowe](./media/BDM_overview_new_template3.png)

<span data-ttu-id="27599-130">Przycisk **Nowy dokument** umożliwia użytkownikom tworzenie i edytowanie szablonu w konfiguracji formatu sprawozdawczości elektronicznej (ER) dostarczonej przez innego dostawcę.</span><span class="sxs-lookup"><span data-stu-id="27599-130">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="27599-131">W przykładzie przedstawionym w tym temacie dostawcą jest Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27599-131">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="27599-132">Kliknięcie przycisku **Nowy dokument** powoduje wyświetlenie wszystkich szablonów należących do bieżącego i innych dostawców.</span><span class="sxs-lookup"><span data-stu-id="27599-132">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="27599-133">Po wybraniu szablonu, zostanie on otwarty do edycji.</span><span class="sxs-lookup"><span data-stu-id="27599-133">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="27599-134">Edytowany szablon zostanie następnie zapisany w nowej konfiguracji formatu, która jest generowana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="27599-134">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

<span data-ttu-id="27599-135">Aby uzyskać więcej informacji, zajrzyj do omówienia [Zarządzania dokumentami biznesowymi](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="27599-135">For more information, see [Business document management overview](er-business-document-management.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]