---
title: Przekazywanie i obsługiwanie plików statycznych
description: W tym temacie opisano sposób przekazywania pliku statycznego do kreatora witryn Microsoft Dynamics 365 Commerce oraz tworzenia niestandardowego adresu URL i nazwy pliku, które mogą być używane do żądania tego pliku.
author: StuHarg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 1d709d99737ad05af1fb19d9f3ef7b87a8db80d3
ms.sourcegitcommit: da17648c296b22d517eadb2f71c7803672e5648d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2021
ms.locfileid: "5031827"
---
# <a name="upload-and-serve-static-files"></a><span data-ttu-id="8d957-103">Przekazywanie i obsługiwanie plików statycznych</span><span class="sxs-lookup"><span data-stu-id="8d957-103">Upload and serve static files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8d957-104">W tym temacie opisano sposób przekazywania pliku statycznego do kreatora witryn Microsoft Dynamics 365 Commerce oraz tworzenia niestandardowego adresu URL i nazwy pliku, które mogą być używane do żądania tego pliku.</span><span class="sxs-lookup"><span data-stu-id="8d957-104">This topic describes how to upload a static file into Microsoft Dynamics 365 Commerce site builder, and how to create a custom URL and file name that can be used to request that file.</span></span>

<span data-ttu-id="8d957-105">Niektóre łączniki innych firm wymagają, aby plik był hostowany i obsługiwany przez witrynę handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="8d957-105">Some third-party connectors require that a file be hosted and served from the e-commerce site.</span></span> <span data-ttu-id="8d957-106">Te łączniki oczekują, że plik będzie zwracany przez żądania do konkretnej ścieżki URL wywołania zwrotnego i nazwy pliku.</span><span class="sxs-lookup"><span data-stu-id="8d957-106">These connectors expect that the file will be returned by requests to a specific callback URL path and file name.</span></span> <span data-ttu-id="8d957-107">W tym temacie opisano sposób przekazywania i obsługiwania pliku statycznego, który ma definiowany przez użytkownika adres URL i nazwę pliku w witrynie handlu elektronicznego Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8d957-107">Therefore, this topic explains how to upload and serve a static file that has a user-definable URL and file name on a Dynamics 365 Commerce e-commerce site.</span></span>

## <a name="create-a-site-url-that-returns-a-static-file"></a><span data-ttu-id="8d957-108">Utwórz adres URL witryny, który zwraca plik statyczny</span><span class="sxs-lookup"><span data-stu-id="8d957-108">Create a site URL that returns a static file</span></span>

<span data-ttu-id="8d957-109">Aby utworzyć adres URL witryny, który zwraca plik statyczny w kreatorze witryny Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8d957-109">To create a site URL that returns a static file in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="8d957-110">Przejdź do biblioteki multimediów w witrynie i przekaż plik, który powinien być obsługiwany przez żądania kierowane do zdefiniowanego adresu URL.</span><span class="sxs-lookup"><span data-stu-id="8d957-110">Go to your site's Media library, and upload the file that should be served by requests to the URL that you will define.</span></span> <span data-ttu-id="8d957-111">Jeśli plik został już przekazany, można pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="8d957-111">If you've already uploaded the file, you can skip this step.</span></span>
1. <span data-ttu-id="8d957-112">Przejdź do **adresów URL** witryny.</span><span class="sxs-lookup"><span data-stu-id="8d957-112">Go to **URLs** for your site.</span></span>
1. <span data-ttu-id="8d957-113">Wybierz pozycję **Nowy \> Nowy adres URL**.</span><span class="sxs-lookup"><span data-stu-id="8d957-113">Select **New \> New URL**.</span></span>
1. <span data-ttu-id="8d957-114">W oknie dialogowym **Nowy adres URL** wybierz opcję **Zasób biblioteki multimediów**.</span><span class="sxs-lookup"><span data-stu-id="8d957-114">In the **New URL** dialog box, select **Media library asset**.</span></span>
1. <span data-ttu-id="8d957-115">W polu **Ścieżka URL** wprowadź ścieżkę URL.</span><span class="sxs-lookup"><span data-stu-id="8d957-115">In the **URL path** field, enter the URL path.</span></span> <span data-ttu-id="8d957-116">Umożliwia uwzględnienie nazwy pliku w ścieżce.</span><span class="sxs-lookup"><span data-stu-id="8d957-116">Include the file name in the path.</span></span>
1. <span data-ttu-id="8d957-117">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="8d957-117">Select **Next**.</span></span> <span data-ttu-id="8d957-118">Biblioteka multimediów jest otwarta i zawiera wszystkie zasoby multimedialne typu **dokument**, które zostały przekazane.</span><span class="sxs-lookup"><span data-stu-id="8d957-118">The Media library is opened and shows all media assets of the **document** type that have been uploaded.</span></span>
1. <span data-ttu-id="8d957-119">Wybierz plik, który ma być obsługiwany dla żądań dla adresu URL zdefiniowanego w kroku 5.</span><span class="sxs-lookup"><span data-stu-id="8d957-119">Select the file that should be served for requests to the URL that you defined in step 5.</span></span>
1. <span data-ttu-id="8d957-120">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8d957-120">Select **Save**.</span></span>

