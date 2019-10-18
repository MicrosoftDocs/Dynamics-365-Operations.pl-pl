---
title: Tworzenie pól niestandardowych i praca z nimi
description: W tym temacie opisano, jak usługa pozwala niektórym użytkownikom tworzyć niestandardowe pola w celu dostosowania aplikacji do unikatowych potrzeb firmy.
author: jasongre
manager: AnnBe
ms.date: 07/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: af2066c095c675aa0003ac2cf66bebba48a1e8a5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190863"
---
# <a name="create-and-work-with-custom-fields"></a><span data-ttu-id="8a3ba-103">Tworzenie pól niestandardowych i praca z nimi</span><span class="sxs-lookup"><span data-stu-id="8a3ba-103">Create and work with custom fields</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a3ba-104">Zawiera już w standardzie rozbudowany zestaw pól do zarządzania różnorodnymi procesami biznesowymi, ale czasami firma musi śledzić dodatkowe informacje w systemie.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-104">While there is an extensive set of fields out-of-the-box for managing a broad range of business processes, sometimes there is a need for a company to track additional information in the system.</span></span> <span data-ttu-id="8a3ba-105">W reakcji na tę potrzebę można tworzyć niestandardowe pola w celu dostosowania aplikacji do specyfiki firmy, o ile tylko masz uprawnienia wobec tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-105">To accommodate this need, you can create custom fields to tailor the application to fit your business, provided you have permissions to the feature.</span></span>

<span data-ttu-id="8a3ba-106">Opcja dodawania pól niestandardowych jest dostępna w aktualizacji platformy 13 i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-106">The ability to add custom fields is available in platform update 13 and later.</span></span>

