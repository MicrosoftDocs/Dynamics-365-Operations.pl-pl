---
title: Włączanie drukowania etykiet numeru identyfikacyjnego
description: Ta procedura umożliwia automatyczne drukowanie etykiety z numerem seryjnym kontenera wysyłkowego (SSCC) po pobraniu ostatniego towaru z magazynu w procesie pracy pobierania dla sprzedaży.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d906ca9f5a6536870fa0c322a0792ed5672c25e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "324038"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="edfab-103">Włączanie drukowania etykiet numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="edfab-103">Enable license plate label printing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="edfab-104">Ta procedura umożliwia automatyczne drukowanie etykiety z numerem seryjnym kontenera wysyłkowego (SSCC) po pobraniu ostatniego towaru z magazynu w procesie pracy pobierania dla sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="edfab-104">This procedure enables the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="edfab-105">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="edfab-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="edfab-106">Jeśli wykonujesz procedurę przy użyciu własnych danych, trzeba mieć zdefiniowaną sekwencję numeracji dla numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="edfab-106">If you’re run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="edfab-107">Przed rozpoczęciem tego zadania należy skonfigurować drukarkę etykiet.</span><span class="sxs-lookup"><span data-stu-id="edfab-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="edfab-108">Wybierz kolejno opcje Administrowanie organizacją > Ustawienia > Drukarki sieciowe.</span><span class="sxs-lookup"><span data-stu-id="edfab-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="edfab-109">W okienku akcji kliknij przycisk Opcje, a następnie kliknij przycisk Pobierz instalatora agenta rozsyłania dokumentów.</span><span class="sxs-lookup"><span data-stu-id="edfab-109">On the Action pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="edfab-110">Uruchom instalatora i przed rozpoczęciem procedury upewnij się, że działająca drukarka sieciowa ma ustawiony status Aktywna.</span><span class="sxs-lookup"><span data-stu-id="edfab-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="edfab-111">Konfigurowanie prefiksu GS1 firmy</span><span class="sxs-lookup"><span data-stu-id="edfab-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="edfab-112">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="edfab-112">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="edfab-113">W polu Prefiks GS1 firmy wprowadź 7-cyfrowy numer GS1 firmy.</span><span class="sxs-lookup"><span data-stu-id="edfab-113">In the GS1 company prefix field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="edfab-114">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="edfab-114">Click Save.</span></span>
4. <span data-ttu-id="edfab-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="edfab-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="edfab-116">Konfigurowanie sekwencji numeracji w numerze identyfikacyjnym SSCC</span><span class="sxs-lookup"><span data-stu-id="edfab-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="edfab-117">Wybierz kolejno opcje Administrowanie organizacją > Sekwencje numerów > Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="edfab-117">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="edfab-118">W polu Obszar wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="edfab-118">In the Area field, select an option.</span></span>
3. <span data-ttu-id="edfab-119">W polu Odwołanie wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="edfab-119">In the Reference field, select an option.</span></span>
4. <span data-ttu-id="edfab-120">W polu Firma wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="edfab-120">In the Company field, type a value.</span></span>
5. <span data-ttu-id="edfab-121">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="edfab-121">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="edfab-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="edfab-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="edfab-123">Rozwiń sekcję Segmenty.</span><span class="sxs-lookup"><span data-stu-id="edfab-123">Expand the Segments section.</span></span>
8. <span data-ttu-id="edfab-124">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="edfab-124">Click Edit.</span></span>
9. <span data-ttu-id="edfab-125">W tabeli segmentów zaznacz pierwszy wiersz</span><span class="sxs-lookup"><span data-stu-id="edfab-125">In the Segments table, select the first row</span></span>
10. <span data-ttu-id="edfab-126">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="edfab-126">Click Remove.</span></span>
11. <span data-ttu-id="edfab-127">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="edfab-127">Click Remove.</span></span>
12. <span data-ttu-id="edfab-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="edfab-128">Click Save.</span></span>
13. <span data-ttu-id="edfab-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="edfab-129">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="edfab-130">Tworzenie układu trasy dokumentów</span><span class="sxs-lookup"><span data-stu-id="edfab-130">Create the document route layout</span></span>
1. <span data-ttu-id="edfab-131">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Wybór trasy dokumentów > Układy wyboru trasy dokumentów.</span><span class="sxs-lookup"><span data-stu-id="edfab-131">Go to Warehouse management > Setup > Document routing > Document routing layouts.</span></span>
    * <span data-ttu-id="edfab-132">Włącz układ kodu SSCC.</span><span class="sxs-lookup"><span data-stu-id="edfab-132">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="edfab-133">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="edfab-133">Click New.</span></span>
