--- 
title: "Konfigurowanie sekwencji numeracji za pomocą kreatora"
description: "Sekwencje numeracji są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które ich wymagają."
author: sericks007
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e7d988cd1261c00925ad7ae612a947a0083028ee
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a><span data-ttu-id="b070d-103">Konfigurowanie sekwencji numeracji za pomocą kreatora</span><span class="sxs-lookup"><span data-stu-id="b070d-103">Set up number sequences by using a wizard</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b070d-104">Sekwencje numeracji są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które ich wymagają.</span><span class="sxs-lookup"><span data-stu-id="b070d-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="b070d-105">Rekord transakcji lub danych głównych, który wymaga identyfikatora, odnosi się do odwołania.</span><span class="sxs-lookup"><span data-stu-id="b070d-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="b070d-106">Aby można było tworzyć nowe rekordy dla odwołania, należy ustawić sekwencję numerów i skojarzyć je z odwołaniem.</span><span class="sxs-lookup"><span data-stu-id="b070d-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="b070d-107">W tej procedurze pokazano sposób konfigurowania wszystkich wymaganych sekwencji numeracji w tym samym czasie za pomocą kreatora.</span><span class="sxs-lookup"><span data-stu-id="b070d-107">This procedure explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="b070d-108">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="b070d-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="b070d-109">Wybierz kolejno opcje Administrowanie organizacją > Sekwencje numerów > Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="b070d-109">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="b070d-110">Kliknij przycisk Generuj.</span><span class="sxs-lookup"><span data-stu-id="b070d-110">Click Generate.</span></span>
3. <span data-ttu-id="b070d-111">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="b070d-111">Click Next.</span></span>
    * <span data-ttu-id="b070d-112">Na tej stronie można zmodyfikować kod identyfikacyjny, najniższą wartość i najwyższą wartość.</span><span class="sxs-lookup"><span data-stu-id="b070d-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="b070d-113">Ponadto można wskazać, czy sekwencja numerów musi być ciągła.</span><span class="sxs-lookup"><span data-stu-id="b070d-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
    * <span data-ttu-id="b070d-114">Nie wybieraj opcji Ciągłe, jeśli konieczne jest wstępne przydzielanie numerów w sekwencji numeracji.</span><span class="sxs-lookup"><span data-stu-id="b070d-114">Do not select the Continuous option if you must preallocate numbers for the number sequence.</span></span>     <span data-ttu-id="b070d-115">Aby dodać segment zakresu do formatu sekwencji numeracji, wybierz format z listy, a następnie kliknij opcję Uwzględnij zakres w formacie.</span><span class="sxs-lookup"><span data-stu-id="b070d-115">To add a scope segment to the format of a number sequence, select the format in the list, and then click Include scope in format.</span></span>     <span data-ttu-id="b070d-116">Aby usunąć segment zakresu z formatu sekwencji numeracji, wybierz format z listy, a następnie kliknij opcję Usuń zakres z formatu.</span><span class="sxs-lookup"><span data-stu-id="b070d-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then click Remove scope from format.</span></span>     <span data-ttu-id="b070d-117">Aby wykluczyć sekwencję numeracji z automatycznego generowania, wybierz z listy sekwencję numeracji, a następnie kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="b070d-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then click Delete.</span></span>  
4. <span data-ttu-id="b070d-118">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="b070d-118">Click Next.</span></span>
5. <span data-ttu-id="b070d-119">Kliknij przycisk Zakończ.</span><span class="sxs-lookup"><span data-stu-id="b070d-119">Click Finish.</span></span>


