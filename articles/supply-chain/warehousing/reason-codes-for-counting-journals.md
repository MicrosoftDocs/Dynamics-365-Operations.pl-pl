---
title: Kody przyczyn zliczania zapasów
description: W tym temacie opisano sposób konfigurowania i stosowania kodów przyczyn dla zadań inwentaryzacji.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 1025dd00db2e8b87e3c76e3047a7cf470a2d6641
ms.sourcegitcommit: 8cbaeb6443ce47a4c4bc02b5e1a1212eb0056b38
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "3829808"
---
# <a name="reason-codes-for-inventory-counting"></a><span data-ttu-id="6217c-103">Kody przyczyn zliczania zapasów</span><span class="sxs-lookup"><span data-stu-id="6217c-103">Reason codes for inventory counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6217c-104">Kody przyczyn umożliwiają analizowanie wyników procesu inwentaryzacji (zliczania) i wszelkich rozbieżności pojawiających się w trakcie tego procesu.</span><span class="sxs-lookup"><span data-stu-id="6217c-104">Reason codes let you analyze the results of a counting process and any discrepancies that occur during that process.</span></span> <span data-ttu-id="6217c-105">Można określić przyczynę wykonywania inwentaryzacji, taką jak uszkodzenie palety lub korekta zapasów oparta na próbkach zapasów.</span><span class="sxs-lookup"><span data-stu-id="6217c-105">You can specify the reason for doing the count, such as a broken pallet or a stock adjustment that is based on inventory samples.</span></span>

## <a name="recommendation"></a><span data-ttu-id="6217c-106">Rekomendacja</span><span class="sxs-lookup"><span data-stu-id="6217c-106">Recommendation</span></span>

<span data-ttu-id="6217c-107">Przed skonfigurowaniem systemu zalecamy zdefiniowanie strategii pracy z kodami przyczyn.</span><span class="sxs-lookup"><span data-stu-id="6217c-107">Before you set up the system, we recommend that you define a strategy for working with reason codes.</span></span> <span data-ttu-id="6217c-108">Na przykład spróbuj odpowiedzieć na następujące pytania:</span><span class="sxs-lookup"><span data-stu-id="6217c-108">For example, try to answer the following questions:</span></span>

- <span data-ttu-id="6217c-109">Czy kody przyczyn powinny być wymagane w magazynach?</span><span class="sxs-lookup"><span data-stu-id="6217c-109">Should reason codes be mandatory on warehouses?</span></span>
- <span data-ttu-id="6217c-110">Czy kody przyczyn powinny być obowiązkowe, czy też dla niektórych towarów opcjonalne?</span><span class="sxs-lookup"><span data-stu-id="6217c-110">Should reason codes be mandatory or optional on some items?</span></span>
- <span data-ttu-id="6217c-111">Ile kodów przyczyn potrzeba?</span><span class="sxs-lookup"><span data-stu-id="6217c-111">How many reason codes do you require?</span></span>
- <span data-ttu-id="6217c-112">Jak kody przyczyn powinny być wykorzystywane przez osoby używające skanerów kodów kreskowych?</span><span class="sxs-lookup"><span data-stu-id="6217c-112">How should users of barcode scanners use reason codes?</span></span> <span data-ttu-id="6217c-113">Czy kody przyczyn powinny być wstępnie wybierane, obowiązkowe i nieedytowalne?</span><span class="sxs-lookup"><span data-stu-id="6217c-113">Should the reason codes be preselected, mandatory, or not editable?</span></span>
- <span data-ttu-id="6217c-114">Czy pracownicy magazynu potrzebują innego zachowania kodów przyczyn w przenośnych skanerach?</span><span class="sxs-lookup"><span data-stu-id="6217c-114">Do warehouse workers require different reason code behavior on mobile scanners?</span></span> <span data-ttu-id="6217c-115">Jeśli odpowiedź brzmi „tak”, można utworzyć więcej elementów menu i przypisać je do różnych osób.</span><span class="sxs-lookup"><span data-stu-id="6217c-115">If the answer is yes, you can create more menu items and assign them to different people.</span></span>

## <a name="where-reason-codes-apply"></a><span data-ttu-id="6217c-116">Gdzie stosuje się kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="6217c-116">Where reason codes apply</span></span>