<span data-ttu-id="8d957-121">W tym momencie utworzony adres URL jest w stanie wersji roboczej.</span><span class="sxs-lookup"><span data-stu-id="8d957-121">At this point, the URL that you created is in a draft state.</span></span> <span data-ttu-id="8d957-122">Plik, do którego wskazuje adres URL, nie zostanie zwrócony do momentu opublikowania adresu URL.</span><span class="sxs-lookup"><span data-stu-id="8d957-122">The file that the URL points to won't be returned until you publish the URL.</span></span> <span data-ttu-id="8d957-123">Przed opublikowaniem adresu URL można sprawdzić, czy zwróci on poprawne dane.</span><span class="sxs-lookup"><span data-stu-id="8d957-123">Before you publish the URL, you can validate that it returns the correct data.</span></span>

## <a name="validate-and-publish-a-url"></a><span data-ttu-id="8d957-124">Weryfikowanie i publikowanie adresu URL</span><span class="sxs-lookup"><span data-stu-id="8d957-124">Validate and publish a URL</span></span>

<span data-ttu-id="8d957-125">Aby zweryfikować adres URL przed jego opublikowaniem, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8d957-125">To validate an URL before you publish it, follow these steps.</span></span>

1. <span data-ttu-id="8d957-126">Przejdź do **Adresów URL** swojego serwisu i wybierz adres URL do podglądu.</span><span class="sxs-lookup"><span data-stu-id="8d957-126">Go to **URLs** for your site, and select the URL to preview.</span></span>
2. <span data-ttu-id="8d957-127">W okienku właściwości po prawej stronie, pod przyciskiem **Edycja**, zaznacz odpowiednie łącze URL.</span><span class="sxs-lookup"><span data-stu-id="8d957-127">In the properties pane on the right, below the **Edit** button, select the correct URL link.</span></span> <span data-ttu-id="8d957-128">Zostanie otwarte nowe okno przeglądarki i pojawi się komunikat o błędzie 404.</span><span class="sxs-lookup"><span data-stu-id="8d957-128">A new browser window is opened, and you should receive a 404 error.</span></span>
3. <span data-ttu-id="8d957-129">W adresie URL należy dołączyć ciąg kwerendy w postaci **?preview=inprogress** (na przykład `https://yoursite.com/callback.html?preview=inprogress`), a następnie ponownie załadować stronę.</span><span class="sxs-lookup"><span data-stu-id="8d957-129">Append the **?preview=inprogress** query string to the URL (for example, `https://yoursite.com/callback.html?preview=inprogress`), and reload the page.</span></span> <span data-ttu-id="8d957-130">Plik przekazany do biblioteki multimediów powinien zostać zwrócony w odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="8d957-130">The file that you uploaded to the Media library should be returned in the response.</span></span>

