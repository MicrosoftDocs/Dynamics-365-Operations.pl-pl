---
title: Drukowanie etykiety grupy czynności
description: W tym temacie opisano drukowanie etykiet w grupie czynności i opisano sposób jego konfigurowania.
author: perlynne
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 14a32f7fc4608ef8910646f80786a188c46dc89d
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102621"
---
# <a name="wave-label-printing"></a><span data-ttu-id="fef99-103">Drukowanie etykiety grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-103">Wave label printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fef99-104">Drukowanie etykiet w grupie czynności jest alternatywnym podejściem do drukowania etykiet przez wprowadzenie nowej metody, która umożliwia tworzenie i drukowanie etykiet bezpośrednio z szablonu grupy czynności w trakcie wykonywania czynności typu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-104">Wave label printing offers an alternative approach to label printing by introducing a new wave step method that lets you create and print labels directly from the wave template during wave execution.</span></span> <span data-ttu-id="fef99-105">Dlatego etykiety będą już dostępne, zanim pracownicy uruchomili zlecenie produkcyjne na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="fef99-105">Therefore, the labels will already be available before workers run the work order on a mobile device.</span></span> <span data-ttu-id="fef99-106">Pracownicy mogą następnie dołączać wymagane etykiety podczas pobierania, a nie po ich pobraniu.</span><span class="sxs-lookup"><span data-stu-id="fef99-106">Workers can then attach the required labels during picking instead of after picking.</span></span>

<span data-ttu-id="fef99-107">Drukowanie etykiet w postaci grupy czynności jest używane w języku programowania Zebra (ZPL) do tworzenia układów etykiet.</span><span class="sxs-lookup"><span data-stu-id="fef99-107">Wave label printing uses Zebra Programming Language (ZPL) to create label layouts.</span></span> <span data-ttu-id="fef99-108">Układ etykiety jest podzielony na trzy sekcje (nagłówek, treść i stopka), co pozwala na tworzenie etykiet z powtarzającą się strukturą.</span><span class="sxs-lookup"><span data-stu-id="fef99-108">A label layout is divided into three sections (header, body, and footer) to allow for labels that have repeating structure.</span></span> <span data-ttu-id="fef99-109">Szablony etykiet grupy czynności informują system, który układ etykiety ma być używany.</span><span class="sxs-lookup"><span data-stu-id="fef99-109">Wave label templates tell the system which label layout to use.</span></span> <span data-ttu-id="fef99-110">Użytkownicy mogą określać, która drukarka jest używana.</span><span class="sxs-lookup"><span data-stu-id="fef99-110">Users can specify which printer is used.</span></span> <span data-ttu-id="fef99-111">Mogą również drukować etykiety na kilku drukarkach w tym samym czasie, w zależności od potrzeb.</span><span class="sxs-lookup"><span data-stu-id="fef99-111">They can also print labels on several printers at the same time, as they require.</span></span> <span data-ttu-id="fef99-112">Na stronie **Historia etykiet grupy czynności** wyświetlany jest rekord wszystkich etykiet utworzonych za pomocą tej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="fef99-112">The **Wave label history** page shows a record of all labels that have been created by using this setup.</span></span>

<span data-ttu-id="fef99-113">Etykiety można drukować i sortować na podstawie nagłówków pracy, można drukować etykiety podziału dla każdego nagłówka pracy, a także drukować etykiety zawartości kontenerów, etykiety przypadków i inne podobne etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-113">You can print and collate labels based on work headers, you can print break labels per work header, and you can print container content labels, case labels, and other similar labels.</span></span>

> [!NOTE]
> <span data-ttu-id="fef99-114">Ta funkcja nie zastępuje istniejącej funkcji drukowania etykiet opartej na marszrucie dokumentów.</span><span class="sxs-lookup"><span data-stu-id="fef99-114">This functionality doesn't replace existing label printing functionality that is based on document routing.</span></span>

<span data-ttu-id="fef99-115">W przypadku drukowania etykiet grupy czynności dostępne są następujące udoskonalenia:</span><span class="sxs-lookup"><span data-stu-id="fef99-115">Wave label printing offers the following enhancements:</span></span>

- <span data-ttu-id="fef99-116">Drukowanie etykiet zgodnie z liczbą kartonów w jednym wierszu pracy bez używania konteneryzacji.</span><span class="sxs-lookup"><span data-stu-id="fef99-116">Print labels according to the number of cartons on a single work line, without using containerization.</span></span> <span data-ttu-id="fef99-117">(„Karton” oznacza jednostkę wyznaczoną w wierszach grupy sekwencji jednostek.)</span><span class="sxs-lookup"><span data-stu-id="fef99-117">(A "carton" is a unit that is designated on unit sequence group lines.)</span></span>
- <span data-ttu-id="fef99-118">Umożliwia drukowanie kilku różnych sekwencji etykiet (np. etykiet kartonowych i palet).</span><span class="sxs-lookup"><span data-stu-id="fef99-118">Print several different label sequences (for example, carton and pallet labels).</span></span>
- <span data-ttu-id="fef99-119">Uwzględnij wyliczenie etykiet (na przykład 1/124, 2/124,... 124/124) i zdefiniuj zakres wyliczenia (na przykład wiersz pracy, wiersz ładunku lub wysyłka).</span><span class="sxs-lookup"><span data-stu-id="fef99-119">Include label enumeration (for example, 1/124, 2/124, ... 124/124), and define the range of enumeration (for example, work line, load line, or shipment).</span></span>
- <span data-ttu-id="fef99-120">Utwórz i wydrukuj identyfikator list przewozowy na etykietach przed wygenerowaniem list przewozowy.</span><span class="sxs-lookup"><span data-stu-id="fef99-120">Create and print a bill of lading ID on labels before the bill of lading is generated.</span></span>
- <span data-ttu-id="fef99-121">Utwórz unikatowy numer kontenera wysyłkowego dla każdego kartonu (SSCC) i umieść go na każdej etykiecie.</span><span class="sxs-lookup"><span data-stu-id="fef99-121">Create a unique serial shipping container code (SSCC) for each carton, and include it on each label.</span></span>
- <span data-ttu-id="fef99-122">Umożliwia tworzenie sekwencji numerów zgodnych z GS1 dla identyfikatorów list przewozowych i kodów SSCC.</span><span class="sxs-lookup"><span data-stu-id="fef99-122">Create GS1-compliant number sequences for bill of lading IDs and SSCCs.</span></span>
- <span data-ttu-id="fef99-123">Umożliwia ponowne wydrukowanie etykiet z obu urządzeń przenośnych i klienta wzbogaconego.</span><span class="sxs-lookup"><span data-stu-id="fef99-123">Reprint labels from both mobile devices and the rich client.</span></span>
- <span data-ttu-id="fef99-124">Unieważnij etykiety (na przykład w krótkich scenariuszach pobrania) i wydrukuj je ponownie.</span><span class="sxs-lookup"><span data-stu-id="fef99-124">Void labels (for example, in short pick scenarios), and reprint them.</span></span>
- <span data-ttu-id="fef99-125">Czyszczenie historii etykiety grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-125">Clean up the wave label history.</span></span>
- <span data-ttu-id="fef99-126">Udoskonalenia układów rozsyłania dokumentów są udostępniane między układami rozsyłania dokumentów i układami etykiet grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-126">Improvements to document routing layouts are shared between document routing layouts and wave label layouts.</span></span> <span data-ttu-id="fef99-127">(Aby uzyskać więcej informacji, należy zapoznać się z tematem [Układ rozsyłania dokumentów dla numerów identyfikacyjnych](../warehousing/document-routing-layout-for-license-plates.md) .)</span><span class="sxs-lookup"><span data-stu-id="fef99-127">(For more information, see [Document routing layout for license plates](../warehousing/document-routing-layout-for-license-plates.md).)</span></span>

<span data-ttu-id="fef99-128">Te udoskonalenia zwiększają efektywność tworzenia etykiet kartonowych przed wyłożeniem na palety.</span><span class="sxs-lookup"><span data-stu-id="fef99-128">These enhancements make it more efficient to label cartons before palletization.</span></span> <span data-ttu-id="fef99-129">Są one szczególnie korzystne dla firm dostarczanych do dużych sprzedawców, którzy automatycznie potwierdzają pokwitowania zamówień, skanując poszczególne kartony osobno.</span><span class="sxs-lookup"><span data-stu-id="fef99-129">They especially benefit companies that ship to large retailers that automatically confirm order receipts by scanning each carton separately.</span></span>

> [!NOTE]
> <span data-ttu-id="fef99-130">Scenariusze konfiguracji opisane w tym temacie można zaimplementować oddzielnie lub w połączeniu, zależnie od wymagań biznesowych systemu.</span><span class="sxs-lookup"><span data-stu-id="fef99-130">You can implement the configuration scenarios that are described in this topic either separately or in combination, depending on your business requirements.</span></span> <span data-ttu-id="fef99-131">Istnieje możliwość projektowania kilku szablonów etykiet grupy czynności, które działają w sekwencji (jak w scenariuszu 3).</span><span class="sxs-lookup"><span data-stu-id="fef99-131">You can design several wave label templates that work in sequence (as illustrated in scenario 3).</span></span> <span data-ttu-id="fef99-132">Na przykład w scenariuszu 1 można drukować etykiety kartonów i scenariusz 2, aby drukować etykiety palet (jeśli palety w magazynie są różne w rozmiarach i składzie).</span><span class="sxs-lookup"><span data-stu-id="fef99-132">For example, you can use scenario 1 to print carton labels and scenario 2 to print pallet labels (if pallets in stock vary in size and composition).</span></span>

## <a name="turn-on-the-wave-label-printing-feature"></a><span data-ttu-id="fef99-133">Włączanie funkcji drukowania etykiet grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-133">Turn on the Wave label printing feature</span></span>

<span data-ttu-id="fef99-134">Aby móc używać funkcji *Drukowanie etykiet grupy czynności*, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="fef99-134">Before you can use the *Wave label printing* feature, it must be turned on in your system.</span></span> <span data-ttu-id="fef99-135">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="fef99-135">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="fef99-136">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="fef99-136">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="fef99-137">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="fef99-137">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="fef99-138">**Nazwa funkcji:** *Drukowanie etykiet grup czynności*</span><span class="sxs-lookup"><span data-stu-id="fef99-138">**Feature name:** *Wave label printing*</span></span>

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a><span data-ttu-id="fef99-139">Scenariusz 1: Drukowanie etykiet grupy czynności, w którym jest generowana pojedyncza etykieta grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-139">Scenario 1: Wave label printing where a single wave label is generated</span></span>

<span data-ttu-id="fef99-140">W tym scenariuszu przedstawiono sposób, w jaki firma może drukować etykiety wysyłkowe dla dużego sprzedawców, które automatycznie potwierdzają pokwitowania zamówień, skanując każdy karton z osobna.</span><span class="sxs-lookup"><span data-stu-id="fef99-140">This scenario shows how a company can print shipping labels for a large retailer that automatically confirms order receipts by scanning each carton separately.</span></span>

<span data-ttu-id="fef99-141">Ten scenariusz pokazuje przepływ końcowy na koniec.</span><span class="sxs-lookup"><span data-stu-id="fef99-141">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="fef99-142">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="fef99-142">Make demo data available</span></span>

<span data-ttu-id="fef99-143">W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być wybrana firma **USMF**.</span><span class="sxs-lookup"><span data-stu-id="fef99-143">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="fef99-144">Upewnij się, że metoda etykiet grupy czynności jest dostępna</span><span class="sxs-lookup"><span data-stu-id="fef99-144">Make sure that the wave label method is available</span></span>