<span data-ttu-id="6217c-117">Można utworzyć wiele zasad kodów przyczyn, a każda zasada kodu przyczyny może mieć dwie zasady kodów przyczyn zliczania.</span><span class="sxs-lookup"><span data-stu-id="6217c-117">You can create multiple reason code policies, and each reason code policy can have two counting reason code policies.</span></span> <span data-ttu-id="6217c-118">Zasady kodów przyczyn zliczania mogą być używane na poziomie magazynu lub towaru.</span><span class="sxs-lookup"><span data-stu-id="6217c-118">The counting reason code policies can be used at the warehouse level or the item level.</span></span>

## <a name="set-up-reason-code-policies"></a><span data-ttu-id="6217c-119">Konfigurowanie zasad kodów przyczyn zliczania</span><span class="sxs-lookup"><span data-stu-id="6217c-119">Set up reason code policies</span></span>

1. <span data-ttu-id="6217c-120">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Ustawienia** \> **Zapasy** \> **Zasady kodów przyczyn zliczania** i utwórz nową zasadę kodu przyczyny.</span><span class="sxs-lookup"><span data-stu-id="6217c-120">Select **Inventory management** \> **Setup** \> **Inventory** \> **Counting reason code policies**, and create a new reason code policy.</span></span>
2. <span data-ttu-id="6217c-121">W polu **Typ kodu przyczyny zliczania** wybierz opcję **Wymagane** lub **Opcjonalne**, aby określić, czy wybór kodu przyczyny powinien być działaniem obowiązkowym czy opcjonalnym w jednym z następujących arkuszy inwentaryzacyjnych:</span><span class="sxs-lookup"><span data-stu-id="6217c-121">In the **Counting reason code type** field, select either **Mandatory** or **Optional** to specify whether selection of a reason code should be an optional or mandatory action in one of the following counting journals:</span></span>

    - <span data-ttu-id="6217c-122">Inwentaryzacja ciągła (za pomocą urządzenia przenośnego)</span><span class="sxs-lookup"><span data-stu-id="6217c-122">Cycle Count (mobile device)</span></span>
    - <span data-ttu-id="6217c-123">Inwentaryzacja punktowa (za pomocą urządzenia przenośnego)</span><span class="sxs-lookup"><span data-stu-id="6217c-123">Spot Count (mobile device)</span></span>
    - <span data-ttu-id="6217c-124">Inwentaryzacja progowa (za pomocą urządzenia przenośnego)</span><span class="sxs-lookup"><span data-stu-id="6217c-124">Threshold Count (mobile device)</span></span>
    - <span data-ttu-id="6217c-125">Korekta wewnętrzna (za pomocą urządzenia przenośnego)</span><span class="sxs-lookup"><span data-stu-id="6217c-125">Adjustment In (mobile device)</span></span>
    - <span data-ttu-id="6217c-126">Korekta zewnętrzna (za pomocą urządzenia przenośnego)</span><span class="sxs-lookup"><span data-stu-id="6217c-126">Adjustment Out (mobile device)</span></span>
    - <span data-ttu-id="6217c-127">Arkusz inwentaryzacyjny (za pomocą pełnego klienta)</span><span class="sxs-lookup"><span data-stu-id="6217c-127">Counting Journal (rich client)</span></span>

<span data-ttu-id="6217c-128">Można również skonfigurować kody przyczyn dla poszczególnych magazynów i produktów.</span><span class="sxs-lookup"><span data-stu-id="6217c-128">You can also set up reason codes for individual warehouses and for products.</span></span> <span data-ttu-id="6217c-129">Konfiguracja kodów przyczyn produktów może nie brać pod uwagę konfiguracji dla magazynów.</span><span class="sxs-lookup"><span data-stu-id="6217c-129">The reason code setup for products can disregard the setup for warehouses.</span></span>

## <a name="mandatory-reason-codes"></a><span data-ttu-id="6217c-130">Obowiązkowe kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="6217c-130">Mandatory reason codes</span></span>

