---
title: Definiowanie daty ważności wersji przepływu produkcji
description: Aby zakończyć ważność i przetwarzanie wersji przepływu produkcji w określonym dniu albo zaplanować zastąpienie aktywnej wersji nową wersją, należy ustawić datę ważności wersji.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10260290fba02ebf9313d0d1355c9aa28e3509d7
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843704"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a><span data-ttu-id="09b83-103">Definiowanie daty ważności wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="09b83-103">Define an expiry date for a production flow version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="09b83-104">Aby zakończyć ważność i przetwarzanie wersji przepływu produkcji w określonym dniu albo zaplanować zastąpienie aktywnej wersji nową wersją, należy ustawić datę ważności wersji.</span><span class="sxs-lookup"><span data-stu-id="09b83-104">To end the validity and the processing of a production flow version on a given date, or to plan replacement of an active version with a new version, you have to set an expiry date on the version.</span></span> <span data-ttu-id="09b83-105">Nie jest konieczne dezaktywowanie wersji.</span><span class="sxs-lookup"><span data-stu-id="09b83-105">It is not necessary to deactivate the version.</span></span>


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a><span data-ttu-id="09b83-106">Ustawianie daty ważności w celu zakończenia wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="09b83-106">Set an expiration date to end a production flow version</span></span>
1. <span data-ttu-id="09b83-107">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.</span><span class="sxs-lookup"><span data-stu-id="09b83-107">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="09b83-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="09b83-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="09b83-109">Zaznacz dowolny przepływ produkcji mający wersję, która jest już zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="09b83-109">Select any production flow that has a version that is already defined.</span></span>  
3. <span data-ttu-id="09b83-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="09b83-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="09b83-111">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="09b83-111">Click Edit.</span></span>
5. <span data-ttu-id="09b83-112">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="09b83-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="09b83-113">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="09b83-113">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="09b83-114">Po upływie daty ważności nowa wersja nie rozpocznie się ani nie uaktywni.</span><span class="sxs-lookup"><span data-stu-id="09b83-114">For the expiration date, a new version will not start or become activated.</span></span> <span data-ttu-id="09b83-115">Nie będzie można również tworzyć ani uruchamiać zadań dla tego przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="09b83-115">It will also no longer be possible to create or start jobs for this production flow.</span></span> <span data-ttu-id="09b83-116">Natomiast będzie można dokończyć rozpoczęte zadania.</span><span class="sxs-lookup"><span data-stu-id="09b83-116">You can still complete started jobs after the expiration date.</span></span>  

