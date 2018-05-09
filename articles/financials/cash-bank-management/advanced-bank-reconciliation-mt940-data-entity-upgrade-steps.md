---
title: "Zaawansowane uzgadnianie konta bankowego, import dla formatu MT940 — uaktualnianie złożonej jednostki danych"
description: "Aby zapewnić obsługę formatu MT940, trzeba dodać numer kolejny do importowanej jednostki wyciągu bankowego."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7bb78afe2fa1b17bcec013f54f929c4181fae812
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="ef246-103">Zaawansowane uzgadnianie konta bankowego, import dla formatu MT940 — uaktualnianie złożonej jednostki danych</span><span class="sxs-lookup"><span data-stu-id="ef246-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef246-104">Aby zapewnić obsługę formatu MT940, trzeba dodać numer kolejny do importowanej jednostki wyciągu bankowego.</span><span class="sxs-lookup"><span data-stu-id="ef246-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="ef246-105">Poniższa procedura umożliwia dodanie importowanej jednostki wyciągu bankowego w celu obsługi formatu MT940.</span><span class="sxs-lookup"><span data-stu-id="ef246-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="ef246-106">Skompiluj i zsynchronizuj następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="ef246-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="ef246-107">Jednostka złożona\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="ef246-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="ef246-108">Jednostka\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="ef246-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="ef246-109">Jednostka\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="ef246-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="ef246-110">Jednostka\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="ef246-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="ef246-111">Jednostka\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="ef246-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="ef246-112">Tabele\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="ef246-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="ef246-113">Zarządzanie danymi\\projekty danych.</span><span class="sxs-lookup"><span data-stu-id="ef246-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="ef246-114">Załaduj projekty importu dla formatu MT940</span><span class="sxs-lookup"><span data-stu-id="ef246-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="ef246-115">Zmodyfikuj arkusz stylów XSLT.</span><span class="sxs-lookup"><span data-stu-id="ef246-115">Change XSLT.</span></span>
            -   <span data-ttu-id="ef246-116">Kliknij opcję **Wyświetl mapę**.</span><span class="sxs-lookup"><span data-stu-id="ef246-116">Click **View map**.</span></span>
            -   <span data-ttu-id="ef246-117">Na dokumencie wyciągu bankowego kliknij opcję **Wyświetl mapę**.</span><span class="sxs-lookup"><span data-stu-id="ef246-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="ef246-118">Kliknij opcję **Przekształcenia**.</span><span class="sxs-lookup"><span data-stu-id="ef246-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="ef246-119">Usuń plik BankReconiliation-to-Composite.xslt.</span><span class="sxs-lookup"><span data-stu-id="ef246-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="ef246-120">Dodaj nową wersję pliku BankReconiliation-to-Composite.xsl.</span><span class="sxs-lookup"><span data-stu-id="ef246-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="ef246-121">Udostępnij ustawienie **Numer sekwencyjny** w układzie **Dane źródłowe**.</span><span class="sxs-lookup"><span data-stu-id="ef246-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="ef246-122">Format danych źródłowych = Element XML.</span><span class="sxs-lookup"><span data-stu-id="ef246-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="ef246-123">Nazwa jednostki = Wyciągi bankowe.</span><span class="sxs-lookup"><span data-stu-id="ef246-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="ef246-124">Przekaż plik danych = nowa wersja pliku SampleBankCompositeEntity.xml.</span><span class="sxs-lookup"><span data-stu-id="ef246-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="ef246-125">Kliknij przycisk **Tak**, aby zastąpić istniejący plik.</span><span class="sxs-lookup"><span data-stu-id="ef246-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="ef246-126">Kliknij przycisk **Tak**, aby wygenerować nowe mapowanie.</span><span class="sxs-lookup"><span data-stu-id="ef246-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="ef246-127">Upewnij się, że element **SequenceNumber** jest mapowany.</span><span class="sxs-lookup"><span data-stu-id="ef246-127">Verify that S**equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="ef246-128">W jednostce wyciągu kliknij opcję **Wyświetl mapę**.</span><span class="sxs-lookup"><span data-stu-id="ef246-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="ef246-129">Upewnij się, że element **SequenceNumber** jest mapowany z obszaru Źródło do obszaru Tymczasowy.</span><span class="sxs-lookup"><span data-stu-id="ef246-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="ef246-130">Zaimportuj nowy wyciąg.</span><span class="sxs-lookup"><span data-stu-id="ef246-130">Import the new statement.</span></span>





