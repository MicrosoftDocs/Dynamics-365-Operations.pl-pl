---
title: Zarządzanie plikami robots.txt
description: W tym temacie opisano sposób zarządzania plikami robots.txt w aplikacji Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: afd7982179dc9845c9adc24e8c7c9951a04460a3
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477715"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="8bfb8-103">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="8bfb8-103">Manage robots.txt files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8bfb8-104">W tym temacie opisano sposób zarządzania plikami robots.txt w aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8bfb8-105">Standard wykluczenia robotów lub robots. txt to standard używany przez witryny internetowe do komunikowania się z robotami internetowymi.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-105">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="8bfb8-106">Instruuje on roboty internetowe o obszarach witryny, które nie powinny być odwiedzane.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-106">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="8bfb8-107">Roboty są często używane przez wyszukiwarki do indeksowania witryn internetowych.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-107">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="8bfb8-108">Aby wykluczyć roboty z serwera, należy utworzyć plik na serwerze.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-108">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="8bfb8-109">W tym pliku należy określić zasady dostępu dla robotów.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-109">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="8bfb8-110">Plik musi być dostępny za pośrednictwem protokołu HTTP w lokalnym adresie URL **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-110">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="8bfb8-111">Plik robots.txt pomaga wyszukiwarkom indeksować zawartość witryny.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-111">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="8bfb8-112">Aplikacja Dynamics 365 Commerce umożliwia przekazanie pliku robots.txt dla domeny.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-112">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="8bfb8-113">Dla każdej domeny w środowisku usługi Commerce można przekazać jeden plik robots.txt i skojarzyć go z tą domeną.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-113">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="8bfb8-114">Więcej informacji na temat pliku robots.txt można znaleźć [na stronach robotów internetowych](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="8bfb8-114">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="8bfb8-115">Przekazywanie pliku robots.txt</span><span class="sxs-lookup"><span data-stu-id="8bfb8-115">Upload a robots.txt file</span></span>

<span data-ttu-id="8bfb8-116">Po utworzeniu i edytowaniu pliku robots.txt zgodnie ze [standardem wykluczania robotów](https://www.robotstxt.org/orig.html) upewnij się, że plik jest dostępny na komputerze, na którym będą używane narzędzia autorskie usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-116">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="8bfb8-117">Plik musi mieć nazwę **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-117">The file must be named **robots.txt**.</span></span> <span data-ttu-id="8bfb8-118">Aby uzyskać najlepsze wyniki, musi być on w formacie, który jest odnotowany w standardzie.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-118">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="8bfb8-119">Każdy klient usługi Commerce jest odpowiedzialny za walidację i utrzymywanie zawartości pliku robots.txt.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-119">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="8bfb8-120">Aby przekazać plik robots.txt, użytkownik musi być zalogowany w usłudze Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-120">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="8bfb8-121">Aby przekazać plik robots.txt w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-121">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8bfb8-122">Zaloguj się do usługi Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-122">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="8bfb8-123">W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-123">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="8bfb8-124">W obszarze **Ustawienia dzierżawy** wybierz pozycję **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-124">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="8bfb8-125">Lista wszystkich domen skojarzonych z danym środowiskiem pojawia się w głównej części okna.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-125">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="8bfb8-126">Wybierz pozycję **Zarządzaj**, aby przekazać plik robots.txt dla domeny w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-126">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="8bfb8-127">W menu po prawej stronie wybierz przycisk **Przekaż** (strzałka wskazująca w górę) obok domeny skojarzonej z plikiem robots.txt.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-127">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="8bfb8-128">Zostanie wyświetlone okno dialogowe przeglądarki plików.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-128">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="8bfb8-129">W oknie dialogowym znajdź i wybierz plik robots.txt, który chcesz przekazać dla skojarzonej domeny, a następnie wybierz pozycję **Otwórz**, aby ukończyć przekazywanie.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-129">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="8bfb8-130">Podczas przekazywania usługa Commerce sprawdza, czy plik jest plikiem tekstowym, ale nie weryfikuje zawartości pliku.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-130">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="8bfb8-131">Pobieranie pliku robots.txt</span><span class="sxs-lookup"><span data-stu-id="8bfb8-131">Download a robots.txt file</span></span>

<span data-ttu-id="8bfb8-132">Aby pobrać plik robots.txt w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-132">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8bfb8-133">Zaloguj się do usługi Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-133">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="8bfb8-134">W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-134">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="8bfb8-135">W obszarze **Ustawienia dzierżawy** wybierz pozycję **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-135">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="8bfb8-136">Lista wszystkich domen skojarzonych z danym środowiskiem pojawia się w głównej części okna.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-136">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="8bfb8-137">Wybierz pozycję **Zarządzaj**, aby pobrać plik robots.txt dla domeny w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-137">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="8bfb8-138">W menu po prawej stronie wybierz przycisk **Pobierz** (strzałka wskazująca w dół) obok domeny skojarzonej z plikiem robots.txt.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-138">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="8bfb8-139">Zostanie wyświetlone okno dialogowe przeglądarki plików.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-139">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="8bfb8-140">W oknie dialogowym przejdź do żądanej lokalizacji na dysku lokalnym, potwierdź lub wprowadź nazwę pliku, a następnie wybierz pozycję **Zapisz**, aby ukończyć pobieranie.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-140">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="8bfb8-141">Tej procedury można używać do pobierania tylko plików robots.txt, które zostały wcześniej przekazane za pomocą narzędzi autorskich usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-141">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="8bfb8-142">Usuwanie pliku robots.txt</span><span class="sxs-lookup"><span data-stu-id="8bfb8-142">Delete a robots.txt file</span></span>

<span data-ttu-id="8bfb8-143">Aby usunąć plik robots.txt w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-143">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8bfb8-144">Zaloguj się do usługi Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-144">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="8bfb8-145">W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-145">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="8bfb8-146">W obszarze **Ustawienia dzierżawy** wybierz pozycję **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-146">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="8bfb8-147">Lista wszystkich domen skojarzonych z danym środowiskiem pojawia się w głównej części okna.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-147">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="8bfb8-148">Wybierz pozycję **Zarządzaj**, aby usunąć plik robots.txt dla domeny w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-148">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="8bfb8-149">W menu po prawej stronie wybierz przycisk **Usuń** (symbol kosza) obok domeny skojarzonej z plikiem robots.txt.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-149">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="8bfb8-150">Zostanie wyświetlone okno przeglądarki plików.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-150">A file browser window appears.</span></span>
6. <span data-ttu-id="8bfb8-151">W oknie przeglądarki plików znajdź i wybierz plik robots.txt, który chcesz usunąć dla domeny, a następnie wybierz pozycję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-151">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="8bfb8-152">Zostanie wyświetlone okno z komunikatem ostrzegawczym.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-152">A warning message box appears.</span></span>
7. <span data-ttu-id="8bfb8-153">W oknie komunikatu wybierz pozycję **Usuń**, aby potwierdzić usunięcie pliku robots.txt.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-153">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="8bfb8-154">Tej procedury można używać do usuwania tylko plików robots.txt, które zostały wcześniej przekazane za pomocą narzędzi autorskich usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="8bfb8-154">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8bfb8-155">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8bfb8-155">Additional resources</span></span>

[<span data-ttu-id="8bfb8-156">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="8bfb8-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="8bfb8-157">Wdrażanie nowej dzierżawy handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="8bfb8-157">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="8bfb8-158">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="8bfb8-158">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="8bfb8-159">Kojarzenie witryny Dynamics 365 Commerce z kanałem online</span><span class="sxs-lookup"><span data-stu-id="8bfb8-159">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="8bfb8-160">Zbiorowe przekazanie przekierowań adresów URL</span><span class="sxs-lookup"><span data-stu-id="8bfb8-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="8bfb8-161">Konfigurowanie dzierżawy B2C w module Commerce</span><span class="sxs-lookup"><span data-stu-id="8bfb8-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="8bfb8-162">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="8bfb8-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="8bfb8-163">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="8bfb8-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="8bfb8-164">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="8bfb8-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="8bfb8-165">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="8bfb8-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