<span data-ttu-id="6217c-131">Jeśli parametr **Wymagane** jest ustawiony w konfiguracji kodów przyczyn dla magazynów lub towarów, arkusz inwentaryzacyjny można sfinalizować i zamknąć dopiero po podaniu kodu przyczyny.</span><span class="sxs-lookup"><span data-stu-id="6217c-131">If the **Mandatory** parameter is set in the configuration of reason codes for warehouses or items, the counting journal can't be completed and closed until a reason code is provided.</span></span>

### <a name="set-up-reason-codes-for-warehouses"></a><span data-ttu-id="6217c-132">Konfigurowanie kodów przyczyn dla magazynów</span><span class="sxs-lookup"><span data-stu-id="6217c-132">Set up reason codes for warehouses</span></span>

1. <span data-ttu-id="6217c-133">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Ustawienia** \> **Podział magazynu** \> **Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="6217c-133">Select **Inventory Management** \> **Setup** \> **Inventory breakdown** \> **Warehouses**.</span></span>
2. <span data-ttu-id="6217c-134">Na karcie **Magazyn** w polu **Zasada kodów przyczyn zliczania** wybierz jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="6217c-134">On the **Warehouse** tab, in the **Counting reason code policy** field, select one of the following options:</span></span>

    - <span data-ttu-id="6217c-135">**Puste** — parametr skonfigurowany dla towaru jest używany do ustalania, czy arkusze inwentaryzacyjne są wymagane dla produktu.</span><span class="sxs-lookup"><span data-stu-id="6217c-135">**Blank** – The parameter that is set up for the item is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="6217c-136">**Wymagane** — kod przyczyny jest zawsze wymagany w arkuszach inwentaryzacyjnych dla magazynu.</span><span class="sxs-lookup"><span data-stu-id="6217c-136">**Mandatory** – A reason code is always required on counting journals for the warehouse.</span></span>
    - <span data-ttu-id="6217c-137">**Opcjonalnie** — kod przyczyny nie jest wymagany w arkuszach inwentaryzacyjnych dla magazynu.</span><span class="sxs-lookup"><span data-stu-id="6217c-137">**Optional** – A reason code isn't required on counting journals for the warehouse.</span></span>

### <a name="set-up-reason-codes-for-products"></a><span data-ttu-id="6217c-138">Konfigurowanie kodów przyczyn dla produktów</span><span class="sxs-lookup"><span data-stu-id="6217c-138">Set up reason codes for products</span></span>

1. <span data-ttu-id="6217c-139">Wybierz kolejno opcje **Zarządzanie informacjami o produktach** \> **Produkty** \> **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="6217c-139">Select **Product information management** \> **Products** \> **Released products**.</span></span>
2. <span data-ttu-id="6217c-140">Na karcie **Produkt** wybierz opcję **Zasada kodów przyczyn zliczania**, a następnie wybierz jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="6217c-140">On the **Product** tab, select **Counting reason code policy**, and then select one of the following options:</span></span>

    - <span data-ttu-id="6217c-141">**Puste** — parametr skonfigurowany dla magazynu jest używany do ustalania, czy arkusze inwentaryzacyjne są wymagane dla produktu.</span><span class="sxs-lookup"><span data-stu-id="6217c-141">**Blank** – The parameter that is set up for the warehouse is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="6217c-142">**Wymagane** — kod przyczyny jest zawsze wymagany w arkuszach inwentaryzacyjnych dla produktu.</span><span class="sxs-lookup"><span data-stu-id="6217c-142">**Mandatory** – A reason code is always required on counting journals for the product.</span></span> <span data-ttu-id="6217c-143">To ustawienie zastępuje wszelkie ustawienia kodów przyczyn na poziomie magazynu.</span><span class="sxs-lookup"><span data-stu-id="6217c-143">This setting overrides any reason code setting at the warehouse level.</span></span>
    - <span data-ttu-id="6217c-144">**Opcjonalnie** — kod przyczyny nie jest wymagany w arkuszach inwentaryzacyjnych dla produktu.</span><span class="sxs-lookup"><span data-stu-id="6217c-144">**Optional** – A reason code isn't required on counting journals for the product.</span></span> <span data-ttu-id="6217c-145">To ustawienie zastępuje wszelkie ustawienia kodów przyczyn na poziomie magazynu.</span><span class="sxs-lookup"><span data-stu-id="6217c-145">This setting overrides any reason code setting at the warehouse level.</span></span>

