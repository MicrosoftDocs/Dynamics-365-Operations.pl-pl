---
title: Implementowanie pól niestandardowych aplikacji mobilnej Microsoft Dynamics 365 Project Timesheet w systemach iOS i Android
description: W tym temacie przedstawiono typowe wzorce używania rozszerzeń do implementowania pól niestandardowych.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: 48854c15e429d51dcf30ea804eb636dee7965443
ms.sourcegitcommit: a356299be9a593990d9948b3a6b754bd058a5b3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/21/2020
ms.locfileid: "3080779"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a><span data-ttu-id="8c59e-103">Implementowanie pól niestandardowych aplikacji mobilnej Microsoft Dynamics 365 Project Timesheet w systemach iOS i Android</span><span class="sxs-lookup"><span data-stu-id="8c59e-103">Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8c59e-104">W tym temacie przedstawiono typowe wzorce używania rozszerzeń do implementowania pól niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-104">This topic provides common patterns for using extensions to implement custom fields.</span></span> <span data-ttu-id="8c59e-105">Omawiane są następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="8c59e-105">The following topics are covered:</span></span>

- <span data-ttu-id="8c59e-106">Różne typy danych obsługiwane przez strukturę pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="8c59e-106">The various data types that the custom field framework supports</span></span>
- <span data-ttu-id="8c59e-107">Sposób wyświetlania pól tylko do odczytu lub edytowalnych we wpisach karty czasu pracy oraz zapisywania wartości wprowadzonych przez użytkownika z powrotem do bazy danych</span><span class="sxs-lookup"><span data-stu-id="8c59e-107">How to show read-only or editable fields on timesheet entries, and save user-provided values back to the database</span></span>
- <span data-ttu-id="8c59e-108">Sposób wyświetlania pól tylko do odczytu w nagłówku karty czasu pracy</span><span class="sxs-lookup"><span data-stu-id="8c59e-108">How to show read-only fields on the timesheet header</span></span>
- <span data-ttu-id="8c59e-109">Sposób integrowania innej niestandardowej logiki biznesowej w celu wprowadzania wartości domyślnych w polach i przeprowadzania dodatkowej weryfikacji</span><span class="sxs-lookup"><span data-stu-id="8c59e-109">How to integrate other custom business logic to enter default values in fields and do additional validation</span></span>

## <a name="audience"></a><span data-ttu-id="8c59e-110">Odbiorcy</span><span class="sxs-lookup"><span data-stu-id="8c59e-110">Audience</span></span>

<span data-ttu-id="8c59e-111">Ten temat jest przeznaczony dla deweloperów integrujących pola niestandardowe w aplikacji mobilnej Microsoft Dynamics 365 Project Timesheet dostępnej na systemy Apple iOS i Google Android.</span><span class="sxs-lookup"><span data-stu-id="8c59e-111">This topic is intended for developers who are integrating their custom fields into the Microsoft Dynamics 365 Project Timesheet mobile application that is available for Apple iOS and Google Android.</span></span> <span data-ttu-id="8c59e-112">Przyjmuje się, że czytelnicy umieją programować w języku X++ i znają funkcje karty czasu pracy projektu.</span><span class="sxs-lookup"><span data-stu-id="8c59e-112">The assumption is that readers are familiar with X++ development and project timesheet functionality.</span></span>

## <a name="data-contract--tstimesheetcustomfield-x-class"></a><span data-ttu-id="8c59e-113">Umowa dotycząca danych — klasa X++ TSTimesheetCustomField</span><span class="sxs-lookup"><span data-stu-id="8c59e-113">Data contract – TSTimesheetCustomField X++ class</span></span>

<span data-ttu-id="8c59e-114">Klasa **TSTimesheetCustomField** jest klasą umowy dotyczącej danych języka X++, która reprezentuje informacje o polu niestandardowym dla funkcji karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="8c59e-114">The **TSTimesheetCustomField** class is the X++ data contract class that represents information about a custom field for timesheet functionality.</span></span> <span data-ttu-id="8c59e-115">Listy obiektów pól niestandardowych są przekazywane zarówno w umowie dotyczącej danych TSTimesheetDetails, jak i umowie dotyczącej danych TSTimesheetEntry w celu wyświetlania pól niestandardowych w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="8c59e-115">Lists of the custom field objects are passed on both the TSTimesheetDetails data contract and the TSTimesheetEntry data contract to show custom fields in the mobile app.</span></span>

- <span data-ttu-id="8c59e-116">**TSTimesheetDetails** — umowa dotycząca nagłówka karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="8c59e-116">**TSTimesheetDetails** - The timesheet header contract.</span></span>
- <span data-ttu-id="8c59e-117">**TSTimesheetEntry** — umowa dotycząca transakcji karty czasu pracy</span><span class="sxs-lookup"><span data-stu-id="8c59e-117">**TSTimesheetEntry** - The timesheet transaction contract.</span></span> <span data-ttu-id="8c59e-118">Grupy tych obiektów, których same informacje o projekcie i wartość **timesheetLineRecId** są takie same, tworzą wiersz.</span><span class="sxs-lookup"><span data-stu-id="8c59e-118">Groups of these objects that have the same project information and **timesheetLineRecId** value constitute a line.</span></span>

### <a name="fieldbasetype-types"></a><span data-ttu-id="8c59e-119">fieldBaseType (typy)</span><span class="sxs-lookup"><span data-stu-id="8c59e-119">fieldBaseType (Types)</span></span>

<span data-ttu-id="8c59e-120">Właściwość **FieldBaseType** obiektu **TsTimesheetCustom** określa typ pola, które pojawia się w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-120">The **FieldBaseType** property on the **TsTimesheetCustom** object determines the type of the field that appears in the app.</span></span> <span data-ttu-id="8c59e-121">Obsługiwane są następujące wartości **Typu**:</span><span class="sxs-lookup"><span data-stu-id="8c59e-121">The following **Types** values that are supported.</span></span>