3. <span data-ttu-id="edfab-134">W polu Identyfikator układu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="edfab-134">In the Layout ID field, type a value.</span></span>
4. <span data-ttu-id="edfab-135">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="edfab-135">In the Description field, type a value.</span></span>
5. <span data-ttu-id="edfab-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="edfab-136">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="edfab-137">Kliknij przycisk Wstaw na końcu tekstu.</span><span class="sxs-lookup"><span data-stu-id="edfab-137">Click Insert at end of text.</span></span>
7. <span data-ttu-id="edfab-138">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="edfab-138">Click Save.</span></span>
8. <span data-ttu-id="edfab-139">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="edfab-139">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="edfab-140">Konfigurowanie opcji wyboru trasy dokumentów</span><span class="sxs-lookup"><span data-stu-id="edfab-140">Set up the document routing</span></span>
1. <span data-ttu-id="edfab-141">Wybierz kolejno opcje Zarządzanie magazynem > ustawienia > Wybór trasy dokumentów > Wybór trasy dokumentów.</span><span class="sxs-lookup"><span data-stu-id="edfab-141">Go to Warehouse management > Setup > Document routing > Document routing.</span></span>
2. <span data-ttu-id="edfab-142">W polu Typ zlecenia wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="edfab-142">In the Work order type field, select an option.</span></span>
3. <span data-ttu-id="edfab-143">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="edfab-143">Click New.</span></span>
4. <span data-ttu-id="edfab-144">W polu Magazyn wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="edfab-144">In the Warehouse field, type a value.</span></span>
5. <span data-ttu-id="edfab-145">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="edfab-145">In the Name field, type a value.</span></span>
6. <span data-ttu-id="edfab-146">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="edfab-146">Click New.</span></span>
7. <span data-ttu-id="edfab-147">W polu Identyfikator układu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="edfab-147">In the Layout ID field, enter or select a value.</span></span>
8. <span data-ttu-id="edfab-148">W polu Nazwa wpisz nazwę drukarki, której chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="edfab-148">In the Name field, enter the printer name that you want to use..</span></span>
9. <span data-ttu-id="edfab-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="edfab-149">Click Save.</span></span>
10. <span data-ttu-id="edfab-150">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="edfab-150">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="edfab-151">Utwórz menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="edfab-151">Create mobile device menu</span></span>
1. <span data-ttu-id="edfab-152">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="edfab-152">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="edfab-153">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="edfab-153">Click New.</span></span>
3. <span data-ttu-id="edfab-154">W polu Nazwa elementu menu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="edfab-154">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="edfab-155">W polu Tytuł wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="edfab-155">In the Title field, type a value.</span></span>
5. <span data-ttu-id="edfab-156">W polu Tryb wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="edfab-156">In the Mode field, select an option.</span></span>
6. <span data-ttu-id="edfab-157">W polu Użyj istniejącej pracy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="edfab-157">Select Yes in the Use existing work field.</span></span>
7. <span data-ttu-id="edfab-158">W polu Generuj numer identyfikacyjny zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="edfab-158">Select Yes in the Generate license plate field.</span></span>
8. <span data-ttu-id="edfab-159">Rozwiń sekcję Klasy robocze.</span><span class="sxs-lookup"><span data-stu-id="edfab-159">Expand the Work classes section.</span></span>
9. <span data-ttu-id="edfab-160">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="edfab-160">Click New.</span></span>
10. <span data-ttu-id="edfab-161">W polu Identyfikator klasy roboczej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="edfab-161">In the Work class ID field, type a value.</span></span>
11. <span data-ttu-id="edfab-162">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="edfab-162">Click Save.</span></span>
12. <span data-ttu-id="edfab-163">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="edfab-163">Close the page.</span></span>
13. <span data-ttu-id="edfab-164">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Menu urządzeń przenośnych.</span><span class="sxs-lookup"><span data-stu-id="edfab-164">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
14. <span data-ttu-id="edfab-165">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="edfab-165">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="edfab-166">W drzewie zaznacz utworzony wcześniej element menu.</span><span class="sxs-lookup"><span data-stu-id="edfab-166">In the tree, select 'In the tree, select the menu item that you created before.'.</span></span>
16. <span data-ttu-id="edfab-167">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="edfab-167">Click Edit.</span></span>
17. <span data-ttu-id="edfab-168">Kliknij strzałkę, aby dodać element menu do menu.</span><span class="sxs-lookup"><span data-stu-id="edfab-168">Click on the arrow to add the menu item to the menu.</span></span>
18. <span data-ttu-id="edfab-169">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="edfab-169">Click Save.</span></span>
19. <span data-ttu-id="edfab-170">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="edfab-170">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="edfab-171">Aktualizacja szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="edfab-171">Update a work template</span></span>
1. <span data-ttu-id="edfab-172">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Szablony pracy.</span><span class="sxs-lookup"><span data-stu-id="edfab-172">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="edfab-173">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="edfab-173">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="edfab-174">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="edfab-174">Click Edit.</span></span>
4. <span data-ttu-id="edfab-175">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="edfab-175">Click New.</span></span>
5. <span data-ttu-id="edfab-176">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="edfab-176">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="edfab-177">W polu Typ pracy zaznacz opcję „Drukowanie”.</span><span class="sxs-lookup"><span data-stu-id="edfab-177">In the Work type field, select 'Print'.</span></span>
7. <span data-ttu-id="edfab-178">W polu Identyfikator klasy roboczej wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="edfab-178">In the Work class ID field, enter or select a value.</span></span>
8. <span data-ttu-id="edfab-179">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="edfab-179">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="edfab-180">Kliknij przycisk W górę.</span><span class="sxs-lookup"><span data-stu-id="edfab-180">Click Move up.</span></span>
10. <span data-ttu-id="edfab-181">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="edfab-181">Click Save.</span></span>
11. <span data-ttu-id="edfab-182">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="edfab-182">Close the page.</span></span>