### <a name="use-reason-codes-in-counting-journals"></a><span data-ttu-id="6217c-146">Używanie kodów przyczyn w arkuszach inwentaryzacyjnych</span><span class="sxs-lookup"><span data-stu-id="6217c-146">Use reason codes in counting journals</span></span>

<span data-ttu-id="6217c-147">W arkuszu inwentaryzacyjnym można dodawać kody przyczyn dla następujących typów inwentaryzacji:</span><span class="sxs-lookup"><span data-stu-id="6217c-147">In a counting journal, you can add reason codes for counts of the following types:</span></span>

- <span data-ttu-id="6217c-148">Inwentaryzacja ciągła</span><span class="sxs-lookup"><span data-stu-id="6217c-148">Cycle Count</span></span>
- <span data-ttu-id="6217c-149">Inwentaryzacja punktowa</span><span class="sxs-lookup"><span data-stu-id="6217c-149">Spot Count</span></span>
- <span data-ttu-id="6217c-150">Inwentaryzacja progowa</span><span class="sxs-lookup"><span data-stu-id="6217c-150">Threshold Count</span></span>
- <span data-ttu-id="6217c-151">Korekta wewnętrzna</span><span class="sxs-lookup"><span data-stu-id="6217c-151">Adjustment In</span></span>
- <span data-ttu-id="6217c-152">Korekta zewnętrzna</span><span class="sxs-lookup"><span data-stu-id="6217c-152">Adjustment Out</span></span>

<span data-ttu-id="6217c-153">Kody przyczyn są dodawane do wierszy arkusza w arkuszach inwentaryzacyjnych typu **Arkusz zliczania**.</span><span class="sxs-lookup"><span data-stu-id="6217c-153">Reason codes are added to the journal lines in counting journals of the **Counting journal** type.</span></span>

1. <span data-ttu-id="6217c-154">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Wpisy w arkuszu** \> **Zliczanie pozycji** \> **Inwentaryzacja**.</span><span class="sxs-lookup"><span data-stu-id="6217c-154">Select **Inventory management** \> **Journal entries** \> **Item counting** \> **Counting**.</span></span>
2. <span data-ttu-id="6217c-155">W wierszu szczegółów arkusza inwentaryzacyjnego w polu **Kod przyczyny zliczania** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="6217c-155">In the line details of the counting journal, in the **Counting reason code** field, select an option.</span></span>

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a><span data-ttu-id="6217c-156">Wyświetlanie historii inwentaryzacji zarejestrowanej według kodów przyczyn</span><span class="sxs-lookup"><span data-stu-id="6217c-156">View the counting history as it's recorded by reason codes</span></span>

- <span data-ttu-id="6217c-157">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Historia inwentaryzacji**, a następnie w polu **Kod przyczyny zliczania** obejrzyj historię inwentaryzacji zarejestrowaną za pomocą kodu przyczyny.</span><span class="sxs-lookup"><span data-stu-id="6217c-157">Select **Inventory management** \> **Inquiries and reports** \> **Counting history**, and then, in the **Counting reason code** field, view the counting history that has been recorded through a reason code.</span></span>

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a><span data-ttu-id="6217c-158">Używanie kodu przyczyny do korygowania ilości</span><span class="sxs-lookup"><span data-stu-id="6217c-158">Use a reason code for a quantity adjustment</span></span>

1. <span data-ttu-id="6217c-159">Na stronie **Dostępne zapasy** wybierz opcję **Korekta ilości**.</span><span class="sxs-lookup"><span data-stu-id="6217c-159">On the **On-hand inventory** page, select **Adjust quantity**.</span></span> <span data-ttu-id="6217c-160">Stronę **Dostępne zapasy** można otworzyć na kilka sposobów.</span><span class="sxs-lookup"><span data-stu-id="6217c-160">You can open the **On-hand inventory** page in several ways.</span></span> <span data-ttu-id="6217c-161">Na przykład wybierz kolejno opcje **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Dostępne zapasy**.</span><span class="sxs-lookup"><span data-stu-id="6217c-161">For example, select **Inventory management** \> **Inquiries and reports** \> **On-hand inventory**.</span></span>
2. <span data-ttu-id="6217c-162">Wybierz opcję **Korekta ilości**, a następnie w polu **Kod przyczyny zliczania** wybierz kod przyczyny.</span><span class="sxs-lookup"><span data-stu-id="6217c-162">Select **Adjust quantity**, and then, in the **Counting reason code** field, select a reason code.</span></span>

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a><span data-ttu-id="6217c-163">Konfigurowanie kodów przyczyn dla elementów menu na urządzeniu przenośnym</span><span class="sxs-lookup"><span data-stu-id="6217c-163">Configure reason codes for mobile device menu items</span></span>

