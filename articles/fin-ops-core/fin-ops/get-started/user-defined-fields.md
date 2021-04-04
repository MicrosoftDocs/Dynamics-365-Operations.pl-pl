---
title: Tworzenie pól niestandardowych i praca z nimi
description: W tym temacie opisano, jak tworzyć niestandardowe pola za pomocą interfejsu użytkownika w celu dostosowania aplikacji do unikatowych potrzeb firmy.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 9c97393419278e49b112f98ba6dcc4bec9565cb7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566277"
---
# <a name="create-and-work-with-custom-fields"></a><span data-ttu-id="c6ae2-103">Tworzenie pól niestandardowych i praca z nimi</span><span class="sxs-lookup"><span data-stu-id="c6ae2-103">Create and work with custom fields</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6ae2-104">Zawiera już w standardzie rozbudowany zestaw pól do zarządzania różnorodnymi procesami biznesowymi, ale czasami firma musi śledzić dodatkowe informacje w systemie.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-104">While there is an extensive set of fields out-of-the-box for managing a broad range of business processes, sometimes there is a need for a company to track additional information in the system.</span></span> <span data-ttu-id="c6ae2-105">Podczas gdy programiści mogą dodawać te pola jako rozszerzenia w narzędziach programistycznych, funkcja pól niestandardowych umożliwia dodawanie pól bezpośrednio z interfejsu użytkownika, co pozwala na dostosowanie aplikacji do potrzeb firmy przy użyciu przeglądarki sieci Web.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-105">While programmers can be used to add those fields as extensions in the developer tools, the custom fields feature allows fields to be added directly from the user interface, thereby allowing you to tailor the application to fit your business using your web browser.</span></span>

<span data-ttu-id="c6ae2-106">Opcja dodawania pól niestandardowych jest dostępna w aktualizacji platformy 13 i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-106">The ability to add custom fields is available in platform update 13 and later.</span></span> <span data-ttu-id="c6ae2-107">Tylko użytkownicy z uprawnieniami specjalnymi mają dostęp do tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-107">Only users with special permissions have access to this feature.</span></span>