| <span data-ttu-id="8c59e-122">Wartości typu</span><span class="sxs-lookup"><span data-stu-id="8c59e-122">Types value</span></span> | <span data-ttu-id="8c59e-123">Typ</span><span class="sxs-lookup"><span data-stu-id="8c59e-123">Type</span></span>              | <span data-ttu-id="8c59e-124">Notatki</span><span class="sxs-lookup"><span data-stu-id="8c59e-124">Notes</span></span> |
|-------------|-------------------|-------|
| <span data-ttu-id="8c59e-125">0</span><span class="sxs-lookup"><span data-stu-id="8c59e-125">0</span></span>           | <span data-ttu-id="8c59e-126">Ciąg (i Wyliczenie)</span><span class="sxs-lookup"><span data-stu-id="8c59e-126">String (and Enum)</span></span> | <span data-ttu-id="8c59e-127">Pole jest wyświetlane jako pole tekstowe.</span><span class="sxs-lookup"><span data-stu-id="8c59e-127">The field appears as a text field.</span></span> |
| <span data-ttu-id="8c59e-128">1</span><span class="sxs-lookup"><span data-stu-id="8c59e-128">1</span></span>           | <span data-ttu-id="8c59e-129">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="8c59e-129">Integer</span></span>           | <span data-ttu-id="8c59e-130">Wartość jest pokazywana jako liczba bez miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-130">The value is shown as a number without decimal places.</span></span> |
| <span data-ttu-id="8c59e-131">2</span><span class="sxs-lookup"><span data-stu-id="8c59e-131">2</span></span>           | <span data-ttu-id="8c59e-132">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="8c59e-132">Real</span></span>              | <span data-ttu-id="8c59e-133">Wartość jest pokazywana jako liczba z miejscami dziesiętnymi.</span><span class="sxs-lookup"><span data-stu-id="8c59e-133">The value is shown as a number that has decimal places.</span></span><p><span data-ttu-id="8c59e-134">Aby w aplikacji była wyświatlana wartość rzeczywista w walucie, należy skorzystać z właściwości **fieldExtenededType**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-134">To show the real value as a currency in the app, use the **fieldExtenededType** property.</span></span> <span data-ttu-id="8c59e-135">Właściwość **numberOfDecimals** służy do ustawiania liczby wyświetlanych miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-135">You can use the **numberOfDecimals** property to set the number of decimal places that are shown.</span></span></p> |
| <span data-ttu-id="8c59e-136">3</span><span class="sxs-lookup"><span data-stu-id="8c59e-136">3</span></span>           | <span data-ttu-id="8c59e-137">Data</span><span class="sxs-lookup"><span data-stu-id="8c59e-137">Date</span></span>              | <span data-ttu-id="8c59e-138">Formaty daty zależą od ustawienia **Format daty, godziny i liczb** użytkownika, które jest określone w sekcji **Preferencje dotyczące języka i kraju/regionu** w oknie **Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-138">Date formats are determined by the user's **Date, times, and number format** setting that is specified under **Language and country/region preference** in **User options**.</span></span> |
| <span data-ttu-id="8c59e-139">4</span><span class="sxs-lookup"><span data-stu-id="8c59e-139">4</span></span>           | <span data-ttu-id="8c59e-140">Wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="8c59e-140">Boolean</span></span>           | |
| <span data-ttu-id="8c59e-141">15</span><span class="sxs-lookup"><span data-stu-id="8c59e-141">15</span></span>          | <span data-ttu-id="8c59e-142">GUID</span><span class="sxs-lookup"><span data-stu-id="8c59e-142">GUID</span></span>              | |
| <span data-ttu-id="8c59e-143">16</span><span class="sxs-lookup"><span data-stu-id="8c59e-143">16</span></span>          | <span data-ttu-id="8c59e-144">Int64</span><span class="sxs-lookup"><span data-stu-id="8c59e-144">Int64</span></span>             | |

- <span data-ttu-id="8c59e-145">Jeśli właściwość **stringOptions** nie została podana w obiekcie **TSTimesheetCustomField**, użytkownikowi jest udostępniane pole tekstu niezależnego.</span><span class="sxs-lookup"><span data-stu-id="8c59e-145">If the **stringOptions** property isn't provided on the **TSTimesheetCustomField** object, a free-text field is provided to the user.</span></span>

    <span data-ttu-id="8c59e-146">Właściwość **stringLength** może służyć do ustawienia maksymalnej długości ciągu, jaką użytkownicy mogą wprowadzać.</span><span class="sxs-lookup"><span data-stu-id="8c59e-146">The **stringLength** property can be used to set the maximum string length that users can enter.</span></span>

- <span data-ttu-id="8c59e-147">Jeśli właściwość **stringOptions** jest podana w obiekcie **TSTimesheetCustomField**, te elementy listy są jedynymi wartościami, które użytkownicy mogą wybierać za pomocą przycisków opcji (przycisków radiowych).</span><span class="sxs-lookup"><span data-stu-id="8c59e-147">If the **stringOptions** property is provided on the **TSTimesheetCustomField** object, those list elements are the only values that users can select by using option buttons (radio buttons).</span></span>

    <span data-ttu-id="8c59e-148">W takim przypadku pole ciągu może pełnić funkcję wartości wyliczenia na potrzeby wprowadzania wartości przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8c59e-148">In this case, the string field can act as an enum value for the purpose of user entry.</span></span> <span data-ttu-id="8c59e-149">Aby zapisać wartość w bazie danych jako wyliczenie, należy ręcznie zmapować wartość ciągu z powrotem na wartość wyliczenia przed zapisaniem jej w bazie danych za pomocą łańcucha poleceń (stosowny przykład jest pokazany w sekcji „Zapisywanie wpisu karty czasu pracy zwrotnie z aplikacji w bazie danych przy użyciu łańcucha poleceń na klasie TSTimesheetEntryService”).</span><span class="sxs-lookup"><span data-stu-id="8c59e-149">To save the value to the database as an enum, manually map the string value back to the enum value before you save to the database by using chain of command (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a><span data-ttu-id="8c59e-150">fieldExtendedType (TSCustomFieldExtendedType)</span><span class="sxs-lookup"><span data-stu-id="8c59e-150">fieldExtendedType (TSCustomFieldExtendedType)</span></span>

<span data-ttu-id="8c59e-151">Ta właściwość służy do formatowania wartości rzeczywistych w walucie.</span><span class="sxs-lookup"><span data-stu-id="8c59e-151">You can use this property to format real values as currency.</span></span> <span data-ttu-id="8c59e-152">Takie podejście ma zastosowanie tylko wtedy, gdy wartością **fieldBaseType** jest **Rzeczywista**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-152">This approach is applicable only when the **fieldBaseType** value is **Real**.</span></span>

