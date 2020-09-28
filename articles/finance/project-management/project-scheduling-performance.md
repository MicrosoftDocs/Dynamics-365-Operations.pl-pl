---
title: Planowanie wydajności zasobów projektu
description: Ten temat zawiera informacje o sposobach zwiększania wydajności planowania zasobów dla dużej liczby projektów.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760639"
---
# <a name="project-resource-scheduling-performance"></a><span data-ttu-id="a9824-103">Planowanie wydajności zasobów projektu</span><span class="sxs-lookup"><span data-stu-id="a9824-103">Project resource scheduling performance</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


<span data-ttu-id="a9824-104">Problemy z wydajnością związane z planowaniem zasobów mogą wystąpić, gdy liczba projektów będzie liczona w tysiącach.</span><span class="sxs-lookup"><span data-stu-id="a9824-104">Performance issues related to resource scheduling can occur when the number of projects reaches into the thousands.</span></span> <span data-ttu-id="a9824-105">Aby poprawić wydajność planowania zasobów, dostępna jest funkcja umożliwiająca użytkownikom skrócenie czasu niezbędnego do uruchomienia formularza dostępności zasobu.</span><span class="sxs-lookup"><span data-stu-id="a9824-105">To improve resource scheduling performance, a feature is available that allows users to reduce the time that it takes to launch the resource availability form.</span></span> <span data-ttu-id="a9824-106">Powoduje to usunięcie procesu synchronizacji dyspozycyjności zasobów i zastosowanie tabeli **ResProjectResource** w celu przyspieszenia wyszukiwania zasobów.</span><span class="sxs-lookup"><span data-stu-id="a9824-106">Specifically, this removes the resource capacity roll-up synchronization process and uses the **ResProjectResource** table to speed up the resource lookup.</span></span> <span data-ttu-id="a9824-107">Zauważ, że tabela **ResRollup** nie będzie już używana.</span><span class="sxs-lookup"><span data-stu-id="a9824-107">Note that the **ResRollup** table will no longer be used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9824-108">Jeśli istnieje zależność od procesu synchronizacji zdolności produkcyjnych zasobów lub tabeli **ResProjectResource**, nie należy stosować tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="a9824-108">If there is a dependency on either the resource capacity roll-up synchronization process or the **ResProjectResource** table, do not use this feature.</span></span>

## <a name="enable-resource-scheduling-performance-enhancement"></a><span data-ttu-id="a9824-109">Włączanie rozszerzania wydajności planowania zasobów</span><span class="sxs-lookup"><span data-stu-id="a9824-109">Enable resource scheduling performance enhancement</span></span>
<span data-ttu-id="a9824-110">Aby włączyć rozszerzanie wydajności planowania zasobów, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a9824-110">To enable resource scheduling performance enhancement, complete the following steps.</span></span>

1. <span data-ttu-id="a9824-111">Przejdź do funkcji **Zarządzanie funkcjami** > **Wszystko**, a na liście funkcji znajdź pozycję **Włącz funkcję zwiększania wydajności planowania zasobów projektu**.</span><span class="sxs-lookup"><span data-stu-id="a9824-111">Go to **Feature management** > **All**, and in the feature list, locate **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="a9824-112">Wybierz **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="a9824-112">Select **Enable now**.</span></span>

> [!NOTE]
> <span data-ttu-id="a9824-113">Jeśli nie możesz odnaleźć tej funkcji na liście, wybierz opcję **Sprawdź dostępność aktualizacji**, aby odświeżyć listę.</span><span class="sxs-lookup"><span data-stu-id="a9824-113">If you can't find the feature in the list, select **Check for updates** to refresh the list.</span></span>

3. <span data-ttu-id="a9824-114">Odśwież przeglądarkę, a następnie przejdź do obszaru **Zarządzanie projektami i księgowanie** > **Okresowe** > **Zasoby projektu** > **Synchronizuj kalendarze zasobów między wszystkimi firmami**.</span><span class="sxs-lookup"><span data-stu-id="a9824-114">Refresh your browser, and then go to **Project management and accounting** > **Periodic** > **Project resources** > **Synchronize resource calendars capacity across all companies**.</span></span>
4. <span data-ttu-id="a9824-115">Ustaw wartość **Usuń istniejące rekordy zdolności produkcyjnych** na **Tak**, aby usunąć poprzednie dane.</span><span class="sxs-lookup"><span data-stu-id="a9824-115">Set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="a9824-116">Jeśli chcesz generować przyrostowe dane, wybierz wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="a9824-116">If you want generate incremental data, set it to **No**.</span></span>
5. <span data-ttu-id="a9824-117">W polu **Kod okresu** wybierz okres, dla którego mają zostać wygenerowane dane.</span><span class="sxs-lookup"><span data-stu-id="a9824-117">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="a9824-118">W przypadku wybrania kodu okresu nie trzeba definiować daty rozpoczęcia i zakończenia.</span><span class="sxs-lookup"><span data-stu-id="a9824-118">If you select a period code, a start and end date do not need to be defined.</span></span>
6. <span data-ttu-id="a9824-119">Jeśli pole **Kod okresu** pozostanie puste, w celu wygenerowania danych wybierz określone daty rozpoczęcia i zakończenia.</span><span class="sxs-lookup"><span data-stu-id="a9824-119">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
7. <span data-ttu-id="a9824-120">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9824-120">Select **OK**.</span></span>

 > [!NOTE]
 > <span data-ttu-id="a9824-121">Spowoduje to dystrybuowanie ogólnych danych do tabeli **ResCalendarCapacity** we wszystkich firmach w danym środowisku, więc zadanie wsadowe należy uruchomić tylko w jednej firmie.</span><span class="sxs-lookup"><span data-stu-id="a9824-121">This will distribute general data to the **ResCalendarCapacity** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="a9824-122">Dane w tym zadaniu wsadowym są potrzebne do obliczenia zdolności produkcyjnych zasobu za pośrednictwem skojarzonego z nim kalendarza.</span><span class="sxs-lookup"><span data-stu-id="a9824-122">The data in this batch job is needed to calculate resource capacity through the associated calendar.</span></span>

