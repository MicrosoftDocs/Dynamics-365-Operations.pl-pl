---
title: Konfigurowanie nazw pól aplikacji w aplikacji magazynowej
description: W tym temacie opisano sposób definiowania i konfigurowania nazw i priorytetów pól aplikacji magazynowej w usłudze Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7a4cfe62aa50c423adfd116a81d7962c30b25fcf
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530496"
---
# <a name="configure-app-field-names-in-the-warehouse-app"></a><span data-ttu-id="6a132-103">Konfigurowanie nazw pól aplikacji w aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="6a132-103">Configure app field names in the warehouse app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6a132-104">W tym temacie opisano sposób definiowania i konfigurowania nazw i priorytetów pól aplikacji magazynowej w usłudze Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6a132-104">This topic describes how to define and configure warehouse app field names and priorities in Dynamics 365 Supply Chain Management.</span></span> 

> [!NOTE]
> <span data-ttu-id="6a132-105">Ten temat dotyczy funkcji w module Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="6a132-105">This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="6a132-106">Nie ma zastosowania do funkcji w module Zarządzanie zapasami.</span><span class="sxs-lookup"><span data-stu-id="6a132-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="6a132-107">Magazynowanie to aplikacja umożliwiająca wykonywanie zadań magazynowych.</span><span class="sxs-lookup"><span data-stu-id="6a132-107">Warehousing is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="6a132-108">Można zdefiniować i skonfigurować nazwy pól używanych w aplikacji, a także skonfigurować priorytety, do których te nazwy pól powinny być przypisane.</span><span class="sxs-lookup"><span data-stu-id="6a132-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="6a132-109">W tym temacie wyjaśniono sposób definiowania i konfigurowania nazw i priorytetów tych pól aplikacji magazynowej oraz ich używanie w aplikacji Magazynowanie.</span><span class="sxs-lookup"><span data-stu-id="6a132-109">This topic explains how to define and configure these warehouse app field names and priorities, and how they are used in Warehousing.</span></span> <span data-ttu-id="6a132-110">Aby uzyskać szczegółowe informacje dotyczące konfigurowania połączenia z aplikacją magazynową, skorzystaj z samouczka [Omówienie instalowania i konfiguracji aplikacji magazynowej](install-configure-warehousing-app.md).</span><span class="sxs-lookup"><span data-stu-id="6a132-110">For detailed information about how to configure the connection to FWarehousing, refer to the tutorial [Install and configure the warehouse app overview](install-configure-warehousing-app.md).</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="6a132-111">Konfigurowanie nazw pól w aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="6a132-111">Configure warehouse app field names</span></span>

