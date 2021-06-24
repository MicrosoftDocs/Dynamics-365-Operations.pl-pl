---
title: Konfigurowanie pól aplikacji mobilnej Warehouse Management
description: W tym temacie opisano, jak definiować i konfigurować nazwy i priorytety pól wyświetlanych w aplikacji mobilnej Warehouse Management.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bc224d3fd6cf5b111f61066202090f10ba4a7e8a
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189257"
---
# <a name="configure-fields-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="1ce89-103">Konfigurowanie pól aplikacji mobilnej Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="1ce89-103">Configure fields for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ce89-104">W tym temacie opisano, jak definiować i konfigurować nazwy i priorytety pól wyświetlanych w aplikacji mobilnej Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="1ce89-104">This topic describes how to define and configure names and priorities of fields shown in the Warehouse Management mobile app.</span></span>

> [!NOTE]
> <span data-ttu-id="1ce89-105">Ten temat dotyczy funkcji w module Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="1ce89-105">This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="1ce89-106">Nie ma zastosowania do funkcji w module Zarządzanie zapasami.</span><span class="sxs-lookup"><span data-stu-id="1ce89-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="1ce89-107">Aplikacja mobilna Warehouse Management to aplikacja, za pomocą której można wykonywać zadania magazynowe.</span><span class="sxs-lookup"><span data-stu-id="1ce89-107">The Warehouse Management mobile app is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="1ce89-108">Można zdefiniować i skonfigurować nazwy pól używanych w aplikacji, a także skonfigurować priorytety, do których te nazwy pól powinny być przypisane.</span><span class="sxs-lookup"><span data-stu-id="1ce89-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="1ce89-109">W tym temacie wyjaśniono, jak definiować i konfigurować nazwy i priorytety tych pól aplikacji mobilnej Warehouse Management oraz sposób ich używania.</span><span class="sxs-lookup"><span data-stu-id="1ce89-109">This topic explains how to define and configure these Warehouse Management mobile app field names and priorities, and how they are used.</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="1ce89-110">Konfigurowanie nazw pól w aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="1ce89-110">Configure warehouse app field names</span></span>

<span data-ttu-id="1ce89-111">Gdy używasz aplikacji Magazynowanie na urządzeniu mobilnym, można na stronie **Nazwy pól w aplikacji Magazynowanie** skonfigurować sposób wyświetlania metadanych na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="1ce89-111">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="1ce89-112">W nowej firmie wybierz opcję **Utwórz konfigurację domyślną**, aby wygenerować wszystkie nazwy pól, które będą używane w przepływach pracy magazynu na urządzeniu, a następnie przypisz do nich preferowany tryb wprowadzania i typ danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="1ce89-112">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="1ce89-113">Po wygenerowaniu wszystkich nazw pól można wybrać następujące opcje wprowadzania danych:</span><span class="sxs-lookup"><span data-stu-id="1ce89-113">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ce89-114">Opcja</span><span class="sxs-lookup"><span data-stu-id="1ce89-114">Option</span></span></th>
<th><span data-ttu-id="1ce89-115">opis</span><span class="sxs-lookup"><span data-stu-id="1ce89-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1ce89-116">Preferowany tryb wprowadzania</span><span class="sxs-lookup"><span data-stu-id="1ce89-116">Preferred input mode</span></span></td>
<td><span data-ttu-id="1ce89-117">Ta opcja określa, czy dla wybranej nazwy pola ma być wyświetlane pole wprowadzania danych przez skanowania, czy przez ręczne wpisywanie.</span><span class="sxs-lookup"><span data-stu-id="1ce89-117">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="1ce89-118">Rozróżnianie pól jest przydatne, jeśli dla pola są używane kody kreskowe.</span><span class="sxs-lookup"><span data-stu-id="1ce89-118">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="1ce89-119"><strong>Uwaga:</strong> Dla nazw pól o preferowanym trybie wprowadzania <strong>Skanowanie</strong> można wprowadzać dane ręcznie, jeśli kod kreskowy jest uszkodzony lub nieczytelny.</span><span class="sxs-lookup"><span data-stu-id="1ce89-119"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1ce89-120">Typ danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="1ce89-120">Input type</span></span></td>
<td><span data-ttu-id="1ce89-121">Ta opcja określa, który tryb wprowadzania powinien być stosowany do wybranej nazwy pola.</span><span class="sxs-lookup"><span data-stu-id="1ce89-121">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="1ce89-122">Dostępne są cztery opcje:</span><span class="sxs-lookup"><span data-stu-id="1ce89-122">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="1ce89-123"><strong>Wybór</strong> - Zawiera listę opcji do wyboru.</span><span class="sxs-lookup"><span data-stu-id="1ce89-123"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="1ce89-124">Nazwy pól z tą opcją nie mogą być edytowane.</span><span class="sxs-lookup"><span data-stu-id="1ce89-124">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="1ce89-125"><strong>Data</strong> - Nazwy pól określone jako daty będą pokazywały format daty z etykietą.</span><span class="sxs-lookup"><span data-stu-id="1ce89-125"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="1ce89-126">Dzięki temu pracownicy magazynu łatwiej widzą, w jakim formacie należy wpisać datę.</span><span class="sxs-lookup"><span data-stu-id="1ce89-126">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="1ce89-127">Nazwy pól z tą opcją nie mogą być edytowane.</span><span class="sxs-lookup"><span data-stu-id="1ce89-127">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="1ce89-128"><strong>Alfa</strong> - Gdy wybierzesz tę opcję, podczas ręcznego wprowadzania informacji w aplikacji będzie używana klawiatury urządzenia.</span><span class="sxs-lookup"><span data-stu-id="1ce89-128"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="1ce89-129">Zachowanie klawiatury można zmieniać w zależności od wykorzystywanego urządzenia.</span><span class="sxs-lookup"><span data-stu-id="1ce89-129">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="1ce89-130"><strong>Numeryczna</strong> - Dla nazw pól wykorzystujących tylko numeryczne dane wejściowe można wybrać tę opcję, a zamiast klawiatury urządzenia będzie wyświetlana niestandardowa klawiatura numeryczna z polem wprowadzania.</span><span class="sxs-lookup"><span data-stu-id="1ce89-130"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="1ce89-131">Konfigurowanie priorytetu pól w aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="1ce89-131">Configure warehouse app field priority</span></span>

