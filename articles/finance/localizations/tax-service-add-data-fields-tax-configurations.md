---
title: Dodawanie pól danych w konfiguracjach podatków
description: W tym temacie opisano sposób dostosowywania konfiguracji podatków przez dodanie pól danych.
author: kailiang
ms.date: 03/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b9d9fce81151ad70d57c69e389e238a6f9137d56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819431"
---
# <a name="add-data-fields-in-tax-configurations"></a><span data-ttu-id="ae6b8-103">Dodawanie pól danych w konfiguracjach podatków</span><span class="sxs-lookup"><span data-stu-id="ae6b8-103">Add data fields in tax configurations</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="ae6b8-104">W tym temacie opisano sposób dostosowywania konfiguracji podatków przy użyciu [pól danych dodawanych w integracji podatków](tax-service-add-data-fields-tax-integration-by-extension.md).</span><span class="sxs-lookup"><span data-stu-id="ae6b8-104">This topic explains how to customize tax configurations by using [data fields that are added in the tax integration](tax-service-add-data-fields-tax-integration-by-extension.md).</span></span>

## <a name="customize-the-tax-data-model"></a><span data-ttu-id="ae6b8-105">Dostosuj model danych podatkowych</span><span class="sxs-lookup"><span data-stu-id="ae6b8-105">Customize the tax data model</span></span>

1. <span data-ttu-id="ae6b8-106">W Microsoft Dynamics 365 Finance przejdź do **Elektroniczne raportowanie** \> **Konfiguracje podatku**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-106">In Microsoft Dynamics 365 Finance, go to **Electronic Reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="ae6b8-107">W drzewie konfiguracji wybierz **Model danych podatkowych — Europa**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-107">In the configuration tree, select **Tax Data Model - Europe**.</span></span> <span data-ttu-id="ae6b8-108">W okienku akcji wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-108">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="ae6b8-109">W oknie dialogowym listy rozwijanej wybierz **Model dokumentów podlegających opodatkowaniu uzyskany na podstawie pola Nazwa: Model danych podatkowych — Europa**, opcja firmy Microsoft, wprowadź nazwę nowego modelu danych podatkowych, a następnie wybierz pozycję **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-109">In the drop-down dialog box, select the **Taxable document model derived from Name: Tax Data Model -- Europe, Microsoft** option, enter a name for the new tax data model, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="ae6b8-110">Wybierz właśnie utworzony model danych podatku, a następnie w okienku akcji wybierz pozycję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-110">Select the tax data model that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="ae6b8-111">Rozwiń drzewo modeli danych, zaznacz **Wiersze**, a następnie wybierz **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-111">Expand the data model tree, select **Lines**, and then select **New**.</span></span>
6. <span data-ttu-id="ae6b8-112">W oknie dialogowym **Tworzenie węzła** wprowadź nazwę, określ typ towaru, a następnie wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-112">In the **Create node** dialog box, enter a name, specify the item type, and then select **Add**.</span></span>
7. <span data-ttu-id="ae6b8-113">Dodaj wymagane kolumny.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-113">Add any required columns.</span></span>
8. <span data-ttu-id="ae6b8-114">W okienku akcji wybierz opcję **Zapisz**, a następnie wybierz opcję **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-114">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="ae6b8-115">Zamknij stronę i wyświetl ukończoną wersję modelu danych podatku.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-115">Close the page, and view the completed version of your tax data model.</span></span>

## <a name="customize-the-tax-configuration"></a><span data-ttu-id="ae6b8-116">Dostosuj konfigurację podatku</span><span class="sxs-lookup"><span data-stu-id="ae6b8-116">Customize the tax configuration</span></span>

1. <span data-ttu-id="ae6b8-117">W Finance przejdź do **Elektroniczne raportowanie** \> **Konfiguracje podatku**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-117">In Finance, go to **Electronic reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="ae6b8-118">W drzewie konfiguracji wybierz **Konfiguracja podatku — Europa**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-118">In the configuration tree, select **Tax Configuration -- Europe**.</span></span> <span data-ttu-id="ae6b8-119">W okienku akcji wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-119">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="ae6b8-120">W oknie dialogowym listy rozwijanej wybierz **Konfiguracja usługi podatkowej pochodząca z nazwy: Konfiguracja podatku — Europa**, opcja firmy Microsoft, wprowadź nazwę nowej konfiguracji danych podatkowych, a następnie wybierz pozycję **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-120">In the drop-down dialog box, select the **Tax service configuration derived from Name: Tax Configuration -- Europe, Microsoft** option, enter a name for the new tax configuration, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="ae6b8-121">Wybierz właśnie utworzoną konfigurację podatku, a następnie w okienku akcji wybierz pozycję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-121">Select the tax configuration that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="ae6b8-122">W sekcji **Właściwości**, w polu **Model danych** wybierz niestandardowy model danych podatkowych utworzony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-122">In the **Properties** section, in the **Data model** field, select the customized tax data model that you created earlier.</span></span>
6. <span data-ttu-id="ae6b8-123">W polu **Wersja modelu danych** wybierz wersję akończoną modelu danych podatku.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-123">In the **Data model version** field, select the completed version of the tax data model.</span></span>
7. <span data-ttu-id="ae6b8-124">Wybierz opcję **Dodaj** i dodaj wymagane miary podatku.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-124">Select **Add**, and add the required tax measures.</span></span>
8. <span data-ttu-id="ae6b8-125">W okienku akcji wybierz opcję **Zapisz**, a następnie wybierz opcję **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-125">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="ae6b8-126">Zamknij stronę i wyświetl ukończoną wersję konfiguracji podatku.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-126">Close page, and view the completed version of your tax configuration.</span></span>

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a><span data-ttu-id="ae6b8-127">Implementowanie funkcji podatków w dostosowanej konfiguracji podatków</span><span class="sxs-lookup"><span data-stu-id="ae6b8-127">Implement tax features in the customized tax configuration</span></span>

1. <span data-ttu-id="ae6b8-128">W Regulatory Configuration Services (RCS) przejdź do **Funkcje globalizacji** \> **Podatek**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-128">In Regulatory Configuration Service (RCS), go to **Globalization Features** \> **Tax**.</span></span>
2. <span data-ttu-id="ae6b8-129">Wybierz **Dodaj**, wprowadź informacje o nowej funkcji, a następnie **Utwórz funkcję**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-129">Select **Add**, enter information about the new feature, and then select **Create feature**.</span></span>
3. <span data-ttu-id="ae6b8-130">Na karcie **Wersje** wybierz funkcję, a następnie **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-130">On the **Versions** tab, select the feature, and then select **Edit**.</span></span>
4. <span data-ttu-id="ae6b8-131">Na karcie **Ogólne** w polu **Wersja konfiguracji** wybierz niestandardową konfigurację i wersję podatku.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-131">On the **General** tab, in the **Configuration version** field, select the customized tax configuration and version.</span></span>
5. <span data-ttu-id="ae6b8-132">W oknie dialogowym **Zarządzaj kolumnami** wybierz nagłówek i kolumny wierszy, które chcesz uwzględnić w niestandardowej mierze podatkowej, a następnie wybierz przycisk strzałki w prawo, aby dodać je do listy **Wybrane kolumny**.</span><span class="sxs-lookup"><span data-stu-id="ae6b8-132">In the **Manage columns** dialog box, select the header and line columns that you want to include in your customized tax measure, and then select the right arrow button to add them to the **Selected columns** list.</span></span>