<span data-ttu-id="6a132-112">Gdy używasz aplikacji Magazynowanie na urządzeniu mobilnym, można na stronie **Nazwy pól w aplikacji Magazynowanie** skonfigurować sposób wyświetlania metadanych na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="6a132-112">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="6a132-113">W nowej firmie wybierz opcję **Utwórz konfigurację domyślną**, aby wygenerować wszystkie nazwy pól, które będą używane w przepływach pracy magazynu na urządzeniu, a następnie przypisz do nich preferowany tryb wprowadzania i typ danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="6a132-113">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="6a132-114">Po wygenerowaniu wszystkich nazw pól można wybrać następujące opcje wprowadzania danych:</span><span class="sxs-lookup"><span data-stu-id="6a132-114">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a132-115">Opcja</span><span class="sxs-lookup"><span data-stu-id="6a132-115">Option</span></span></th>
<th><span data-ttu-id="6a132-116">opis</span><span class="sxs-lookup"><span data-stu-id="6a132-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6a132-117">Preferowany tryb wprowadzania</span><span class="sxs-lookup"><span data-stu-id="6a132-117">Preferred input mode</span></span></td>
<td><span data-ttu-id="6a132-118">Ta opcja określa, czy dla wybranej nazwy pola ma być wyświetlane pole wprowadzania danych przez skanowania, czy przez ręczne wpisywanie.</span><span class="sxs-lookup"><span data-stu-id="6a132-118">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="6a132-119">Rozróżnianie pól jest przydatne, jeśli dla pola są używane kody kreskowe.</span><span class="sxs-lookup"><span data-stu-id="6a132-119">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="6a132-120"><strong>Uwaga:</strong> Dla nazw pól o preferowanym trybie wprowadzania <strong>Skanowanie</strong> można wprowadzać dane ręcznie, jeśli kod kreskowy jest uszkodzony lub nieczytelny.</span><span class="sxs-lookup"><span data-stu-id="6a132-120"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6a132-121">Typ danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="6a132-121">Input type</span></span></td>
<td><span data-ttu-id="6a132-122">Ta opcja określa, który tryb wprowadzania powinien być stosowany do wybranej nazwy pola.</span><span class="sxs-lookup"><span data-stu-id="6a132-122">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="6a132-123">Dostępne są cztery opcje:</span><span class="sxs-lookup"><span data-stu-id="6a132-123">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="6a132-124"><strong>Wybór</strong> - Zawiera listę opcji do wyboru.</span><span class="sxs-lookup"><span data-stu-id="6a132-124"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="6a132-125">Nazwy pól z tą opcją nie mogą być edytowane.</span><span class="sxs-lookup"><span data-stu-id="6a132-125">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="6a132-126"><strong>Data</strong> - Nazwy pól określone jako daty będą pokazywały format daty z etykietą.</span><span class="sxs-lookup"><span data-stu-id="6a132-126"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="6a132-127">Dzięki temu pracownicy magazynu łatwiej widzą, w jakim formacie należy wpisać datę.</span><span class="sxs-lookup"><span data-stu-id="6a132-127">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="6a132-128">Nazwy pól z tą opcją nie mogą być edytowane.</span><span class="sxs-lookup"><span data-stu-id="6a132-128">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="6a132-129"><strong>Alfa</strong> - Gdy wybierzesz tę opcję, podczas ręcznego wprowadzania informacji w aplikacji będzie używana klawiatury urządzenia.</span><span class="sxs-lookup"><span data-stu-id="6a132-129"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="6a132-130">Zachowanie klawiatury można zmieniać w zależności od wykorzystywanego urządzenia.</span><span class="sxs-lookup"><span data-stu-id="6a132-130">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="6a132-131"><strong>Numeryczna</strong> - Dla nazw pól wykorzystujących tylko numeryczne dane wejściowe można wybrać tę opcję, a zamiast klawiatury urządzenia będzie wyświetlana niestandardowa klawiatura numeryczna z polem wprowadzania.</span><span class="sxs-lookup"><span data-stu-id="6a132-131"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="6a132-132">Konfigurowanie priorytetu pól w aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="6a132-132">Configure warehouse app field priority</span></span>