- <span data-ttu-id="8c59e-153">**TSCustomFieldExtendedType: brak** — formatowanie nie jest stosowane.</span><span class="sxs-lookup"><span data-stu-id="8c59e-153">**TSCustomFieldExtendedType:None** – No formatting is applied.</span></span>
- <span data-ttu-id="8c59e-154">**TSCustomFieldExtendedType::Waluta** — formatowanie wartości jako waluty.</span><span class="sxs-lookup"><span data-stu-id="8c59e-154">**TSCustomFieldExtendedType::Currency** – Format the value as currency.</span></span>

    <span data-ttu-id="8c59e-155">Jeśli formatowanie waluty jest aktywne, przy użyciu pola **stringValue** można przekazać kod waluty, który ma być wyświetlany w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-155">When currency formatting is active, the **stringValue** field can be used pass the currency code that should be shown in the app.</span></span> <span data-ttu-id="8c59e-156">Wartość jest tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="8c59e-156">The value is a read-only value.</span></span>

    <span data-ttu-id="8c59e-157">Pole **realValue** zawiera kwotę pieniędzy, która ma zostać zapisana w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-157">The **realValue** field contains the money amount that should be saved to the database.</span></span>

### <a name="fieldsection-tscustomfieldsection"></a><span data-ttu-id="8c59e-158">fieldSection (TSCustomFieldSection)</span><span class="sxs-lookup"><span data-stu-id="8c59e-158">fieldSection (TSCustomFieldSection)</span></span>

<span data-ttu-id="8c59e-159">Ta właściwość służy do określania, gdzie w aplikacji ma być wyświetlane pole niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="8c59e-159">You can use this property specify where the custom field should appear in the app.</span></span>

- <span data-ttu-id="8c59e-160">**TSCustomFieldSection::Nagłówek** — pole będzie wyświetlane w sekcji **Wyświetl więcej szczegółów** w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-160">**TSCustomFieldSection::Header** – The field will appear in the **View more details** section in the app.</span></span> <span data-ttu-id="8c59e-161">Te pola są zawsze tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="8c59e-161">These fields are always read-only.</span></span>
- <span data-ttu-id="8c59e-162">**TSCustomFieldSection::Wiersz** — pole będzie wyświetlane po wszystkich polach gotowych wierszy we wpisach karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="8c59e-162">**TSCustomFieldSection::Line** – The field will appear after all the out-of-box line fields on timesheet entries.</span></span> <span data-ttu-id="8c59e-163">Mogą to być pola z możliwością edycji lub tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="8c59e-163">These fields can be either editable or read-only.</span></span>

### <a name="fieldname-fieldnameshort"></a><span data-ttu-id="8c59e-164">fieldName (FieldNameShort)</span><span class="sxs-lookup"><span data-stu-id="8c59e-164">fieldName (FieldNameShort)</span></span>

<span data-ttu-id="8c59e-165">Ta właściwość identyfikuje pole, gdy wartości dostarczone przez aplikację są zapisywane z powrotem w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-165">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="tablename-tablenameshort"></a><span data-ttu-id="8c59e-166">tableName (TableNameShort)</span><span class="sxs-lookup"><span data-stu-id="8c59e-166">tableName (TableNameShort)</span></span>

<span data-ttu-id="8c59e-167">Ta właściwość identyfikuje pole, gdy wartości dostarczone przez aplikację są zapisywane z powrotem w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-167">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="iseditable-noyes"></a><span data-ttu-id="8c59e-168">isEditable (NoYes)</span><span class="sxs-lookup"><span data-stu-id="8c59e-168">isEditable (NoYes)</span></span>

<span data-ttu-id="8c59e-169">Jeśli użytkownicy mają mieć możliwość edytowania pola w sekcji wpisu karty czasy pracy, należy ustawić wartość **Tak** tej właściwości.</span><span class="sxs-lookup"><span data-stu-id="8c59e-169">Set this property to **Yes** to specify that the field in the timesheet entry section should be editable by users.</span></span> <span data-ttu-id="8c59e-170">Jeśli pole ma być tylko do odczytu, należy ustawić wartość **Nie** właściwości.</span><span class="sxs-lookup"><span data-stu-id="8c59e-170">Set the property to **No** to make the field read-only.</span></span>

### <a name="ismandatory-noyes"></a><span data-ttu-id="8c59e-171">isMandatory (NoYes)</span><span class="sxs-lookup"><span data-stu-id="8c59e-171">isMandatory (NoYes)</span></span>

<span data-ttu-id="8c59e-172">Jeśli pole w sekcji wpisu karty czasy pracy ma być obowiązkowe, należy ustawić wartość **Tak** tej właściwości.</span><span class="sxs-lookup"><span data-stu-id="8c59e-172">Set this property to **Yes** to specify that the field in the timesheet entry section should be mandatory.</span></span>

### <a name="label-str"></a><span data-ttu-id="8c59e-173">label (str)</span><span class="sxs-lookup"><span data-stu-id="8c59e-173">label (str)</span></span>

<span data-ttu-id="8c59e-174">Ta właściwość określa etykietę wyświetlaną obok pola w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-174">This property specifies the label that is shown next the field in the app.</span></span>

### <a name="stringoptions-list-of-strings"></a><span data-ttu-id="8c59e-175">stringOptions (lista ciągów)</span><span class="sxs-lookup"><span data-stu-id="8c59e-175">stringOptions (List of Strings)</span></span>

<span data-ttu-id="8c59e-176">Ta właściwość ma znaczenie tylko wtedy, gdy ustawioną wartością właściwości **fieldBaseType** jest **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-176">This property is applicable only when **fieldBaseType** is set to **String**.</span></span> <span data-ttu-id="8c59e-177">Jeśli jest ustawiona właściwość **stringOptions**, wartości ciągów, które użytkownik może wybrać za pomocą przycisków opcji (przycisków radiowych), są określane przez ciągi na liście.</span><span class="sxs-lookup"><span data-stu-id="8c59e-177">If **stringOptions** is set, the string values that are available for selection via option buttons (radio buttons) are specified by the strings in the list.</span></span> <span data-ttu-id="8c59e-178">Jeśli nie podano żadnych ciągów, w polu ciągu jest dozwolony tekst niezależny (stosowny przykład jest pokazany w sekcji „Zapisywanie wpisu karty czasu pracy zwrotnie z aplikacji w bazie danych przy użyciu łańcucha poleceń na klasie TSTimesheetEntryService”).</span><span class="sxs-lookup"><span data-stu-id="8c59e-178">If no strings are provided, free-text entry in the string field is allowed (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="stringlength-int"></a><span data-ttu-id="8c59e-179">stringLength (int)</span><span class="sxs-lookup"><span data-stu-id="8c59e-179">stringLength (int)</span></span>

