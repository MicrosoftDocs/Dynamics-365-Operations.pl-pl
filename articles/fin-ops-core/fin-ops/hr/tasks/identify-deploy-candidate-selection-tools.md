---
title: Identyfikowanie i wdrażanie narzędzi do wybierania kandydatów
description: Znajdowanie puli wykwalifikowanych kandydatów do zapełnienia wakatów może być trudne, zwłaszcza gdy stanowisko wymaga unikatowego zestawu umiejętności.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmSkillMapping, HcmJobLookup, HcmSkillMappingLine, HcmPersonCertificate, CCHTMLPrintPreview
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d8a05ad7f100e6c54ccf1ecf7b76509cf44dbb8
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143956"
---
# <a name="identify-and-deploy-candidate-selection-tools"></a><span data-ttu-id="2dd08-103">Identyfikowanie i wdrażanie narzędzi do wybierania kandydatów</span><span class="sxs-lookup"><span data-stu-id="2dd08-103">Identify and deploy candidate selection tools</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2dd08-104">Znajdowanie puli wykwalifikowanych kandydatów do zapełnienia wakatów może być trudne, zwłaszcza gdy stanowisko wymaga unikatowego zestawu umiejętności.</span><span class="sxs-lookup"><span data-stu-id="2dd08-104">Finding a qualified pool of candidates to fill vacancies can be difficult, especially when a position requires a unique set of skills.</span></span>  <span data-ttu-id="2dd08-105">Z drugiej strony kandydaci mający niezbędne kwalifikacje mogą już być pracownikami Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="2dd08-105">However, candidates with the skills you need might already be employed in your organization.</span></span> <span data-ttu-id="2dd08-106">Można wyszukiwać określone zbiory umiejętności wśród istniejących pracowników lub nowych kandydatów.</span><span class="sxs-lookup"><span data-stu-id="2dd08-106">You can search for a specific skill set among existing employees, or new applicants.</span></span> <span data-ttu-id="2dd08-107">Dzięki temu osoba rekrutująca może szybko zebrać i przejrzeć dane kandydatów ubiegających się o wolne stanowisko teraz lub w przeszłości albo znaleźć potencjalnych kandydatów wśród istniejących pracowników.</span><span class="sxs-lookup"><span data-stu-id="2dd08-107">This allows a recruiter to quickly gather and screen applicants who have applied for open position now or in the past, or to find potential candidates from their existing pool of employees.</span></span> <span data-ttu-id="2dd08-108">Z tego nagrania zadania można się dowiedzieć, jak funkcje mapowania umiejętności pomogą znaleźć właściwą osobę na wolne stanowisko.</span><span class="sxs-lookup"><span data-stu-id="2dd08-108">Use this task recording to learn how the skill mapping functionality can help you find the right person for an open position.</span></span> <span data-ttu-id="2dd08-109">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="2dd08-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="2dd08-110">Wybierz kolejno opcje Zasoby ludzkie > Kompetencje > Analiza kwalifikacji > Profile mapowania kwalifikacji.</span><span class="sxs-lookup"><span data-stu-id="2dd08-110">Go to Human resources > Competencies > Skill analysis > Skill mapping profiles.</span></span>
2. <span data-ttu-id="2dd08-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2dd08-111">Click New.</span></span>
3. <span data-ttu-id="2dd08-112">W polu Mapowanie kwalifikacji nadaj nazwę mapowaniu umiejętności.</span><span class="sxs-lookup"><span data-stu-id="2dd08-112">In the Skill mapping field, enter a name for your skill mapping.</span></span>  <span data-ttu-id="2dd08-113">Przykład: Księgowy.</span><span class="sxs-lookup"><span data-stu-id="2dd08-113">Example: Accountant.</span></span>
4. <span data-ttu-id="2dd08-114">W polu Opis wprowadź opis mapowania umiejętności.</span><span class="sxs-lookup"><span data-stu-id="2dd08-114">In the Description field, enter a description of the skill mapping..</span></span>
5. <span data-ttu-id="2dd08-115">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="2dd08-115">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="2dd08-116">Kliknij przycisk Odtwórz profil.</span><span class="sxs-lookup"><span data-stu-id="2dd08-116">Click Retrieve profile.</span></span>
    * <span data-ttu-id="2dd08-117">Opcja Odtwórz profil służy do pobierania informacji o certyfikatach, umiejętnościach i wykształceniu z danych wybranej osoby, zadania lub kursu w celu użycia jako podstawy wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="2dd08-117">Use Retrieve profile to pull in the Certificate, Skill, and Education data from a selected Person, Job or Course as the basis for your search.</span></span>   <span data-ttu-id="2dd08-118">Następnie można dodać lub usunąć kryteria, określić, czy kryteria są opcjonalne, i określić ważność kryteriów.</span><span class="sxs-lookup"><span data-stu-id="2dd08-118">You can then add or remove criteria, state if the criteria is optional and rank the importance of the criteria.</span></span>  
