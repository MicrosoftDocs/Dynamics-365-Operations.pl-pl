---
title: Uzależnienie pytania od odpowiedzi na poprzednie pytanie
description: Pytania warunkowe umożliwiają określenie, jakie pytanie uzupełniające zostanie wyświetlone osobie udzielającej odpowiedzi na podstawie odpowiedzi na poprzednie pytanie.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: deb79398f5a0ebdbdb774c106c90ca50a69c275e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "341288"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a><span data-ttu-id="98686-103">Uzależnienie pytania od odpowiedzi na poprzednie pytanie</span><span class="sxs-lookup"><span data-stu-id="98686-103">Make a question dependent on the answer of the previous question</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98686-104">Pytania warunkowe umożliwiają określenie, jakie pytanie uzupełniające zostanie wyświetlone osobie udzielającej odpowiedzi na podstawie odpowiedzi na poprzednie pytanie.</span><span class="sxs-lookup"><span data-stu-id="98686-104">Conditional questions allow you to specify what follow-up question will be presented to a respondent, based on the answer to the preceding question.</span></span> <span data-ttu-id="98686-105">Na przykład jeśli zapytasz „Wolisz kawę czy herbatę”, logiczne pytanie uzupełniające można określić w zależności od tego, czy osoba udzielająca odpowiedzi wybierze kawę czy herbatę.</span><span class="sxs-lookup"><span data-stu-id="98686-105">For example, if you ask "Do you prefer coffee or tea," a logical follow-up question can be determined depending on whether the respondent selects coffee or tea as their answer.</span></span> <span data-ttu-id="98686-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="98686-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-existing-questionnaire"></a><span data-ttu-id="98686-107">Znajdowanie istniejącego kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="98686-107">Find the existing questionnaire</span></span>
1. <span data-ttu-id="98686-108">Wybierz kolejno opcje Kwestionariusz > Projekt > Kwestionariusze.</span><span class="sxs-lookup"><span data-stu-id="98686-108">Go to Questionnaire > Design > Questionnaires.</span></span>
2. <span data-ttu-id="98686-109">Na liście zaznacz kwestionariusz WorkFH.</span><span class="sxs-lookup"><span data-stu-id="98686-109">In the list, select the WorkFH questionnaire.</span></span>

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a><span data-ttu-id="98686-110">Dodawanie wszystkich pytań głównych i podrzędnych do kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="98686-110">Add all questions and sub-questions to the Questionnaire</span></span>
1. <span data-ttu-id="98686-111">Kliknij przycisk Pytania.</span><span class="sxs-lookup"><span data-stu-id="98686-111">Click Questions.</span></span>
2. <span data-ttu-id="98686-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="98686-112">Click New.</span></span>
3. <span data-ttu-id="98686-113">W polu Pytanie wybierz pytanie numer 00016.</span><span class="sxs-lookup"><span data-stu-id="98686-113">In the Question field, select question number 00016.</span></span>
4. <span data-ttu-id="98686-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="98686-114">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="98686-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="98686-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="98686-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="98686-116">Click Save.</span></span>
7. <span data-ttu-id="98686-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="98686-117">Close the page.</span></span>

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a><span data-ttu-id="98686-118">Ustawianie warunkowości sekwencji kwestionariusza i uzależnianie pytań od właściwych odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="98686-118">Set the Questionnaire Sequence to Conditional and make the question dependent on the appropriate question</span></span>
1. <span data-ttu-id="98686-119">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="98686-119">Click Edit.</span></span>
2. <span data-ttu-id="98686-120">Rozwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="98686-120">Expand the Setup section.</span></span>
3. <span data-ttu-id="98686-121">W polu Kolejność pytań wybierz opcję „Warunkowe”.</span><span class="sxs-lookup"><span data-stu-id="98686-121">In the Question order field, select 'Conditional'.</span></span>
4. <span data-ttu-id="98686-122">Kliknij opcję Pytanie warunkowe.</span><span class="sxs-lookup"><span data-stu-id="98686-122">Click Conditional question.</span></span>
5. <span data-ttu-id="98686-123">W drzewie zaznacz element „Pytania\Wyjaśnij powód udzielenia takiej a nie innej odpowiedzi na poprzednie pytanie.".</span><span class="sxs-lookup"><span data-stu-id="98686-123">In the tree, select 'Questions\Explain why you answered the previous question the way you did?'.</span></span>
6. <span data-ttu-id="98686-124">W polu Pytanie główne wybierz pytanie 00009.</span><span class="sxs-lookup"><span data-stu-id="98686-124">In the Primary question field, select question 00009</span></span>
7. <span data-ttu-id="98686-125">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="98686-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="98686-126">W polu Odpowiedź wprowadź identyfikator kolejności opcji odpowiedzi, od której ma zależeć pytanie.</span><span class="sxs-lookup"><span data-stu-id="98686-126">In the Answer field, enter the answer sequence ID of the answer option you want to make the question dependent on.</span></span> <span data-ttu-id="98686-127">Na przykład wprowadź wartość 1 dla pierwszej opcji odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="98686-127">For example, enter 1 for the first answer option.</span></span>
9. <span data-ttu-id="98686-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="98686-128">Click Save.</span></span>
10. <span data-ttu-id="98686-129">W drzewie zaznacz element „Pytania\Otrzymuję uczciwe wynagrodzenie za wykonywaną pracę.”.</span><span class="sxs-lookup"><span data-stu-id="98686-129">In the tree, select 'Questions\I am paid fairly for the work I do.'.</span></span>
    * <span data-ttu-id="98686-130">Należy zauważyć, że drzewo pytań zostało zaktualizowane w celu pokazania zależności.</span><span class="sxs-lookup"><span data-stu-id="98686-130">Note that the question tree updated to show the dependency.</span></span>  