<span data-ttu-id="8c59e-180">Ta właściwość określa maksymalną długość pola ciągu.</span><span class="sxs-lookup"><span data-stu-id="8c59e-180">This property specifies the maximum length for a string field.</span></span> <span data-ttu-id="8c59e-181">Ma znaczenie tylko wtedy, gdy ustawioną wartością właściwości **fieldBaseType** jest **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-181">It's applicable only when **fieldBaseType** is set to **String**.</span></span>

### <a name="numberofdecimals-int"></a><span data-ttu-id="8c59e-182">numberOfDecimals (int)</span><span class="sxs-lookup"><span data-stu-id="8c59e-182">numberOfDecimals (int)</span></span>

<span data-ttu-id="8c59e-183">Ta właściwość określa liczbę miejsc dziesiętnych wyświetlanych dla pola wartości rzeczywistej.</span><span class="sxs-lookup"><span data-stu-id="8c59e-183">This property specifies the number of decimal places that are shown for a real field.</span></span> <span data-ttu-id="8c59e-184">Ma znaczenie tylko wtedy, gdy ustawioną wartością właściwości **fieldBaseType** jest **Rzeczywista**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-184">It's applicable only when **fieldBaseType** is set to **Real**.</span></span>

### <a name="ordersequence-int"></a><span data-ttu-id="8c59e-185">orderSequence (int)</span><span class="sxs-lookup"><span data-stu-id="8c59e-185">orderSequence (int)</span></span>

<span data-ttu-id="8c59e-186">Ta właściwość określa kolejność wyświetlania pól niestandardowych w aplikacji w przypadku określenia więcej niż jednego pola niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="8c59e-186">This property controls the order in which the custom fields are shown in the app when more than one custom field is specified.</span></span> <span data-ttu-id="8c59e-187">Pola, które mają mniejsze numery, są wyświetlane jako pierwsze.</span><span class="sxs-lookup"><span data-stu-id="8c59e-187">Fields that have lower numbers are shown first.</span></span>

### <a name="booleanvalue-boolean"></a><span data-ttu-id="8c59e-188">booleanValue (wartość logiczna)</span><span class="sxs-lookup"><span data-stu-id="8c59e-188">booleanValue (boolean)</span></span>

<span data-ttu-id="8c59e-189">W przypadku pól typu **Wartość logiczna** ta właściwość przekazuje wartość logiczną pola między serwerem i aplikacją.</span><span class="sxs-lookup"><span data-stu-id="8c59e-189">For fields of the **Boolean** type, this property passes the Boolean value of the field between the server and the app.</span></span>

### <a name="guidvalue-guid"></a><span data-ttu-id="8c59e-190">guidValue (guid)</span><span class="sxs-lookup"><span data-stu-id="8c59e-190">guidValue (guid)</span></span>

<span data-ttu-id="8c59e-191">W przypadku pól typu **GUID** ta właściwość przekazuje wartość unikatowego identyfikatora globalnego (GUID) pola między serwerem i aplikacją.</span><span class="sxs-lookup"><span data-stu-id="8c59e-191">For fields of the **GUID** type, this property passes the globally unique identifier (GUID) value of the field between the server and the app.</span></span>

### <a name="int64value-int64"></a><span data-ttu-id="8c59e-192">int64Value (int64)</span><span class="sxs-lookup"><span data-stu-id="8c59e-192">int64Value (int64)</span></span>

<span data-ttu-id="8c59e-193">W przypadku pól typu **Int64** ta właściwość przekazuje wartość int64 pola między serwerem i aplikacją.</span><span class="sxs-lookup"><span data-stu-id="8c59e-193">For fields of the **Int64** type, this property passes the int64 value of the field between the server and the app.</span></span>

### <a name="intvalue-int"></a><span data-ttu-id="8c59e-194">intValue (int)</span><span class="sxs-lookup"><span data-stu-id="8c59e-194">intValue (int)</span></span>

<span data-ttu-id="8c59e-195">W przypadku pól typu **Int** ta właściwość przekazuje wartość int pola między serwerem i aplikacją.</span><span class="sxs-lookup"><span data-stu-id="8c59e-195">For fields of the **Int** type, this property passes the int value of the field between the server and the app.</span></span>

### <a name="realvalue-real"></a><span data-ttu-id="8c59e-196">realValue (real)</span><span class="sxs-lookup"><span data-stu-id="8c59e-196">realValue (real)</span></span>

<span data-ttu-id="8c59e-197">W przypadku pól typu **Rzeczywista** ta właściwość przekazuje wartość rzeczywistą pola między serwerem i aplikacją.</span><span class="sxs-lookup"><span data-stu-id="8c59e-197">For fields of the **Real** type, this property passes the real value of the field between the server and the app .</span></span>

### <a name="stringvalue-str"></a><span data-ttu-id="8c59e-198">stringValue (str)</span><span class="sxs-lookup"><span data-stu-id="8c59e-198">stringValue (str)</span></span>

<span data-ttu-id="8c59e-199">W przypadku pól typu **Ciąg** ta właściwość przekazuje wartość ciągu pola między serwerem i aplikacją.</span><span class="sxs-lookup"><span data-stu-id="8c59e-199">For fields of the **String** type, this property passes the string value of the field between the server and the app.</span></span> <span data-ttu-id="8c59e-200">Jest ona również stosowana do pól typu **Rzeczywista**, które są sformatowane jako waluta.</span><span class="sxs-lookup"><span data-stu-id="8c59e-200">It's also used for fields of the **Real** type that are formatted as currency.</span></span> <span data-ttu-id="8c59e-201">W przypadku tych pól właściwość służy do przekazania kodu waluty do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-201">For those fields, the property is used to pass the currency code to the app.</span></span>

### <a name="datevalue-date"></a><span data-ttu-id="8c59e-202">dateValue (data)</span><span class="sxs-lookup"><span data-stu-id="8c59e-202">dateValue (date)</span></span>