7. <span data-ttu-id="2dd08-119">Kliknij przycisk Zadanie.</span><span class="sxs-lookup"><span data-stu-id="2dd08-119">Click Job.</span></span>
8. <span data-ttu-id="2dd08-120">W polu Zadanie wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2dd08-120">In the Job field, enter or select a value.</span></span>
9. <span data-ttu-id="2dd08-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2dd08-121">Click OK.</span></span>
10. <span data-ttu-id="2dd08-122">Rozwiń skróconą kartę zakresu i dodaj wszelkie informacje dodatkowe, takie jak dział.</span><span class="sxs-lookup"><span data-stu-id="2dd08-122">Expand the range fast tab, and add any additional information, such as department.</span></span>
11. <span data-ttu-id="2dd08-123">Rozwiń skróconą kartę certyfikatów, aby obejrzeć lub edytować certyfikaty.</span><span class="sxs-lookup"><span data-stu-id="2dd08-123">Expand the certificates fast tab to view or edit the certificates.</span></span>
12. <span data-ttu-id="2dd08-124">Rozwiń skróconą kartę Umiejętności, aby obejrzeć lub edytować kompetencje.</span><span class="sxs-lookup"><span data-stu-id="2dd08-124">Expand the Skills fast tab to view or edit the skills.</span></span>
13. <span data-ttu-id="2dd08-125">Rozwiń skróconą kartę Wykształcenie, aby wyświetlić lub edytować kryteria wykształcenia.</span><span class="sxs-lookup"><span data-stu-id="2dd08-125">Expand the Education fast tab to view or edit the education criteria.</span></span>
14. <span data-ttu-id="2dd08-126">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="2dd08-126">Click Execute.</span></span>
15. <span data-ttu-id="2dd08-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2dd08-127">Click OK.</span></span>
16. <span data-ttu-id="2dd08-128">Kliknij przycisk Wynik.</span><span class="sxs-lookup"><span data-stu-id="2dd08-128">Click Result.</span></span>
17. <span data-ttu-id="2dd08-129">Kliknij przycisk Wynik.</span><span class="sxs-lookup"><span data-stu-id="2dd08-129">Click Result.</span></span>
18. <span data-ttu-id="2dd08-130">Kliknij przycisk Wznów.</span><span class="sxs-lookup"><span data-stu-id="2dd08-130">Click Resume.</span></span>
19. <span data-ttu-id="2dd08-131">Kliknij przycisk Certyfikaty.</span><span class="sxs-lookup"><span data-stu-id="2dd08-131">Click Certificates.</span></span>
    * <span data-ttu-id="2dd08-132">Można przechodzić do kolejnych poziomów szczegółów każdej osoby na liście i obejrzeć informacje dotyczące jej wykształcenia, umiejętności, doświadczenia zawodowego itp.</span><span class="sxs-lookup"><span data-stu-id="2dd08-132">You can drill further into each person listed and see details regarding their education, skills, professional experience etc.</span></span>  
20. <span data-ttu-id="2dd08-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dd08-133">Close the page.</span></span>
21. <span data-ttu-id="2dd08-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dd08-134">Close the page.</span></span>
22. <span data-ttu-id="2dd08-135">Zaznacz ponownie wynik.</span><span class="sxs-lookup"><span data-stu-id="2dd08-135">Select result again.</span></span>
23. <span data-ttu-id="2dd08-136">Kliknij przycisk Raport.</span><span class="sxs-lookup"><span data-stu-id="2dd08-136">Click Report.</span></span>
    * <span data-ttu-id="2dd08-137">W raporcie najlepiej pasujące pozycje znajdą się u góry listy.</span><span class="sxs-lookup"><span data-stu-id="2dd08-137">The report will list the best matches at the top of the report.</span></span>  <span data-ttu-id="2dd08-138">Widać element luki.</span><span class="sxs-lookup"><span data-stu-id="2dd08-138">You can see that there is a gap element listed.</span></span>  <span data-ttu-id="2dd08-139">Jest to różnica między poziomem, który został podany w mapowaniu umiejętności, a poziomem umiejętności przypisanym do osoby.</span><span class="sxs-lookup"><span data-stu-id="2dd08-139">This is the difference between the level that was listed on the skill mapping, and the level of the skill that is assigned to the person.</span></span>  
24. <span data-ttu-id="2dd08-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2dd08-140">Close the page.</span></span>
25. <span data-ttu-id="2dd08-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2dd08-141">Click Save.</span></span>