<span data-ttu-id="6217c-164">Kody przyczyn można skonfigurować dla każdego typu inwentaryzacji obsługiwanego za pomocą elementu menu na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="6217c-164">You can configure reason codes for any type of count on a mobile device menu item.</span></span> <span data-ttu-id="6217c-165">Konfiguracja pozycji menu dla urządzenia przenośnego zawiera następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="6217c-165">The configuration of the mobile device menu item includes the following information:</span></span>

- <span data-ttu-id="6217c-166">Czy kod przyczyny jest widoczny dla pracownika korzystającego z urządzenia przenośnego podczas inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="6217c-166">Whether the reason code is shown to the mobile device worker during counting.</span></span>
- <span data-ttu-id="6217c-167">Domyślny kod przyczyny wyświetlany w elemencie menu na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="6217c-167">The default reason code that is shown on a mobile device menu item.</span></span>
- <span data-ttu-id="6217c-168">Czy użytkownik może edytować kod przyczyny.</span><span class="sxs-lookup"><span data-stu-id="6217c-168">Whether the user can edit the reason code.</span></span>

### <a name="set-up-reason-codes-on-a-mobile-device"></a><span data-ttu-id="6217c-169">Konfigurowanie kodów przyczyn na urządzeniu przenośnym</span><span class="sxs-lookup"><span data-stu-id="6217c-169">Set up reason codes on a mobile device</span></span>

1. <span data-ttu-id="6217c-170">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Urządzenie przenośne** \> **Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="6217c-170">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="6217c-171">Na karcie **Inwentaryzacja ciągła** wybierz opcję **Inwentaryzacja ciągła**.</span><span class="sxs-lookup"><span data-stu-id="6217c-171">On the **Cycle count** tab, select **Cycle counting**.</span></span>
3. <span data-ttu-id="6217c-172">W polu **Domyślny kod przyczyny zliczania** ustaw domyślny kod przyczyny, który ma być rejestrowany podczas inwentaryzacji za pomocą elementu menu na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="6217c-172">In the **Default counting reason code** field, set the default reason code that should be recorded when counting is done by using the mobile device menu item.</span></span>
4. <span data-ttu-id="6217c-173">W polu **Wyświetl kod przyczyny zliczania** wybierz opcję **Wiersz**, aby był pokazywany kod przyczyny po zarejestrowaniu każdego odchylenia.</span><span class="sxs-lookup"><span data-stu-id="6217c-173">In the **Display counting reason code** field, select **Line** to show the reason code after each variance is recorded.</span></span> <span data-ttu-id="6217c-174">Alternatywnie wybierz opcję **Ukryj**, jeśli kod przyczyny nie powinien być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="6217c-174">Alternatively, select **Hide** if the reason code shouldn't be shown.</span></span>
5. <span data-ttu-id="6217c-175">W opcji **Edytuj kod przyczyny zliczania** ustaw wartość **Tak** lub **Nie**.</span><span class="sxs-lookup"><span data-stu-id="6217c-175">Set the **Edit counting reason code** option to either **Yes** or **No**.</span></span> <span data-ttu-id="6217c-176">Jeśli ustawisz wartość **Tak**, pracownik może edytować kod przyczyny wyświetlony na urządzeniu przenośnym podczas inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="6217c-176">If you set this option to **Yes**, the worker can edit the reason code when it's shown on the mobile device during counting.</span></span>

> [!NOTE]
> <span data-ttu-id="6217c-177">Przycisk **Inwentaryzacja ciągła** można włączyć dla każdego elementu menu na urządzeniu przenośnym służącym do wykonywania inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="6217c-177">The **Cycle counting** button can be enabled on any mobile device menu item where counting can be done.</span></span> <span data-ttu-id="6217c-178">Przykładem są elementy menu dla inwentaryzacji punktowych, pracy sterowanej przez użytkownika i pracy sterowanej przez system.</span><span class="sxs-lookup"><span data-stu-id="6217c-178">Example include the menu items for spot counts, user-directed work, and system-directed work.</span></span>