<span data-ttu-id="1ce89-132">Na stronie **Priorytet pola w aplikacji magazynowej** można umieścić nazwy pól w różnych grupach priorytetu.</span><span class="sxs-lookup"><span data-stu-id="1ce89-132">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="1ce89-133">Dzięki temu można zdecydować, które informacje mają być wyświetlane na głównej stronie zadań, gdy pracownicy magazynu wykonują zadania za pomocą aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1ce89-133">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="1ce89-134">Jeśli klikniesz opcję **Utwórz konfigurację domyślną**, zostanie wygenerowany domyślny zestaw grup priorytetu.</span><span class="sxs-lookup"><span data-stu-id="1ce89-134">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="1ce89-135">Można utworzyć dowolną potrzebną liczbę grup priorytetu, ale tylko trzy będą wyświetlane na stronie zadania.</span><span class="sxs-lookup"><span data-stu-id="1ce89-135">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="1ce89-136">Gdy system wysyła metadane do aplikacji, przypisuje każdemu polu względny priorytet w zależności od jego grupy priorytetu, a aplikacja wyświetla na stronie zadania pierwsze trzy grupy priorytetu zawarte w metadanych.</span><span class="sxs-lookup"><span data-stu-id="1ce89-136">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="1ce89-137">Pozostała zawartość metadanych będzie wyświetlana na pomocniczej stronie szczegółów.</span><span class="sxs-lookup"><span data-stu-id="1ce89-137">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="1ce89-138">Poniższa tabela pokazuje przykład pięciu grup priorytetu.</span><span class="sxs-lookup"><span data-stu-id="1ce89-138">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ce89-139">Grupa priorytetu</span><span class="sxs-lookup"><span data-stu-id="1ce89-139">Priority group</span></span></th>
<th><span data-ttu-id="1ce89-140">Przypisane pola</span><span class="sxs-lookup"><span data-stu-id="1ce89-140">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="1ce89-141">Priorytet 10</span><span class="sxs-lookup"><span data-stu-id="1ce89-141">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="1ce89-142">Element</span><span class="sxs-lookup"><span data-stu-id="1ce89-142">Item</span></span></li>
<li><span data-ttu-id="1ce89-143">Ilość</span><span class="sxs-lookup"><span data-stu-id="1ce89-143">Quantity</span></span></li>
<li><span data-ttu-id="1ce89-144">Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="1ce89-144">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="1ce89-145">Priorytet 20</span><span class="sxs-lookup"><span data-stu-id="1ce89-145">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="1ce89-146">Stanowisko w grupie</span><span class="sxs-lookup"><span data-stu-id="1ce89-146">Cluster position</span></span></li>
<li><span data-ttu-id="1ce89-147">Grupa</span><span class="sxs-lookup"><span data-stu-id="1ce89-147">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="1ce89-148">Priorytet 30</span><span class="sxs-lookup"><span data-stu-id="1ce89-148">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="1ce89-149">Opis towaru</span><span class="sxs-lookup"><span data-stu-id="1ce89-149">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="1ce89-150">Priorytet 40</span><span class="sxs-lookup"><span data-stu-id="1ce89-150">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="1ce89-151">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="1ce89-151">Configuration</span></span></li>
<li><span data-ttu-id="1ce89-152">Kolor</span><span class="sxs-lookup"><span data-stu-id="1ce89-152">Color</span></span></li>
<li><span data-ttu-id="1ce89-153">Rozmiar</span><span class="sxs-lookup"><span data-stu-id="1ce89-153">Size</span></span></li>
<li><span data-ttu-id="1ce89-154">Styl</span><span class="sxs-lookup"><span data-stu-id="1ce89-154">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="1ce89-155">Priorytet 50</span><span class="sxs-lookup"><span data-stu-id="1ce89-155">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="1ce89-156">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="1ce89-156">Location</span></span></li>
<li><span data-ttu-id="1ce89-157">Numer identyfikacyjny</span><span class="sxs-lookup"><span data-stu-id="1ce89-157">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1ce89-158">Na przykład gdy pracownik magazynu wykonuje zadanie na urządzeniu przenośnym, a metadane, które będą wyświetlane w aplikacji, składają się z następujących pól:</span><span class="sxs-lookup"><span data-stu-id="1ce89-158">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="1ce89-159">Element</span><span class="sxs-lookup"><span data-stu-id="1ce89-159">Item</span></span>
-   <span data-ttu-id="1ce89-160">Ilość</span><span class="sxs-lookup"><span data-stu-id="1ce89-160">Quantity</span></span>
-   <span data-ttu-id="1ce89-161">Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="1ce89-161">Unit of measure</span></span>
-   <span data-ttu-id="1ce89-162">Opis towaru</span><span class="sxs-lookup"><span data-stu-id="1ce89-162">Item description</span></span>
-   <span data-ttu-id="1ce89-163">Rozmiar i lokalizacja</span><span class="sxs-lookup"><span data-stu-id="1ce89-163">Size and Location</span></span>