<span data-ttu-id="8c59e-203">W przypadku pól typu **Data** ta właściwość przekazuje wartość daty pola między serwerem i aplikacją.</span><span class="sxs-lookup"><span data-stu-id="8c59e-203">For fields of the **Date** type, this property passes the date value of the field between the server and the app.</span></span>

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a><span data-ttu-id="8c59e-204">Wyświetlanie i zapisywanie pola niestandardowego w sekcji wpisu karty czasu pracy</span><span class="sxs-lookup"><span data-stu-id="8c59e-204">Show and save a custom field in the timesheet entry section</span></span>

<span data-ttu-id="8c59e-205">Poniżej znajduje się zrzut ekranu tworzenia wpisu karty czasu pracy w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="8c59e-205">Below is a screenshot from the mobile app of a timesheet entry creation.</span></span> <span data-ttu-id="8c59e-206">Są w nim widoczne gotowe pola oraz pole niestandardowe w sekcji „Wpis czasu” o nazwie „Ciąg testowy” z ustawioną wartością wyliczenia „Druga opcja”.</span><span class="sxs-lookup"><span data-stu-id="8c59e-206">It shows the out-of-box fields and a custom field in the "Time entry" section called "Test string" with an enum value of "Second option" already set.</span></span>

![Pole niestandardowe ciągu testowego w aplikacji](media/timesheet-entry.jpg)



<span data-ttu-id="8c59e-208">Poniżej znajduje się zrzut ekranu, na którym użytkownik wybiera jedną z opcji wyliczenia dostępnych w polu niestandardowym „Ciąg testowy” w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="8c59e-208">Below is a screenshot from the mobile app of the user selecting one of the enum options available for the "Test string" custom field.</span></span>  <span data-ttu-id="8c59e-209">Opcje „Pierwsza opcja” i „Druga opcja” są wyświetlane jako przyciski radiowe.</span><span class="sxs-lookup"><span data-stu-id="8c59e-209">The two options are "First option" and "Second option" shown as radio buttons.</span></span> <span data-ttu-id="8c59e-210">Zaznaczona jest druga opcja.</span><span class="sxs-lookup"><span data-stu-id="8c59e-210">The second option is currently selected.</span></span>

