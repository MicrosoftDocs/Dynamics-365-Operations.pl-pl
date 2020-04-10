---
title: Konfigurowanie numeracji za pomocą kreatora
description: W tym temacie pokazano sposób konfigurowania wszystkich wymaganych sekwencji numeracji w tym samym czasie za pomocą kreatora.
author: sericks007
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 76dc32f2254ffd2a2e33eef594d6e602092bcb6f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140512"
---
# <a name="set-up-number-sequences-using-a-wizard"></a><span data-ttu-id="7092a-103">Konfigurowanie numeracji za pomocą kreatora</span><span class="sxs-lookup"><span data-stu-id="7092a-103">Set up number sequences using a wizard</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7092a-104">Sekwencje numeracji są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które ich wymagają.</span><span class="sxs-lookup"><span data-stu-id="7092a-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="7092a-105">Rekord transakcji lub danych głównych, który wymaga identyfikatora, odnosi się do odwołania.</span><span class="sxs-lookup"><span data-stu-id="7092a-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="7092a-106">Aby można było tworzyć nowe rekordy dla odwołania, należy ustawić sekwencję numerów i skojarzyć je z odwołaniem.</span><span class="sxs-lookup"><span data-stu-id="7092a-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="7092a-107">W tym temacie pokazano sposób konfigurowania wszystkich wymaganych sekwencji numeracji w tym samym czasie za pomocą kreatora.</span><span class="sxs-lookup"><span data-stu-id="7092a-107">This topic explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="7092a-108">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="7092a-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="7092a-109">Otwórz **Nawigacja > Moduły > Administrowanie organizacją > Sekwencje numerów > Sekwencje numerów**.</span><span class="sxs-lookup"><span data-stu-id="7092a-109">Go to **Navigation > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="7092a-110">Wybierz **Generuj**.</span><span class="sxs-lookup"><span data-stu-id="7092a-110">Select **Generate**.</span></span>
3. <span data-ttu-id="7092a-111">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="7092a-111">Select **Next**.</span></span>

   - <span data-ttu-id="7092a-112">Na tej stronie można zmodyfikować kod identyfikacyjny, najniższą wartość i najwyższą wartość.</span><span class="sxs-lookup"><span data-stu-id="7092a-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="7092a-113">Ponadto można wskazać, czy sekwencja numerów musi być ciągła.</span><span class="sxs-lookup"><span data-stu-id="7092a-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
   - <span data-ttu-id="7092a-114">Nie wybieraj opcji **Ciągłe**, jeśli konieczne jest wstępne przydzielanie numerów w sekwencji numeracji.</span><span class="sxs-lookup"><span data-stu-id="7092a-114">Do not select the **Continuous** option if you must preallocate numbers for the number sequence.</span></span> <span data-ttu-id="7092a-115">Aby dodać segment zakresu do formatu sekwencji numeracji, wybierz format z listy, a następnie wybierz **Uwzględnij zakres w formacie**.</span><span class="sxs-lookup"><span data-stu-id="7092a-115">To add a scope segment to the format of a number sequence, select the format in the list, and then select **Include scope in format**.</span></span> <span data-ttu-id="7092a-116">Aby usunąć segment zakresu z formatu sekwencji numerów, wybierz format z listy, a następnie kliknij opcję **Usuń zakres z formatu**.</span><span class="sxs-lookup"><span data-stu-id="7092a-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then select **Remove scope from format**.</span></span> <span data-ttu-id="7092a-117">Aby wykluczyć sekwencję numerów z automatycznego generowania, wybierz z listy sekwencję numerów, a następnie wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="7092a-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then select **Delete**.</span></span>  

4. <span data-ttu-id="7092a-118">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="7092a-118">Select **Next**.</span></span>
5. <span data-ttu-id="7092a-119">Wybierz **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="7092a-119">Select **Finish**.</span></span>

