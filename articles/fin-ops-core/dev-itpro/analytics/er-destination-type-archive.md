---
title: Typ miejsca docelowego modelu archiwizacji
description: Ten temat zawiera informacje dotyczące konfigurowania miejsca docelowego archiwum dla każdego składnika typu FOLDER lub PLIK w formacie raportowania elektronicznego (ER).
author: NickSelin
manager: AnnBe
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0067024d7a29e2a1db3b7fdba9ea3c6a63aad648
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094136"
---
# <a name="archive-er-destination-type"></a><span data-ttu-id="b57c5-103">Typ miejsca docelowego modelu archiwizacji</span><span class="sxs-lookup"><span data-stu-id="b57c5-103">Archive ER destination type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b57c5-104">Możesz konfigurować lokalizację docelową archiwum dla poszczególnych składników **Folder** lub **Plik** formatu raportowania elektronicznego (ER) skonfigurowanego do generowania dokumentów wychodzących.</span><span class="sxs-lookup"><span data-stu-id="b57c5-104">You can configure an archive destination for each **Folder** or **File** component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="b57c5-105">Na podstawie ustawienia lokalizacji docelowej wygenerowany dokument jest przechowywany jako załącznik do rekordu listy zadań ER.</span><span class="sxs-lookup"><span data-stu-id="b57c5-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span> <span data-ttu-id="b57c5-106">Wyniki można obejrzeć w oknie **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zadania raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="b57c5-106">To view the results, go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting jobs**.</span></span>

<span data-ttu-id="b57c5-107">Ta opcja służy do wysyłania wygenerowanego dokumentu do folderu programu Microsoft SharePoint lub magazynu w usłudze Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="b57c5-107">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="b57c5-108">W ustawieniu **Włączone** zaznacz wartość **Tak**, aby wysłać dane wyjściowe do miejsca docelowego zdefiniowanego przez wybrany typ dokumentu.</span><span class="sxs-lookup"><span data-stu-id="b57c5-108">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="b57c5-109">Do wyboru są dostępne tylko typy dokumentów, dla których ustawiono grupę **Plik**.</span><span class="sxs-lookup"><span data-stu-id="b57c5-109">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="b57c5-110">Definiowanie typów dokumentów odbywa się w oknie [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) **Administrowanie organizacją** \> **Zarządzanie dokumentami** \> **Typy dokumentów**.</span><span class="sxs-lookup"><span data-stu-id="b57c5-110">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="b57c5-111">Konfiguracja miejsc docelowych ER jest taka sama, jak konfiguracja w systemie zarządzania dokumentami.</span><span class="sxs-lookup"><span data-stu-id="b57c5-111">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="b57c5-112">[![Strona Typy dokumentów](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="b57c5-112">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="b57c5-113">Lokalizacja określa, gdzie plik jest zapisywany.</span><span class="sxs-lookup"><span data-stu-id="b57c5-113">The location determines where the file is saved.</span></span> <span data-ttu-id="b57c5-114">Po włączeniu miejsca docelowego **Archiwum** wyniki mogą być zapisywane w archiwum zadania.</span><span class="sxs-lookup"><span data-stu-id="b57c5-114">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="b57c5-115">Wyniki można obejrzeć w oknie **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zarchiwizowane zadania raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="b57c5-115">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="b57c5-116">Wybierz typ dokumentu dla archiwum zadań poprzez przejście do sekcji **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne** \> **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="b57c5-116">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="b57c5-117">Aby uzyskać więcej informacji, zobacz [Konfigurowanie struktury modułu Raportowanie elektroniczne (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="b57c5-117">For more information, see [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="b57c5-118">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b57c5-118">SharePoint</span></span>

<span data-ttu-id="b57c5-119">Plik można zapisać w wyznaczonym folderze programu SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b57c5-119">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="b57c5-120">Domyślny serwer programu SharePoint definiuje się w oknie **Administrowanie organizacją** \> **Zarządzanie dokumentami** \> **Parametry zarządzania dokumentami**.</span><span class="sxs-lookup"><span data-stu-id="b57c5-120">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="b57c5-121">Na karcie **SharePoint**, skonfiguruj folder SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b57c5-121">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="b57c5-122">Następnie można wybrać tę opcję jako folder, w którym zostanie zapisana produkcja globalna ER.</span><span class="sxs-lookup"><span data-stu-id="b57c5-122">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="b57c5-123">W **SharePoint** w tym typie dokumentu należy wybrać lokalizację.</span><span class="sxs-lookup"><span data-stu-id="b57c5-123">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="b57c5-124">[![Wybieranie folderu programu SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="b57c5-124">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="b57c5-125">Magazyn Azure</span><span class="sxs-lookup"><span data-stu-id="b57c5-125">Azure Storage</span></span>

<span data-ttu-id="b57c5-126">Gdy w ustawieniu lokalizacji typu dokumentu zostanie zaznaczona wartość **Magazyn Azure**, można zapisać plik do magazynu usługi Azure.</span><span class="sxs-lookup"><span data-stu-id="b57c5-126">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

> [!NOTE] 
> <span data-ttu-id="b57c5-127">Struktura modułu ER trwale przechowuje pliki w magazynie obiektów Blob systemu Azure, w przeciwieństwie do struktury zarządzania danymi, która stosuje zasadę przechowywania przez siedem dni dla dokumentów, które muszą zostać przetworzone.</span><span class="sxs-lookup"><span data-stu-id="b57c5-127">The ER framework permanently stores files in Azure Blob storage unlike the Data management framework that applies the seven-day retention policy for documents that must be processed.</span></span> <span data-ttu-id="b57c5-128">Aby uzyskać więcej informacji, zobacz [Interfejs API pobierania informacji o stanie wiadomości](../data-entities/recurring-integrations.md#api-for-getting-message-status) i [Interfejs API sprawdzania stanu](../data-entities/data-management-api.md#status-check-api).</span><span class="sxs-lookup"><span data-stu-id="b57c5-128">For more information, see [API for getting message status](../data-entities/recurring-integrations.md#api-for-getting-message-status) and [Status check API](../data-entities/data-management-api.md#status-check-api).</span></span> <span data-ttu-id="b57c5-129">Pliki powiązane z modułem ER będą przechowywane w magazynie obiektów Blob platformy Azure jako załączniki do rekordów tabeli aplikacji tak długo, jak jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="b57c5-129">The ER-related files will be stored in Azure Blob storage as attachments of application table records as long as necessary.</span></span> <span data-ttu-id="b57c5-130">Plik jest usuwany z magazynu obiektów Blob systemu Azure wraz z rekordem tabeli aplikacji, do którego był dołączony.</span><span class="sxs-lookup"><span data-stu-id="b57c5-130">A single file will be deleted from Azure Blob storage along with the application table record that this file was attached to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b57c5-131">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b57c5-131">Additional resources</span></span>

- [<span data-ttu-id="b57c5-132">Omówienie raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="b57c5-132">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="b57c5-133">Miejsca docelowe raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="b57c5-133">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="b57c5-134">Konfigurowanie zarządzania dokumentami</span><span class="sxs-lookup"><span data-stu-id="b57c5-134">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