<span data-ttu-id="fef99-145">Może być konieczne ponowne wygenerowanie metod przetwarzania grupy czynności, aby można było udostępnić metodę drukowania etykiet grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-145">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="fef99-146">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-146">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="fef99-147">Potwierdź, że **waveLabelPrinting** jest na liście.</span><span class="sxs-lookup"><span data-stu-id="fef99-147">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="fef99-148">Jeśli nie, wybierz polecenie **Wygeneruj ponownie metody** w okienku akcji, aby dodać metodę.</span><span class="sxs-lookup"><span data-stu-id="fef99-148">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="fef99-149">Skonfiguruj szablon grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-149">Configure a wave template</span></span>

<span data-ttu-id="fef99-150">Szablony grupy czynności umożliwiają łączenie konkretnych instancji metod grupy czynności z odpowiednim szablonem etykiety grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-150">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="fef99-151">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="fef99-152">Wybierz szablon grupy czynności, na przykład **Domyślna 62-godzinna wysyłka**.</span><span class="sxs-lookup"><span data-stu-id="fef99-152">Select a template, such as **62 Shipping Default**.</span></span>
1. <span data-ttu-id="fef99-153">Na skróconej karcie **Metody** należy przenieść metodę **Drukowania etykiet grupy czynności** do kolumny **Wybrane metody**.</span><span class="sxs-lookup"><span data-stu-id="fef99-153">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="fef99-154">W kolumnie **Wybrane metody** wybierz metodę **Drukowania etykiet grupy czynności** i określ w polu **Kod kroku grupy czynności** wartość *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="fef99-154">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="fef99-155">Aby uzyskać więcej informacji o kodach kroku grupy czynności, przejrzyj [Kody etapów grupy czynności](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="fef99-155">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="fef99-156">Tworzenie układu etykiety grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-156">Create a wave label layout</span></span>

<span data-ttu-id="fef99-157">Układ etykiety decyduje o tym, jakie informacje są drukowane na etykiecie i w jaki sposób. W tym miejscu należy wprowadzić kod ZPL, który zostanie wysłany do drukarki.</span><span class="sxs-lookup"><span data-stu-id="fef99-157">The label layout controls what information is printed on the label and how it's laid out. Here, you enter the ZPL code that is sent to the printer.</span></span>

1. <span data-ttu-id="fef99-158">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Układy etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-158">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="fef99-159">Dodaj rekord z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-159">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="fef99-160">**Identyfikator układu etykiety:** *Karton*</span><span class="sxs-lookup"><span data-stu-id="fef99-160">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="fef99-161">**Opis:** *Karton (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="fef99-161">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="fef99-162">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fef99-162">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fef99-163">W okienku akcji wybierz opcję **Ustawienia wiersza etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-163">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="fef99-164">Zostanie wyświetlona strona **Ustawienia wiersza etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-164">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="fef99-165">W tym miejscu można skonfigurować dynamiczną część etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-165">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="fef99-166">Dodaj wiersz z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-166">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-167">**Identyfikator wiersza:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="fef99-167">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="fef99-168">**Nazwa tabeli wierszy:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="fef99-168">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="fef99-169">**Pozycja początkowa wiersza:** *0*</span><span class="sxs-lookup"><span data-stu-id="fef99-169">**Row start position:** *0*</span></span>

        <span data-ttu-id="fef99-170">To pole określa pozycję w pionie, w której wiersz będzie zaczynał się na etykiecie.</span><span class="sxs-lookup"><span data-stu-id="fef99-170">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="fef99-171">**Wysokość wiersza:** *0*</span><span class="sxs-lookup"><span data-stu-id="fef99-171">**Row height:** *0*</span></span>

        <span data-ttu-id="fef99-172">To pole definiuje wysokość każdego wiersza (w punktach) zgodnie ze standardem ZPL.</span><span class="sxs-lookup"><span data-stu-id="fef99-172">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="fef99-173">Wysokość wiersza jest dodatnia dla etykiet poziomych i wartości ujemnych dla etykiet pionowych.</span><span class="sxs-lookup"><span data-stu-id="fef99-173">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="fef99-174">Ponieważ w tym przykładzie występuje tylko jeden wiersz, można nadać mu wartość *0* (zero).</span><span class="sxs-lookup"><span data-stu-id="fef99-174">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="fef99-175">**Liczba wierszy na stronę:** *1*</span><span class="sxs-lookup"><span data-stu-id="fef99-175">**Rows per page:** *1*</span></span>

        <span data-ttu-id="fef99-176">To pole definiuje liczbę wierszy, które mogą być drukowane na każdej etykiecie.</span><span class="sxs-lookup"><span data-stu-id="fef99-176">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="fef99-177">Ta konfiguracja spowoduje wydrukowanie osobnej etykiety ZPL dla każdego rekordu w tabeli etykiety grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-177">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="fef99-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="fef99-178">Close the page.</span></span>
1. <span data-ttu-id="fef99-179">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="fef99-179">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="fef99-180">W oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-180">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-181">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-181">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-182">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-182">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-183">**Pole:** *Typ pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-183">**Field:** *Work type*</span></span>
    - <span data-ttu-id="fef99-184">**Kryteria:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="fef99-184">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="fef99-185">To zapytanie zapewnia, że na etykiecie będą drukowane tylko wiersze pracy typu pobranie, a nie typy wierszy pracy.</span><span class="sxs-lookup"><span data-stu-id="fef99-185">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="fef99-186">Jeśli chcesz mieć możliwość drukowania identyfikatora list przewozowy, na karcie **Sprzężenia** wybierz tabelę **Wiersze pracy** i przyłącz się do tabeli **Wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="fef99-186">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="fef99-187">Zamknij okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-187">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="fef99-188">Skrócona karta **Układ tekstu drukarki** zawiera trzy sekcje, w których można wpisać kod drukarki: **Sekcja nagłówka**, **Sekcja treści** i **Sekcja stopki**.</span><span class="sxs-lookup"><span data-stu-id="fef99-188">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="fef99-189">W **Sekcji nagłówka**, w polu **Nagłówek etykiety** wprowadź kod dla wymaganego nagłówka.</span><span class="sxs-lookup"><span data-stu-id="fef99-189">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="fef99-190">Jeśli na przykład używane są drukarki Zebra, można użyć poniższego kodu.</span><span class="sxs-lookup"><span data-stu-id="fef99-190">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="fef99-191">W **Sekcji treści**, w polu **Treść etykiety** wprowadź kod ZPL dla wymaganej treści.</span><span class="sxs-lookup"><span data-stu-id="fef99-191">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="fef99-192">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="fef99-192">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="fef99-193">W **Sekcji treści**, w polu **Stopka etykiety** wprowadź kod ZPL dla wymaganej stopki.</span><span class="sxs-lookup"><span data-stu-id="fef99-193">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="fef99-194">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="fef99-194">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="fef99-195">Ta instalacja spowoduje wydrukowanie jednej kopii każdej etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-195">This setup will print one copy of each label.</span></span> <span data-ttu-id="fef99-196">Jeśli wymagane jest więcej kopii (na przykład jedna kopia dla każdej strony palety), należy określić wartość **n** dla sekcji **\^PQn** w stopce w wymaganej liczbie kopii.</span><span class="sxs-lookup"><span data-stu-id="fef99-196">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="fef99-197">Na przykład, aby wydrukować cztery kopie każdej etykiety, należy określić **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="fef99-197">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="fef99-198">Twoja etykieta jest teraz gotowa do użycia.</span><span class="sxs-lookup"><span data-stu-id="fef99-198">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-type"></a><span data-ttu-id="fef99-199">Tworzenie typu etykiety grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-199">Create a wave label type</span></span>

<span data-ttu-id="fef99-200">Typy etykiet grupy czynności służą do łączenia szablonów etykietek grupy czynności z jednostkami w wierszach grup sekwencji jednostek.</span><span class="sxs-lookup"><span data-stu-id="fef99-200">Wave label types are used to link wave label templates to a unit on unit sequence group lines.</span></span>

1. <span data-ttu-id="fef99-201">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Typy etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-201">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="fef99-202">Dodaj typ etykiety grupy zynności z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-202">Add a wave label type that has the following settings:</span></span>

    - <span data-ttu-id="fef99-203">**Typ etykiety:** *Karton*</span><span class="sxs-lookup"><span data-stu-id="fef99-203">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="fef99-204">**Opis:** *Karton*</span><span class="sxs-lookup"><span data-stu-id="fef99-204">**Description:** *Carton*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="fef99-205">Ustaw grupy sekwencji jednostek</span><span class="sxs-lookup"><span data-stu-id="fef99-205">Set up unit sequence groups</span></span>

<span data-ttu-id="fef99-206">Następnie skonfiguruj grupę sekwencji jednostek dla typu etykiety grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-206">Next, set up the unit sequence group for the wave label type.</span></span>

1. <span data-ttu-id="fef99-207">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Grupy sekwencji jednostek**.</span><span class="sxs-lookup"><span data-stu-id="fef99-207">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="fef99-208">Wybierz grupę **Każde Pudełko PL**.</span><span class="sxs-lookup"><span data-stu-id="fef99-208">Select the **Ea Box PL** group.</span></span>
1. <span data-ttu-id="fef99-209">W przypadku wiersza **Pudełko** należy określić wartość w polu **Typ poziomu grupy czynności** na *Karton*.</span><span class="sxs-lookup"><span data-stu-id="fef99-209">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="fef99-210">Tworzenie szablonu etykiety grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-210">Create a wave label template</span></span>

<span data-ttu-id="fef99-211">Następnie utwórz szablon etykiety grupy czynności dla typu etykiety grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-211">Next, create the wave label template for the wave label type.</span></span>

1. <span data-ttu-id="fef99-212">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Szablony etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-212">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="fef99-213">Dodaj szablon poziomu grupy czynności i określ następujące wartości w nagłówku:</span><span class="sxs-lookup"><span data-stu-id="fef99-213">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="fef99-214">**Nazwa szablonu etykiety:** *Etykiety kartonu*</span><span class="sxs-lookup"><span data-stu-id="fef99-214">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="fef99-215">**Opis:** *Etykiety kartonu*</span><span class="sxs-lookup"><span data-stu-id="fef99-215">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="fef99-216">**Kod kroku grupy czynności:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="fef99-216">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="fef99-217">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="fef99-217">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="fef99-218">Na skróconej karcie **Ogólne** należy określić wartość w polu **Typ etykiety grupy czynności** na *Karton*.</span><span class="sxs-lookup"><span data-stu-id="fef99-218">On the **General** FastTab, set the **Wave label type** field to *Carton*.</span></span>
1. <span data-ttu-id="fef99-219">Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** dodaj nowy wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-219">On the **Wave label template details** FastTab, add a new row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-220">**Identyfikator układu etykiety:** *Karton*</span><span class="sxs-lookup"><span data-stu-id="fef99-220">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="fef99-221">**Nazwa drukarki:** Wybierz odpowiednią drukarkę ZPL.</span><span class="sxs-lookup"><span data-stu-id="fef99-221">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="fef99-222">**Uruchom kwerendę:** *Tak* (To ustawienie jest opcjonalne, ale jest zalecane w przypadku optymalnej wydajności.)</span><span class="sxs-lookup"><span data-stu-id="fef99-222">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="fef99-223">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fef99-223">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fef99-224">Opcjonalnie: Jeśli konfigurujesz projekt etykiety właściwy dla odbiorcy, musisz utworzyć kwerendę, aby znaleźć konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fef99-224">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="fef99-225">Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** wybierz opcję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="fef99-225">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="fef99-226">Następnie w oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-226">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-227">**Tabela:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="fef99-227">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="fef99-228">**Tabela pochodna:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="fef99-228">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="fef99-229">**Pole:** *Numer konta*</span><span class="sxs-lookup"><span data-stu-id="fef99-229">**Field:** *Account number*</span></span>
    - <span data-ttu-id="fef99-230">**Kryteria**: Należy wprowadzić odpowiedni numer konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fef99-230">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="fef99-231">Po zakończeniu kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-231">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="fef99-232">W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edytora zapytań dla całego szablonu etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-232">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="fef99-233">W oknie dialogowym edytora zapytań na karcie **Sortowanie** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-233">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-234">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-234">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-235">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-235">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-236">**Pole:** *Odwołanie do identyfikatora wiersza ładunku (identyfikator rekordu)*</span><span class="sxs-lookup"><span data-stu-id="fef99-236">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="fef99-237">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="fef99-237">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="fef99-238">Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-238">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="fef99-239">Zostanie wyświetlone okno komunikatu z monitem o potwierdzenie operacji resetowania grup.</span><span class="sxs-lookup"><span data-stu-id="fef99-239">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="fef99-240">Wybierz przycisk **Tak**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="fef99-240">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="fef99-241">W okienku akcji wybierz opcję **Grupa szablonu etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-241">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="fef99-242">W oknie dialogowym **Grupa szablonów etykiety grupy czynności** wybierz wiersz, w którym pole **Nazwa pola odwołania** ma wartość *Odwołanie do identyfikatora wiersza ładunku*, a następnie zaznacz pole wyboru **Identyfikator kompilacji etykiety** dla tego wiersza.</span><span class="sxs-lookup"><span data-stu-id="fef99-242">In the **Wave label template group** dialog box, select the row where the **Reference field name** field is set to *Reference load line id*, and then select the **Label build ID** check box for this row.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fef99-243">Ten Instalator utworzy jedną sekwencję etykiet („Karton 1 z X”) dla każdego wiersza ładunku w rzucie, niezależnie od konfiguracji grupowania pracy.</span><span class="sxs-lookup"><span data-stu-id="fef99-243">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="fef99-244">Tę sekwencję etykiet można wydrukować w układzie etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-244">This label sequence can be printed on the label layout.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="fef99-245">Konfigurowanie sekwencji identyfikatorów</span><span class="sxs-lookup"><span data-stu-id="fef99-245">Configure number sequence extensions</span></span>

<span data-ttu-id="fef99-246">Rozszerzenia sekwencji identyfikatorów kontrolują zgodność GS1 z określonymi sekwencjami identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="fef99-246">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="fef99-247">Ta konfiguracja jest opcjonalna dla bieżącego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="fef99-247">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="fef99-248">Aby uzyskać więcej informacji i instrukcji konfiguracyjnych, zobacz [Konfigurowanie rozszerzeń sekwencji identyfikatorów](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="fef99-248">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="fef99-249">Utwórz zamówienie sprzedaży i zwolnij je do magazynu</span><span class="sxs-lookup"><span data-stu-id="fef99-249">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="fef99-250">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienie sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="fef99-250">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="fef99-251">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-251">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="fef99-252">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="fef99-252">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="fef99-253">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="fef99-253">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="fef99-254">Dodaj dwa wiersze zamówienia sprzedaży o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-254">Add two sales order lines that have the following settings:</span></span>

    - <span data-ttu-id="fef99-255">Wiersz zamówienia sprzedaży 1:</span><span class="sxs-lookup"><span data-stu-id="fef99-255">Sales order line 1:</span></span>

        - <span data-ttu-id="fef99-256">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="fef99-256">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="fef99-257">**Ilość:** *9024*</span><span class="sxs-lookup"><span data-stu-id="fef99-257">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="fef99-258">**Jednostka:** *Każdy* (9024 Każdy = 376 Pudełko = 47 Paleta)</span><span class="sxs-lookup"><span data-stu-id="fef99-258">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="fef99-259">Wiersz zamówienia sprzedaży 2:</span><span class="sxs-lookup"><span data-stu-id="fef99-259">Sales order line 2:</span></span>

        - <span data-ttu-id="fef99-260">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="fef99-260">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="fef99-261">**Ilość:** *9016*</span><span class="sxs-lookup"><span data-stu-id="fef99-261">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="fef99-262">**Jednostka:** *Każdy* (9016 Każdy = 322 Pudełko = 46 Paleta)</span><span class="sxs-lookup"><span data-stu-id="fef99-262">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="fef99-263">Podane tu towary i ilości są tylko przykładami.</span><span class="sxs-lookup"><span data-stu-id="fef99-263">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="fef99-264">Muszą one mieć zdefiniowaną wcześniej zdefiniowaną jednostkę, dlatego dla nich musi zostać zdefiniowana odpowiednia konwersja jednostek z *Każdy* na *Pudełko* na *Paleta* oraz musi mieć zapas w magazynie *62*.</span><span class="sxs-lookup"><span data-stu-id="fef99-264">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="fef99-265">Aby uzyskać więcej informacji, zajrzyj do [Jednostka miary i zasady składowania](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fef99-265">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="fef99-266">Wybierz wiersz zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="fef99-266">Select sales order line 1.</span></span> <span data-ttu-id="fef99-267">W sekcji **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacje**.</span><span class="sxs-lookup"><span data-stu-id="fef99-267">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="fef99-268">Na stronie **Rezerwacje** w okienku akcji wybierz **Rezerwacja partii** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="fef99-268">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="fef99-269">Powtórz kroki 4 i 5 dla wiersza zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="fef99-269">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="fef99-270">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="fef99-270">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="fef99-271">Występują wówczas następujące zdarzenia:</span><span class="sxs-lookup"><span data-stu-id="fef99-271">The following events occur:</span></span>

    - <span data-ttu-id="fef99-272">System przetwarza utworzoną wysyłkę za pomocą szablonu, który zawiera krok drukowania etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-272">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="fef99-273">Układ etykiety zostanie użyty do zdefiniowania formatu etykiety, a jego wynikiem będzie etykieta drukowana na drukarce wybranej w szablonie etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-273">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="fef99-274">Etykiety grupy czynności są generowane i drukowane.</span><span class="sxs-lookup"><span data-stu-id="fef99-274">Wave labels are generated and printed.</span></span> <span data-ttu-id="fef99-275">Liczba etykiet będzie równa liczbie kartonów (w tym przykładzie 376 etykiet pudełek dla linii 1 i 322 etykiet pudełek dla linii 2).</span><span class="sxs-lookup"><span data-stu-id="fef99-275">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1 and 322 Box labels for line 2).</span></span>
    - <span data-ttu-id="fef99-276">Nowy identyfikator list przewozowy jest generowany dla wysyłek.</span><span class="sxs-lookup"><span data-stu-id="fef99-276">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="fef99-277">Jeśli skonfigurowano rozszerzenia sekwencji identyfikatorów, identyfikatory etykiet grupy czynności są zgodne z formatem numerów **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="fef99-277">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="fef99-278">Etykiety grupy czynności można przeglądać i ponownie drukować z następujących stron.</span><span class="sxs-lookup"><span data-stu-id="fef99-278">You can view and reprint wave labels from the following pages.</span></span> <span data-ttu-id="fef99-279">W okienku akcji na każdej stronie na karcie **Wysyłki**, w grupie **Informacje pokrewne** wybierz **Etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-279">On the Action Pane of each page, on the **Shipments** tab, in the **Related information** group, select **Wave labels**.</span></span>

- <span data-ttu-id="fef99-280">Wszystkie wysyłki \> Szczegóły wysyłki</span><span class="sxs-lookup"><span data-stu-id="fef99-280">All shipments \> Shipment details</span></span>
- <span data-ttu-id="fef99-281">Wszystkie ładunki \> Szczegóły ładunku</span><span class="sxs-lookup"><span data-stu-id="fef99-281">All loads \> Load details</span></span>
- <span data-ttu-id="fef99-282">Wszystkie grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-282">All waves</span></span>
- <span data-ttu-id="fef99-283">Etykiety grup czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-283">Wave labels</span></span>
- <span data-ttu-id="fef99-284">Historia etykiet grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-284">Wave label history</span></span>

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a><span data-ttu-id="fef99-285">Scenariusz 2: Drukowanie etykiety grupy czynności do konteneryzacji (bez rekordów etykiet grupy czynności)</span><span class="sxs-lookup"><span data-stu-id="fef99-285">Scenario 2: Wave label printing for containerization (without wave label records)</span></span>

<span data-ttu-id="fef99-286">Ten scenariusz umożliwia drukowanie etykiet grup czynności w przypadku używania konteneryzacji do automatycznego dzielenia towarów na kartony i dlatego nie wymagają rekordu etykiety grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-286">This scenario lets you print wave labels when you use containerization to automatically split items into cartons and therefore don't require a wave label record.</span></span> <span data-ttu-id="fef99-287">W tym przypadku identyfikator kontenera pełni rolę symbolu zastępczego dla SSCC.</span><span class="sxs-lookup"><span data-stu-id="fef99-287">In this case, the container ID acts as a placeholder for the SSCC.</span></span>

<span data-ttu-id="fef99-288">Oto główne różnice między tym scenariuszem a scenariuszem 1:</span><span class="sxs-lookup"><span data-stu-id="fef99-288">Here are the main differences between this scenario and scenario 1:</span></span>

- <span data-ttu-id="fef99-289">**Szablony etykiet grupy czynności:** Nie będzie można wybrać typu etykiety grupy czynności w szablonie etykiety grupy czynności i nie będzie wymagane grupowanie kompilacji etykiet.</span><span class="sxs-lookup"><span data-stu-id="fef99-289">**Wave label templates:** You won't select a wave label type on the wave label template, and you won't require a label build grouping.</span></span> <span data-ttu-id="fef99-290">W przeciwnym razie zostanie skonfigurowany szablon etykiety grupy czynności i łącze do szablonu grupy czynności w taki sam sposób, jak opisano w scenariuszu 1.</span><span class="sxs-lookup"><span data-stu-id="fef99-290">Otherwise, you will configure the wave label template and link to the wave template in the same way that is described in scenario 1.</span></span> <span data-ttu-id="fef99-291">Aby nie można było wygenerować etykiet grupy czynności, należy pozostawić pustą etykietę grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-291">You must leave the wave label type blank to prevent wave labels from being generated.</span></span>
- <span data-ttu-id="fef99-292">**Układy etykiet grupy czynności:** Skonfiguruj ustawienia wiersza układu etykiety grupy czynności dla wierszy pracy zamiast rekordów etykiet.</span><span class="sxs-lookup"><span data-stu-id="fef99-292">**Wave label layouts:** You will configure the wave label layout row settings for work lines instead of wave label records.</span></span> <span data-ttu-id="fef99-293">Należy skonfigurować ustawienie wiersza dla układu etykiety, używając tabeli **WHSWorkLine** zamiast tabeli **WHSWaveLabel**.</span><span class="sxs-lookup"><span data-stu-id="fef99-293">You must configure the row setting for the label layout by using the **WHSWorkLine** table instead of the **WHSWaveLabel** table.</span></span> <span data-ttu-id="fef99-294">Ustawienie **Wiersze na stronę** określa liczbę wierszy, jaką będzie miała sekcja treści.</span><span class="sxs-lookup"><span data-stu-id="fef99-294">The **Rows per page** setting controls the number of rows that the body section will have.</span></span> 

<span data-ttu-id="fef99-295">Ta konfiguracja jest również odpowiednia dla scenariuszy biznesowych, w których wiele różnych elementów jest pakowanych w jedno oznaczone pudełko lub na paletę, a ten proces pakowania można zdefiniować przez tworzenie pracy (na przykład praca grupowana według wysyłki).</span><span class="sxs-lookup"><span data-stu-id="fef99-295">This configuration is also suitable for business scenarios where multiple different items are packed into one labeled box or into a pallet, and this packing process can be defined by work creation (for example, work that is grouped by shipment).</span></span>

<span data-ttu-id="fef99-296">Ten scenariusz pokazuje przepływ końcowy na koniec.</span><span class="sxs-lookup"><span data-stu-id="fef99-296">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="fef99-297">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="fef99-297">Make demo data available</span></span>

<span data-ttu-id="fef99-298">W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być wybrana firma **USMF**.</span><span class="sxs-lookup"><span data-stu-id="fef99-298">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="fef99-299">Upewnij się, że metoda etykiet grupy czynności jest dostępna</span><span class="sxs-lookup"><span data-stu-id="fef99-299">Make sure that the wave label method is available</span></span>

<span data-ttu-id="fef99-300">Może być konieczne ponowne wygenerowanie metod przetwarzania grupy czynności, aby można było udostępnić metodę drukowania etykiet grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-300">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="fef99-301">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-301">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="fef99-302">Potwierdź, że **waveLabelPrinting** jest na liście.</span><span class="sxs-lookup"><span data-stu-id="fef99-302">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="fef99-303">Jeśli nie, wybierz polecenie **Wygeneruj ponownie metody** w okienku akcji, aby dodać metodę.</span><span class="sxs-lookup"><span data-stu-id="fef99-303">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="fef99-304">Konfigurowanie szablonu grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-304">Set up a wave template</span></span>

<span data-ttu-id="fef99-305">Szablony grupy czynności umożliwiają łączenie konkretnych instancji metod grupy czynności z odpowiednim szablonem etykiety grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-305">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="fef99-306">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-306">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="fef99-307">Wybierz szablon grupy czynności, na przykład **Konteneryzacja 63**.</span><span class="sxs-lookup"><span data-stu-id="fef99-307">Select a template, such as **63 Containerization**.</span></span>
1. <span data-ttu-id="fef99-308">Na skróconej karcie **Metody** należy przenieść metodę **Drukowania etykiet grupy czynności** do kolumny **Wybrane metody**.</span><span class="sxs-lookup"><span data-stu-id="fef99-308">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="fef99-309">W kolumnie **Wybrane metody** wybierz metodę **Drukowania etykiet grupy czynności** i określ w polu **Kod kroku grupy czynności** wartość *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="fef99-309">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="fef99-310">Aby uzyskać więcej informacji o kodach kroku grupy czynności, przejrzyj [Kody etapów grupy czynności](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="fef99-310">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="fef99-311">Tworzenie układu etykiety grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-311">Create a wave label layout</span></span>

1. <span data-ttu-id="fef99-312">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Układy etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-312">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="fef99-313">Dodaj rekord z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-313">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="fef99-314">**Identyfikator układu etykiety:** *Karton*</span><span class="sxs-lookup"><span data-stu-id="fef99-314">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="fef99-315">**Opis:** *Karton (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="fef99-315">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="fef99-316">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fef99-316">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fef99-317">W okienku akcji wybierz opcję **Ustawienia wiersza etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-317">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="fef99-318">Zostanie wyświetlona strona **Ustawienia wiersza etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-318">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="fef99-319">W tym miejscu można skonfigurować dynamiczną część etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-319">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="fef99-320">Dodaj wiersz z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-320">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-321">**Identyfikator wiersza:** *WorkLine*</span><span class="sxs-lookup"><span data-stu-id="fef99-321">**Row Id:** *WorkLine*</span></span>
    - <span data-ttu-id="fef99-322">**Nazwa tabeli wierszy:** *WHSWorkLine*</span><span class="sxs-lookup"><span data-stu-id="fef99-322">**Row table name:** *WHSWorkLine*</span></span>
    - <span data-ttu-id="fef99-323">**Pozycja początkowa wiersza:** *500*</span><span class="sxs-lookup"><span data-stu-id="fef99-323">**Row start position:** *500*</span></span>

        <span data-ttu-id="fef99-324">To pole określa pozycję w pionie, w której wiersz będzie zaczynał się na etykiecie.</span><span class="sxs-lookup"><span data-stu-id="fef99-324">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="fef99-325">**Wysokość wiersza:** *-50*</span><span class="sxs-lookup"><span data-stu-id="fef99-325">**Row height:** *-50*</span></span>

        <span data-ttu-id="fef99-326">To pole definiuje wysokość każdego wiersza.</span><span class="sxs-lookup"><span data-stu-id="fef99-326">This field defines the height of each row.</span></span> <span data-ttu-id="fef99-327">Wysokość wiersza jest dodatnia dla etykiet poziomych i wartości ujemnych dla etykiet pionowych.</span><span class="sxs-lookup"><span data-stu-id="fef99-327">The row height is positive for horizontal labels and negative for vertical labels.</span></span>

    - <span data-ttu-id="fef99-328">**Liczba wierszy na stronę:** *5*</span><span class="sxs-lookup"><span data-stu-id="fef99-328">**Rows per page:** *5*</span></span>

        <span data-ttu-id="fef99-329">To pole definiuje liczbę wierszy, które mogą być drukowane na każdej etykiecie.</span><span class="sxs-lookup"><span data-stu-id="fef99-329">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="fef99-330">Ta konfiguracja będzie drukowała kilka etykiet ZPL dla pracy, gdzie każda strona może zawierać do pięciu wierszy pracy.</span><span class="sxs-lookup"><span data-stu-id="fef99-330">This setup will print several ZPL labels per work, where each page can hold up to five work lines.</span></span> <span data-ttu-id="fef99-331">Jeśli na przykład zostanie wydrukowana etykieta dla kontenera, który ma 12 wierszy, drukowane będą trzy etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-331">For example, if a label is printed for a container that has 12 lines, three labels will be printed.</span></span> <span data-ttu-id="fef99-332">Aby wydrukować oddzielną etykietę dla każdego wiersza pobrania, należy nadać tej wartości wartość *1*.</span><span class="sxs-lookup"><span data-stu-id="fef99-332">If you want to print a separate label for each pick line, set this value to *1*.</span></span>

1. <span data-ttu-id="fef99-333">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="fef99-333">Close the page.</span></span>
1. <span data-ttu-id="fef99-334">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="fef99-334">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="fef99-335">W oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-335">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-336">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-336">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-337">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-337">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-338">**Pole:** *Typ pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-338">**Field:** *Work type*</span></span>
    - <span data-ttu-id="fef99-339">**Kryteria:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="fef99-339">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="fef99-340">Jeśli chcesz mieć możliwość drukowania identyfikatora list przewozowy, na karcie **Sprzężenia** wybierz tabelę **Wiersze pracy** i przyłącz się do tabeli **Wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="fef99-340">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="fef99-341">Zamknij okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-341">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="fef99-342">Skrócona karta **Układ tekstu drukarki** zawiera trzy sekcje, w których można wpisać kod drukarki: **Sekcja nagłówka**, **Sekcja treści** i **Sekcja stopki**.</span><span class="sxs-lookup"><span data-stu-id="fef99-342">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="fef99-343">W **Sekcji nagłówka**, w polu **Nagłówek etykiety** wprowadź kod dla wymaganego nagłówka.</span><span class="sxs-lookup"><span data-stu-id="fef99-343">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="fef99-344">Jeśli na przykład używane są drukarki Zebra, można użyć poniższego kodu.</span><span class="sxs-lookup"><span data-stu-id="fef99-344">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="fef99-345">W **Sekcji treści**, w polu **Treść etykiety** wprowadź kod ZPL dla wymaganej treści.</span><span class="sxs-lookup"><span data-stu-id="fef99-345">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="fef99-346">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="fef99-346">Here is an example.</span></span>

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="fef99-347">W **Sekcji treści**, w polu **Stopka etykiety** wprowadź kod ZPL dla wymaganej stopki.</span><span class="sxs-lookup"><span data-stu-id="fef99-347">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="fef99-348">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="fef99-348">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="fef99-349">Ta instalacja spowoduje wydrukowanie jednej kopii każdej etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-349">This setup will print one copy of each label.</span></span> <span data-ttu-id="fef99-350">Jeśli wymagane jest więcej kopii (na przykład jedna kopia dla każdej strony palety), należy określić wartość **n** dla sekcji **\^PQn** w stopce w wymaganej liczbie kopii.</span><span class="sxs-lookup"><span data-stu-id="fef99-350">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="fef99-351">Na przykład, aby wydrukować cztery kopie każdej etykiety, należy określić **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="fef99-351">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="fef99-352">Twoja etykieta jest teraz gotowa do użycia.</span><span class="sxs-lookup"><span data-stu-id="fef99-352">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="fef99-353">Tworzenie szablonu etykiety grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-353">Create a wave label template</span></span>

1. <span data-ttu-id="fef99-354">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Szablony etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-354">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="fef99-355">Dodaj szablon poziomu grupy czynności i określ następujące wartości w nagłówku:</span><span class="sxs-lookup"><span data-stu-id="fef99-355">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="fef99-356">**Nazwa szablonu etykiety:** *Etykiety kontenera*</span><span class="sxs-lookup"><span data-stu-id="fef99-356">**Label template name:** *Container labels*</span></span>
    - <span data-ttu-id="fef99-357">**Opis:** *Etykiety kontenerów*</span><span class="sxs-lookup"><span data-stu-id="fef99-357">**Description:** *Container labels*</span></span>
    - <span data-ttu-id="fef99-358">**Kod kroku grupy czynności:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="fef99-358">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="fef99-359">**Magazyn:** *63*</span><span class="sxs-lookup"><span data-stu-id="fef99-359">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="fef99-360">Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-360">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-361">**Identyfikator układu etykiety:** *Kontener*</span><span class="sxs-lookup"><span data-stu-id="fef99-361">**Label layout ID:** *Container*</span></span>
    - <span data-ttu-id="fef99-362">**Nazwa drukarki:** Wybierz odpowiednią drukarkę ZPL.</span><span class="sxs-lookup"><span data-stu-id="fef99-362">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="fef99-363">**Uruchom kwerendę:** *Tak* (To ustawienie jest opcjonalne, ale jest zalecane w przypadku optymalnej wydajności.)</span><span class="sxs-lookup"><span data-stu-id="fef99-363">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="fef99-364">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fef99-364">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fef99-365">Opcjonalnie: Jeśli konfigurujesz projekt etykiety właściwy dla odbiorcy, musisz utworzyć kwerendę, aby znaleźć konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fef99-365">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="fef99-366">Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** wybierz opcję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="fef99-366">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="fef99-367">Następnie w oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-367">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-368">**Tabela:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="fef99-368">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="fef99-369">**Tabela pochodna:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="fef99-369">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="fef99-370">**Pole:** *Numer konta*</span><span class="sxs-lookup"><span data-stu-id="fef99-370">**Field:** *Account number*</span></span>
    - <span data-ttu-id="fef99-371">**Kryteria**: Należy wprowadzić odpowiedni numer konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fef99-371">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="fef99-372">Po zakończeniu kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-372">When you've finished, select **OK** to close the query editor dialog box.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="fef99-373">Konfigurowanie sekwencji identyfikatorów</span><span class="sxs-lookup"><span data-stu-id="fef99-373">Configure number sequence extensions</span></span>

<span data-ttu-id="fef99-374">Rozszerzenia sekwencji identyfikatorów kontrolują zgodność GS1 z określonymi sekwencjami identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="fef99-374">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="fef99-375">Ta konfiguracja jest opcjonalna dla bieżącego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="fef99-375">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="fef99-376">Aby uzyskać więcej informacji i instrukcji konfiguracyjnych, zobacz [Konfigurowanie rozszerzeń sekwencji identyfikatorów](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="fef99-376">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="fef99-377">Utwórz zamówienie sprzedaży i zwolnij je do magazynu</span><span class="sxs-lookup"><span data-stu-id="fef99-377">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="fef99-378">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienie sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="fef99-378">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="fef99-379">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-379">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="fef99-380">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="fef99-380">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="fef99-381">**Magazyn:** *63*</span><span class="sxs-lookup"><span data-stu-id="fef99-381">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="fef99-382">Dodaj pięć wierszy zamówienia sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="fef99-382">Add five sales order lines:</span></span>

    - <span data-ttu-id="fef99-383">Wiersz zamówienia sprzedaży 1:</span><span class="sxs-lookup"><span data-stu-id="fef99-383">Sales order line 1:</span></span>

        - <span data-ttu-id="fef99-384">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="fef99-384">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="fef99-385">**Ilość:** *10*</span><span class="sxs-lookup"><span data-stu-id="fef99-385">**Quantity:** *10*</span></span>

    - <span data-ttu-id="fef99-386">Wiersz zamówienia sprzedaży 2:</span><span class="sxs-lookup"><span data-stu-id="fef99-386">Sales order line 2:</span></span>

        - <span data-ttu-id="fef99-387">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="fef99-387">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="fef99-388">**Ilość:** *20*</span><span class="sxs-lookup"><span data-stu-id="fef99-388">**Quantity:** *20*</span></span>

    - <span data-ttu-id="fef99-389">Wiersz zamówienia sprzedaży 3:</span><span class="sxs-lookup"><span data-stu-id="fef99-389">Sales order line 3:</span></span>

        - <span data-ttu-id="fef99-390">**Numer pozycji:** *L0006*</span><span class="sxs-lookup"><span data-stu-id="fef99-390">**Item number:** *L0006*</span></span>
        - <span data-ttu-id="fef99-391">**Ilość:** *20*</span><span class="sxs-lookup"><span data-stu-id="fef99-391">**Quantity:** *20*</span></span>

    - <span data-ttu-id="fef99-392">Wiersz zamówienia sprzedaży 4:</span><span class="sxs-lookup"><span data-stu-id="fef99-392">Sales order line 4:</span></span>

        - <span data-ttu-id="fef99-393">**Numer pozycji:** *L0100*</span><span class="sxs-lookup"><span data-stu-id="fef99-393">**Item number:** *L0100*</span></span>
        - <span data-ttu-id="fef99-394">**Ilość:** *40*</span><span class="sxs-lookup"><span data-stu-id="fef99-394">**Quantity:** *40*</span></span>

    - <span data-ttu-id="fef99-395">Wiersz zamówienia sprzedaży 5:</span><span class="sxs-lookup"><span data-stu-id="fef99-395">Sales order line 5:</span></span>

        - <span data-ttu-id="fef99-396">**Numer pozycji:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="fef99-396">**Item number:** *L0101*</span></span>
        - <span data-ttu-id="fef99-397">**Ilość:** *50*</span><span class="sxs-lookup"><span data-stu-id="fef99-397">**Quantity:** *50*</span></span>

    > [!NOTE]
    > <span data-ttu-id="fef99-398">Podane tu towary i ilości są tylko przykładami.</span><span class="sxs-lookup"><span data-stu-id="fef99-398">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="fef99-399">Muszą mieć zapasy w określonym magazynie.</span><span class="sxs-lookup"><span data-stu-id="fef99-399">They must have stock in the specified warehouse.</span></span>

1. <span data-ttu-id="fef99-400">Wybierz wiersz zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="fef99-400">Select sales order line 1.</span></span> <span data-ttu-id="fef99-401">W sekcji **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacje**.</span><span class="sxs-lookup"><span data-stu-id="fef99-401">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="fef99-402">Na stronie **Rezerwacje** w okienku akcji wybierz **Rezerwacja partii** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="fef99-402">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="fef99-403">Powtórz kroki 4 i 5 dla każdego dodatkowego wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="fef99-403">Repeat steps 4 and 5 for each additional sales order line.</span></span>
1. <span data-ttu-id="fef99-404">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="fef99-404">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="fef99-405">Występują wówczas następujące zdarzenia:</span><span class="sxs-lookup"><span data-stu-id="fef99-405">The following events occur:</span></span>

    - <span data-ttu-id="fef99-406">System przetwarza utworzoną wysyłkę za pomocą szablonu, który zawiera krok drukowania etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-406">The system processes the created shipment using the template that includes the label printing step.</span></span> <span data-ttu-id="fef99-407">Układ etykiety zostanie użyty do zdefiniowania formatu etykiety, a jego wynikiem końcowym będzie etykieta z pięcioma wierszami drukowana na drukarce wybranej w szablonie etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-407">The label layout will be used to define the format of the label, and the end result will be a label that has five lines and that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="fef99-408">Nowy identyfikator list przewozowy jest generowany dla wysyłek.</span><span class="sxs-lookup"><span data-stu-id="fef99-408">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="fef99-409">Jeśli skonfigurowano rozszerzenia sekwencji identyfikatorów, identyfikatory etykiet grupy czynności są zgodne z formatem numerów **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="fef99-409">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="fef99-410">Etykiety te można ponownie wydrukować, przechodząc do **Zarządzanie magazynem \> Zapytania i raporty \> Historia etykiet grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-410">You can reprint these wave labels by going to **Warehouse management \> Inquiries and reports \> Wave label history**.</span></span>

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a><span data-ttu-id="fef99-411">Scenariusz 3: Drukowanie etykiety grupy czynności w przypadku etykiet wielowarstwowych</span><span class="sxs-lookup"><span data-stu-id="fef99-411">Scenario 3: Wave label printing for multi-tiered labels</span></span>

<span data-ttu-id="fef99-412">W tym scenariuszu przedstawiono sposób korzystania z funkcji drukowania etykiet grupy czynności, gdy procesy magazynowania wymagają kilku różnych warstw na etykietach wysyłkowych.</span><span class="sxs-lookup"><span data-stu-id="fef99-412">This scenario shows how to use the wave label printing functionality when the warehousing processes require several tiers of shipping labels.</span></span> <span data-ttu-id="fef99-413">Na przykład może być konieczne wydrukowanie oddzielnych etykiet dla kartonów i palet, a etykieta podziału może być drukowana dla całej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="fef99-413">For example, separate labels might have to be printed for cartons and pallets, and a break label might have to be printed for a whole shipment.</span></span> <span data-ttu-id="fef99-414">Etykiety podziału to osobny typ etykiety, który może być używany jako separator między rolkami i kontenerami, takimi jak etykiety dla identyfikatora wysyłki i kodu kreskowego, dzięki czemu można łatwo posortować etykiety po wydrukowaniu.</span><span class="sxs-lookup"><span data-stu-id="fef99-414">Break labels are a separate type of label that can be used as a divider between rolls and containers, such as labels for the shipment ID and a barcode, so that the labels can easily be sorted after they are printed.</span></span>

<span data-ttu-id="fef99-415">Główna różnica między konfiguracją tego scenariusza a konfiguracją scenariusza 1, oprócz faktu, że etykiety podziału są włączone, to czy wiele typów etykiet grupy czynności musi być skojarzonych z szablonami etykiet i wierszy grup sekwencji jednostek.</span><span class="sxs-lookup"><span data-stu-id="fef99-415">The main difference between the configuration of this scenario and the configuration of scenario 1, besides the fact that break labels are enabled, is that multiple wave label types must be associated with wave label templates and unit sequence group lines.</span></span> <span data-ttu-id="fef99-416">Aby wykonać tę konfigurację, należy skonfigurować następujące elementy w tym scenariuszu:</span><span class="sxs-lookup"><span data-stu-id="fef99-416">To accomplish this configuration, you set up the following elements for this scenario:</span></span>

- <span data-ttu-id="fef99-417">**Metody przetwarzania grupy czynności:** Doszablonu grupy czynności należy oznaczyć metodę etykietowania metodą „powtarzalne” (czyli więcej razy), a następnie określić różne kody etapów.</span><span class="sxs-lookup"><span data-stu-id="fef99-417">**Wave processing methods:** You will mark the wave label method as "repeatable," add it two (or more) times to the wave template, and set different wave step codes.</span></span>
- <span data-ttu-id="fef99-418">**Szablony etykiet grupy czynności:** Konfiguruje się szablony etykiet grupy czynności i łączy je z szablonem grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-418">**Wave label templates:** You will configure the wave label templates and link them to the wave template.</span></span> <span data-ttu-id="fef99-419">Każdy szablon etykiety grupy czynności ma własny typ etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-419">Each wave label template has its own wave label type.</span></span>
- <span data-ttu-id="fef99-420">**Układy etykiet grupy czynności:** Zostaną utworzone różne układy etykiet grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-420">**Wave label layouts:** You will create multiple wave label layouts.</span></span> <span data-ttu-id="fef99-421">Dla każdej „warstwy” etykiet zostanie oddzielny układ etykiety, a także układ etykiety podziału.</span><span class="sxs-lookup"><span data-stu-id="fef99-421">There will be a separate label layout for each "tier" of labels, and there will also be a break label layout.</span></span>

<span data-ttu-id="fef99-422">Ten scenariusz pokazuje przepływ końcowy na koniec.</span><span class="sxs-lookup"><span data-stu-id="fef99-422">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="fef99-423">Udostępnianie danych pokazu</span><span class="sxs-lookup"><span data-stu-id="fef99-423">Make demo data available</span></span>

<span data-ttu-id="fef99-424">W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być wybrana firma **USMF**.</span><span class="sxs-lookup"><span data-stu-id="fef99-424">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-wave-process-method"></a><span data-ttu-id="fef99-425">Konfigurowanie metody przetwarzania grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-425">Set up a wave process method</span></span>

1. <span data-ttu-id="fef99-426">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-426">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="fef99-427">Potwierdź, że **waveLabelPrinting** jest na liście.</span><span class="sxs-lookup"><span data-stu-id="fef99-427">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="fef99-428">Jeśli nie, wybierz polecenie **Wygeneruj ponownie metody** w okienku akcji, aby dodać metodę.</span><span class="sxs-lookup"><span data-stu-id="fef99-428">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>
1. <span data-ttu-id="fef99-429">W przypadku metody **waveLabelPrinting** zaznacz pole wyboru **Spraw, aby metoda była powtarzalna**.</span><span class="sxs-lookup"><span data-stu-id="fef99-429">For the **waveLabelPrinting** method, select the **Make method repeatable** check box.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="fef99-430">Konfigurowanie szablonu grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-430">Set up a wave template</span></span>

1. <span data-ttu-id="fef99-431">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-431">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
2. <span data-ttu-id="fef99-432">Wybierz szablon grupy czynności, na przykład **Domyślna 62-godzinna wysyłka**.</span><span class="sxs-lookup"><span data-stu-id="fef99-432">Select a template, such as **62 Shipping Default**.</span></span>
3. <span data-ttu-id="fef99-433">Na skróconej karcie **Metody** należy przenieść metodę **Drukowania etykiet grupy czynności** do kolumny **Wybrane metody**.</span><span class="sxs-lookup"><span data-stu-id="fef99-433">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
4. <span data-ttu-id="fef99-434">W kolumnie **Wybrane metody** przypisz wartość **Kod kroku grupy czynności**, np. *Karton*, do metody **Drukowanie etykiet grup czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-434">In the **Selected methods** column, assign a **Wave step code** value, such as *Carton*, to the **Wave label printing** method.</span></span> <span data-ttu-id="fef99-435">Aby uzyskać więcej informacji o kodach kroku grupy czynności, przejrzyj [Kody etapów grupy czynności](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="fef99-435">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>
5. <span data-ttu-id="fef99-436">Należy ponownie przenieść metodę **Drukowania etykiet grupy czynności** do kolumny **Wybrane metody**.</span><span class="sxs-lookup"><span data-stu-id="fef99-436">Move the **Wave label printing** method to the **Selected methods** column a second time.</span></span>
6. <span data-ttu-id="fef99-437">W kolumnie **Wybrane metody** przypisz inną wartość **Kod kroku grupy czynności**, np. *Paleta*, do drugiej metody **Drukowanie etykiet grup czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-437">In the **Selected methods** column, assign a different **Wave step code** value, such as *Pallet*, to the second **Wave label printing** method.</span></span> <span data-ttu-id="fef99-438">Aby uzyskać więcej informacji o kodach kroku grupy czynności, przejrzyj [Kody etapów grupy czynności](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="fef99-438">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-three-wave-label-layouts"></a><span data-ttu-id="fef99-439">Tworzenie trzech układów etykiety grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-439">Create three wave label layouts</span></span>

1. <span data-ttu-id="fef99-440">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Układy etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-440">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="fef99-441">Dodaj rekord z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-441">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="fef99-442">**Identyfikator układu etykiety:** *Karton*</span><span class="sxs-lookup"><span data-stu-id="fef99-442">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="fef99-443">**Opis:** *Karton (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="fef99-443">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="fef99-444">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fef99-444">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fef99-445">W okienku akcji wybierz opcję **Ustawienia wiersza etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-445">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="fef99-446">Zostanie wyświetlona strona **Ustawienia wiersza etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-446">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="fef99-447">W tym miejscu można skonfigurować dynamiczną część etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-447">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="fef99-448">Dodaj wiersz z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-448">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-449">**Identyfikator wiersza:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="fef99-449">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="fef99-450">**Nazwa tabeli wierszy:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="fef99-450">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="fef99-451">**Pozycja początkowa wiersza:** *0*</span><span class="sxs-lookup"><span data-stu-id="fef99-451">**Row start position:** *0*</span></span>

        <span data-ttu-id="fef99-452">To pole określa pozycję w pionie, w której wiersz będzie zaczynał się na etykiecie.</span><span class="sxs-lookup"><span data-stu-id="fef99-452">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="fef99-453">**Wysokość wiersza:** *0*</span><span class="sxs-lookup"><span data-stu-id="fef99-453">**Row height:** *0*</span></span>

        <span data-ttu-id="fef99-454">To pole definiuje wysokość każdego wiersza (w punktach) zgodnie ze standardem ZPL.</span><span class="sxs-lookup"><span data-stu-id="fef99-454">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="fef99-455">Wysokość wiersza jest dodatnia dla etykiet poziomych i wartości ujemnych dla etykiet pionowych.</span><span class="sxs-lookup"><span data-stu-id="fef99-455">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="fef99-456">Ponieważ w tym przykładzie występuje tylko jeden wiersz, można nadać mu wartość *0* (zero).</span><span class="sxs-lookup"><span data-stu-id="fef99-456">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="fef99-457">**Liczba wierszy na stronę:** *1*</span><span class="sxs-lookup"><span data-stu-id="fef99-457">**Rows per page:** *1*</span></span>

        <span data-ttu-id="fef99-458">To pole definiuje liczbę wierszy, które mogą być drukowane na każdej etykiecie.</span><span class="sxs-lookup"><span data-stu-id="fef99-458">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="fef99-459">Ta konfiguracja spowoduje wydrukowanie osobnej etykiety ZPL dla każdego rekordu w tabeli etykiety grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-459">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="fef99-460">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="fef99-460">Close the page.</span></span>
1. <span data-ttu-id="fef99-461">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="fef99-461">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="fef99-462">W oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-462">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-463">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-463">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-464">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-464">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-465">**Pole:** *Typ pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-465">**Field:** *Work type*</span></span>
    - <span data-ttu-id="fef99-466">**Kryteria:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="fef99-466">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="fef99-467">To zapytanie zapewnia, że na etykiecie będą drukowane tylko wiersze pracy typu pobranie, a nie typy wierszy pracy.</span><span class="sxs-lookup"><span data-stu-id="fef99-467">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="fef99-468">Jeśli chcesz mieć możliwość drukowania identyfikatora list przewozowy, na karcie **Sprzężenia** wybierz tabelę **Wiersze pracy** i przyłącz się do tabeli **Wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="fef99-468">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span> 
1. <span data-ttu-id="fef99-469">Zamknij okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-469">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="fef99-470">Skrócona karta **Układ tekstu drukarki** zawiera trzy sekcje, w których można wpisać kod drukarki: **Sekcja nagłówka**, **Sekcja treści** i **Sekcja stopki**.</span><span class="sxs-lookup"><span data-stu-id="fef99-470">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="fef99-471">W **Sekcji nagłówka**, w polu **Nagłówek etykiety** wprowadź kod dla wymaganego nagłówka.</span><span class="sxs-lookup"><span data-stu-id="fef99-471">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="fef99-472">Jeśli na przykład używane są drukarki Zebra, można użyć poniższego kodu.</span><span class="sxs-lookup"><span data-stu-id="fef99-472">For example, if you're using Zebra printers, you can use the following code.</span></span>


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="fef99-473">W **Sekcji treści**, w polu **Treść etykiety** wprowadź kod ZPL dla wymaganej treści.</span><span class="sxs-lookup"><span data-stu-id="fef99-473">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="fef99-474">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="fef99-474">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="fef99-475">W **Sekcji treści**, w polu **Stopka etykiety** wprowadź kod ZPL dla wymaganej stopki.</span><span class="sxs-lookup"><span data-stu-id="fef99-475">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="fef99-476">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="fef99-476">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="fef99-477">Ta instalacja spowoduje wydrukowanie jednej kopii każdej etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-477">This setup will print one copy of each label.</span></span> <span data-ttu-id="fef99-478">Jeśli wymagane jest więcej kopii (na przykład jedna kopia dla każdej strony palety), należy określić wartość **n** dla sekcji **\^PQn** w stopce w wymaganej liczbie kopii.</span><span class="sxs-lookup"><span data-stu-id="fef99-478">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="fef99-479">Na przykład, aby wydrukować cztery kopie każdej etykiety, należy określić **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="fef99-479">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="fef99-480">Pierwsza etykieta jest teraz gotowa do użycia.</span><span class="sxs-lookup"><span data-stu-id="fef99-480">The first label is now ready to use.</span></span>
1. <span data-ttu-id="fef99-481">Dodaj drugi rekord układu z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-481">Create a second layout record that has the following settings:</span></span>

    - <span data-ttu-id="fef99-482">**Identyfikator układu etykiety:** *Paleta*</span><span class="sxs-lookup"><span data-stu-id="fef99-482">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="fef99-483">**Opis:** *Paleta*</span><span class="sxs-lookup"><span data-stu-id="fef99-483">**Description:** *Pallet*</span></span>

1. <span data-ttu-id="fef99-484">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fef99-484">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fef99-485">W okienku akcji wybierz opcję **Ustawienia wiersza etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-485">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="fef99-486">Zostanie wyświetlona strona **Ustawienia wiersza etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-486">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="fef99-487">W tym miejscu można skonfigurować dynamiczną część etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-487">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="fef99-488">Dodaj wiersz z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-488">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-489">**Identyfikator wiersza:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="fef99-489">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="fef99-490">**Nazwa tabeli wierszy:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="fef99-490">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="fef99-491">**Pozycja początkowa wiersza:** *0*</span><span class="sxs-lookup"><span data-stu-id="fef99-491">**Row start position:** *0*</span></span>

        <span data-ttu-id="fef99-492">To pole określa pozycję w pionie, w której wiersz będzie zaczynał się na etykiecie.</span><span class="sxs-lookup"><span data-stu-id="fef99-492">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="fef99-493">**Wysokość wiersza:** *0*</span><span class="sxs-lookup"><span data-stu-id="fef99-493">**Row height:** *0*</span></span>

        <span data-ttu-id="fef99-494">To pole definiuje wysokość każdego wiersza (w punktach) zgodnie ze standardem ZPL.</span><span class="sxs-lookup"><span data-stu-id="fef99-494">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="fef99-495">Wysokość wiersza jest dodatnia dla etykiet poziomych i wartości ujemnych dla etykiet pionowych.</span><span class="sxs-lookup"><span data-stu-id="fef99-495">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="fef99-496">Ponieważ w tym przykładzie występuje tylko jeden wiersz, można nadać mu wartość *0* (zero).</span><span class="sxs-lookup"><span data-stu-id="fef99-496">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="fef99-497">**Liczba wierszy na stronę:** *1*</span><span class="sxs-lookup"><span data-stu-id="fef99-497">**Rows per page:** *1*</span></span>

        <span data-ttu-id="fef99-498">To pole definiuje liczbę wierszy, które mogą być drukowane na każdej etykiecie.</span><span class="sxs-lookup"><span data-stu-id="fef99-498">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="fef99-499">Ta konfiguracja powoduje wydrukowanie osobnej etykiety ZPL dla każdego rekordu w tabeli etykiety grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="fef99-499">This setup causes a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="fef99-500">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="fef99-500">Close the page.</span></span>
1. <span data-ttu-id="fef99-501">W okienku akcji wybierz pozycję **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="fef99-501">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="fef99-502">W oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-502">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-503">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-503">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-504">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-504">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-505">**Pole:** *Typ pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-505">**Field:** *Work type*</span></span>
    - <span data-ttu-id="fef99-506">**Kryteria:** *Pobranie*</span><span class="sxs-lookup"><span data-stu-id="fef99-506">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="fef99-507">To zapytanie zapewnia, że na etykiecie będą drukowane tylko wiersze pracy typu pobranie, a nie typy wierszy pracy.</span><span class="sxs-lookup"><span data-stu-id="fef99-507">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="fef99-508">Jeśli chcesz mieć możliwość drukowania identyfikatora list przewozowy, na karcie **Sprzężenia** wybierz tabelę **Wiersze pracy** i przyłącz się do tabeli **Wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="fef99-508">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="fef99-509">Zamknij okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-509">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="fef99-510">Skrócona karta **Układ tekstu drukarki** zawiera trzy sekcje, w których można wpisać kod drukarki: **Sekcja nagłówka**, **Sekcja treści** i **Sekcja stopki**.</span><span class="sxs-lookup"><span data-stu-id="fef99-510">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="fef99-511">W **Sekcji nagłówka**, w polu **Nagłówek etykiety** wprowadź kod dla wymaganego nagłówka.</span><span class="sxs-lookup"><span data-stu-id="fef99-511">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="fef99-512">Jeśli na przykład używane są drukarki Zebra, można użyć poniższego kodu.</span><span class="sxs-lookup"><span data-stu-id="fef99-512">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="fef99-513">W **Sekcji treści**, w polu **Treść etykiety** wprowadź kod ZPL dla wymaganej treści.</span><span class="sxs-lookup"><span data-stu-id="fef99-513">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="fef99-514">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="fef99-514">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="fef99-515">W **Sekcji treści**, w polu **Stopka etykiety** wprowadź kod ZPL dla wymaganej stopki.</span><span class="sxs-lookup"><span data-stu-id="fef99-515">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="fef99-516">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="fef99-516">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="fef99-517">Ta instalacja spowoduje wydrukowanie jednej kopii każdej etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-517">This setup will print one copy of each label.</span></span> <span data-ttu-id="fef99-518">Jeśli wymagane jest więcej kopii (na przykład jedna kopia dla każdej strony palety), należy określić wartość **n** dla sekcji **\^PQn** w stopce w wymaganej liczbie kopii.</span><span class="sxs-lookup"><span data-stu-id="fef99-518">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="fef99-519">Na przykład, aby wydrukować cztery kopie każdej etykiety, należy określić **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="fef99-519">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="fef99-520">Druga etykieta jest teraz gotowa do użycia.</span><span class="sxs-lookup"><span data-stu-id="fef99-520">The second label is now ready to use.</span></span>
1. <span data-ttu-id="fef99-521">Dodaj trzeci rekord układu z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-521">Create a third layout record that has the following settings:</span></span>

    - <span data-ttu-id="fef99-522">**Identyfikator układu etykiety:** *Podział*</span><span class="sxs-lookup"><span data-stu-id="fef99-522">**Label layout ID:** *Break*</span></span>
    - <span data-ttu-id="fef99-523">**Opis:** *Etykieta podziału*</span><span class="sxs-lookup"><span data-stu-id="fef99-523">**Description:** *Break label*</span></span>

1. <span data-ttu-id="fef99-524">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fef99-524">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fef99-525">Skrócona karta **Układ tekstu drukarki** zawiera trzy sekcje, w których można wpisać kod drukarki: **Sekcja nagłówka**, **Sekcja treści** i **Sekcja stopki**.</span><span class="sxs-lookup"><span data-stu-id="fef99-525">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="fef99-526">W **Sekcji nagłówka**, w polu **Nagłówek etykiety** wprowadź kod ZPL dla wymaganego nagłówka.</span><span class="sxs-lookup"><span data-stu-id="fef99-526">In the **Header section** section, in the **Label header** field, enter ZPL code for the required header.</span></span> <span data-ttu-id="fef99-527">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="fef99-527">Here is an example.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. <span data-ttu-id="fef99-528">Tym razem żadna treść nie jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="fef99-528">This time, no body is required.</span></span> <span data-ttu-id="fef99-529">W tym celu wystarczy wprowadzić wymagany tekst w **Sekcji stopki**.</span><span class="sxs-lookup"><span data-stu-id="fef99-529">Therefore, just enter the required text in the **Footer section** section.</span></span> <span data-ttu-id="fef99-530">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="fef99-530">Here is an example.</span></span>

    ```plaintext
    ^XZ
    ```

    <span data-ttu-id="fef99-531">Trzecia etykieta jest teraz gotowa do użycia.</span><span class="sxs-lookup"><span data-stu-id="fef99-531">The third label is now ready to use.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fef99-532">Trzecia etykieta jest etykietą podziału, która będzie używana jako separator między rolkami etykiet.</span><span class="sxs-lookup"><span data-stu-id="fef99-532">This third label is a break label that will be used as a divider between label rolls.</span></span>

### <a name="create-two-wave-label-types"></a><span data-ttu-id="fef99-533">Tworzenie dwóch typów etykiety grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-533">Create two wave label types</span></span>

1. <span data-ttu-id="fef99-534">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Typy etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-534">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="fef99-535">Dodaj rekord z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-535">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="fef99-536">**Typ etykiety:** *Karton*</span><span class="sxs-lookup"><span data-stu-id="fef99-536">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="fef99-537">**Opis:** *Karton*</span><span class="sxs-lookup"><span data-stu-id="fef99-537">**Description:** *Carton*</span></span>

1. <span data-ttu-id="fef99-538">Dodaj drugi rekord z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-538">Create a second record that has the following settings:</span></span>

    - <span data-ttu-id="fef99-539">**Typ etykiety:** *Paleta*</span><span class="sxs-lookup"><span data-stu-id="fef99-539">**Label type:** *Pallet*</span></span>
    - <span data-ttu-id="fef99-540">**Opis:** *Paleta*</span><span class="sxs-lookup"><span data-stu-id="fef99-540">**Description:** *Pallet*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="fef99-541">Ustaw grupy sekwencji jednostek</span><span class="sxs-lookup"><span data-stu-id="fef99-541">Set up unit sequence groups</span></span>

1. <span data-ttu-id="fef99-542">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Grupy sekwencji jednostek**.</span><span class="sxs-lookup"><span data-stu-id="fef99-542">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="fef99-543">Wybierz lub utwórz grupę **Każde Pudełko PL**.</span><span class="sxs-lookup"><span data-stu-id="fef99-543">Select or create an **Ea Box PL** group.</span></span>
1. <span data-ttu-id="fef99-544">W przypadku wiersza **Pudełko** należy określić wartość w polu **Typ poziomu grupy czynności** na *Karton*.</span><span class="sxs-lookup"><span data-stu-id="fef99-544">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>
1. <span data-ttu-id="fef99-545">W przypadku wiersza **Numer identyfikacyjny** należy określić wartość w polu **Typ poziomu grupy czynności** na *Paleta*.</span><span class="sxs-lookup"><span data-stu-id="fef99-545">For the **PL** line, set the **Wave level type** field to *Pallet*.</span></span>

### <a name="create-wave-label-templates"></a><span data-ttu-id="fef99-546">Tworzenie szablonów etykiety grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-546">Create wave label templates</span></span>

1. <span data-ttu-id="fef99-547">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Szablony etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-547">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="fef99-548">Dodaj szablon etykiety z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-548">Create a label template that has the following settings:</span></span>

    - <span data-ttu-id="fef99-549">**Nazwa szablonu etykiety:** *Etykiety kartonu*</span><span class="sxs-lookup"><span data-stu-id="fef99-549">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="fef99-550">**Opis:** *Etykiety kartonu*</span><span class="sxs-lookup"><span data-stu-id="fef99-550">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="fef99-551">**Kod kroku grupy czynności:** *Karton*</span><span class="sxs-lookup"><span data-stu-id="fef99-551">**Wave step code:** *Carton*</span></span>
    - <span data-ttu-id="fef99-552">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="fef99-552">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="fef99-553">Na skróconej karcie **Ogólne** w polu **Typ etykiety grupy czynności** wybierz wartość, np. *Karton*.</span><span class="sxs-lookup"><span data-stu-id="fef99-553">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Carton*.</span></span>
1. <span data-ttu-id="fef99-554">Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-554">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-555">**Identyfikator układu etykiety:** *Karton*</span><span class="sxs-lookup"><span data-stu-id="fef99-555">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="fef99-556">**Nazwa drukarki:** Wybierz odpowiednią drukarkę ZPL.</span><span class="sxs-lookup"><span data-stu-id="fef99-556">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="fef99-557">**Uruchom kwerendę:** *Tak* (To ustawienie jest opcjonalne, ale jest zalecane w przypadku optymalnej wydajności.)</span><span class="sxs-lookup"><span data-stu-id="fef99-557">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="fef99-558">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fef99-558">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fef99-559">Opcjonalnie: Jeśli konfigurujesz projekt etykiety właściwy dla odbiorcy, musisz utworzyć kwerendę, aby znaleźć konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fef99-559">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="fef99-560">Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** wybierz opcję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="fef99-560">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="fef99-561">Następnie w oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-561">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-562">**Tabela:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="fef99-562">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="fef99-563">**Tabela pochodna:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="fef99-563">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="fef99-564">**Pole:** *Numer konta*</span><span class="sxs-lookup"><span data-stu-id="fef99-564">**Field:** *Account number*</span></span>
    - <span data-ttu-id="fef99-565">**Kryteria**: Należy wprowadzić odpowiedni numer konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fef99-565">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="fef99-566">Po zakończeniu kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-566">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="fef99-567">W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edytora zapytań dla całego szablonu etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-567">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="fef99-568">W oknie dialogowym edytora zapytań na karcie **Sortowanie** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-568">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-569">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-569">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-570">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-570">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-571">**Pole:** *Odwołanie do identyfikatora wiersza ładunku (identyfikator rekordu)*</span><span class="sxs-lookup"><span data-stu-id="fef99-571">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="fef99-572">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="fef99-572">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="fef99-573">Dodaj drugi wiersz z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-573">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-574">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-574">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-575">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-575">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-576">**Pole:** *Identyfikator wysyłki*</span><span class="sxs-lookup"><span data-stu-id="fef99-576">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="fef99-577">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="fef99-577">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="fef99-578">Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-578">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="fef99-579">Zostanie wyświetlone okno komunikatu z monitem o potwierdzenie operacji resetowania grup.</span><span class="sxs-lookup"><span data-stu-id="fef99-579">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="fef99-580">Wybierz przycisk **Tak**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="fef99-580">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="fef99-581">W okienku akcji wybierz opcję **Grupa szablonu etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-581">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="fef99-582">W oknie dialogowym **Grupa szablonów etykiety grupy czynności** dla wiersza, w którym w polu **Nazwa pola odwołania** jest ustawiona wartość *Identyfikator wysyłki*, należy określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="fef99-582">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="fef99-583">**Drukuj etykietę podziału:** To pole wyboru należy zaznaczyć.</span><span class="sxs-lookup"><span data-stu-id="fef99-583">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="fef99-584">**Identyfikator układu etykiety:** Umożliwia wybór etykiety podziału.</span><span class="sxs-lookup"><span data-stu-id="fef99-584">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="fef99-585">(Na przykład wybierz opcję układ etykiety *Podziału* utworzoną wcześniej w tym scenariuszu.)</span><span class="sxs-lookup"><span data-stu-id="fef99-585">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="fef99-586">**Nazwa drukarki:** Wybierz drukarkę dla etykiety podziału.</span><span class="sxs-lookup"><span data-stu-id="fef99-586">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="fef99-587">(Zazwyczaj w celu rozdzielania przeniesień etykiet należy wybrać tę samą drukarkę, która została wybrana na skróconej karcie **Szczegóły szablonu etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-587">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="fef99-588">Możliwe są jednak inne scenariusze.)</span><span class="sxs-lookup"><span data-stu-id="fef99-588">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="fef99-589">W wierszu, w którym pole **Nazwy pola odwołania** ma wartość *Odwołanie do identyfikatora wiersza ładunku*, zaznacz pole wyboru **Identyfikator kompilacji etykiety**.</span><span class="sxs-lookup"><span data-stu-id="fef99-589">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fef99-590">Ten Instalator utworzy jedną sekwencję etykiet („Karton 1 z X”) dla każdego wiersza ładunku w rzucie, niezależnie od konfiguracji grupowania pracy.</span><span class="sxs-lookup"><span data-stu-id="fef99-590">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="fef99-591">Tę sekwencję etykiet można wydrukować w układzie etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-591">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="fef99-592">Ponadto etykiety różnych wysyłek będą oddzielone wybraną etykietą podziału.</span><span class="sxs-lookup"><span data-stu-id="fef99-592">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

1. <span data-ttu-id="fef99-593">Wybierz **OK**, aby zamknąć okno dialogowe **Grupa szablonu etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-593">Select **OK** to close the **Wave label template group** dialog box.</span></span>
1. <span data-ttu-id="fef99-594">Dodaj drugi szablon etykiety z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-594">Create a second label template that has the following settings:</span></span>

    - <span data-ttu-id="fef99-595">**Nazwa szablonu etykiety:** *Etykiety palety*</span><span class="sxs-lookup"><span data-stu-id="fef99-595">**Label template name:** *Pallet labels*</span></span>
    - <span data-ttu-id="fef99-596">**Opis:** *Etykiety palety*</span><span class="sxs-lookup"><span data-stu-id="fef99-596">**Description:** *Pallet labels*</span></span>
    - <span data-ttu-id="fef99-597">**Kod kroku grupy czynności:** *Paleta*</span><span class="sxs-lookup"><span data-stu-id="fef99-597">**Wave step code:** *Pallet*</span></span>
    - <span data-ttu-id="fef99-598">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="fef99-598">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="fef99-599">Na skróconej karcie **Ogólne** w polu **Typ etykiety grupy czynności** wybierz wartość, np. *Paleta*.</span><span class="sxs-lookup"><span data-stu-id="fef99-599">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Pallet*.</span></span>
1. <span data-ttu-id="fef99-600">Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-600">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-601">**Identyfikator układu etykiety:** *Paleta*</span><span class="sxs-lookup"><span data-stu-id="fef99-601">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="fef99-602">**Nazwa drukarki:** Wybierz odpowiednią drukarkę ZPL.</span><span class="sxs-lookup"><span data-stu-id="fef99-602">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="fef99-603">**Uruchom kwerendę:** *Tak* (To ustawienie jest opcjonalne, ale jest zalecane w przypadku optymalnej wydajności.)</span><span class="sxs-lookup"><span data-stu-id="fef99-603">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="fef99-604">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fef99-604">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fef99-605">Opcjonalnie: Jeśli konfigurujesz projekt etykiety właściwy dla odbiorcy, musisz utworzyć kwerendę, aby znaleźć konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fef99-605">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="fef99-606">Na skróconej karcie **Szczegóły szablonu etykiety grupy czynności** wybierz opcję **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="fef99-606">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="fef99-607">Następnie w oknie dialogowym edytora zapytań na karcie **Zakres** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-607">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-608">**Tabela:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="fef99-608">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="fef99-609">**Tabela pochodna:** *Wysyłki*</span><span class="sxs-lookup"><span data-stu-id="fef99-609">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="fef99-610">**Pole:** *Numer konta*</span><span class="sxs-lookup"><span data-stu-id="fef99-610">**Field:** *Account number*</span></span>
    - <span data-ttu-id="fef99-611">**Kryteria**: Należy wprowadzić odpowiedni numer konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fef99-611">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="fef99-612">Po zakończeniu kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-612">When you've finished, select **OK** to close the query editor dialog box.</span></span> 

1. <span data-ttu-id="fef99-613">W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edytora zapytań dla całego szablonu etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-613">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="fef99-614">W oknie dialogowym edytora zapytań na karcie **Sortowanie** dodaj wiersz o następujących ustawieniach:</span><span class="sxs-lookup"><span data-stu-id="fef99-614">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-615">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-615">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-616">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-616">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-617">**Pole:** *Odwołanie do identyfikatora wiersza ładunku (identyfikator rekordu)*</span><span class="sxs-lookup"><span data-stu-id="fef99-617">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="fef99-618">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="fef99-618">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="fef99-619">Dodaj drugi wiersz z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-619">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="fef99-620">**Tabela:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-620">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-621">**Tabela pochodna:** *Wiersze pracy*</span><span class="sxs-lookup"><span data-stu-id="fef99-621">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef99-622">**Pole:** *Identyfikator wysyłki*</span><span class="sxs-lookup"><span data-stu-id="fef99-622">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="fef99-623">**Kierunek wyszukiwania:** *Rosnąco*</span><span class="sxs-lookup"><span data-stu-id="fef99-623">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="fef99-624">Kliknij przycisk **OK**, aby zamknąć okno dialogowe edytora zapytań.</span><span class="sxs-lookup"><span data-stu-id="fef99-624">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="fef99-625">Zostanie wyświetlone okno komunikatu z monitem o potwierdzenie operacji resetowania grup.</span><span class="sxs-lookup"><span data-stu-id="fef99-625">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="fef99-626">Wybierz przycisk **Tak**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="fef99-626">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="fef99-627">W okienku akcji wybierz opcję **Grupa szablonu etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-627">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="fef99-628">W oknie dialogowym **Grupa szablonów etykiety grupy czynności** dla wiersza, w którym w polu **Nazwa pola odwołania** jest ustawiona wartość *Identyfikator wysyłki*, należy określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="fef99-628">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="fef99-629">**Drukuj etykietę podziału:** To pole wyboru należy zaznaczyć.</span><span class="sxs-lookup"><span data-stu-id="fef99-629">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="fef99-630">**Identyfikator układu etykiety:** Umożliwia wybór etykiety podziału.</span><span class="sxs-lookup"><span data-stu-id="fef99-630">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="fef99-631">(Na przykład wybierz opcję układ etykiety *Podziału* utworzoną wcześniej w tym scenariuszu.)</span><span class="sxs-lookup"><span data-stu-id="fef99-631">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="fef99-632">**Nazwa drukarki:** Wybierz drukarkę dla etykiety podziału.</span><span class="sxs-lookup"><span data-stu-id="fef99-632">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="fef99-633">(Zazwyczaj w celu rozdzielania przeniesień etykiet należy wybrać tę samą drukarkę, która została wybrana na skróconej karcie **Szczegóły szablonu etykiety grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="fef99-633">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="fef99-634">Możliwe są jednak inne scenariusze.)</span><span class="sxs-lookup"><span data-stu-id="fef99-634">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="fef99-635">W wierszu, w którym pole **Nazwy pola odwołania** ma wartość *Odwołanie do identyfikatora wiersza ładunku*, zaznacz pole wyboru **Identyfikator kompilacji etykiety**.</span><span class="sxs-lookup"><span data-stu-id="fef99-635">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fef99-636">Ten Instalator utworzy jedną sekwencję etykiet („Karton 1 z X”) dla każdego wiersza ładunku w rzucie, niezależnie od konfiguracji grupowania pracy.</span><span class="sxs-lookup"><span data-stu-id="fef99-636">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="fef99-637">Tę sekwencję etykiet można wydrukować w układzie etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-637">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="fef99-638">Ponadto etykiety różnych wysyłek będą oddzielone wybraną etykietą podziału.</span><span class="sxs-lookup"><span data-stu-id="fef99-638">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="fef99-639">Konfigurowanie sekwencji identyfikatorów</span><span class="sxs-lookup"><span data-stu-id="fef99-639">Configure number sequence extensions</span></span>

<span data-ttu-id="fef99-640">Rozszerzenia sekwencji identyfikatorów kontrolują zgodność GS1 z określonymi sekwencjami identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="fef99-640">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="fef99-641">Ta konfiguracja jest opcjonalna dla bieżącego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="fef99-641">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="fef99-642">Aby uzyskać więcej informacji i instrukcji konfiguracyjnych, zobacz [Konfigurowanie rozszerzeń sekwencji identyfikatorów](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="fef99-642">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="fef99-643">Utwórz zamówienie sprzedaży i zwolnij je do magazynu</span><span class="sxs-lookup"><span data-stu-id="fef99-643">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="fef99-644">Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienie sprzedaży \> Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="fef99-644">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="fef99-645">Utwórz zamówienie sprzedaży z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="fef99-645">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="fef99-646">**Konto odbiorcy:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="fef99-646">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="fef99-647">**Magazyn:** *62*</span><span class="sxs-lookup"><span data-stu-id="fef99-647">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="fef99-648">Dodaj dwa wiersze zamówienia sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="fef99-648">Add two sales order lines:</span></span>

    - <span data-ttu-id="fef99-649">Wiersz zamówienia sprzedaży 1:</span><span class="sxs-lookup"><span data-stu-id="fef99-649">Sales order line 1:</span></span>

        - <span data-ttu-id="fef99-650">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="fef99-650">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="fef99-651">**Ilość:** *9024*</span><span class="sxs-lookup"><span data-stu-id="fef99-651">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="fef99-652">**Jednostka:** *Każdy* (9024 Każdy = 376 Pudełko = 47 Paleta)</span><span class="sxs-lookup"><span data-stu-id="fef99-652">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="fef99-653">Wiersz zamówienia sprzedaży 2:</span><span class="sxs-lookup"><span data-stu-id="fef99-653">Sales order line 2:</span></span>

        - <span data-ttu-id="fef99-654">**Numer pozycji:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="fef99-654">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="fef99-655">**Ilość:** *9016*</span><span class="sxs-lookup"><span data-stu-id="fef99-655">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="fef99-656">**Jednostka:** *Każdy* (9016 Każdy = 322 Pudełko = 46 Paleta)</span><span class="sxs-lookup"><span data-stu-id="fef99-656">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="fef99-657">Podane tu towary i ilości są tylko przykładami.</span><span class="sxs-lookup"><span data-stu-id="fef99-657">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="fef99-658">Muszą one mieć zdefiniowaną wcześniej zdefiniowaną jednostkę, dlatego dla nich musi zostać zdefiniowana odpowiednia konwersja jednostek z *Każdy* na *Pudełko* na *Paleta* oraz musi mieć zapas w magazynie *62*.</span><span class="sxs-lookup"><span data-stu-id="fef99-658">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="fef99-659">Aby uzyskać więcej informacji, zajrzyj do [Jednostka miary i zasady składowania](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fef99-659">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="fef99-660">Wybierz wiersz zamówienia sprzedaży 1.</span><span class="sxs-lookup"><span data-stu-id="fef99-660">Select sales order line 1.</span></span> <span data-ttu-id="fef99-661">W sekcji **Wiersze zamówienia sprzedaży**, w menu **Zapasy** wybierz opcję **Rezerwacje**.</span><span class="sxs-lookup"><span data-stu-id="fef99-661">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="fef99-662">Na stronie **Rezerwacje** w okienku akcji wybierz **Rezerwacja partii** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="fef99-662">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="fef99-663">Powtórz kroki 4 i 5 dla wiersza zamówienia sprzedaży 2.</span><span class="sxs-lookup"><span data-stu-id="fef99-663">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="fef99-664">W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="fef99-664">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="fef99-665">Występują wówczas następujące zdarzenia:</span><span class="sxs-lookup"><span data-stu-id="fef99-665">The following events occur:</span></span> 

    - <span data-ttu-id="fef99-666">System przetwarza utworzoną wysyłkę za pomocą szablonu, który zawiera krok drukowania etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-666">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="fef99-667">Układ etykiety zostanie użyty do zdefiniowania formatu etykiety, a jego wynikiem będzie etykieta drukowana na drukarce wybranej w szablonie etykiety.</span><span class="sxs-lookup"><span data-stu-id="fef99-667">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="fef99-668">Etykiety grupy czynności są generowane i drukowane.</span><span class="sxs-lookup"><span data-stu-id="fef99-668">Wave labels are generated and printed.</span></span> <span data-ttu-id="fef99-669">Liczba etykiet będzie równa liczbie kartonów (w tym przykładzie 376 etykiet pudełek dla wiersza 1, 322 etykiet pudełek dla wiersza 2, 47 etykiet PL dla wiersza 1, 47 etykiet PL dla wiersza 2 i dwie etykiety podziału, które mają identyfikator przesyłki).</span><span class="sxs-lookup"><span data-stu-id="fef99-669">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1, 322 Box labels for line 2, 47 PL labels for line 1, 47 PL labels for line 2, and two break labels that have the shipment ID).</span></span>
    - <span data-ttu-id="fef99-670">Nowy identyfikator list przewozowy jest generowany dla wysyłek.</span><span class="sxs-lookup"><span data-stu-id="fef99-670">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="fef99-671">Jeśli skonfigurowano rozszerzenia sekwencji identyfikatorów, identyfikatory etykiet grupy czynności są zgodne z formatem numerów **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="fef99-671">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="fef99-672">Etykiety grupy czynności można przeglądać i ponownie drukować z następujących stron:</span><span class="sxs-lookup"><span data-stu-id="fef99-672">You can view and reprint wave labels from the following pages:</span></span>

- <span data-ttu-id="fef99-673">Wszystkie wysyłki \> Szczegóły wysyłki</span><span class="sxs-lookup"><span data-stu-id="fef99-673">All shipments \> Shipment details</span></span>
- <span data-ttu-id="fef99-674">Wszystkie ładunki \> Szczegóły ładunku</span><span class="sxs-lookup"><span data-stu-id="fef99-674">All loads \> Load details</span></span>
- <span data-ttu-id="fef99-675">Wszystkie grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-675">All waves</span></span>
- <span data-ttu-id="fef99-676">Etykiety grup czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-676">Wave labels</span></span>
- <span data-ttu-id="fef99-677">Historia etykiet grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-677">Wave label history</span></span>

<span data-ttu-id="fef99-678">W przypadku większości tych stron można znaleźć odpowiednią funkcję, zaznaczając odpowiednie **Etykiety grupy czynności** w grupie **Informacje pokrewne** na karcie **Wysyłki** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="fef99-678">For most of these pages, you can find the relevant function by selecting **Wave labels** in the **Related information** group on the **Shipments** tab of the Action Pane.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fef99-679">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fef99-679">Additional resources</span></span>

- [<span data-ttu-id="fef99-680">Ponowne drukowanie i unieważnianie etykiet grupy czynności</span><span class="sxs-lookup"><span data-stu-id="fef99-680">Reprint and void wave labels</span></span>](reprint-and-void-wave-labels.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]