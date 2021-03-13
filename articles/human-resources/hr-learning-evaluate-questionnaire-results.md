---
title: Wyświetlanie i ocenianie wyników kwestionariuszy
description: W tym artykule wyjaśniono, jak można wyświetlać i oceniać wyniki kwestionariuszy wypełnianych przez respondentów.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: ff2136e1f0a87b7d77968ca1163e64f8838b234b
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2021
ms.locfileid: "5116123"
---
# <a name="view-and-evaluate-the-results-of-questionnaires"></a><span data-ttu-id="7d2c9-103">Wyświetlanie i ocenianie wyników kwestionariuszy</span><span class="sxs-lookup"><span data-stu-id="7d2c9-103">View and evaluate the results of questionnaires</span></span>

<span data-ttu-id="7d2c9-104">W tym artykule wyjaśniono, jak można wyświetlać i oceniać wyniki kwestionariuszy wypełnianych przez respondentów.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-104">This article explains how you can view and evaluate the results of questionnaires that respondents complete.</span></span> 

<span data-ttu-id="7d2c9-105">Po wypełnieniu kwestionariusza przez respondentów można wyświetlić i ocenić wyniki na kilka sposobów:</span><span class="sxs-lookup"><span data-stu-id="7d2c9-105">After respondents complete a questionnaire, you can view and evaluate the questionnaire results in the following ways:</span></span>

-   <span data-ttu-id="7d2c9-106">**Zakończone sesje odpowiedzi** — wyświetlanie szczegółowych informacji dotyczących kwestionariuszy wypełnionych przez respondentów i generowanie raportów do podsumowania odpowiedzi i uzyskanych punktów.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-106">**Completed answer sessions** – View details about the questionnaires that respondents have completed, and generate reports to summarize answers and any points that were earned.</span></span>
-   <span data-ttu-id="7d2c9-107">**Grupy wyników** — wyświetlanie szczegółów grup wyników i statystyk kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-107">**Result groups** – View result group details and statistics for questionnaires.</span></span> <span data-ttu-id="7d2c9-108">Statystyki grupy wyników mogą być generowane dla sesji pojedynczej odpowiedzi kwestionariusza lub dla wszystkich sesji odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-108">Result group statistics can be generated for either a single answer session  of a questionnaire or all answer sessions.</span></span>
-   <span data-ttu-id="7d2c9-109">**Statystyki kwestionariusza** — umożliwia określenie kryteriów do obliczania statystyk dla określonej grupy respondentów.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-109">**Questionnaire statistics** – Specify criteria to calculate statistics for a specific group of respondents.</span></span>

<span data-ttu-id="7d2c9-110">Można również generować różne raporty w celu wyświetlania wyników, które są sortowane według sesji odpowiedzi, osoby lub grupy wyników.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-110">You can also generate various reports to view results that are sorted by person, answer session, or result group.</span></span> <span data-ttu-id="7d2c9-111">Dostępne są następujące raporty, które są powiązane z wypełnionymi kwestionariuszami:</span><span class="sxs-lookup"><span data-stu-id="7d2c9-111">The following reports that are related to completed questionnaires are available:</span></span>

-   <span data-ttu-id="7d2c9-112">Odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="7d2c9-112">Answers</span></span>
-   <span data-ttu-id="7d2c9-113">Odpowiedzi na kwestionariusz</span><span class="sxs-lookup"><span data-stu-id="7d2c9-113">Answers per questionnaire</span></span>
-   <span data-ttu-id="7d2c9-114">Odpowiedzi na osobę</span><span class="sxs-lookup"><span data-stu-id="7d2c9-114">Answers per person</span></span>
-   <span data-ttu-id="7d2c9-115">Analiza informacji zwrotnych</span><span class="sxs-lookup"><span data-stu-id="7d2c9-115">Feedback analysis</span></span>

## <a name="answer-session-results"></a><span data-ttu-id="7d2c9-116">Wyniki sesji odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="7d2c9-116">Answer session results</span></span>

<span data-ttu-id="7d2c9-117">Kiedy respondenci wypełnią kwestionariusz, można wyświetlić wyniki zakończonych sesji odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-117">After respondents complete a questionnaire, you can view the results of the completed answer sessions.</span></span> <span data-ttu-id="7d2c9-118">Sesja odpowiedzi jest odpowiedzią jednego użytkownika na kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-118">An answer session is one user’s response to a questionnaire.</span></span> <span data-ttu-id="7d2c9-119">Umożliwia wyświetlenie szczegółowych informacji o sesji odpowiedzi na stronie **Odpowiedzi**.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-119">You can view details about completed answer sessions on the **Answers** page.</span></span> <span data-ttu-id="7d2c9-120">Sesje odpowiedzi, które są uwzględnione na stronie **Odpowiedzi** są filtrowane na różne sposoby, w zależności od tego, jak strona zostanie otwarta:</span><span class="sxs-lookup"><span data-stu-id="7d2c9-120">The answer sessions that are included on the **Answers** page are filtered in various ways, depending on how you open the page:</span></span>

-   <span data-ttu-id="7d2c9-121">Wszystkie kwestionariusze</span><span class="sxs-lookup"><span data-stu-id="7d2c9-121">All questionnaires</span></span>
-   <span data-ttu-id="7d2c9-122">Wybrane kwestionariusze</span><span class="sxs-lookup"><span data-stu-id="7d2c9-122">A specific questionnaire</span></span>
-   <span data-ttu-id="7d2c9-123">Wybrana osoba</span><span class="sxs-lookup"><span data-stu-id="7d2c9-123">A specific person</span></span>