<span data-ttu-id="8d957-131">Po sprawdzeniu adresu URL można go opublikować.</span><span class="sxs-lookup"><span data-stu-id="8d957-131">After you've validated the URL, you can publish it.</span></span>

1. <span data-ttu-id="8d957-132">Przejdź do **Adresów URL** swojego serwisu i wybierz adres URL.</span><span class="sxs-lookup"><span data-stu-id="8d957-132">Go to **URLs** for your site, and select the URL.</span></span>
2. <span data-ttu-id="8d957-133">Na pasku poleceń wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="8d957-133">Select **Publish** on the command bar.</span></span>

## <a name="update-the-file-that-a-url-points-to"></a><span data-ttu-id="8d957-134">Aktualizacja pliku, na który wskazuje adres URL</span><span class="sxs-lookup"><span data-stu-id="8d957-134">Update the file that a URL points to</span></span>

<span data-ttu-id="8d957-135">Po opublikowaniu adresu URL można go aktualizować w taki sposób, aby wskazywał inny plik.</span><span class="sxs-lookup"><span data-stu-id="8d957-135">After a URL is published, you can update it so that it points to a different file.</span></span> <span data-ttu-id="8d957-136">Można również zaktualizować adres URL, tak aby wskazywał inny typ zasobu, zgodnie z opisem w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="8d957-136">Alternatively, you can update the URL so that it points to a different the type of resource, as described in the next section.</span></span> <span data-ttu-id="8d957-137">Można na przykład wskazać adres URL na stronie wewnętrznej lub przekierowaniu.</span><span class="sxs-lookup"><span data-stu-id="8d957-137">For example, you can point the URL to an internal page or a redirect.</span></span>

<span data-ttu-id="8d957-138">Aby zaktualizować plik, na który wskazuje adres URL, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8d957-138">To update the file that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="8d957-139">Przejdź do **Adresów URL** swojego serwisu i wybierz adres URL do aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="8d957-139">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="8d957-140">W panelu właściwości po prawej stronie wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="8d957-140">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="8d957-141">W obszarze **Przypisywanie adresów URL** zaznacz pole **Krok 2**, a następnie wybierz nowy dokument z biblioteki multimediów.</span><span class="sxs-lookup"><span data-stu-id="8d957-141">Under **URL assignment**, select the **Step 2** box, and then select a new document from the Media library.</span></span>
1. <span data-ttu-id="8d957-142">Wybierz opcję **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="8d957-142">Select **Apply**.</span></span>

## <a name="update-the-asset-type-that-a-url-points-to"></a><span data-ttu-id="8d957-143">Aktualizacja typu zasobu, na który wskazuje adres URL</span><span class="sxs-lookup"><span data-stu-id="8d957-143">Update the asset type that a URL points to</span></span>

<span data-ttu-id="8d957-144">Można również zaktualizować adres URL, aby wskazywał na inny typ elementu zawartości (zasobu), taki jak wewnętrzna strona lub przekierowanie.</span><span class="sxs-lookup"><span data-stu-id="8d957-144">You can also update a URL so that it points to a different type of asset (resource), such as an internal page or a redirect.</span></span>

<span data-ttu-id="8d957-145">Aby zaktualizować typ zasobu, na który wskazuje adres URL, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8d957-145">To update the asset type that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="8d957-146">Przejdź do **Adresów URL** swojego serwisu i wybierz adres URL do aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="8d957-146">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="8d957-147">W panelu właściwości po prawej stronie wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="8d957-147">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="8d957-148">W obszarze **Przypisywanie adresu URL** w **Kroku 1** wybierz inny typ zasobu.</span><span class="sxs-lookup"><span data-stu-id="8d957-148">Under **URL assignment**, under **Step 1**, select a different asset type.</span></span>
1. <span data-ttu-id="8d957-149">Zaznacz pole **Krok 2**, a następnie wybierz nowy zasób.</span><span class="sxs-lookup"><span data-stu-id="8d957-149">Select the **Step 2** box, and then select the new asset.</span></span>
1. <span data-ttu-id="8d957-150">Wybierz opcję **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="8d957-150">Select **Apply**.</span></span>