8. <span data-ttu-id="a9824-123">Przejdź do obszaru **Zarządzanie projektami i księgowanie** > **Okresowe** > **Zasoby projektu** > **Wypełnij zasoby projektu we wszystkich firmach**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9824-123">Go to **Project management and accounting** > **Periodic** > **Project resources** > **Populate project resources across all companies** and then select **OK**.</span></span> <span data-ttu-id="a9824-124">To jest skrypt uaktualnienia danych dla ogólnych danych w tabelach **ResProjectResource**, **ResCalendarDateTimeRange** i **ResEffectiveDateTimeRange**.</span><span class="sxs-lookup"><span data-stu-id="a9824-124">This is the data upgrade script for general data in the **ResProjectResource**, **ResCalendarDateTimeRange**, and **ResEffectiveDateTimeRange** tables.</span></span> <span data-ttu-id="a9824-125">Wartości pola **PSAPRojSchedRole.RootActivity** również zostaną zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="a9824-125">Values for the **PSAPRojSchedRole.RootActivity** field are also updated.</span></span> <span data-ttu-id="a9824-126">Jeśli nie zostanie uruchomiony, podczas próby wykonania operacji planowania zasobów zostanie wyświetlone ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="a9824-126">If this is not run, you will receive a warning when you try to execute resource scheduling operations.</span></span>
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a><span data-ttu-id="a9824-127">Wyłączanie rozszerzania wydajności planowania zasobów</span><span class="sxs-lookup"><span data-stu-id="a9824-127">Turn off resource scheduling performance enhancement</span></span>

1. <span data-ttu-id="a9824-128">Przejdź do funkcji **Zarządzanie funkcjami** > **Wszystko**, a na liście funkcji znajdź **Włącz funkcję zwiększania wydajności planowania zasobów projektu**.</span><span class="sxs-lookup"><span data-stu-id="a9824-128">Go to **Feature management** > **All**  and search for **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="a9824-129">Wybierz funkcję, a następnie wybierz **Wyłącz**.</span><span class="sxs-lookup"><span data-stu-id="a9824-129">Select the feature, and then select the **Disable** button.</span></span>
3. <span data-ttu-id="a9824-130">Odśwież przeglądarkę.</span><span class="sxs-lookup"><span data-stu-id="a9824-130">Refresh your browser.</span></span>
4. <span data-ttu-id="a9824-131">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** > **Okresowe** > **Synchronizacja zdolności produkcyjnych** > **Synchronizuj zestawienia zdolności produkcyjnych zasobów**.</span><span class="sxs-lookup"><span data-stu-id="a9824-131">Go to **Project management and accounting** > **Periodic** > **Capacity synchronization** > **Synchronize resource capacity roll-ups**.</span></span>
5. <span data-ttu-id="a9824-132">Na stronie **Synchronizacja zdolności produkcyjnych** ustaw dla opcji **Usuń istniejące rekordy zdolności produkcyjnych** wartość **Tak**, aby usunąć poprzednie dane.</span><span class="sxs-lookup"><span data-stu-id="a9824-132">On the **Capacity roll-up synchronization** page, set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="a9824-133">Jeśli chcesz generować przyrostowe dane, wybierz wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="a9824-133">If you want to generate incremental data, set it to **No**.</span></span>
6. <span data-ttu-id="a9824-134">W polu **Kod okresu** wybierz okres, dla którego mają zostać wygenerowane dane.</span><span class="sxs-lookup"><span data-stu-id="a9824-134">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="a9824-135">W przypadku wybrania kodu okresu nie trzeba definiować daty rozpoczęcia i zakończenia.</span><span class="sxs-lookup"><span data-stu-id="a9824-135">If you select a period code, a start and end date do not need to be defined.</span></span>
7. <span data-ttu-id="a9824-136">Jeśli pole **Kod okresu** pozostanie puste, w celu wygenerowania danych wybierz określone daty rozpoczęcia i zakończenia.</span><span class="sxs-lookup"><span data-stu-id="a9824-136">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
8. <span data-ttu-id="a9824-137">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9824-137">Select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="a9824-138">Spowoduje to dystrybuowanie ogólnych danych do tabeli **ResRollup** we wszystkich firmach w danym środowisku, więc zadanie wsadowe należy uruchomić tylko w jednej firmie.</span><span class="sxs-lookup"><span data-stu-id="a9824-138">This will distribute general data to the **ResRollup** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="a9824-139">To zadanie wsadowe jest wymagane w przypadku wszystkich widoków **Dostępności zasobów**.</span><span class="sxs-lookup"><span data-stu-id="a9824-139">This batch job is needed for all **Resource Availability** views.</span></span> <span data-ttu-id="a9824-140">Jeśli to zadanie wsadowe nie zostanie uruchomione, dane **ResRollup** będą generowane na bieżąco, co może być czasochłonne.</span><span class="sxs-lookup"><span data-stu-id="a9824-140">If this batch job is not run, the **ResRollup** data will be generated on the fly, which can take time.</span></span>