<span data-ttu-id="c6ae2-108">W tym nagraniu wideo przedstawiono, jak łatwe jest do dodawanie niestandardowego pola do strony: [Dodawanie pól niestandardowych](https://www.youtube.com/watch?v=gWSGZI9Vtnc).</span><span class="sxs-lookup"><span data-stu-id="c6ae2-108">This video shows how easy it is to add a custom field to a page: [Adding custom fields](https://www.youtube.com/watch?v=gWSGZI9Vtnc).</span></span>

## <a name="creating-custom-fields"></a><span data-ttu-id="c6ae2-109">Tworzenie pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="c6ae2-109">Creating custom fields</span></span>

<span data-ttu-id="c6ae2-110">Po stwierdzeniu, które dodatkowe informacje mają być śledzone w aplikacji, można utworzyć niestandardowe pole w odpowiedniej tabeli, po czym udostępnić je na stronie.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-110">After you've identified additional information that you would like to track in the application, you can create the custom field on the appropriate table and expose that new field on a page.</span></span>

<span data-ttu-id="c6ae2-111">Kroki poniżej opisują proces tworzenia niestandardowego pola i umieszczania go w formularzu.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-111">The following steps describe the process for creating a custom field and placing that field on a form.</span></span>

1. <span data-ttu-id="c6ae2-112">Przejdź do formularza, w którym jest potrzebne nowe pole.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-112">Navigate to the form where the new field is needed.</span></span>
2. <span data-ttu-id="c6ae2-113">Ponieważ ostatecznym celem jest uwidocznienie niestandardowego pola w formularzu, punkt wejścia tworzenia niestandardowych pól znajduje się wewnątrz środowiska personalizacji.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-113">Because the end goal is to expose the custom field on a form, the entry point for creating custom fields exists inside the personalization experience.</span></span> <span data-ttu-id="c6ae2-114">Otwórz pasek narzędzi personalizacji, wybierając kolejno polecenia **Opcje** i **Personalizuj ten formularz**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-114">Open the personalization toolbar by selecting **Options**, and then **Personalize this form**.</span></span>
3. <span data-ttu-id="c6ae2-115">Kliknij kolejno opcje **Wstaw** i **Pole**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-115">Click **Insert** and then **Field**.</span></span>
4. <span data-ttu-id="c6ae2-116">Wybierz region formularza, w którym nowe pole ma być wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-116">Select the region of the form where you want to expose the new field.</span></span> <span data-ttu-id="c6ae2-117">Po zaznaczeniu regionu w oknie dialogowym **Wstaw pola** zostanie wyświetlona lista istniejących pól, które można wstawić do wybranego regionu.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-117">After selection, the **Insert fields** dialog box will display a list of existing fields that can be inserted into the selected region of the form.</span></span>
5. <span data-ttu-id="c6ae2-118">Upewnij się, że interesujące Cię pole jeszcze nie występuje na liście.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-118">Ensure that the field you are interested in does not already exist in the list.</span></span> <span data-ttu-id="c6ae2-119">Jeśli występuje, możesz po prostu zaznaczyć je na liście i kliknąć przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-119">If it does, you can simply select that field in the list and click **Insert**.</span></span>
6. <span data-ttu-id="c6ae2-120">Nad listą kliknij przycisk **Utwórz nowe pole**, aby zainicjować proces tworzenia pola niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-120">Click the **Create new field** button above the list to initiate the process of creating a custom field.</span></span> <span data-ttu-id="c6ae2-121">Spowoduje to otwarcie okna dialogowego **Utwórz nowe pole**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-121">This will open the **Create new field** dialog box.</span></span>

    <span data-ttu-id="c6ae2-122">Jeśli nie widać przycisku **Utwórz nowe pole**, nie masz uprawnień niezbędnych do korzystania z tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-122">If you do not see the **Create new field** button, you do not have the necessary permissions to use this feature.</span></span>

7. <span data-ttu-id="c6ae2-123">W oknie dialogowym **Utwórz nowe pole** wprowadź następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-123">In the **Create new field** dialog box, enter the following information.</span></span>

    1. <span data-ttu-id="c6ae2-124">Wybierz tabelę bazy danych, do której powinno zostać dodane to pole.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-124">Select the database table where this field should be added.</span></span> <span data-ttu-id="c6ae2-125">Należy zauważyć, że na liście rozwijanej będą wyświetlane tylko tabele, które obsługują niestandardowe pola.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-125">Note that only tables that support custom fields will appear in the drop-down list.</span></span> <span data-ttu-id="c6ae2-126">Sekcja poniżej zawiera szczegółowe informacje techniczne o obsługiwanych tabelach.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-126">See the section below for technical details on supported tables.</span></span>
    2. <span data-ttu-id="c6ae2-127">Wybierz typ danych dla nowego pola.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-127">Select the data type for the new field.</span></span> <span data-ttu-id="c6ae2-128">Dostępne typy danych to Pole wyboru, Data, Data i godzina, Liczba dziesiętna, Liczba, Lista wyboru i Tekst.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-128">The available data types are checkbox, date, date time, decimal, number, picklist, and text.</span></span>

        - <span data-ttu-id="c6ae2-129">Jeśli wybrano typ danych Tekst, można również określić maksymalną długości tekstu, jaki można wprowadzić w tym polu.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-129">If you choose the text data type, you can also specify the maximum length of the text that can be entered in this field.</span></span>
        - <span data-ttu-id="c6ae2-130">W przypadku wybrania typu danych Lista wyboru można także wybrać zestaw prawidłowych wartości dla pola.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-130">If you choose the picklist data type, you can also select the set of valid values for the field.</span></span>

    3. <span data-ttu-id="c6ae2-131">Wprowadź nazwę, etykietę i tekst pomocy dla pola.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-131">Provide a name, label, and help text for the field.</span></span> <span data-ttu-id="c6ae2-132">Nazwa odpowiada fizycznej nazwie pola w bazie danych, podczas gdy etykieta i tekst pomocy to teksty używane do reprezentowania tego pola w interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-132">The name corresponds to the physical field name in the database, whereas the label and help text are the text used to represent this field in the user interface.</span></span>

8. <span data-ttu-id="c6ae2-133">Jeśli jest to jedyne pole, które trzeba utworzyć dla tego formularza, kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-133">If this is the only field that you need to create for this form, click **Save**.</span></span> <span data-ttu-id="c6ae2-134">Jeśli trzeba utworzyć dodatkowe pola, kliknij przycisk **Zapisz i nowy**, a następnie wróć do kroku 7.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-134">If you need to create additional fields, click **Save and new** and go back to step 7.</span></span> <span data-ttu-id="c6ae2-135">Należy zauważyć, że obecnie istnieje limit **20 niestandardowych pól na każdą tabelę**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-135">Note that there is currently a limit of **20 custom fields per table**.</span></span>
9. <span data-ttu-id="c6ae2-136">Opuszczenie okna dialogowego **Utwórz nowe pole** spowoduje powrót do okna dialogowego **Wstaw pola**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-136">Leaving the **Create new field** dialog box will return you to the **Insert fields** dialog box.</span></span> <span data-ttu-id="c6ae2-137">Wszystkie właśnie dodane pola niestandardowe zostaną automatycznie oznaczone na liście pól jako przeznaczone do wstawienia do formularza.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-137">Any custom fields that were just added will be automatically marked in the field list to be inserted into the form.</span></span>
10. <span data-ttu-id="c6ae2-138">Kliknij przycisk **Wstaw**, aby wstawić oznaczone pola do wybranego regionu formularza.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-138">Click **Insert** to insert the marked fields into the selected region of the form.</span></span>
11. <span data-ttu-id="c6ae2-139">**Opcjonalnie:** Na pasku narzędzi personalizacji włącz tryb **Przenieś**, aby przenieść nowe pola w żądane miejsce w wybranym regionie.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-139">**Optional:** Enable **Move** mode from the personalization toolbar to move the new fields to their desired location in the selected region.</span></span> <span data-ttu-id="c6ae2-140">Zobacz temat [Dostosowanie do użytkownika](personalize-user-experience.md), aby uzyskać więcej informacji na temat używania różnych funkcji personalizacji w celu dostosowania formularza do własnych potrzeb.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-140">See [Personalize the user experience](personalize-user-experience.md) for more information about how to use the various personalization capabilities to optimize a form for your personal usage.</span></span>

## <a name="sharing-custom-fields-with-other-users"></a><span data-ttu-id="c6ae2-141">Udostępnianie niestandardowych pól innym użytkownikom</span><span class="sxs-lookup"><span data-stu-id="c6ae2-141">Sharing custom fields with other users</span></span>

<span data-ttu-id="c6ae2-142">Po utworzeniu niestandardowego pola i jego uwidocznieniu w formularzu można innym użytkownikom w systemie udostępnić zaktualizowany widok strony zawierający nowe pole.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-142">After you have created a custom field and exposed it on a form, you might want to provide this updated page view that includes the new field to other users in the system.</span></span> <span data-ttu-id="c6ae2-143">Można to zrobić na dwa różne sposoby przy użyciu funkcji personalizacji produktu:</span><span class="sxs-lookup"><span data-stu-id="c6ae2-143">This can be accomplished in two different ways using the personalization capabilities of the product:</span></span>

- <span data-ttu-id="c6ae2-144">Zalecanym sposobem jest skorzystanie z pośrednictwa administratora systemu, który może rozesłać personalizację do wszystkich użytkowników lub tylko do grupy użytkowników.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-144">The recommended route is through the system administrator, who can push a personalization to all users or a subset of users.</span></span> <span data-ttu-id="c6ae2-145">Aby uzyskać więcej informacji, zobacz [Dostosowanie do użytkownika](personalize-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="c6ae2-145">See [Personalize the user experience](personalize-user-experience.md) for more details.</span></span>
- <span data-ttu-id="c6ae2-146">Alternatywnie można wyeksportować swoje zmiany (nazywane *personalizacjami*), wysłać do jednego lub więcej użytkowników, a następnie polecić użytkownikom, aby zaimportowali zmiany.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-146">Alternatively, you can export your changes (called *personalizations*), send them to one or more users, and have each of those users import your changes.</span></span> <span data-ttu-id="c6ae2-147">Opcja **Zarządzaj** umieszczona na pasku narzędzi personalizacji umożliwia eksportowanie i importowanie personalizacji.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-147">The **Manage** option on the personalization toolbar enables you to export and import personalizations.</span></span>

## <a name="managing-custom-fields"></a><span data-ttu-id="c6ae2-148">Zarządzanie polami niestandardowymi</span><span class="sxs-lookup"><span data-stu-id="c6ae2-148">Managing custom fields</span></span>

<span data-ttu-id="c6ae2-149">Zarządzanie wszystkimi polami niestandardowymi w systemie można realizować za pomocą strony **Pola niestandardowe** w module Administrowanie systemem.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-149">Management of all the custom fields in the system can be accomplished through the **Custom fields** page in the System administration module.</span></span> <span data-ttu-id="c6ae2-150">Ta strona umożliwia użytkownikom dostęp do wielu funkcji, takich jak:</span><span class="sxs-lookup"><span data-stu-id="c6ae2-150">This page allows users access to many capabilities, including:</span></span>

- <span data-ttu-id="c6ae2-151">Wyświetlanie listy wszystkich niestandardowych pól w systemie.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-151">Viewing a list of all custom fields in the system.</span></span>
- <span data-ttu-id="c6ae2-152">Ograniczone edytowanie istniejących pól niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-152">Limited editing of existing custom fields.</span></span>
- <span data-ttu-id="c6ae2-153">Usuwanie pól niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-153">Deleting custom fields.</span></span>
- <span data-ttu-id="c6ae2-154">Udostępnianie niestandardowych pól w jednostkach danych.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-154">Exposing custom fields on data entities.</span></span>
- <span data-ttu-id="c6ae2-155">Tłumaczenie etykiet i tekstów pomocy pól niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-155">Providing translations of custom field labels and help text.</span></span>

### <a name="viewing-all-custom-fields"></a><span data-ttu-id="c6ae2-156">Wyświetlanie wszystkich pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="c6ae2-156">Viewing all custom fields</span></span>

<span data-ttu-id="c6ae2-157">Strona **Pola niestandardowe** umożliwia podgląd wszystkich pól niestandardowych, które zostały zdefiniowane w systemie.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-157">The **Custom fields** page provides visibility to all the custom fields that have been defined in the system.</span></span> <span data-ttu-id="c6ae2-158">Po prostu zaznacz tabelę, która Cię interesuje, a strona zostanie zaktualizowana, pokazując listę pól niestandardowych skojarzonych z tą tabelą.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-158">Simply select the table that you are interested in, and the page will update to show a list of the custom fields associated with that table.</span></span> <span data-ttu-id="c6ae2-159">Wybranie pola niestandardowego z listy pozwoli wyświetlić wszystkie szczegółowe informacje o polu.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-159">Choosing a custom field from the list will allow you to view all the details about the field.</span></span>

### <a name="editing-custom-fields"></a><span data-ttu-id="c6ae2-160">Edytowanie pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="c6ae2-160">Editing custom fields</span></span>

<span data-ttu-id="c6ae2-161">Po utworzeniu pola niestandardowego tylko niektóre informacje o tym polu można modyfikować na stronie **Pola niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-161">After a custom field has been created, only certain pieces of information about the custom field can be modified on the **Custom fields** page.</span></span>

<span data-ttu-id="c6ae2-162">*Można* modyfikować następujące atrybuty:</span><span class="sxs-lookup"><span data-stu-id="c6ae2-162">You *can* modify these attributes:</span></span>

- <span data-ttu-id="c6ae2-163">Etykiety</span><span class="sxs-lookup"><span data-stu-id="c6ae2-163">Label</span></span>
- <span data-ttu-id="c6ae2-164">Tekst pomocy</span><span class="sxs-lookup"><span data-stu-id="c6ae2-164">Help text</span></span>
- <span data-ttu-id="c6ae2-165">Długość w przypadku pól tekstowych</span><span class="sxs-lookup"><span data-stu-id="c6ae2-165">Length, for Text fields</span></span>

<span data-ttu-id="c6ae2-166">*Nie można* edytować następujących atrybutów:</span><span class="sxs-lookup"><span data-stu-id="c6ae2-166">You *cannot* edit the following attributes:</span></span>

- <span data-ttu-id="c6ae2-167">Nazwa pola</span><span class="sxs-lookup"><span data-stu-id="c6ae2-167">Field name</span></span>
- <span data-ttu-id="c6ae2-168">Typ danych</span><span class="sxs-lookup"><span data-stu-id="c6ae2-168">Data type</span></span>

<span data-ttu-id="c6ae2-169">Ponadto w przypadku pól list wyboru można zmienić kolejność zestawu prawidłowych wartości dla pola niestandardowego oraz dodać nowe wartości, ale nie można usunąć istniejących wartości pola listy wyboru.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-169">Additionally, for picklist fields, the set of valid values for the custom field can be reordered, and new values can be added; however, existing values for the picklist field cannot be removed.</span></span> <span data-ttu-id="c6ae2-170">Pamiętaj, aby kliknąć przycisk **Zastosuj zmiany** po zakończeniu edytowania pól konkretnej tabeli, tak zmiany aby zostały zapisane.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-170">Remember to click **Apply changes** when you are done editing fields for a particular table so the changes are saved.</span></span>

### <a name="exposing-custom-fields-on-data-entities"></a><span data-ttu-id="c6ae2-171">Udostępnianie niestandardowych pól w jednostkach danych</span><span class="sxs-lookup"><span data-stu-id="c6ae2-171">Exposing custom fields on data entities</span></span>

<span data-ttu-id="c6ae2-172">Może być również ważne, aby pola niestandardowe były wyświetlane w jednostkach danych.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-172">It may also be important to allow custom fields to be visible on data entities.</span></span> <span data-ttu-id="c6ae2-173">Jednostki danych są wykorzystywane w funkcji [Omówienie integracji danych z pakietem Office](../../dev-itpro/office-integration/office-integration.md), jak również w scenariuszach importu/eksportu danych.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-173">Data entities are utilized in the [Office integration overview](../../dev-itpro/office-integration/office-integration.md) feature, as well as for data import/export scenarios.</span></span>

<span data-ttu-id="c6ae2-174">Wykonaj poniższe czynności, aby włączyć wyświetlanie pola niestandardowego w jednostce danych:</span><span class="sxs-lookup"><span data-stu-id="c6ae2-174">Follow these steps to expose a custom field on a data entity:</span></span>

1. <span data-ttu-id="c6ae2-175">Wybierz pole niestandardowe w formularzu **Pola niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-175">Select the custom field on the **Custom fields** form.</span></span>
2. <span data-ttu-id="c6ae2-176">Rozwiń sekcję **Jednostki**, aby zobaczyć zestaw odnośnych jednostek.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-176">Expand the **Entities** section to view the set of relevant entities.</span></span>
3. <span data-ttu-id="c6ae2-177">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-177">Click the **Edit** button.</span></span>
4. <span data-ttu-id="c6ae2-178">Zmodyfikuj ustawienie pola **Włączone** w taki sposób, aby było wybierane dla każdej jednostki, w której ma być widoczne.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-178">Modify the **Enabled** field to be selected for each entity that should expose this field.</span></span>
5. <span data-ttu-id="c6ae2-179">Kliknij przycisk **Zastosuj zmiany**, aby zapisać wybrane ustawienia.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-179">Click **Apply changes** to save your selections.</span></span>

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a><span data-ttu-id="c6ae2-180">Pozwalanie na wyświetlanie niestandardowych pól w innych językach</span><span class="sxs-lookup"><span data-stu-id="c6ae2-180">Allowing custom fields to be displayed in other languages</span></span>

<span data-ttu-id="c6ae2-181">Ponieważ dostępu do pól niestandardowych mogą potrzebować użytkownicy posługujący się różnymi językami, strona **Pola niestandardowe** zawiera mechanizm umożliwiający tłumaczenie etykiety i tekstu pomocy pola niestandardowego na inne języki.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-181">Because custom fields may need to be accessed by users in a variety of languages, the **Custom fields** page provides a mechanism to allow the label and help text for a custom field to be translated into other languages.</span></span>

<span data-ttu-id="c6ae2-182">Kroki poniżej opisują proces tłumaczenia pól niestandardowych na inne języki:</span><span class="sxs-lookup"><span data-stu-id="c6ae2-182">The following steps describe the process for translating custom fields in other languages:</span></span>

1. <span data-ttu-id="c6ae2-183">Wybierz pole niestandardowe na stronie **Pola niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-183">Select the custom field on the **Custom fields** page.</span></span>
2. <span data-ttu-id="c6ae2-184">W okienku akcji wybierz przycisk **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-184">Select the **Translations** button in the Action Pane.</span></span> <span data-ttu-id="c6ae2-185">Spowoduje to otwarcie menu rozwijanego z istniejącymi tłumaczeniami dla tego pola.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-185">This will open a drop-down menu with existing translations for this field.</span></span>
3. <span data-ttu-id="c6ae2-186">Menu rozwijane **Język** zawiera zestaw języków, dla których zostały już przygotowane tłumaczenia.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-186">The **Language** drop-down menu shows the set of languages for which translations have already been provided.</span></span>

    <span data-ttu-id="c6ae2-187">Jeśli chcesz edytować istniejące tłumaczenie, wybierz żądany język z menu, a następnie zmodyfikuj wartości etykiety i tekstu pomocy.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-187">If you want to edit an existing translation, select the desired language from the menu and modify the values for the label and help text.</span></span>

    <span data-ttu-id="c6ae2-188">W przeciwnym razie kliknij przycisk **Dodaj język**, wybierz żądany język z menu, a następnie wprowadź wartości tłumaczeń dla etykiety i tekstu pomocy.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-188">Otherwise, click the **Add language** button, select the desired language from the menu, and then provide translated values for the label and help text.</span></span>

4. <span data-ttu-id="c6ae2-189">Po zakończeniu kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-189">Click **OK** when you are finished.</span></span>

### <a name="deleting-custom-fields"></a><span data-ttu-id="c6ae2-190">Usuwanie pól niestandardowych</span><span class="sxs-lookup"><span data-stu-id="c6ae2-190">Deleting custom fields</span></span>

<span data-ttu-id="c6ae2-191">W rzadkich przypadkach może się okazać, że pole niestandardowe nie jest już potrzebne.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-191">In some rare cases, you may decide that a custom field is no longer needed.</span></span> <span data-ttu-id="c6ae2-192">W takiej sytuacji administrator systemu może usunąć pole ze strony **Pola niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-192">When this occurs, a system administrator can choose to delete the field from the **Custom fields** page.</span></span> <span data-ttu-id="c6ae2-193">W tym celu upewnij się, że jest zaznaczone poprawne pole, kliknij przycisk **Usuń**, kliknij przycisk **Tak**, aby potwierdzić zamiar usunięcia, a na koniec kliknij przycisk **Zastosuj zmiany**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-193">To do this, ensure the correct field is selected, click **Delete**, click **Yes** to confirm the deletion, and finally click **Apply changes**.</span></span>

> [!NOTE]
> <span data-ttu-id="c6ae2-194">Tej czynności nie będzie można cofnąć, a jej wynikiem będzie trwałe usunięcie danych skojarzonych z polem z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-194">This action cannot be undone, and will result in the data associated with the field being permanently deleted from the database.</span></span>

## <a name="appendix"></a><span data-ttu-id="c6ae2-195">Dodatek</span><span class="sxs-lookup"><span data-stu-id="c6ae2-195">Appendix</span></span>

### <a name="who-can-create-custom-fields"></a><span data-ttu-id="c6ae2-196">Kto może tworzyć pola niestandardowe?</span><span class="sxs-lookup"><span data-stu-id="c6ae2-196">Who can create custom fields?</span></span>

<span data-ttu-id="c6ae2-197">Dla bezpieczeństwa systemu tylko administratorzy systemu mogą domyślnie tworzyć pola niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-197">As a safeguard to the system, only system administrators are able to create custom fields by default.</span></span> <span data-ttu-id="c6ae2-198">Jeśli jednak organizacja uzna za konieczne, administrator systemu może niektórym użytkownikom zaawansowanym nadać prawo tworzenia niestandardowych pól, używając do tego roli **Użytkownik zaawansowany personalizacji środowiska uruchomieniowego**.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-198">However, those power users whom the organization deems necessary can be given rights to create custom fields by a system administrator using the **Runtime customization power user** security role.</span></span> <span data-ttu-id="c6ae2-199">Użytkownicy bez tej roli zabezpieczeń nie będą mogli tworzyć pól niestandardowych, ale będą widzieć pola niestandardowe dodane przez innych użytkowników w systemie oraz będą mogli z nich korzystać.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-199">Users without this security role will not be able to create custom fields, but will still be able to see and interact with custom fields added by other users in the system.</span></span>

### <a name="what-tables-support-custom-fields"></a><span data-ttu-id="c6ae2-200">Które tabele obsługują pola niestandardowe?</span><span class="sxs-lookup"><span data-stu-id="c6ae2-200">What tables support custom fields?</span></span>

<span data-ttu-id="c6ae2-201">Ze względów wydajnościowych i technicznych obecnie pola niestandardowe można dodawać tylko do tabel spełniających następujące warunki.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-201">For performance and technical reasons, only tables that meet the following conditions currently allow custom fields to be added.</span></span>

- <span data-ttu-id="c6ae2-202">Tabela musi być oznakowana jako należąca do jednej z poniższych grup:</span><span class="sxs-lookup"><span data-stu-id="c6ae2-202">The table must be tagged as one of these groups:</span></span>

    - <span data-ttu-id="c6ae2-203">Grupa</span><span class="sxs-lookup"><span data-stu-id="c6ae2-203">Group</span></span>
    - <span data-ttu-id="c6ae2-204">WorksheetHeader</span><span class="sxs-lookup"><span data-stu-id="c6ae2-204">WorksheetHeader</span></span>
    - <span data-ttu-id="c6ae2-205">Główny</span><span class="sxs-lookup"><span data-stu-id="c6ae2-205">Main</span></span>
    - <span data-ttu-id="c6ae2-206">Różne</span><span class="sxs-lookup"><span data-stu-id="c6ae2-206">Miscellaneous</span></span>
    - <span data-ttu-id="c6ae2-207">Parametr</span><span class="sxs-lookup"><span data-stu-id="c6ae2-207">Parameter</span></span>
    - <span data-ttu-id="c6ae2-208">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="c6ae2-208">Reference</span></span>
    - <span data-ttu-id="c6ae2-209">TransactionHeader</span><span class="sxs-lookup"><span data-stu-id="c6ae2-209">TransactionHeader</span></span>

- <span data-ttu-id="c6ae2-210">Tabela nie może być rozszerzeniem innej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-210">The table cannot extend another table.</span></span>
- <span data-ttu-id="c6ae2-211">Tabela nie może być oznaczona jako systemowa.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-211">The table cannot be marked as a system table.</span></span>
- <span data-ttu-id="c6ae2-212">Tabela nie może być tymczasowa.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-212">The table cannot be a temporary table.</span></span>

### <a name="can-i-reference-custom-fields-from-the-developer-tools"></a><span data-ttu-id="c6ae2-213">Czy mogę odwoływać się do niestandardowych pól z poziomu narzędzi deweloperskich?</span><span class="sxs-lookup"><span data-stu-id="c6ae2-213">Can I reference custom fields from the developer tools?</span></span>  

<span data-ttu-id="c6ae2-214">Pola niestandardowe mogą być zarządzane tylko za pośrednictwem interfejsu użytkownika i nie może odwoływać się do niego kod.</span><span class="sxs-lookup"><span data-stu-id="c6ae2-214">Custom fields can only be managed through the user interface and cannot be referenced by code.</span></span> 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]