## <a name="cycle-count-approvals"></a><span data-ttu-id="6217c-179">Zatwierdzenia inwentaryzacji ciągłej</span><span class="sxs-lookup"><span data-stu-id="6217c-179">Cycle count approvals</span></span>

<span data-ttu-id="6217c-180">Przed zatwierdzeniem inwentaryzacji użytkownik może zmienić kod przyczyny skojarzony z inwentaryzacją.</span><span class="sxs-lookup"><span data-stu-id="6217c-180">Before a count is approved, the user can change the reason code that is associated with the count.</span></span> <span data-ttu-id="6217c-181">Po zatwierdzeniu inwentaryzacji kod przyczyny jest wprowadzany w wierszach arkusza inwentaryzacyjnego.</span><span class="sxs-lookup"><span data-stu-id="6217c-181">When the count is approved, the reason code is entered on the counting journal lines.</span></span>

### <a name="modify-cycle-count-approvals"></a><span data-ttu-id="6217c-182">Modyfikowanie zatwierdzeń inwentaryzacji ciągłej</span><span class="sxs-lookup"><span data-stu-id="6217c-182">Modify cycle count approvals</span></span>

1. <span data-ttu-id="6217c-183">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Inwentaryzacja ciągła** \> **Praca inwentaryzacji ciągłej oczekuje na przegląd**.</span><span class="sxs-lookup"><span data-stu-id="6217c-183">Select **Warehouse management** \> **Cycle counting** \> **Cycle count work pending review**.</span></span>
2. <span data-ttu-id="6217c-184">Wybierz opcję **Inwentaryzacja ciągła**, a następnie w polu **Kod przyczyny** wybierz nowy kod przyczyny.</span><span class="sxs-lookup"><span data-stu-id="6217c-184">Select **Cycle counting**, and then, in the **Reason code** field, select a new reason code.</span></span>

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a><span data-ttu-id="6217c-185">Modyfikowanie elementu menu na urządzeniu przenośnym dla korekty wewnętrznej i zewnętrznej</span><span class="sxs-lookup"><span data-stu-id="6217c-185">Modify the mobile device menu item for Adjustment in and Adjustment out</span></span>

1. <span data-ttu-id="6217c-186">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Urządzenie przenośne** \> **Elementy menu urządzenia przenośnego**, a następnie wybierz opcję **Korekta wewnętrzna i zewnętrzna**.</span><span class="sxs-lookup"><span data-stu-id="6217c-186">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**, and then select **Adjustment in and out**.</span></span>
2. <span data-ttu-id="6217c-187">W opcji **Użyj istniejącej pracy** ustaw wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="6217c-187">Set the **Use existing work** option to **No**.</span></span>
3. <span data-ttu-id="6217c-188">W polu **Proces tworzenia pracy** wybierz opcję **Korekta wewnętrzna**.</span><span class="sxs-lookup"><span data-stu-id="6217c-188">In the **Work creation process** field, select **Adjustment in**.</span></span>

<span data-ttu-id="6217c-189">Następujące pola zostaną dodane do elementu menu na urządzeniu przenośnym po wybraniu opcji **Korekta wewnętrzna** lub **Korekta zewnętrzna** w trakcie procesu tworzenia pracy:</span><span class="sxs-lookup"><span data-stu-id="6217c-189">The following fields will be added to the mobile device menu item when **Adjustment in** or **Adjustment out** is selected during the work creation process:</span></span>

- <span data-ttu-id="6217c-190">Domyślny kod przyczyny zliczania</span><span class="sxs-lookup"><span data-stu-id="6217c-190">Default counting reason code</span></span>
- <span data-ttu-id="6217c-191">Wyświetl kod przyczyny zliczania</span><span class="sxs-lookup"><span data-stu-id="6217c-191">Display counting reason code</span></span>
- <span data-ttu-id="6217c-192">Edytuj kod przyczyny zliczania</span><span class="sxs-lookup"><span data-stu-id="6217c-192">Edit counting reason code</span></span>