<span data-ttu-id="6a132-133">Na stronie **Priorytet pola w aplikacji magazynowej** można umieścić nazwy pól w różnych grupach priorytetu.</span><span class="sxs-lookup"><span data-stu-id="6a132-133">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="6a132-134">Dzięki temu można zdecydować, które informacje mają być wyświetlane na głównej stronie zadań, gdy pracownicy magazynu wykonują zadania za pomocą aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6a132-134">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="6a132-135">Jeśli klikniesz opcję **Utwórz konfigurację domyślną**, zostanie wygenerowany domyślny zestaw grup priorytetu.</span><span class="sxs-lookup"><span data-stu-id="6a132-135">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="6a132-136">Można utworzyć dowolną potrzebną liczbę grup priorytetu, ale tylko trzy będą wyświetlane na stronie zadania.</span><span class="sxs-lookup"><span data-stu-id="6a132-136">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="6a132-137">Gdy system wysyła metadane do aplikacji, przypisuje każdemu polu względny priorytet w zależności od jego grupy priorytetu, a aplikacja wyświetla na stronie zadania pierwsze trzy grupy priorytetu zawarte w metadanych.</span><span class="sxs-lookup"><span data-stu-id="6a132-137">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="6a132-138">Pozostała zawartość metadanych będzie wyświetlana na pomocniczej stronie szczegółów.</span><span class="sxs-lookup"><span data-stu-id="6a132-138">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="6a132-139">Poniższa tabela pokazuje przykład pięciu grup priorytetu.</span><span class="sxs-lookup"><span data-stu-id="6a132-139">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a132-140">Grupa priorytetu</span><span class="sxs-lookup"><span data-stu-id="6a132-140">Priority group</span></span></th>
<th><span data-ttu-id="6a132-141">Przypisane pola</span><span class="sxs-lookup"><span data-stu-id="6a132-141">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="6a132-142">Priorytet 10</span><span class="sxs-lookup"><span data-stu-id="6a132-142">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="6a132-143">Element</span><span class="sxs-lookup"><span data-stu-id="6a132-143">Item</span></span></li>
<li><span data-ttu-id="6a132-144">Ilość</span><span class="sxs-lookup"><span data-stu-id="6a132-144">Quantity</span></span></li>
<li><span data-ttu-id="6a132-145">Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="6a132-145">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="6a132-146">Priorytet 20</span><span class="sxs-lookup"><span data-stu-id="6a132-146">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="6a132-147">Stanowisko w grupie</span><span class="sxs-lookup"><span data-stu-id="6a132-147">Cluster position</span></span></li>
<li><span data-ttu-id="6a132-148">Grupa</span><span class="sxs-lookup"><span data-stu-id="6a132-148">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="6a132-149">Priorytet 30</span><span class="sxs-lookup"><span data-stu-id="6a132-149">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="6a132-150">Opis towaru</span><span class="sxs-lookup"><span data-stu-id="6a132-150">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="6a132-151">Priorytet 40</span><span class="sxs-lookup"><span data-stu-id="6a132-151">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="6a132-152">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="6a132-152">Configuration</span></span></li>
<li><span data-ttu-id="6a132-153">Kolor</span><span class="sxs-lookup"><span data-stu-id="6a132-153">Color</span></span></li>
<li><span data-ttu-id="6a132-154">Rozmiar</span><span class="sxs-lookup"><span data-stu-id="6a132-154">Size</span></span></li>
<li><span data-ttu-id="6a132-155">Styl</span><span class="sxs-lookup"><span data-stu-id="6a132-155">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="6a132-156">Priorytet 50</span><span class="sxs-lookup"><span data-stu-id="6a132-156">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="6a132-157">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="6a132-157">Location</span></span></li>
<li><span data-ttu-id="6a132-158">Numer identyfikacyjny</span><span class="sxs-lookup"><span data-stu-id="6a132-158">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a132-159">Na przykład gdy pracownik magazynu wykonuje zadanie na urządzeniu przenośnym, a metadane, które będą wyświetlane w aplikacji, składają się z następujących pól:</span><span class="sxs-lookup"><span data-stu-id="6a132-159">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="6a132-160">Element</span><span class="sxs-lookup"><span data-stu-id="6a132-160">Item</span></span>
-   <span data-ttu-id="6a132-161">Ilość</span><span class="sxs-lookup"><span data-stu-id="6a132-161">Quantity</span></span>
-   <span data-ttu-id="6a132-162">Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="6a132-162">Unit of measure</span></span>
-   <span data-ttu-id="6a132-163">Opis towaru</span><span class="sxs-lookup"><span data-stu-id="6a132-163">Item description</span></span>
-   <span data-ttu-id="6a132-164">Rozmiar i lokalizacja</span><span class="sxs-lookup"><span data-stu-id="6a132-164">Size and Location</span></span>

<span data-ttu-id="6a132-165">Na podstawie priorytetu pól aplikacji magazynowej skonfigurowanego w tabeli powyżej następujące 3 wiersze informacji będą wyświetlane na stronie zadania:</span><span class="sxs-lookup"><span data-stu-id="6a132-165">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="6a132-166">Wiersz 1: Towar, Ilość, Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="6a132-166">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="6a132-167">Wiersz 2: Opis towaru</span><span class="sxs-lookup"><span data-stu-id="6a132-167">Row 2: Item description</span></span>
-   <span data-ttu-id="6a132-168">Wiersz 3: Rozmiar</span><span class="sxs-lookup"><span data-stu-id="6a132-168">Row 3: Size</span></span>

<span data-ttu-id="6a132-169">Pozostałe metadane, na przykład Lokalizacja, nie będą wyświetlane na stronie zadania, ale będą wyświetlane na stronie szczegółów.</span><span class="sxs-lookup"><span data-stu-id="6a132-169">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="6a132-170">Aby dowiedzieć się więcej i zobaczyć przykłady interfejsu użytkownika, należy się zapoznać z wpisem na blogu [Zapowiedź aplikacji Finance and Operations — Magazynowanie](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="6a132-170">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

<a name="additional-resources"></a><span data-ttu-id="6a132-171">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6a132-171">Additional resources</span></span>
--------

[<span data-ttu-id="6a132-172">Omówienie instalowania i konfiguracji aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="6a132-172">Install and configure the warehouse app overview</span></span>](install-configure-warehousing-app.md)