<span data-ttu-id="7d2c9-124">Na stronie **Odpowiedzi** można wyświetlić szczegóły dotyczące punktów uzyskanych, odpowiedzi respondenta w poszczególnych grupach wyników i hierarchii pytań, użytych w wybranym kwestionariuszu, jeśli użyto hierarchii pytań.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-124">From the **Answers** page, you can view details about answers, points that were earned, a respondent’s responses in each result group, and the question hierarchy that was used on the selected questionnaire, if a question hierarchy was used.</span></span> <span data-ttu-id="7d2c9-125">Można również wygenerować i wydrukować następujące raporty:</span><span class="sxs-lookup"><span data-stu-id="7d2c9-125">You can also generate and print the following reports:</span></span>

-   <span data-ttu-id="7d2c9-126">**Raport wyników** — graficzna prezentacja uzyskanych punktów według grupy wyników dla wybranej sesji odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-126">**Results report** – This report shows a graphical representation of the points that were earned per result group for the selected answer session.</span></span>
-   <span data-ttu-id="7d2c9-127">**Raport odpowiedzi** — pokazuje odpowiedzi wybrane przez respondenta dla każdego pytania w kwestionariuszu.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-127">**Answer report** – This report shows the answers that the respondent selected for each question on the questionnaire.</span></span>
-   <span data-ttu-id="7d2c9-128">**Niepoprawne odpowiedzi** — pokazuje informacje dotyczące nieprawidłowych odpowiedzi wybranych przez respondenta.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-128">**Incorrect answers** – This report shows information that is related to the incorrect answers that the respondent selected.</span></span>

> [!NOTE]
> <span data-ttu-id="7d2c9-129">Strona **Wyniki** jest dostępna tylko w przypadku korzystania z grup wyników w kwestionariuszu i jeśli wybrano opcję **Strona wyników** na stronie **Kwestionariusze**.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-129">The **Results** report is available only if you use results groups on the questionnaire, and if you selected **Results page** on the **Questionnaires** page.</span></span> <span data-ttu-id="7d2c9-130">Strona **Odpowiedzi** oraz raport **Nieprawidłowe odpowiedzi** są dostępne tylko w przypadku wybrania opcji **Raport odpowiedzi** na stronie **Kwestionariusze**.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-130">The **Answer** report and the **Incorrect answers** report are available only if you selected **Answer report** on the **Questionnaires** page.</span></span>

## <a name="questionnaire-statistics"></a><span data-ttu-id="7d2c9-131">Statystyki kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="7d2c9-131">Questionnaire statistics</span></span>

<span data-ttu-id="7d2c9-132">Można użyć statystyk kwestionariusza do analizy wyników wypełnionego kwestionariusza na podstawie obliczeń zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-132">You can use questionnaire statistics to analyze the results of a completed questionnaire, based on calculations that you define.</span></span> <span data-ttu-id="7d2c9-133">Aby zdefiniować obliczenia, należy wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="7d2c9-133">To define calculations, you must complete the following tasks:</span></span>

-   <span data-ttu-id="7d2c9-134">Wybierz kryteria obliczania i wyświetlania statystyk.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-134">Select criteria to calculate and display the statistics.</span></span>
    -   <span data-ttu-id="7d2c9-135">Możesz wyświetlać statystyki według kwestionariusza, pytań, wierszy pytań lub grup wyników.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-135">You can show statistics by questionnaire, questions, question rows, or results groups.</span></span>
    -   <span data-ttu-id="7d2c9-136">Wybierz typ wykresu, który będzie używany podczas wyświetlania wyników.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-136">Select the type of chart that will be used when you view results.</span></span>
    -   <span data-ttu-id="7d2c9-137">Wybierz typy osób z sieci, np. pracownicy, osoby kontaktowe lub kandydaci, których odpowiedzi mają zostać uwzględnione.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-137">Select the types of people from the network, such as employees, contact persons, or applicants, to include answers for.</span></span> <span data-ttu-id="7d2c9-138">Można również uwzględnić odpowiedzi z kwestionariuszy, które zostały wypełnione anonimowo.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-138">You can also include answers from questionnaires that were completed anonymously.</span></span>
    -   <span data-ttu-id="7d2c9-139">Skonfiguruj interwały opartych na wieku lub stażu do analizowania wyników.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-139">Set up intervals that are based on age or seniority to analyze results.</span></span>
-   <span data-ttu-id="7d2c9-140">Wymierz lub sprawdź poprawność ustawień, które precyzują zakres statysty.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-140">Select or verify settings that refine the subject of the statistics.</span></span> <span data-ttu-id="7d2c9-141">Na przykład wybierając kod pocztowy, można analizować wyniki dla wszystkich respondentów w konkretnym obszarze geograficznym.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-141">For example, by selecting a ZIP Code or postal code, you can analyze results for all respondents within a specific geographic area.</span></span>
-   <span data-ttu-id="7d2c9-142">Określ lub sprawdź poprawność kryteriów do analizy wyników według cech respondenta lub kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-142">Select or verify criteria to analyze results by respondent or questionnaire characteristics.</span></span> <span data-ttu-id="7d2c9-143">Na przykład, wybierając **kod pocztowy**, można analizować korelację między lokalizacją respondenta i poprawnymi odpowiedziami.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-143">For example, by selecting **ZIP/postal code**, you can analyze the correlation between a respondent’s location and correct answers.</span></span>

<span data-ttu-id="7d2c9-144">Ustawienia określone przez użytkownika są zapisywane i mogą być używane do okresowego ponownego obliczania wyników.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-144">The settings that you define are saved and can be used to periodically recalculate results.</span></span>