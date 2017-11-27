--- 
title: "Ustawianie typów dokumentów I-9"
description: "W tej procedurze pokazano sposób wyświetlania i konfigurowania typów dokumentów, które są używane w celu weryfikacji formularza I-9."
author: ShielaSogge
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 950237499441e7f1d5b9e3355c4bd9513ad3783e
ms.openlocfilehash: b47998eccd7509154ee8863e2e19594cc59ac945
ms.contentlocale: pl-pl
ms.lasthandoff: 11/01/2017

---
# <a name="set-up-i-9-document-types"></a><span data-ttu-id="c9989-103">Ustawianie typów dokumentów I-9</span><span class="sxs-lookup"><span data-stu-id="c9989-103">Set up I-9 document types</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="c9989-104">W tej procedurze pokazano sposób wyświetlania i konfigurowania typów dokumentów, które są używane w celu weryfikacji formularza I-9.</span><span class="sxs-lookup"><span data-stu-id="c9989-104">This procedure shows how to view and set up document types that are used for I-9 verification.</span></span> <span data-ttu-id="c9989-105">Przed skonfigurowaniem typów dokumentów dla formularza I-9 należy również skonfigurować agencje wystawiające i typy identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="c9989-105">Before you set up I-9 document types, you must also set up the issuing agencies and identification types.</span></span> <span data-ttu-id="c9989-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Są tam przykłady agencji wystawiających i typów identyfikatorów potrzebnych do wykonania procedury.</span><span class="sxs-lookup"><span data-stu-id="c9989-106">The demo data company used to create this procedure is USMF, which includes examples of the issue agencies and identification types that are needed to complete the procedure.</span></span>

1. <span data-ttu-id="c9989-107">Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > I-9 > Typy dokumentów I-9.</span><span class="sxs-lookup"><span data-stu-id="c9989-107">Go to Human resources > Workers > I-9 > I-9 document types.</span></span>
2. <span data-ttu-id="c9989-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c9989-108">Click New.</span></span>
3. <span data-ttu-id="c9989-109">W polu Typ dokumentów I-9 wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c9989-109">In the I-9 document type field, type a value.</span></span>
    * <span data-ttu-id="c9989-110">Przykład: Identyfikator szkoły.</span><span class="sxs-lookup"><span data-stu-id="c9989-110">Example: School ID.</span></span>  
4. <span data-ttu-id="c9989-111">Wybierz typ identyfikatora.</span><span class="sxs-lookup"><span data-stu-id="c9989-111">Select the identification type.</span></span>  <span data-ttu-id="c9989-112">Przykład: Identyfikator szkoły.</span><span class="sxs-lookup"><span data-stu-id="c9989-112">Example:  School ID</span></span>
    * <span data-ttu-id="c9989-113">Przykładami typów identyfikatorów są numer PESEL (SSN), numer wizy, numer paszportu lub numer prawa jazdy.</span><span class="sxs-lookup"><span data-stu-id="c9989-113">Examples of identification types include a Social Security number (SSN), visa number, passport ID, or driver's license.</span></span>  
5. <span data-ttu-id="c9989-114">Zaznacz listę dokumentów I-9 używaną dla typu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="c9989-114">Select the I-9 document list that is used for the document type.</span></span>
    * <span data-ttu-id="c9989-115">W ramach procesu wypełniania formularza I-9 pracownicy muszą przedstawić dokumentację pokazującą pracodawcy tożsamość i prawo do zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="c9989-115">As part of the I-9 process, employees must present documentation that shows the employer their identity and employment authorization.</span></span> <span data-ttu-id="c9989-116">Witryna internetowa poświęcona amerykańskiemu obywatelstwu i usługom imigracyjnym zawiera informacje o tym, które dokumenty są akceptowane i do której listy należą.</span><span class="sxs-lookup"><span data-stu-id="c9989-116">The US Citizenship and Immigration Services website contains information about which documents are acceptable, and which list they belong to.</span></span>  <span data-ttu-id="c9989-117">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="c9989-117">http://www.uscis.gov</span></span>  
6. <span data-ttu-id="c9989-118">W polu Formularz wprowadź urzędowy numer dokumentu.</span><span class="sxs-lookup"><span data-stu-id="c9989-118">In the Form field, Enter the official form number for the document type.</span></span> <span data-ttu-id="c9989-119">Przykład: Identyfikator szkoły.</span><span class="sxs-lookup"><span data-stu-id="c9989-119">Example: School ID.</span></span>
    * <span data-ttu-id="c9989-120">Urzędowe numery formularzy znajdują się w witrynie internetowej poświęconej amerykańskiemu obywatelstwu i usługom imigracyjnym.</span><span class="sxs-lookup"><span data-stu-id="c9989-120">The official form numbers can be found on the US Citizenship and Immigration Services website.</span></span>  <span data-ttu-id="c9989-121">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="c9989-121">http://www.uscis.gov</span></span>  
7. <span data-ttu-id="c9989-122">Zaznacz pole wyboru Aktywny lub usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="c9989-122">Check or uncheck the Active checkbox.</span></span>
8. <span data-ttu-id="c9989-123">W polu Wygaśnięcie ustaw datę „2019-10-27”.</span><span class="sxs-lookup"><span data-stu-id="c9989-123">In the Expire field, set the date to '2019-10-27'.</span></span>
    * <span data-ttu-id="c9989-124">Data ważności jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="c9989-124">The expiration date is optional.</span></span>  
9. <span data-ttu-id="c9989-125">Wybierz organ, który wystawił typ dokumentu.</span><span class="sxs-lookup"><span data-stu-id="c9989-125">Select the agency that issued the document type.</span></span> <span data-ttu-id="c9989-126">Przykład: Prowincja/terytorium</span><span class="sxs-lookup"><span data-stu-id="c9989-126">Example: Province/territory</span></span>
10. <span data-ttu-id="c9989-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c9989-127">Click Save.</span></span>