![Przyciski opcji (przyciski radiowe) pola niestandardowego ciągu testowego](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="8c59e-212">Rozszerzanie tabeli TSTimesheetLine o pole niestandardowe</span><span class="sxs-lookup"><span data-stu-id="8c59e-212">Extend the TSTimesheetLine table so that it has a custom field</span></span>

<span data-ttu-id="8c59e-213">W typowych scenariuszach pole niestandardowe sekcji wpisu karty czasu pracy jest zazwyczaj zapisywane w tabeli TSTimesheetLine.</span><span class="sxs-lookup"><span data-stu-id="8c59e-213">In typical scenarios, it's likely that the data for a custom field in the timesheet entry section will be saved to the TSTimesheetLine table.</span></span> <span data-ttu-id="8c59e-214">Możliwe jest jednak użycie innych tabel, jeśli dane mogą być pobierane na podstawie dostarczonego rekordu TSTimesheetTrans lub jeśli nie ma on określonego kontekstu rekordów (na przykład, jeśli w parametrach projektu pole jest ustawione jako tylko do odczytu).</span><span class="sxs-lookup"><span data-stu-id="8c59e-214">However, other tables can be used if the data can be retrieved based on a TSTimesheetTrans record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="8c59e-215">Należy pamiętać, że pola niestandardowe nie muszą zawierać żadnych kopii zapasowych rekordów bazy danych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-215">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="8c59e-216">Można je dynamicznie generować na podstawie logiki X++.</span><span class="sxs-lookup"><span data-stu-id="8c59e-216">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="8c59e-217">Ta metoda może być przydatna w scenariuszach tylko do odczytu (przykłady dynamicznie generowanych wartości pól niestandardowych są pokazane w sekcji „Wypełnianie szczegółów karty czasy pracy przy użyciu łańcucha poleceń na klasie TSTimesheetDetails class, metodzie buildCustomFieldListForHeader”).</span><span class="sxs-lookup"><span data-stu-id="8c59e-217">This approach can be useful in read-only scenarios (see the “Use chain of command on the TSTimesheetDetails class, buildCustomFieldListForHeader method to fill in timesheet details” section for an example of dynamically generated custom field values.)</span></span>

<span data-ttu-id="8c59e-218">Poniżej znajduje się zrzut ekranu drzewa obiektów aplikacji z programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8c59e-218">Below is a screenshot from Visual Studio of the Application Object Tree.</span></span> <span data-ttu-id="8c59e-219">Jest w nim widoczne rozszerzenie tabeli TSTimesheetLine z polem TestLineString dodanym jako pole niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="8c59e-219">It shows an extension of the TSTimesheetLine table with the TestLineString field added as a custom field.</span></span>

![Ciąg wiersza](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a><span data-ttu-id="8c59e-221">Wyświetlanie pola w sekcji wpisu karty czasu pracy przy użyciu łańcucha poleceń na metodzie buildCustomFieldList klasy TSTimesheetSettings</span><span class="sxs-lookup"><span data-stu-id="8c59e-221">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the timesheet entry section</span></span>

<span data-ttu-id="8c59e-222">Ten kod steruje ustawieniami wyświetlania pola w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-222">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="8c59e-223">Na przykład określa typ pola, etykietę, czy pole jest wymagane oraz sekcję, w której jest wyświetlane pole.</span><span class="sxs-lookup"><span data-stu-id="8c59e-223">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="8c59e-224">Poniższy przykład przedstawia pole ciągu we wpisach czasu.</span><span class="sxs-lookup"><span data-stu-id="8c59e-224">The following example shows a string field on time entries.</span></span> <span data-ttu-id="8c59e-225">W tym polu dostępne są dwie opcje, **Pierwsza opcja** i **Druga opcja**, które są dostępne za pośrednictwem przycisków opcji (przycisków radiowych).</span><span class="sxs-lookup"><span data-stu-id="8c59e-225">This field has two options, **First option** and **Second option**, that are available via option buttons (radio buttons).</span></span> <span data-ttu-id="8c59e-226">Pole w aplikacji jest skojarzone z polem **TestLineString**, które jest dodawane do tabeli TSTimesheetLine.</span><span class="sxs-lookup"><span data-stu-id="8c59e-226">The field in the app is associated with the **TestLineString** field that is added to the TSTimesheetLine table.</span></span>

<span data-ttu-id="8c59e-227">Należy zwrócić uwagę na użycie metody **TSTimesheetCustomField::newFromMetatdata()** w celu uproszczenia inicjowania właściwości pól niestandardowych: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** i **numberOfDecimals**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-227">Note the use of the **TSTimesheetCustomField::newFromMetatdata()** method to simplify the initialization of the custom field properties: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength**, and **numberOfDecimals**.</span></span> <span data-ttu-id="8c59e-228">Parametry te można również ustawić ręcznie.</span><span class="sxs-lookup"><span data-stu-id="8c59e-228">You can also set these parameters manually, as you prefer.</span></span>

```xpp
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a><span data-ttu-id="8c59e-229">Wprowadzanie wartości we wpisie karty czasu pracy użyciu łańcucha poleceń na metodzie buildCustomFieldListForEntry klasy TSTimesheetEntry</span><span class="sxs-lookup"><span data-stu-id="8c59e-229">Use chain of command on the buildCustomFieldListForEntry method of the TSTimesheetEntry class to enter values in a timesheet entry</span></span>

<span data-ttu-id="8c59e-230">Metoda **buildCustomFieldListForEntry** służy do wprowadzania wartości w zapisanych wierszach karty czasu pracy w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="8c59e-230">The **buildCustomFieldListForEntry** method is used to enter values on the saved timesheet lines in the mobile app.</span></span> <span data-ttu-id="8c59e-231">Przyjmuje ona rekord TSTimesheetTrans jako parametr.</span><span class="sxs-lookup"><span data-stu-id="8c59e-231">It takes a TSTimesheetTrans record as a parameter.</span></span> <span data-ttu-id="8c59e-232">Pola z tego rekordu mogą być używane do wstawiania wartości pola niestandardowego w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-232">Fields from that record can be used to fill in the custom field value in the app.</span></span>

```xpp
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a><span data-ttu-id="8c59e-233">Zapisywanie wpisu karty czasu pracy zwrotnie z aplikacji w bazie danych przy użyciu łańcucha poleceń na klasie TSTimesheetEntryService</span><span class="sxs-lookup"><span data-stu-id="8c59e-233">Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database</span></span>

<span data-ttu-id="8c59e-234">Aby zapisać pole niestandardowe z powrotem w bazie danych w typowym użyciu, należy rozszerzyć wiele metod:</span><span class="sxs-lookup"><span data-stu-id="8c59e-234">To save a custom field back to the database in typical usage, you must extend multiple methods:</span></span>

- <span data-ttu-id="8c59e-235">Metoda **timesheetLineNeedsUpdating** służy do określenia, czy rekord wiersza został zmieniony przez użytkownika w aplikacji i musi zostać zapisany w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-235">The **timesheetLineNeedsUpdating** method is used to determine whether the line record has been changed by the user in the app and must be saved to the database.</span></span> <span data-ttu-id="8c59e-236">Jeśli wydajność nie jest istotna, można uprościć tę metodę, tak aby zawsze zwracała wartość **true**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-236">If performance isn't a concern, this method can be simplified so that it always returns **true**.</span></span>
- <span data-ttu-id="8c59e-237">Metody **populateTimesheetLineFromEntryDuringCreate** i **populateTimesheetLineFromEntryDuringUpdate** można rozszerzać, tak aby wprowadzały w rekordzie bazy danych TSTimesheetLine wartości z dostarczonego rekordu umowy dotyczącej danych TSTimesheetEntry.</span><span class="sxs-lookup"><span data-stu-id="8c59e-237">The **populateTimesheetLineFromEntryDuringCreate** and **populateTimesheetLineFromEntryDuringUpdate** methods can be extended so that they enter values in the TSTimesheetLine database record from the TSTimesheetEntry data contract record that is provided.</span></span> <span data-ttu-id="8c59e-238">W poniższym przykładzie należy zauważyć, że mapowanie między polem bazy danych i polem wprowadzania jest wykonywane ręcznie za pomocą kodu X++.</span><span class="sxs-lookup"><span data-stu-id="8c59e-238">In the example that follows, notice how the mapping between the database field and the entry field is manually done via X++ code.</span></span>
- <span data-ttu-id="8c59e-239">Metodę **populateTimesheetWeekFromEntry** można również rozszerzyć, jeśli pole niestandardowe zmapowane do obiektu **TSTimesheetEntry** musi zostać zapisane z powrotem w tabeli bazy danych TSTimesheetLineweek.</span><span class="sxs-lookup"><span data-stu-id="8c59e-239">The **populateTimesheetWeekFromEntry** method can also be extended if the custom field that is mapped to the **TSTimesheetEntry** object must write back to the TSTimesheetLineweek database table.</span></span>

> [!NOTE]
> <span data-ttu-id="8c59e-240">W poniższym przykładzie wartość **firstOption** lub **secondOption**, zależnie od wyboru użytkownika, jest zapisywana w bazie danych jako wartość ciągu nieprzetworzonego.</span><span class="sxs-lookup"><span data-stu-id="8c59e-240">The following example saves the **firstOption** or **secondOption** value that the user selects to the database as a raw string value.</span></span> <span data-ttu-id="8c59e-241">Jeśli pole bazy danych jest polem typu **Wyliczenie**, wartości te można zamapować ręcznie na wartość wyliczenia, a następnie zapisać je w polu wyliczenia w tabeli bazy danych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-241">If the database field is a field of the **Enum** type, those values can be manually mapped to an enum value and then saved to an enum field on the database table.</span></span>

```xpp
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a><span data-ttu-id="8c59e-242">Wyświetlanie pola niestandardowego w sekcji nagłówka karty czasu pracy</span><span class="sxs-lookup"><span data-stu-id="8c59e-242">Show a custom field in the timesheet header section</span></span>

<span data-ttu-id="8c59e-243">Poniżej znajduje się zrzut ekranu do przeglądania karty czasu pracy w aplikacji mobilnej przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8c59e-243">Below is a screenshot from the mobile app of a user viewing a timesheet.</span></span> <span data-ttu-id="8c59e-244">W prawym górnym rogu naciśnięto przycisk „Więcej informacji”, aby wyświetlić opcję „Wyświetl więcej szczegółów”.</span><span class="sxs-lookup"><span data-stu-id="8c59e-244">The "More information" button has been selected in the upper-right corner to show the "View more details" option.</span></span>  

![Polecenie Wyświetl więcej szczegółów](media/show-more.png)

<span data-ttu-id="8c59e-246">Poniżej znajduje się zrzut ekranu z sekcją „Więcej” karty czasu pracy w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="8c59e-246">Below is a screenshot from the mobile app showing the “More” section of a timesheet.</span></span> <span data-ttu-id="8c59e-247">Do sekcji nagłówka karty czasu pracy dodano pole niestandardowe o nazwie „Stopień wykorzystania tej karty czasu pracy (obliczone pole niestandardowe)”</span><span class="sxs-lookup"><span data-stu-id="8c59e-247">A custom field called “Utilization rate of this timesheet (computed custom field)” has been added to the timesheet header section.</span></span> <span data-ttu-id="8c59e-248">W polu niestandardowym ustawiono wartość tylko do odczytu „0,667”.</span><span class="sxs-lookup"><span data-stu-id="8c59e-248">A read-only value of "0.667" is set on the custom field.</span></span>

![Sekcja Więcej](media/more-section.jpg)

### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="8c59e-250">Rozszerzanie tabeli TSTimesheetTable o pole niestandardowe</span><span class="sxs-lookup"><span data-stu-id="8c59e-250">Extend the TSTimesheetTable table so that it has a custom field</span></span>

<span data-ttu-id="8c59e-251">W typowych scenariuszach pole niestandardowe sekcji nagłówka pochodzi zazwyczaj z tabeli TSTimesheetHeader.</span><span class="sxs-lookup"><span data-stu-id="8c59e-251">In typical scenarios, it's likely that the data for a custom field in the header section will be pulled from the TSTimesheetHeader table.</span></span> <span data-ttu-id="8c59e-252">Możliwe jest jednak użycie innych tabel, jeśli dane mogą być pobierane na podstawie dostarczonego rekordu TSTimesheetTable lub jeśli nie ma on określonego kontekstu rekordów (na przykład, jeśli w parametrach projektu pole jest ustawione jako tylko do odczytu).</span><span class="sxs-lookup"><span data-stu-id="8c59e-252">However, other tables can be used if the data can be retrieved based on a TSTimesheetTable record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="8c59e-253">Należy pamiętać, że pola niestandardowe nie muszą zawierać żadnych kopii zapasowych rekordów bazy danych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-253">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="8c59e-254">Można je dynamicznie generować na podstawie logiki X++.</span><span class="sxs-lookup"><span data-stu-id="8c59e-254">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="8c59e-255">Poniższy przykład ilustruje to podejście.</span><span class="sxs-lookup"><span data-stu-id="8c59e-255">The example that follows shows this approach.</span></span>

<span data-ttu-id="8c59e-256">Pola w sekcji nagłówka są zawsze tylko do odczytu w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-256">Fields in the header section are always read-only in the app.</span></span>

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a><span data-ttu-id="8c59e-257">Wyświetlanie pola w sekcji nagłówka przy użyciu łańcucha poleceń na metodzie buildCustomFieldList klasy TSTimesheetSettings</span><span class="sxs-lookup"><span data-stu-id="8c59e-257">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the header section</span></span>

<span data-ttu-id="8c59e-258">Ten kod steruje ustawieniami wyświetlania pola w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-258">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="8c59e-259">Na przykład określa typ pola, etykietę, czy pole jest wymagane oraz sekcję, w której jest wyświetlane pole.</span><span class="sxs-lookup"><span data-stu-id="8c59e-259">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="8c59e-260">W poniższym przykładzie przedstawiono obliczoną wartość w sekcji nagłówka w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-260">The following example shows a computed value in the header section in the app.</span></span>

```xpp
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a><span data-ttu-id="8c59e-261">Wypełnianie szczegółów karty czasu pracy użyciu łańcucha poleceń na metodzie buildCustomFieldListForHeader klasy TSTimesheetDetails</span><span class="sxs-lookup"><span data-stu-id="8c59e-261">Use chain of command on the buildCustomFieldListForHeader method of the TSTimesheetDetails class to fill in timesheet details</span></span>

<span data-ttu-id="8c59e-262">Metoda **buildCustomFieldListForHeader** służy do wypełniania szczegółów nagłówka karty czasu pracy w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="8c59e-262">The **buildCustomFieldListForHeader** method is used to fill in the timesheet header details in the mobile app.</span></span> <span data-ttu-id="8c59e-263">Przyjmuje ona rekord TSTimesheetTable jako parametr.</span><span class="sxs-lookup"><span data-stu-id="8c59e-263">It takes a TSTimesheetTable record as a parameter.</span></span> <span data-ttu-id="8c59e-264">Pola z tego rekordu mogą być używane do wstawiania wartości pola niestandardowego w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-264">Fields from that record can be used to fill in the custom field value in the app.</span></span> <span data-ttu-id="8c59e-265">W poniższym przykładzie nie są odczytywane żadne wartości z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="8c59e-265">The following example doesn't read any values from the database.</span></span> <span data-ttu-id="8c59e-266">Zamiast tego przy użyciu logiki X++ generowana jest obliczona wartość, która jest następnie wyświetlana w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8c59e-266">Instead, it uses X++ logic to generate a computed value that is then shown in the app.</span></span>


```xpp
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a><span data-ttu-id="8c59e-267">Inne możliwości konfigurowania/rozszerzania</span><span class="sxs-lookup"><span data-stu-id="8c59e-267">Other configurability/extensibility opportunities</span></span>

### <a name="adding-additional-validation-for-the-app"></a><span data-ttu-id="8c59e-268">Wstawianie dodatkowych weryfikacji do aplikacji</span><span class="sxs-lookup"><span data-stu-id="8c59e-268">Adding additional validation for the app</span></span>

<span data-ttu-id="8c59e-269">Istniejąca logika funkcji karty czasu pracy na poziomie bazy danych będzie nadal działać zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="8c59e-269">Existing logic for timesheet functionality at the database level will still work as expected.</span></span> <span data-ttu-id="8c59e-270">Aby przerwać kończenie operacji zapisywania lub przesyłania i wyświetlić określony komunikat o błędzie, można dodać wiersz **throw error("message to user")** do kodu za pośrednictwem łańcucha rozszerzenia polecenia.</span><span class="sxs-lookup"><span data-stu-id="8c59e-270">To interrupt the completion of save or submit operations and show a specific error message, you can add **throw error("message to user")** to the code via a chain of command extension.</span></span> <span data-ttu-id="8c59e-271">Oto trzy przykłady przydatnych metod rozszerzania:</span><span class="sxs-lookup"><span data-stu-id="8c59e-271">Here are three examples of useful extensible methods:</span></span>

- <span data-ttu-id="8c59e-272">Jeśli **validateWrite** w tabeli TSTimesheetLine zwraca wartość **false** podczas operacji zapisywania wiersza karty czasu pracy, w aplikacji mobilnej jest wyświetlany komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="8c59e-272">If **validateWrite** on the TSTimesheetLine table returns **false** during a save operation for a timesheet line, an error message is shown in the mobile app.</span></span>
- <span data-ttu-id="8c59e-273">Jeśli **validateSubmit** w tabeli TSTimesheetTable zwraca wartość **false** podczas przesyłania karty czasu pracy w aplikacji, użytkownikowi jest wyświetlany komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="8c59e-273">If **validateSubmit** on the TSTimesheetTable table returns **false** during timesheet submission in the app, an error message is shown to the user.</span></span>
- <span data-ttu-id="8c59e-274">Logika, która wypełnia pola (na przykład **Właściwośćwiersza**) w trakcie metody **insert** w tabeli TSTimesheetLine, będzie nadal działać.</span><span class="sxs-lookup"><span data-stu-id="8c59e-274">Logic that fills in fields (for example, **Line Property**) during the **insert** method on the TSTimesheetLine table will still run.</span></span>

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a><span data-ttu-id="8c59e-275">Ukrywanie i oznaczanie gotowych pól jako tylko do odczytu za pomocą konfiguracji</span><span class="sxs-lookup"><span data-stu-id="8c59e-275">Hiding and marking out-of-box fields as read-only via configuration</span></span>

<span data-ttu-id="8c59e-276">Z poziomu parametrów projektu można tworzyć gotowe pola tylko do odczytu lub ukryte w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="8c59e-276">From the project parameters, you can make out-of-box fields read-only or hidden in the mobile app.</span></span> <span data-ttu-id="8c59e-277">Opcje są ustawiane w sekcji **Mobilne karty czasu pracy** na karcie **Karta czasu pracy** strony **Parametry modułu Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-277">Set the options in the **Mobile timesheets** section on the **Timesheet** tab of the **Project management and accounting parameters** page.</span></span>

![Parametry projektu](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a><span data-ttu-id="8c59e-279">Zmienianie działań dostępnych do wybrania za pomocą rozszerzeń</span><span class="sxs-lookup"><span data-stu-id="8c59e-279">Changing the activities that are available for selection via extensions</span></span>

<span data-ttu-id="8c59e-280">Działania dostępne do wybrania dla projektu są wypełniane za pośrednictwem metod **getActivitiesForProject ()** i **getActivityQuery ()** w klasie **TsTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-280">The activities that are available for selection for a project are filled in via the **getActivitiesForProject()** and **getActivityQuery()** methods in the **TsTimesheetProjectService** class.</span></span> <span data-ttu-id="8c59e-281">Za pomocą łańcucha poleceń można zmienić to zachowanie w celu dopasowania go do scenariusza biznesowego dla działań dostępnych do wybrania dla konkretnego projektu.</span><span class="sxs-lookup"><span data-stu-id="8c59e-281">You can use chain of command to change this behavior to match your business scenario for the activities that are available for selection for a specific project.</span></span>

### <a name="entering-a-default-project-category-on-timesheet-entries"></a><span data-ttu-id="8c59e-282">Wprowadzanie domyślnej kategorii projektu we wpisach karty czasu pracy</span><span class="sxs-lookup"><span data-stu-id="8c59e-282">Entering a default project category on timesheet entries</span></span>

<span data-ttu-id="8c59e-283">Wprowadzanie domyślnej kategorii projektu we wpisach karty czasu pracy odbywa się na trzech poziomach.</span><span class="sxs-lookup"><span data-stu-id="8c59e-283">Entry of a default project category on timesheet entries occurs at three levels.</span></span> <span data-ttu-id="8c59e-284">Zachowanie na dowolnym z tych poziomów można rozszerzyć za pomocą łańcucha poleceń, aby osiągnąć pożądane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="8c59e-284">You can use chain of command to extend the behavior at any or all of these levels to achieve the desired behavior.</span></span> <span data-ttu-id="8c59e-285">Obowiązuje następująca hierarchia:</span><span class="sxs-lookup"><span data-stu-id="8c59e-285">The following hierarchy is used:</span></span>

1. <span data-ttu-id="8c59e-286">Aplikacja próbuje umieścić domyślną kategorię z zasobu projektu.</span><span class="sxs-lookup"><span data-stu-id="8c59e-286">The app tries to put the default category from the project resource.</span></span> <span data-ttu-id="8c59e-287">Ta kategoria domyślna jest ustawiana w metodach **getCurrentUserResource** i **getDelegatedResourcesForCurrentUser** w klasie **TSTimesheetSettingsService**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-287">This default category is set in the **getCurrentUserResource** and **getDelegatedResourcesForCurrentUser** methods in the **TSTimesheetSettingsService** class.</span></span>
2. <span data-ttu-id="8c59e-288">Jeśli na poziomie zasobów projektu nie określono kategorii domyślnej, aplikacja próbuje ściągnąć ją z działania projektu.</span><span class="sxs-lookup"><span data-stu-id="8c59e-288">If the default category isn't provided at the project resource level, the app tries to pull it from the project activity.</span></span> <span data-ttu-id="8c59e-289">Ta kategoria domyślna jest ustawiana w metodzie **getActivitiesForProject** w klasie **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-289">This default category is set in the **getActivitiesForProject** method in the **TSTimesheetProjectService** class.</span></span>
3. <span data-ttu-id="8c59e-290">Jeśli na poziomie działania projektu nie określono kategorii domyślnej, kategoria domyślna jest pobierana z parametrów projektu.</span><span class="sxs-lookup"><span data-stu-id="8c59e-290">If the default category isn't provided at the project activity level, the default category it taken from the project parameters.</span></span> <span data-ttu-id="8c59e-291">Ta kategoria domyślna jest ustawiana w metodzie **getProjectDetailsbyRule** w klasie **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="8c59e-291">This default category is set in the **getProjectDetailsbyRule** method in the **TSTimesheetProjectService** class.</span></span>
