---
title: Aktualizowanie jednostki złożonej arkusza bankowego
description: Poniższe czynności są niezbędne w celu wstawienia dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity.
author: ShylaThompson
manager: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ec196600a54a2aed4565cf422dc386d6646ff524
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446663"
---
# <a name="update-the-bank-journal-composite-entity"></a><span data-ttu-id="d82d7-103">Aktualizowanie jednostki złożonej arkusza bankowego</span><span class="sxs-lookup"><span data-stu-id="d82d7-103">Update the bank journal composite entity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d82d7-104">Poniższe czynności są niezbędne w celu wstawienia dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity.</span><span class="sxs-lookup"><span data-stu-id="d82d7-104">The following steps are needed in order to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

<span data-ttu-id="d82d7-105">Poniższa procedura umożliwia wstawienie dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity.</span><span class="sxs-lookup"><span data-stu-id="d82d7-105">Use the following steps to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

1.  <span data-ttu-id="d82d7-106">Skompiluj i zsynchronizuj następujące jednostki złożone, jednostki i tabele tymczasowe w arkuszu bankowym:</span><span class="sxs-lookup"><span data-stu-id="d82d7-106">Compile and synchronize the following bank journal composite entities, entities, and staging tables:</span></span>
    -   <span data-ttu-id="d82d7-107">Jednostka złożona\\BankJournalEntity</span><span class="sxs-lookup"><span data-stu-id="d82d7-107">Composite Entity\\BankJournalEntity</span></span>
    -   <span data-ttu-id="d82d7-108">Jednostka\\BankJournalHeaderEntity</span><span class="sxs-lookup"><span data-stu-id="d82d7-108">Entity\\BankJournalHeaderEntity</span></span>
    -   <span data-ttu-id="d82d7-109">Jednostka\\BankJournalLineEntity</span><span class="sxs-lookup"><span data-stu-id="d82d7-109">Entity\\BankJournalLineEntity</span></span>
    -   <span data-ttu-id="d82d7-110">Tabela\\BankJournalHeaderStaging</span><span class="sxs-lookup"><span data-stu-id="d82d7-110">Table\\BankJournalHeaderStaging</span></span>
    -   <span data-ttu-id="d82d7-111">Tabela\\BankJournalLineStaging</span><span class="sxs-lookup"><span data-stu-id="d82d7-111">Table\\BankJournalLineStaging</span></span>

2.  <span data-ttu-id="d82d7-112">Zarządzanie danymi\\projekty danych</span><span class="sxs-lookup"><span data-stu-id="d82d7-112">Data management\\data projects</span></span>
    -   <span data-ttu-id="d82d7-113">Udostępnij typ **Transakcja bankowa** w układzie **Dane źródłowe**.</span><span class="sxs-lookup"><span data-stu-id="d82d7-113">Expose the **Bank Transaction** type on **Source Data** layout.</span></span>
        -   <span data-ttu-id="d82d7-114">Format danych źródłowych = Element XML</span><span class="sxs-lookup"><span data-stu-id="d82d7-114">Source data format = XML-Element</span></span>
        -   <span data-ttu-id="d82d7-115">Nazwa jednostki = Arkusz bankowy</span><span class="sxs-lookup"><span data-stu-id="d82d7-115">Entity name = Bank Journal</span></span>
        -   <span data-ttu-id="d82d7-116">Przekaż plik danych = nowa wersja pliku SampleBankJournalCompositeEntity.xml.</span><span class="sxs-lookup"><span data-stu-id="d82d7-116">Upload data file = new version SampleBankJournalCompositeEntity.xml</span></span>
        -   <span data-ttu-id="d82d7-117">Kliknij przycisk **Tak**, aby zastąpić istniejący plik.</span><span class="sxs-lookup"><span data-stu-id="d82d7-117">Click **Yes** to overwrite the existing file.</span></span>
        -   <span data-ttu-id="d82d7-118">Kliknij przycisk **Tak**, aby wygenerować mapowanie od zera.</span><span class="sxs-lookup"><span data-stu-id="d82d7-118">Click **Yes** to generate mapping from scratch.</span></span>
        -   <span data-ttu-id="d82d7-119">Sprawdź, czy typ transakcji bankowej jest mapowany.</span><span class="sxs-lookup"><span data-stu-id="d82d7-119">Verify that the Bank Transaction Type is mapped.</span></span>
            -   <span data-ttu-id="d82d7-120">W jednostce Wiersz kliknij opcję **Wyświetl mapę**.</span><span class="sxs-lookup"><span data-stu-id="d82d7-120">Click **View map** on Line entity.</span></span>
            -   <span data-ttu-id="d82d7-121">Upewnij się, że typ transakcji bankowej jest mapowany z obszaru Źródło do obszaru Tymczasowy.</span><span class="sxs-lookup"><span data-stu-id="d82d7-121">Verify that Bank Transaction type is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="d82d7-122">Zaimportuj nowy wyciąg.</span><span class="sxs-lookup"><span data-stu-id="d82d7-122">Import the new statement.</span></span>