<span data-ttu-id="1ce89-164">Na podstawie priorytetu pól aplikacji magazynowej skonfigurowanego w tabeli powyżej następujące 3 wiersze informacji będą wyświetlane na stronie zadania:</span><span class="sxs-lookup"><span data-stu-id="1ce89-164">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="1ce89-165">Wiersz 1: Towar, Ilość, Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="1ce89-165">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="1ce89-166">Wiersz 2: Opis towaru</span><span class="sxs-lookup"><span data-stu-id="1ce89-166">Row 2: Item description</span></span>
-   <span data-ttu-id="1ce89-167">Wiersz 3: Rozmiar</span><span class="sxs-lookup"><span data-stu-id="1ce89-167">Row 3: Size</span></span>

<span data-ttu-id="1ce89-168">Pozostałe metadane, na przykład Lokalizacja, nie będą wyświetlane na stronie zadania, ale będą wyświetlane na stronie szczegółów.</span><span class="sxs-lookup"><span data-stu-id="1ce89-168">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="1ce89-169">Aby dowiedzieć się więcej i zobaczyć przykłady interfejsu użytkownika, należy się zapoznać z wpisem na blogu [Zapowiedź aplikacji Finance and Operations — Magazynowanie](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="1ce89-169">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1ce89-170">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1ce89-170">Additional resources</span></span>

[<span data-ttu-id="1ce89-171">Instalowanie i łączenie aplikacji mobilnej Zarządzanie magazynem</span><span class="sxs-lookup"><span data-stu-id="1ce89-171">Install and connect the Warehouse Management mobile app</span></span>](../warehousing/install-configure-warehouse-management-app.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]