<span data-ttu-id="8a3ba-107">W tym nagraniu wideo przedstawiono, jak łatwe jest do dodawanie niestandardowego pola do strony: [Dodawanie pól niestandardowych](https://www.youtube.com/watch?v=gWSGZI9Vtnc).</span><span class="sxs-lookup"><span data-stu-id="8a3ba-107">This video shows how easy it is to add a custom field to a page: [Adding custom fields](https://www.youtube.com/watch?v=gWSGZI9Vtnc).</span></span>

## <a name="creating-custom-fields"></a><span data-ttu-id="8a3ba-108">Tworzenie pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="8a3ba-108">Creating custom fields</span></span>

<span data-ttu-id="8a3ba-109">Po stwierdzeniu, które dodatkowe informacje mają być śledzone w aplikacji, można utworzyć niestandardowe pole w odpowiedniej tabeli, po czym udostępnić je na stronie.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-109">After you've identified additional information that you would like to track in the application, you can create the custom field on the appropriate table and expose that new field on a page.</span></span>

<span data-ttu-id="8a3ba-110">Kroki poniżej opisują proces tworzenia niestandardowego pola i umieszczania go w formularzu.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-110">The following steps describe the process for creating a custom field and placing that field on a form.</span></span>

1. <span data-ttu-id="8a3ba-111">Przejdź do formularza, w którym jest potrzebne nowe pole.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-111">Navigate to the form where the new field is needed.</span></span>
2. <span data-ttu-id="8a3ba-112">Ponieważ ostatecznym celem jest uwidocznienie niestandardowego pola w formularzu, punkt wejścia tworzenia niestandardowych pól znajduje się wewnątrz środowiska personalizacji.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-112">Because the end goal is to expose the custom field on a form, the entry point for creating custom fields exists inside the personalization experience.</span></span> <span data-ttu-id="8a3ba-113">Otwórz pasek narzędzi personalizacji, wybierając kolejno polecenia **Opcje** i **Personalizuj ten formularz**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-113">Open the personalization toolbar by selecting **Options**, and then **Personalize this form**.</span></span>
3. <span data-ttu-id="8a3ba-114">Kliknij kolejno opcje **Wstaw** i **Pole**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-114">Click **Insert** and then **Field**.</span></span>
4. <span data-ttu-id="8a3ba-115">Wybierz region formularza, w którym nowe pole ma być wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-115">Select the region of the form where you want to expose the new field.</span></span> <span data-ttu-id="8a3ba-116">Po zaznaczeniu regionu w oknie dialogowym **Wstaw pola** zostanie wyświetlona lista istniejących pól, które można wstawić do wybranego regionu.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-116">After selection, the **Insert fields** dialog box will display a list of existing fields that can be inserted into the selected region of the form.</span></span>
5. <span data-ttu-id="8a3ba-117">Upewnij się, że interesujące Cię pole jeszcze nie występuje na liście.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-117">Ensure that the field you are interested in does not already exist in the list.</span></span> <span data-ttu-id="8a3ba-118">Jeśli występuje, możesz po prostu zaznaczyć je na liście i kliknąć przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-118">If it does, you can simply select that field in the list and click **Insert**.</span></span>
6. <span data-ttu-id="8a3ba-119">Nad listą kliknij przycisk **Utwórz nowe pole**, aby zainicjować proces tworzenia pola niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-119">Click the **Create new field** button above the list to initiate the process of creating a custom field.</span></span> <span data-ttu-id="8a3ba-120">Spowoduje to otwarcie okna dialogowego **Utwórz nowe pole**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-120">This will open the **Create new field** dialog box.</span></span>

    <span data-ttu-id="8a3ba-121">Jeśli nie widać przycisku **Utwórz nowe pole**, nie masz uprawnień niezbędnych do korzystania z tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-121">If you do not see the **Create new field** button, you do not have the necessary permissions to use this feature.</span></span>

7. <span data-ttu-id="8a3ba-122">W oknie dialogowym **Utwórz nowe pole** wprowadź następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-122">In the **Create new field** dialog box, enter the following information.</span></span>

    1. <span data-ttu-id="8a3ba-123">Wybierz tabelę bazy danych, do której powinno zostać dodane to pole.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-123">Select the database table where this field should be added.</span></span> <span data-ttu-id="8a3ba-124">Należy zauważyć, że na liście rozwijanej będą wyświetlane tylko tabele, które obsługują niestandardowe pola.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-124">Note that only tables that support custom fields will appear in the drop-down list.</span></span> <span data-ttu-id="8a3ba-125">Sekcja poniżej zawiera szczegółowe informacje techniczne o obsługiwanych tabelach.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-125">See the section below for technical details on supported tables.</span></span>
    2. <span data-ttu-id="8a3ba-126">Wybierz typ danych dla nowego pola.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-126">Select the data type for the new field.</span></span> <span data-ttu-id="8a3ba-127">Dostępne typy danych to Pole wyboru, Data, Data i godzina, Liczba dziesiętna, Liczba, Lista wyboru i Tekst.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-127">The available data types are checkbox, date, date time, decimal, number, picklist, and text.</span></span>

        - <span data-ttu-id="8a3ba-128">Jeśli wybrano typ danych Tekst, można również określić maksymalną długości tekstu, jaki można wprowadzić w tym polu.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-128">If you choose the text data type, you can also specify the maximum length of the text that can be entered in this field.</span></span>
        - <span data-ttu-id="8a3ba-129">W przypadku wybrania typu danych Lista wyboru można także wybrać zestaw prawidłowych wartości dla pola.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-129">If you choose the picklist data type, you can also select the set of valid values for the field.</span></span>

    3. <span data-ttu-id="8a3ba-130">Wprowadź nazwę, etykietę i tekst pomocy dla pola.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-130">Provide a name, label, and help text for the field.</span></span> <span data-ttu-id="8a3ba-131">Nazwa odpowiada fizycznej nazwie pola w bazie danych, podczas gdy etykieta i tekst pomocy to teksty używane do reprezentowania tego pola w interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-131">The name corresponds to the physical field name in the database, whereas the label and help text are the text used to represent this field in the user interface.</span></span>

8. <span data-ttu-id="8a3ba-132">Jeśli jest to jedyne pole, które trzeba utworzyć dla tego formularza, kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-132">If this is the only field that you need to create for this form, click **Save**.</span></span> <span data-ttu-id="8a3ba-133">Jeśli trzeba utworzyć dodatkowe pola, kliknij przycisk **Zapisz i nowy**, a następnie wróć do kroku 7.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-133">If you need to create additional fields, click **Save and new** and go back to step 7.</span></span> <span data-ttu-id="8a3ba-134">Należy zauważyć, że obecnie istnieje limit **20 niestandardowych pól na każdą tabelę**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-134">Note that there is currently a limit of **20 custom fields per table**.</span></span>
9. <span data-ttu-id="8a3ba-135">Opuszczenie okna dialogowego **Utwórz nowe pole** spowoduje powrót do okna dialogowego **Wstaw pola**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-135">Leaving the **Create new field** dialog box will return you to the **Insert fields** dialog box.</span></span> <span data-ttu-id="8a3ba-136">Wszystkie właśnie dodane pola niestandardowe zostaną automatycznie oznaczone na liście pól jako przeznaczone do wstawienia do formularza.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-136">Any custom fields that were just added will be automatically marked in the field list to be inserted into the form.</span></span>
10. <span data-ttu-id="8a3ba-137">Kliknij przycisk **Wstaw**, aby wstawić oznaczone pola do wybranego regionu formularza.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-137">Click **Insert** to insert the marked fields into the selected region of the form.</span></span>
11. <span data-ttu-id="8a3ba-138">**Opcjonalnie:** Na pasku narzędzi personalizacji włącz tryb **Przenieś**, aby przenieść nowe pola w żądane miejsce w wybranym regionie.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-138">**Optional:** Enable **Move** mode from the personalization toolbar to move the new fields to their desired location in the selected region.</span></span> <span data-ttu-id="8a3ba-139">Zobacz temat [Dostosowanie do użytkownika](personalize-user-experience.md), aby uzyskać więcej informacji na temat używania różnych funkcji personalizacji w celu dostosowania formularza do własnych potrzeb.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-139">See [Personalize the user experience](personalize-user-experience.md) for more information about how to use the various personalization capabilities to optimize a form for your personal usage.</span></span>

## <a name="sharing-custom-fields-with-other-users"></a><span data-ttu-id="8a3ba-140">Udostępnianie niestandardowych pól innym użytkownikom</span><span class="sxs-lookup"><span data-stu-id="8a3ba-140">Sharing custom fields with other users</span></span>

<span data-ttu-id="8a3ba-141">Po utworzeniu niestandardowego pola i jego uwidocznieniu w formularzu można innym użytkownikom w systemie udostępnić zaktualizowany widok strony zawierający nowe pole.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-141">After you have created a custom field and exposed it on a form, you might want to provide this updated page view that includes the new field to other users in the system.</span></span> <span data-ttu-id="8a3ba-142">Można to zrobić na dwa różne sposoby przy użyciu funkcji personalizacji produktu:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-142">This can be accomplished in two different ways using the personalization capabilities of the product:</span></span>

- <span data-ttu-id="8a3ba-143">Zalecanym sposobem jest skorzystanie z pośrednictwa administratora systemu, który może rozesłać personalizację do wszystkich użytkowników lub tylko do grupy użytkowników.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-143">The recommended route is through the system administrator, who can push a personalization to all users or a subset of users.</span></span> <span data-ttu-id="8a3ba-144">Aby uzyskać więcej informacji, zobacz [Dostosowanie do użytkownika](personalize-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="8a3ba-144">See [Personalize the user experience](personalize-user-experience.md) for more details.</span></span>
- <span data-ttu-id="8a3ba-145">Alternatywnie można wyeksportować swoje zmiany (nazywane *personalizacjami*), wysłać do jednego lub więcej użytkowników, a następnie polecić użytkownikom, aby zaimportowali zmiany.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-145">Alternatively, you can export your changes (called *personalizations*), send them to one or more users, and have each of those users import your changes.</span></span> <span data-ttu-id="8a3ba-146">Opcja **Zarządzaj** umieszczona na pasku narzędzi personalizacji umożliwia eksportowanie i importowanie personalizacji.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-146">The **Manage** option on the personalization toolbar enables you to export and import personalizations.</span></span>

## <a name="managing-custom-fields"></a><span data-ttu-id="8a3ba-147">Zarządzanie polami niestandardowymi</span><span class="sxs-lookup"><span data-stu-id="8a3ba-147">Managing custom fields</span></span>

<span data-ttu-id="8a3ba-148">Zarządzanie wszystkimi polami niestandardowymi w systemie można realizować za pomocą strony **Pola niestandardowe** w module Administrowanie systemem.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-148">Management of all the custom fields in the system can be accomplished through the **Custom fields** page in the System administration module.</span></span> <span data-ttu-id="8a3ba-149">Ta strona umożliwia użytkownikom dostęp do wielu funkcji, takich jak:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-149">This page allows users access to many capabilities, including:</span></span>

- <span data-ttu-id="8a3ba-150">Wyświetlanie listy wszystkich niestandardowych pól w systemie.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-150">Viewing a list of all custom fields in the system.</span></span>
- <span data-ttu-id="8a3ba-151">Ograniczone edytowanie istniejących pól niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-151">Limited editing of existing custom fields.</span></span>
- <span data-ttu-id="8a3ba-152">Usuwanie pól niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-152">Deleting custom fields.</span></span>
- <span data-ttu-id="8a3ba-153">Udostępnianie niestandardowych pól w jednostkach danych.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-153">Exposing custom fields on data entities.</span></span>
- <span data-ttu-id="8a3ba-154">Tłumaczenie etykiet i tekstów pomocy pól niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-154">Providing translations of custom field labels and help text.</span></span>

### <a name="viewing-all-custom-fields"></a><span data-ttu-id="8a3ba-155">Wyświetlanie wszystkich pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="8a3ba-155">Viewing all custom fields</span></span>

<span data-ttu-id="8a3ba-156">Strona **Pola niestandardowe** umożliwia podgląd wszystkich pól niestandardowych, które zostały zdefiniowane w systemie.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-156">The **Custom fields** page provides visibility to all the custom fields that have been defined in the system.</span></span> <span data-ttu-id="8a3ba-157">Po prostu zaznacz tabelę, która Cię interesuje, a strona zostanie zaktualizowana, pokazując listę pól niestandardowych skojarzonych z tą tabelą.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-157">Simply select the table that you are interested in, and the page will update to show a list of the custom fields associated with that table.</span></span> <span data-ttu-id="8a3ba-158">Wybranie pola niestandardowego z listy pozwoli wyświetlić wszystkie szczegółowe informacje o polu.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-158">Choosing a custom field from the list will allow you to view all the details about the field.</span></span>

### <a name="editing-custom-fields"></a><span data-ttu-id="8a3ba-159">Edytowanie pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="8a3ba-159">Editing custom fields</span></span>

<span data-ttu-id="8a3ba-160">Po utworzeniu pola niestandardowego tylko niektóre informacje o tym polu można modyfikować na stronie **Pola niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-160">After a custom field has been created, only certain pieces of information about the custom field can be modified on the **Custom fields** page.</span></span>

<span data-ttu-id="8a3ba-161">*Można* modyfikować następujące atrybuty:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-161">You *can* modify these attributes:</span></span>

- <span data-ttu-id="8a3ba-162">Etykiety</span><span class="sxs-lookup"><span data-stu-id="8a3ba-162">Label</span></span>
- <span data-ttu-id="8a3ba-163">Tekst pomocy</span><span class="sxs-lookup"><span data-stu-id="8a3ba-163">Help text</span></span>
- <span data-ttu-id="8a3ba-164">Długość w przypadku pól tekstowych</span><span class="sxs-lookup"><span data-stu-id="8a3ba-164">Length, for Text fields</span></span>

<span data-ttu-id="8a3ba-165">*Nie można* edytować następujących atrybutów:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-165">You *cannot* edit the following attributes:</span></span>

- <span data-ttu-id="8a3ba-166">Nazwa pola</span><span class="sxs-lookup"><span data-stu-id="8a3ba-166">Field name</span></span>
- <span data-ttu-id="8a3ba-167">Typ danych</span><span class="sxs-lookup"><span data-stu-id="8a3ba-167">Data type</span></span>

<span data-ttu-id="8a3ba-168">Ponadto w przypadku pól list wyboru można zmienić kolejność zestawu prawidłowych wartości dla pola niestandardowego oraz dodać nowe wartości, ale nie można usunąć istniejących wartości pola listy wyboru.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-168">Additionally, for picklist fields, the set of valid values for the custom field can be reordered, and new values can be added; however, existing values for the picklist field cannot be removed.</span></span> <span data-ttu-id="8a3ba-169">Pamiętaj, aby kliknąć przycisk **Zastosuj zmiany** po zakończeniu edytowania pól konkretnej tabeli, tak zmiany aby zostały zapisane.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-169">Remember to click **Apply changes** when you are done editing fields for a particular table so the changes are saved.</span></span>

### <a name="exposing-custom-fields-on-data-entities"></a><span data-ttu-id="8a3ba-170">Udostępnianie niestandardowych pól w jednostkach danych</span><span class="sxs-lookup"><span data-stu-id="8a3ba-170">Exposing custom fields on data entities</span></span>

<span data-ttu-id="8a3ba-171">Może być również ważne, aby pola niestandardowe były wyświetlane w jednostkach danych.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-171">It may also be important to allow custom fields to be visible on data entities.</span></span> <span data-ttu-id="8a3ba-172">Jednostki danych są wykorzystywane w funkcji [Otwórz w aplikacji pakietu Office](../../dev-itpro/office-integration/office-integration.md), jak również w scenariuszach importu/eksportu danych.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-172">Data entities are utilized in the [Open in Office](../../dev-itpro/office-integration/office-integration.md) feature, as well as for data import/export scenarios.</span></span>

<span data-ttu-id="8a3ba-173">Wykonaj poniższe czynności, aby włączyć wyświetlanie pola niestandardowego w jednostce danych:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-173">Follow these steps to expose a custom field on a data entity:</span></span>

1. <span data-ttu-id="8a3ba-174">Wybierz pole niestandardowe w formularzu **Pola niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-174">Select the custom field on the **Custom fields** form.</span></span>
2. <span data-ttu-id="8a3ba-175">Rozwiń sekcję **Jednostki**, aby zobaczyć zestaw odnośnych jednostek.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-175">Expand the **Entities** section to view the set of relevant entities.</span></span>
3. <span data-ttu-id="8a3ba-176">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-176">Click the **Edit** button.</span></span>
4. <span data-ttu-id="8a3ba-177">Zmodyfikuj ustawienie pola **Włączone** w taki sposób, aby było wybierane dla każdej jednostki, w której ma być widoczne.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-177">Modify the **Enabled** field to be selected for each entity that should expose this field.</span></span>
5. <span data-ttu-id="8a3ba-178">Kliknij przycisk **Zastosuj zmiany**, aby zapisać wybrane ustawienia.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-178">Click **Apply changes** to save your selections.</span></span>

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a><span data-ttu-id="8a3ba-179">Pozwalanie na wyświetlanie niestandardowych pól w innych językach</span><span class="sxs-lookup"><span data-stu-id="8a3ba-179">Allowing custom fields to be displayed in other languages</span></span>

<span data-ttu-id="8a3ba-180">Ponieważ dostępu do pól niestandardowych mogą potrzebować użytkownicy posługujący się różnymi językami, strona **Pola niestandardowe** zawiera mechanizm umożliwiający tłumaczenie etykiety i tekstu pomocy pola niestandardowego na inne języki.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-180">Because custom fields may need to be accessed by users in a variety of languages, the **Custom fields** page provides a mechanism to allow the label and help text for a custom field to be translated into other languages.</span></span>

<span data-ttu-id="8a3ba-181">Kroki poniżej opisują proces tłumaczenia pól niestandardowych na inne języki:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-181">The following steps describe the process for translating custom fields in other languages:</span></span>

1. <span data-ttu-id="8a3ba-182">Wybierz pole niestandardowe na stronie **Pola niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-182">Select the custom field on the **Custom fields** page.</span></span>
2. <span data-ttu-id="8a3ba-183">W okienku akcji wybierz przycisk **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-183">Select the **Translations** button in the Action Pane.</span></span> <span data-ttu-id="8a3ba-184">Spowoduje to otwarcie menu rozwijanego z istniejącymi tłumaczeniami dla tego pola.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-184">This will open a drop-down menu with existing translations for this field.</span></span>
3. <span data-ttu-id="8a3ba-185">Menu rozwijane **Język** zawiera zestaw języków, dla których zostały już przygotowane tłumaczenia.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-185">The **Language** drop-down menu shows the set of languages for which translations have already been provided.</span></span>

    <span data-ttu-id="8a3ba-186">Jeśli chcesz edytować istniejące tłumaczenie, wybierz żądany język z menu, a następnie zmodyfikuj wartości etykiety i tekstu pomocy.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-186">If you want to edit an existing translation, select the desired language from the menu and modify the values for the label and help text.</span></span>

    <span data-ttu-id="8a3ba-187">W przeciwnym razie kliknij przycisk **Dodaj język**, wybierz żądany język z menu, a następnie wprowadź wartości tłumaczeń dla etykiety i tekstu pomocy.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-187">Otherwise, click the **Add language** button, select the desired language from the menu, and then provide translated values for the label and help text.</span></span>

4. <span data-ttu-id="8a3ba-188">Po zakończeniu kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-188">Click **OK** when you are finished.</span></span>

### <a name="deleting-custom-fields"></a><span data-ttu-id="8a3ba-189">Usuwanie pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="8a3ba-189">Deleting custom fields</span></span>

<span data-ttu-id="8a3ba-190">W rzadkich przypadkach może się okazać, że pole niestandardowe nie jest już potrzebne.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-190">In some rare cases, you may decide that a custom field is no longer needed.</span></span> <span data-ttu-id="8a3ba-191">W takiej sytuacji administrator systemu może usunąć pole ze strony **Pola niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-191">When this occurs, a system administrator can choose to delete the field from the **Custom fields** page.</span></span> <span data-ttu-id="8a3ba-192">W tym celu upewnij się, że jest zaznaczone poprawne pole, kliknij przycisk **Usuń**, kliknij przycisk **Tak**, aby potwierdzić zamiar usunięcia, a na koniec kliknij przycisk **Zastosuj zmiany**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-192">To do this, ensure the correct field is selected, click **Delete**, click **Yes** to confirm the deletion, and finally click **Apply changes**.</span></span>

> [!NOTE]
> <span data-ttu-id="8a3ba-193">Tej czynności nie będzie można cofnąć, a jej wynikiem będzie trwałe usunięcie danych skojarzonych z polem z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-193">This action cannot be undone, and will result in the data associated with the field being permanently deleted from the database.</span></span>

## <a name="appendix"></a><span data-ttu-id="8a3ba-194">Dodatek</span><span class="sxs-lookup"><span data-stu-id="8a3ba-194">Appendix</span></span>

### <a name="who-can-create-custom-fields"></a><span data-ttu-id="8a3ba-195">Kto może tworzyć pola niestandardowe?</span><span class="sxs-lookup"><span data-stu-id="8a3ba-195">Who can create custom fields?</span></span>

<span data-ttu-id="8a3ba-196">Dla bezpieczeństwa systemu tylko administratorzy systemu mogą domyślnie tworzyć pola niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-196">As a safeguard to the system, only system administrators are able to create custom fields by default.</span></span> <span data-ttu-id="8a3ba-197">Jeśli jednak organizacja uzna za konieczne, administrator systemu może niektórym użytkownikom zaawansowanym nadać prawo tworzenia niestandardowych pól, używając do tego roli **Użytkownik zaawansowany personalizacji środowiska uruchomieniowego**.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-197">However, those power users whom the organization deems necessary can be given rights to create custom fields by a system administrator using the **Runtime customization power user** security role.</span></span> <span data-ttu-id="8a3ba-198">Użytkownicy bez tej roli zabezpieczeń nie będą mogli tworzyć pól niestandardowych, ale będą widzieć pola niestandardowe dodane przez innych użytkowników w systemie oraz będą mogli z nich korzystać.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-198">Users without this security role will not be able to create custom fields, but will still be able to see and interact with custom fields added by other users in the system.</span></span>

### <a name="what-tables-support-custom-fields"></a><span data-ttu-id="8a3ba-199">Które tabele obsługują pola niestandardowe?</span><span class="sxs-lookup"><span data-stu-id="8a3ba-199">What tables support custom fields?</span></span>

<span data-ttu-id="8a3ba-200">Ze względów wydajnościowych i technicznych obecnie pola niestandardowe można dodawać tylko do tabel spełniających następujące warunki.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-200">For performance and technical reasons, only tables that meet the following conditions currently allow custom fields to be added.</span></span>

- <span data-ttu-id="8a3ba-201">Tabela musi być oznakowana jako należąca do jednej z poniższych grup:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-201">The table must be tagged as one of these groups:</span></span>

    - <span data-ttu-id="8a3ba-202">Grupa</span><span class="sxs-lookup"><span data-stu-id="8a3ba-202">Group</span></span>
    - <span data-ttu-id="8a3ba-203">WorksheetHeader</span><span class="sxs-lookup"><span data-stu-id="8a3ba-203">WorksheetHeader</span></span>
    - <span data-ttu-id="8a3ba-204">Główny</span><span class="sxs-lookup"><span data-stu-id="8a3ba-204">Main</span></span>
    - <span data-ttu-id="8a3ba-205">Różne</span><span class="sxs-lookup"><span data-stu-id="8a3ba-205">Miscellaneous</span></span>
    - <span data-ttu-id="8a3ba-206">Parametr</span><span class="sxs-lookup"><span data-stu-id="8a3ba-206">Parameter</span></span>
    - <span data-ttu-id="8a3ba-207">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="8a3ba-207">Reference</span></span>
    - <span data-ttu-id="8a3ba-208">TransactionHeader</span><span class="sxs-lookup"><span data-stu-id="8a3ba-208">TransactionHeader</span></span>

- <span data-ttu-id="8a3ba-209">Tabela nie może być rozszerzeniem innej tabeli.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-209">The table cannot extend another table.</span></span>
- <span data-ttu-id="8a3ba-210">Tabela nie może być oznaczona jako systemowa.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-210">The table cannot be marked as a system table.</span></span>
- <span data-ttu-id="8a3ba-211">Tabela nie może być tymczasowa.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-211">The table cannot be a temporary table.</span></span>
