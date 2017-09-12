--- 
title: "Definiowanie daty ważności wersji przepływu produkcji"
description: "Aby zakończyć ważność i przetwarzanie wersji przepływu produkcji w określonym dniu albo zaplanować zastąpienie aktywnej wersji nową wersją, należy ustawić datę ważności wersji."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6fabeb31720a60bf97d08dabf8ed87ac6af7cbf7
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a><span data-ttu-id="89115-103">Definiowanie daty ważności wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="89115-103">Define an expiry date for a production flow version</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="89115-104">Aby zakończyć ważność i przetwarzanie wersji przepływu produkcji w określonym dniu albo zaplanować zastąpienie aktywnej wersji nową wersją, należy ustawić datę ważności wersji.</span><span class="sxs-lookup"><span data-stu-id="89115-104">To end the validity and the processing of a production flow version on a given date, or to plan replacement of an active version with a new version, you have to set an expiry date on the version.</span></span> <span data-ttu-id="89115-105">Nie jest konieczne dezaktywowanie wersji.</span><span class="sxs-lookup"><span data-stu-id="89115-105">It is not necessary to deactivate the version.</span></span>


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a><span data-ttu-id="89115-106">Ustawianie daty ważności w celu zakończenia wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="89115-106">Set an expiration date to end a production flow version</span></span>
1. <span data-ttu-id="89115-107">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.</span><span class="sxs-lookup"><span data-stu-id="89115-107">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="89115-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="89115-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="89115-109">Zaznacz dowolny przepływ produkcji mający wersję, która jest już zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="89115-109">Select any production flow that has a version that is already defined.</span></span>  
3. <span data-ttu-id="89115-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="89115-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="89115-111">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="89115-111">Click Edit.</span></span>
5. <span data-ttu-id="89115-112">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="89115-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="89115-113">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="89115-113">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="89115-114">Po upływie daty ważności nowa wersja nie rozpocznie się ani nie uaktywni.</span><span class="sxs-lookup"><span data-stu-id="89115-114">For the expiration date, a new version will not start or become activated.</span></span> <span data-ttu-id="89115-115">Nie będzie można również tworzyć ani uruchamiać zadań dla tego przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="89115-115">It will also no longer be possible to create or start jobs for this production flow.</span></span> <span data-ttu-id="89115-116">Natomiast będzie można dokończyć rozpoczęte zadania.</span><span class="sxs-lookup"><span data-stu-id="89115-116">You can still complete started jobs after the expiration date.</span></span>  


