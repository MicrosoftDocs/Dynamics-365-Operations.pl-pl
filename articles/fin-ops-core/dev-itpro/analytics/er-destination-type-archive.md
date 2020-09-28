---
title: Typ miejsca docelowego modelu archiwizacji
description: Ten temat zawiera informacje dotyczące konfigurowania lokalizacji docelowej archiwum dla poszczególnych składników FOLDER lub FILE formatu sprawozdawczości elektronicznej (ER) skonfigurowanych do generowania dokumentów wychodzących.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8797a68507a5116c6adbf1f2d805838fa507958c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745592"
---
# <a name="archive-destination"></a><span data-ttu-id="9a2f9-103">Archiwalne miejsce docelowe</span><span class="sxs-lookup"><span data-stu-id="9a2f9-103">Archive destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a2f9-104">Możesz konfigurować lokalizacje docelową archiwum dla poszczególnych składników FOLDER lub FILE formatu sprawozdawczości elektronicznej (ER) skonfigurowanych do generowania dokumentów wychodzących.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-104">You can configure an archive destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="9a2f9-105">Na podstawie ustawienia lokalizacji docelowej wygenerowany dokument jest przechowywany jako załącznik do rekordu listy zadań ER.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span>

<span data-ttu-id="9a2f9-106">Ta opcja służy do wysyłania wygenerowanego dokumentu do folderu programu Microsoft SharePoint lub magazynu w usłudze Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-106">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="9a2f9-107">W ustawieniu **Włączone** zaznacz wartość **Tak**, aby wysłać dane wyjściowe do miejsca docelowego zdefiniowanego przez wybrany typ dokumentu.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-107">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="9a2f9-108">Do wyboru są dostępne tylko typy dokumentów, dla których ustawiono grupę **Plik**.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-108">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="9a2f9-109">Definiowanie typów dokumentów odbywa się w oknie [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) **Administrowanie organizacją** \> **Zarządzanie dokumentami** \> **Typy dokumentów**.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-109">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="9a2f9-110">Konfiguracja miejsc docelowych ER jest taka sama, jak konfiguracja w systemie zarządzania dokumentami.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-110">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="9a2f9-111">[![Strona Typy dokumentów](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="9a2f9-111">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="9a2f9-112">Lokalizacja określa, gdzie plik jest zapisywany.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-112">The location determines where the file is saved.</span></span> <span data-ttu-id="9a2f9-113">Po włączeniu miejsca docelowego **Archiwum** wyniki mogą być zapisywane w archiwum zadania.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-113">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="9a2f9-114">Wyniki można obejrzeć w oknie **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zarchiwizowane zadania raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-114">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="9a2f9-115">Wybierz typ dokumentu dla archiwum zadań poprzez przejście do sekcji **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne** \> **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-115">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="9a2f9-116">Aby uzyskać więcej informacji, zobacz [Zmiana konfiguracji ram raportowania elektronicznego (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="9a2f9-116">For more information, [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="9a2f9-117">SharePoint</span><span class="sxs-lookup"><span data-stu-id="9a2f9-117">SharePoint</span></span>

<span data-ttu-id="9a2f9-118">Plik można zapisać w wyznaczonym folderze programu SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-118">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="9a2f9-119">Domyślny serwer programu SharePoint definiuje się w oknie **Administrowanie organizacją** \> **Zarządzanie dokumentami** \> **Parametry zarządzania dokumentami**.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-119">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="9a2f9-120">Na karcie **SharePoint**, skonfiguruj folder SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-120">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="9a2f9-121">Następnie można wybrać tę opcję jako folder, w którym zostanie zapisana produkcja globalna ER.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-121">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="9a2f9-122">W **SharePoint** w tym typie dokumentu należy wybrać lokalizację.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-122">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="9a2f9-123">[![Wybieranie folderu programu SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="9a2f9-123">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="9a2f9-124">Magazyn Azure</span><span class="sxs-lookup"><span data-stu-id="9a2f9-124">Azure Storage</span></span>

<span data-ttu-id="9a2f9-125">Gdy w ustawieniu lokalizacji typu dokumentu zostanie zaznaczona wartość **Magazyn Azure**, można zapisać plik do magazynu usługi Azure.</span><span class="sxs-lookup"><span data-stu-id="9a2f9-125">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a2f9-126">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9a2f9-126">Additional resources</span></span>

- [<span data-ttu-id="9a2f9-127">Omówienie raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="9a2f9-127">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="9a2f9-128">Miejsca docelowe raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="9a2f9-128">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="9a2f9-129">Konfigurowanie zarządzania dokumentami</span><span class="sxs-lookup"><span data-stu-id="9a2f9-129">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