## <a name="change-the-url-path"></a><span data-ttu-id="8d957-151">Zmiana ścieżki URL</span><span class="sxs-lookup"><span data-stu-id="8d957-151">Change the URL path</span></span>

<span data-ttu-id="8d957-152">Po utworzeniu adresu URL nie można zmienić jego ścieżki.</span><span class="sxs-lookup"><span data-stu-id="8d957-152">After a URL is created, its path can't be changed.</span></span> <span data-ttu-id="8d957-153">Jeśli trzeba zmienić ścieżkę URL, która obsługuje plik lub jakikolwiek inny typu zasobu, należy utworzyć nowy adres URL, zmapować go do istniejącego pliku lub innego zasobu, a następnie cofnąć publikowanie i usunąć stary adres URL.</span><span class="sxs-lookup"><span data-stu-id="8d957-153">If you must change the URL path that serves a file or any other type of resource, you have to create a new URL, map it to the existing file or other resource, and then unpublish and delete the old URL.</span></span>

<span data-ttu-id="8d957-154">Aby zmienić ścieżkę adresu URL, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8d957-154">To change the URL path, follow these steps.</span></span>

1. <span data-ttu-id="8d957-155">Aby utworzyć nowy adres URL i zmapować go do istniejącego pliku lub innego zasobu, postępuj zgodnie z instrukcjami w sekcji [Tworzenie adresu URL witryny, który zwraca plik statyczny](#create-a-site-url-that-returns-a-static-file), dostępnej powyżej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="8d957-155">To create a new URL and map it to the existing file or another resource, follow the instructions in the [Create a site URL that returns a static file](#create-a-site-url-that-returns-a-static-file) section earlier in this topic.</span></span>
1. <span data-ttu-id="8d957-156">Wybierz nowy adres URL i wybierz opcję **Publikuj** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="8d957-156">Select the new URL, and select **Publish** on the command bar.</span></span> <span data-ttu-id="8d957-157">Nowy adres URL zostanie opublikowany.</span><span class="sxs-lookup"><span data-stu-id="8d957-157">The new URL is published.</span></span>
1. <span data-ttu-id="8d957-158">Aby cofnąć publikowanie starego adresu URL, zaznacz go, a następnie wybierz opcję **Cofnij publikowanie** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="8d957-158">To unpublish the old URL, select it, and then select **Unpublish** on the command bar.</span></span> <span data-ttu-id="8d957-159">W razie potrzeby można teraz usunąć stary adres URL.</span><span class="sxs-lookup"><span data-stu-id="8d957-159">You can now delete the old URL if you want.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8d957-160">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8d957-160">Additional resources</span></span>

[<span data-ttu-id="8d957-161">Omówienie zarządzania cyfrowymi składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="8d957-161">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="8d957-162">Przekazanie obrazów</span><span class="sxs-lookup"><span data-stu-id="8d957-162">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="8d957-163">Przekaż pliki wideo</span><span class="sxs-lookup"><span data-stu-id="8d957-163">Upload videos</span></span>](dam-upload-video.md)

[<span data-ttu-id="8d957-164">Przekazanie plików innych niż obrazy i wideo</span><span class="sxs-lookup"><span data-stu-id="8d957-164">Upload files other than images and videos</span></span>](dam-upload-files.md)

[<span data-ttu-id="8d957-165">Przycinanie obrazów</span><span class="sxs-lookup"><span data-stu-id="8d957-165">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="8d957-166">Dostosowywanie punktów ogniskowych obrazu</span><span class="sxs-lookup"><span data-stu-id="8d957-166">Customize image focal points</span></span>](dam-custom-focal-point.md)
