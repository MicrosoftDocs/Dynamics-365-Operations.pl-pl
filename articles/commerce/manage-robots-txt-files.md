---
title: Zarządzanie plikami robots.txt
description: W tym temacie opisano sposób zarządzania plikami robots. txt w aplikacji Microsoft Dynamics 365 Commerce.
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
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brishoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4b3856a7a0b4b198e71ce9af6691b1d90362f3e7
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533420"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="4d4cf-103">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="4d4cf-103">Manage robots.txt files</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4d4cf-104">W tym temacie opisano sposób zarządzania plikami robots. txt w aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4d4cf-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="4d4cf-105">Overview</span></span>

<span data-ttu-id="4d4cf-106">Standard wykluczenia robotów lub robots. txt to standard używany przez witryny internetowe do komunikowania się z robotami internetowymi.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-106">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="4d4cf-107">Instruuje on roboty internetowe o obszarach witryny, które nie powinny być odwiedzane.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-107">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="4d4cf-108">Roboty są często używane przez wyszukiwarki do indeksowania witryn internetowych.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-108">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="4d4cf-109">Aby wykluczyć roboty z serwera, należy utworzyć plik na serwerze.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-109">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="4d4cf-110">W tym pliku należy określić zasady dostępu dla robotów.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-110">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="4d4cf-111">Plik musi być dostępny za pośrednictwem protokołu HTTP w lokalnym adresie URL **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-111">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="4d4cf-112">Plik robots.txt pomaga wyszukiwarkom indeksować zawartość witryny.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-112">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="4d4cf-113">Aplikacja Dynamics 365 Commerce umożliwia przekazanie pliku robots.txt dla domeny.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-113">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="4d4cf-114">Dla każdej domeny w środowisku usługi Commerce można przekazać jeden plik robots.txt i skojarzyć go z tą domeną.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-114">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="4d4cf-115">Więcej informacji na temat pliku robots.txt można znaleźć [na stronach robotów internetowych](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="4d4cf-115">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="4d4cf-116">Przekazywanie pliku robots.txt</span><span class="sxs-lookup"><span data-stu-id="4d4cf-116">Upload a robots.txt file</span></span>

