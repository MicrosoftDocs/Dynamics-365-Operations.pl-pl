---
title: Włączanie drukowania etykiet numeru identyfikacyjnego
description: Ten temat pokazuje, jak włączyć automatyczne drukowanie etykiety z numerem seryjnym kontenera wysyłkowego (SSCC) po pobraniu ostatniego towaru z magazynu w procesie pracy pobierania dla sprzedaży.
author: perlynne
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a608e9a2356f9dd49bbec1bcbe5489af5931d44
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830889"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="86597-103">Włączanie drukowania etykiet numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="86597-103">Enable license plate label printing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="86597-104">Ten temat pokazuje, jak włączyć automatyczne drukowanie etykiety z numerem seryjnym kontenera wysyłkowego (SSCC) po pobraniu ostatniego towaru z magazynu w procesie pracy pobierania dla sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="86597-104">This topic shows how to enable the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="86597-105">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="86597-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="86597-106">Jeśli wykonujesz procedurę przy użyciu własnych danych, trzeba mieć zdefiniowaną sekwencję numeracji dla numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="86597-106">If you're run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="86597-107">Przed rozpoczęciem tego zadania należy skonfigurować drukarkę etykiet.</span><span class="sxs-lookup"><span data-stu-id="86597-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="86597-108">Wybierz kolejno opcje Administrowanie organizacją > Ustawienia > Drukarki sieciowe.</span><span class="sxs-lookup"><span data-stu-id="86597-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="86597-109">W okienku akcji kliknij przycisk Opcje, a następnie kliknij przycisk Pobierz instalatora agenta rozsyłania dokumentów.</span><span class="sxs-lookup"><span data-stu-id="86597-109">On the Action Pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="86597-110">Uruchom instalatora i przed rozpoczęciem procedury upewnij się, że działająca drukarka sieciowa ma ustawiony status Aktywna.</span><span class="sxs-lookup"><span data-stu-id="86597-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="86597-111">Konfigurowanie prefiksu GS1 firmy</span><span class="sxs-lookup"><span data-stu-id="86597-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="86597-112">Otwórz **Okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="86597-112">Go to **Navigation pane > Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="86597-113">W polu **Prefiks GS1 firmy** wprowadź 7-cyfrowy numer GS1 firmy.</span><span class="sxs-lookup"><span data-stu-id="86597-113">In the **GS1 company prefix** field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="86597-114">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="86597-114">Select **Save**.</span></span>
4. <span data-ttu-id="86597-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="86597-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="86597-116">Konfigurowanie sekwencji numeracji w numerze identyfikacyjnym SSCC</span><span class="sxs-lookup"><span data-stu-id="86597-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="86597-117">Otwórz **Okienko nawigacji > Moduły > Administrowanie organizacją > Sekwencje numerów > Sekwencje numerów**.</span><span class="sxs-lookup"><span data-stu-id="86597-117">Go to **Navigation pane > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="86597-118">W polu **Obszar** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="86597-118">In the **Area** field, select an option.</span></span>
3. <span data-ttu-id="86597-119">W polu **Odwołanie** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="86597-119">In the **Reference** field, select an option.</span></span>
4. <span data-ttu-id="86597-120">W polu **Firma** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="86597-120">In the **Company** field, type a value.</span></span>
5. <span data-ttu-id="86597-121">Rozwiń sekcję **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="86597-121">Expand the **Segments** section.</span></span>
6. <span data-ttu-id="86597-122">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="86597-122">Select **Edit**.</span></span>
7. <span data-ttu-id="86597-123">W tabeli **segmenty** zaznacz pierwszy wiersz.</span><span class="sxs-lookup"><span data-stu-id="86597-123">In the **Segments** table, select the first row</span></span>
8. <span data-ttu-id="86597-124">Wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="86597-124">Select **Remove**.</span></span>
9. <span data-ttu-id="86597-125">Wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="86597-125">Select **Remove**.</span></span>
10. <span data-ttu-id="86597-126">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="86597-126">Select **Save**.</span></span>
11. <span data-ttu-id="86597-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="86597-127">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="86597-128">Tworzenie układu trasy dokumentów</span><span class="sxs-lookup"><span data-stu-id="86597-128">Create the document route layout</span></span>
1. <span data-ttu-id="86597-129">Wybierz kolejno **Okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Wybór trasy dokumentów > Układy wyboru trasy dokumentów**.</span><span class="sxs-lookup"><span data-stu-id="86597-129">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing layouts**.</span></span> <span data-ttu-id="86597-130">Włącz układ kodu SSCC.</span><span class="sxs-lookup"><span data-stu-id="86597-130">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="86597-131">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="86597-131">Select **New**.</span></span>
3. <span data-ttu-id="86597-132">W polu **Identyfikator układu** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="86597-132">In the **Layout ID** field, type a value.</span></span>
4. <span data-ttu-id="86597-133">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="86597-133">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="86597-134">Wybierz **Wstaw na końcu tekstu**.</span><span class="sxs-lookup"><span data-stu-id="86597-134">Select **Insert at end of text**.</span></span>
6. <span data-ttu-id="86597-135">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="86597-135">Select **Save**.</span></span>
7. <span data-ttu-id="86597-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="86597-136">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="86597-137">Konfigurowanie opcji wyboru trasy dokumentów</span><span class="sxs-lookup"><span data-stu-id="86597-137">Set up the document routing</span></span>
1. <span data-ttu-id="86597-138">Wybierz kolejno **Okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Wybór trasy dokumentów > Wybór trasy dokumentów**.</span><span class="sxs-lookup"><span data-stu-id="86597-138">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing**.</span></span>
2. <span data-ttu-id="86597-139">W polu **Typ zlecenia pracy** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="86597-139">In the **Work order type** field, select an option.</span></span>
3. <span data-ttu-id="86597-140">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="86597-140">Select **New**.</span></span>
4. <span data-ttu-id="86597-141">W polu **Magazyn** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="86597-141">In the **Warehouse** field, type a value.</span></span>
5. <span data-ttu-id="86597-142">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="86597-142">In the **Name** field, type a value.</span></span>
6. <span data-ttu-id="86597-143">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="86597-143">Select **New**.</span></span>
7. <span data-ttu-id="86597-144">W polu **Identyfikator układu** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="86597-144">In the **Layout ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="86597-145">W polu **Nazwa** wpisz nazwę drukarki, której chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="86597-145">In the **Name** field, enter the printer name that you want to use.</span></span>
9. <span data-ttu-id="86597-146">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="86597-146">Select **Save**.</span></span>
10. <span data-ttu-id="86597-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="86597-147">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="86597-148">Utwórz menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="86597-148">Create mobile device menu</span></span>
1. <span data-ttu-id="86597-149">Wybierz **Okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="86597-149">Go to **Navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="86597-150">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="86597-150">Select **New**.</span></span>
3. <span data-ttu-id="86597-151">W polu **Nazwa elementu menu** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="86597-151">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="86597-152">W polu **Tytuł** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="86597-152">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="86597-153">W polu **Tryb** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="86597-153">In the **Mode** field, select an option.</span></span>
6. <span data-ttu-id="86597-154">W polu **Użyj istniejącej pracy** zaznacz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="86597-154">Select **Yes** in the **Use existing work** field.</span></span>
7. <span data-ttu-id="86597-155">W polu **Generuj numer identyfikacyjny** zaznacz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="86597-155">Select **Yes** in the **Generate license plate** field.</span></span>
8. <span data-ttu-id="86597-156">Rozwiń sekcję **Klasy robocze**.</span><span class="sxs-lookup"><span data-stu-id="86597-156">Expand the **Work classes** section.</span></span>
9. <span data-ttu-id="86597-157">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="86597-157">Select **New**.</span></span>
10. <span data-ttu-id="86597-158">W polu **Identyfikator klasy roboczej** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="86597-158">In the **Work class ID** field, type a value.</span></span>
11. <span data-ttu-id="86597-159">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="86597-159">Select **Save**.</span></span>
12. <span data-ttu-id="86597-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="86597-160">Close the page.</span></span>
13. <span data-ttu-id="86597-161">Wybierz **okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="86597-161">Go to **navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
14. <span data-ttu-id="86597-162">W widoku drzewa zaznacz element menu, który został wcześniej utworzony.</span><span class="sxs-lookup"><span data-stu-id="86597-162">In the tree, select the menu item that you created before.</span></span>
15. <span data-ttu-id="86597-163">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="86597-163">Select **Edit**.</span></span>
16. <span data-ttu-id="86597-164">Wybierz strzałkę, aby dodać element menu do menu.</span><span class="sxs-lookup"><span data-stu-id="86597-164">Select the arrow to add the menu item to the menu.</span></span>
17. <span data-ttu-id="86597-165">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="86597-165">Select **Save**.</span></span>
18. <span data-ttu-id="86597-166">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="86597-166">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="86597-167">Aktualizacja szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="86597-167">Update a work template</span></span>
1. <span data-ttu-id="86597-168">Przejdź do **Okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Praca > Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="86597-168">Go to **Navigation pane > Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="86597-169">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="86597-169">Select **Edit**.</span></span>
3. <span data-ttu-id="86597-170">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="86597-170">Select **New**.</span></span>
4. <span data-ttu-id="86597-171">W polu **Typ pracy** zaznacz opcję **Drukowanie**.</span><span class="sxs-lookup"><span data-stu-id="86597-171">In the **Work type** field, select **Print**.</span></span>
5. <span data-ttu-id="86597-172">W polu **Identyfikator klasy roboczej** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="86597-172">In the **Work class ID** field, enter or select a value.</span></span>
6. <span data-ttu-id="86597-173">Wybierz **Przenieś w górę**.</span><span class="sxs-lookup"><span data-stu-id="86597-173">Select **Move up**.</span></span>
7. <span data-ttu-id="86597-174">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="86597-174">Select **Save**.</span></span>
8. <span data-ttu-id="86597-175">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="86597-175">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]