---
title: Wprowadzanie danych kandydata i aplikacji ręcznie
description: W tej procedurze pokazano sposób ręcznego obsługiwania informacji dotyczących kandydatów i ich zgłoszeń.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea61e3c1d76ade6e0d694b4b521e4be76fc8799d
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2019
ms.locfileid: "855874"
---
# <a name="enter-applicant-and-application-data-manually"></a><span data-ttu-id="b2d9a-103">Wprowadzanie danych kandydata i aplikacji ręcznie</span><span class="sxs-lookup"><span data-stu-id="b2d9a-103">Enter applicant and application data manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b2d9a-104">W tej procedurze pokazano sposób ręcznego obsługiwania informacji dotyczących kandydatów i ich zgłoszeń.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-104">This procedure shows how to manually maintain information about applicants and their application.</span></span>   <span data-ttu-id="b2d9a-105">Można wprowadzać i obsługiwać informacje osobiste, daty i godziny rozmów kwalifikacyjnych, referencje, kompetencje oraz wnioski kandydatów o zakwaterowanie.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-105">You can enter and maintain personal information, interview dates and times, references, competencies, and accommodation requests for applicants.</span></span> <span data-ttu-id="b2d9a-106">Można także aktualizować stany podań o pracę kandydatów i tworzyć listy lub wiadomości e-mail do komunikacji z kandydatami.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-106">You can also update the status of applicants’ applications for employment and create letters or email messages to communicate with applicants.</span></span> <span data-ttu-id="b2d9a-107">Po utworzeniu rekordu kandydata jest tworzony rekord tej osoby w globalnej książce adresowej.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-107">When you create an applicant record, a person record for that applicant is created in the global address book.</span></span>       <span data-ttu-id="b2d9a-108">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-new-applicant-record"></a><span data-ttu-id="b2d9a-109">Tworzenie rekordu nowego kandydata</span><span class="sxs-lookup"><span data-stu-id="b2d9a-109">Create a new applicant record</span></span>
1. <span data-ttu-id="b2d9a-110">Wybierz kolejno opcje Zasoby ludzkie > Rekrutacja > Kandydaci > Kandydaci.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-110">Go to Human resources > Recruitment > Applicants > Applicants.</span></span>
2. <span data-ttu-id="b2d9a-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-111">Click New.</span></span>
3. <span data-ttu-id="b2d9a-112">W polu Imię wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-112">In the First name field, type a value.</span></span>
4. <span data-ttu-id="b2d9a-113">W polu Nazwisko wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-113">In the Last name field, type a value.</span></span>
    * <span data-ttu-id="b2d9a-114">Jeśli są dostępne, można wprowadzić dodatkowe informacje o kandydacie.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-114">You can enter additional applicant information if it's available.</span></span> <span data-ttu-id="b2d9a-115">Na przykład może to być najwyższy stopień naukowy posiadany przez kandydata, nazwa bieżącego stanowiska lub nazwa poprzedniego pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-115">For example, information can include the applicant's highest degree, current job title, or previous employer.</span></span>  
5. <span data-ttu-id="b2d9a-116">Przełącz rozwinięcie sekcji Informacje kontaktowe.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-116">Toggle the expansion of the Contact information section.</span></span>
6. <span data-ttu-id="b2d9a-117">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-117">Click Add.</span></span>
7. <span data-ttu-id="b2d9a-118">W polu Opis wpisz „Adres e-mail do komunikacji”.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-118">In the Description field, type 'Communications email'.</span></span>
8. <span data-ttu-id="b2d9a-119">W polu Typ wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-119">In the Type field, select an option.</span></span>
9. <span data-ttu-id="b2d9a-120">W polu Numer/adres osoby kontaktowej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-120">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="b2d9a-121">Ten adres e-mail będzie używany do obsługi komunikacji e-mail z kandydatem.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-121">This email address will be used to generate email communication with the applicant.</span></span>  
10. <span data-ttu-id="b2d9a-122">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-122">Click Add.</span></span>
11. <span data-ttu-id="b2d9a-123">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-123">In the Description field, type a value.</span></span>
12. <span data-ttu-id="b2d9a-124">W polu Numer/adres osoby kontaktowej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-124">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="b2d9a-125">Informacje osobiste kandydata.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-125">Applicant personal information.</span></span>  
    * <span data-ttu-id="b2d9a-126">W razie potrzeby można wprowadzić dodatkowe informacje osobiste kandydata.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-126">You can enter additional personal information for the applicant, if needed.</span></span> <span data-ttu-id="b2d9a-127">Może to być na przykład data urodzenia, pochodzenie etniczne, płeć lub stan cywilny.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-127">For example, this can include birth date, ethnic origin, gender, or marital status.</span></span>  
13. <span data-ttu-id="b2d9a-128">W okienku akcji kliknij pozycję Kompetencje.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-128">On the Action Pane, click Competencies.</span></span>
    * <span data-ttu-id="b2d9a-129">Można wprowadzić profil kwalifikacji kandydata, w tym jego umiejętności, doświadczenie zawodowe, wykształcenie, zaliczone testy i posiadane certyfikaty.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-129">You can enter the applicant's competency profile, including their skills, professional experiences, education, tests, or certificates.</span></span>  
    * <span data-ttu-id="b2d9a-130">Te informacje mogą służyć przypisaniu umiejętności kandydata do umiejętności skojarzonych z zadaniami określonymi w danych firmy.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-130">This information can be used to map the applicant's skills to the skills associated with the jobs defined in your company's data.</span></span>   

## <a name="create-an-application-for-the-applicant"></a><span data-ttu-id="b2d9a-131">Tworzenie zgłoszenia dla kandydata</span><span class="sxs-lookup"><span data-stu-id="b2d9a-131">Create an application for the applicant</span></span>
1. <span data-ttu-id="b2d9a-132">Kliknij opcję Zgłoszenia.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-132">Click Applications.</span></span>
2. <span data-ttu-id="b2d9a-133">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-133">Click New.</span></span>
3. <span data-ttu-id="b2d9a-134">W polu Projekt rekrutacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-134">In the Recruitment project field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b2d9a-135">Wybranie projektu rekrutacji spowoduje skojarzenie kandydata z określonym wolnym stanowiskiem istniejącym w tym projekcie rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-135">By selecting a recruitment project, the applicant will be associated with a specific opening included in that recruitment project.</span></span>  
4. <span data-ttu-id="b2d9a-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-136">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="b2d9a-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b2d9a-138">Domyślnie zadanie i dział są oparte na wybranym projekcie rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-138">By default, the job and department are based on the selected recruitment project.</span></span>  
6. <span data-ttu-id="b2d9a-139">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-139">Click Save.</span></span>
    * <span data-ttu-id="b2d9a-140">Po zapisaniu podania o pracę można dołączać do niego dokumenty, w tym o doświadczeniu, nagrodach i list motywacyjny kandydata.</span><span class="sxs-lookup"><span data-stu-id="b2d9a-140">After saving the application, you can attach documents to it, including the applicant's experience, awards, and cover letter.</span></span>  