<span data-ttu-id="4d4cf-117">Po utworzeniu i edytowaniu pliku robots.txt zgodnie ze [standardem wykluczania robotów](https://www.robotstxt.org/orig.html) upewnij się, że plik jest dostępny na komputerze, na którym będą używane narzędzia autorskie usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-117">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="4d4cf-118">Plik musi mieć nazwę **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-118">The file must be named **robots.txt**.</span></span> <span data-ttu-id="4d4cf-119">Aby uzyskać najlepsze wyniki, musi być on w formacie, który jest odnotowany w standardzie.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-119">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="4d4cf-120">Każdy klient usługi Commerce jest odpowiedzialny za walidację i utrzymywanie zawartości pliku robots.txt.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-120">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="4d4cf-121">Aby przekazać plik robots.txt, użytkownik musi być zalogowany w usłudze Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-121">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="4d4cf-122">Aby przekazać plik robots.txt w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-122">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="4d4cf-123">Zaloguj się do usługi Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-123">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="4d4cf-124">W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-124">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="4d4cf-125">W obszarze **Ustawienia dzierżawy** wybierz pozycję **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-125">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="4d4cf-126">Lista wszystkich domen skojarzonych z danym środowiskiem pojawia się w głównej części okna.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-126">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="4d4cf-127">Wybierz pozycję **Zarządzaj**, aby przekazać plik robots.txt dla domeny w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-127">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="4d4cf-128">W menu po prawej stronie wybierz przycisk **Przekaż** (strzałka wskazująca w górę) obok domeny skojarzonej z plikiem robots.txt.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-128">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="4d4cf-129">Zostanie wyświetlone okno dialogowe przeglądarki plików.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-129">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="4d4cf-130">W oknie dialogowym znajdź i wybierz plik robots.txt, który chcesz przekazać dla skojarzonej domeny, a następnie wybierz pozycję **Otwórz**, aby ukończyć przekazywanie.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-130">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="4d4cf-131">Podczas przekazywania usługa Commerce sprawdza, czy plik jest plikiem tekstowym, ale nie weryfikuje zawartości pliku.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-131">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="4d4cf-132">Pobieranie pliku robots.txt</span><span class="sxs-lookup"><span data-stu-id="4d4cf-132">Download a robots.txt file</span></span>

<span data-ttu-id="4d4cf-133">Aby pobrać plik robots.txt w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-133">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="4d4cf-134">Zaloguj się do usługi Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-134">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="4d4cf-135">W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-135">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="4d4cf-136">W obszarze **Ustawienia dzierżawy** wybierz pozycję **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-136">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="4d4cf-137">Lista wszystkich domen skojarzonych z danym środowiskiem pojawia się w głównej części okna.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-137">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="4d4cf-138">Wybierz pozycję **Zarządzaj**, aby pobrać plik robots.txt dla domeny w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-138">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="4d4cf-139">W menu po prawej stronie wybierz przycisk **Pobierz** (strzałka wskazująca w dół) obok domeny skojarzonej z plikiem robots.txt.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-139">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="4d4cf-140">Zostanie wyświetlone okno dialogowe przeglądarki plików.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-140">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="4d4cf-141">W oknie dialogowym przejdź do żądanej lokalizacji na dysku lokalnym, potwierdź lub wprowadź nazwę pliku, a następnie wybierz pozycję **Zapisz**, aby ukończyć pobieranie.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-141">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="4d4cf-142">Tej procedury można używać do pobierania tylko plików robots.txt, które zostały wcześniej przekazane za pomocą narzędzi autorskich usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-142">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="4d4cf-143">Usuwanie pliku robots.txt</span><span class="sxs-lookup"><span data-stu-id="4d4cf-143">Delete a robots.txt file</span></span>

<span data-ttu-id="4d4cf-144">Aby usunąć plik robots.txt w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-144">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="4d4cf-145">Zaloguj się do usługi Commerce jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-145">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="4d4cf-146">W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-146">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="4d4cf-147">W obszarze **Ustawienia dzierżawy** wybierz pozycję **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-147">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="4d4cf-148">Lista wszystkich domen skojarzonych z danym środowiskiem pojawia się w głównej części okna.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-148">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="4d4cf-149">Wybierz pozycję **Zarządzaj**, aby usunąć plik robots.txt dla domeny w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-149">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="4d4cf-150">W menu po prawej stronie wybierz przycisk **Usuń** (symbol kosza) obok domeny skojarzonej z plikiem robots.txt.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-150">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="4d4cf-151">Zostanie wyświetlone okno przeglądarki plików.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-151">A file browser window appears.</span></span>
6. <span data-ttu-id="4d4cf-152">W oknie przeglądarki plików znajdź i wybierz plik robots.txt, który chcesz usunąć dla domeny, a następnie wybierz pozycję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-152">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="4d4cf-153">Zostanie wyświetlone okno z komunikatem ostrzegawczym.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-153">A warning message box appears.</span></span>
7. <span data-ttu-id="4d4cf-154">W oknie komunikatu wybierz pozycję **Usuń**, aby potwierdzić usunięcie pliku robots.txt.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-154">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="4d4cf-155">Tej procedury można używać do usuwania tylko plików robots.txt, które zostały wcześniej przekazane za pomocą narzędzi autorskich usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="4d4cf-155">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4d4cf-156">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4d4cf-156">Additional resources</span></span>

[<span data-ttu-id="4d4cf-157">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="4d4cf-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="4d4cf-158">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="4d4cf-158">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="4d4cf-159">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="4d4cf-159">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="4d4cf-160">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="4d4cf-160">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="4d4cf-161">Przekaż adresy URL przekierowań luzem</span><span class="sxs-lookup"><span data-stu-id="4d4cf-161">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="4d4cf-162">Konfigurowanie dzierżawy B2C w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="4d4cf-162">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="4d4cf-163">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="4d4cf-163">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="4d4cf-164">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="4d4cf-164">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="4d4cf-165">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="4d4cf-165">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="4d4cf-166">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="4d4cf-166">Enable location-based store detection</span></span>](enable-store-detection.md)
