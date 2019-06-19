---
title: Publikowanie ofert pracy z Attract na zewnętrznych stronach
description: W tym temacie wyjaśniono, jak korzystać z Dynamics 365 for Talent - Attract do publikowania ofert pracy w zewnętrznych serwisach rekrutacyjnych
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 9c27d1810a89ed7d7a7745e41c5f118dbdfe5dda
ms.sourcegitcommit: cadce85ca3004d53caf6bc49147a524c1bfd421f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/16/2019
ms.locfileid: "1590489"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a><span data-ttu-id="b198a-103">Publikowanie ofert pracy z Attract na zewnętrznych stronach</span><span class="sxs-lookup"><span data-stu-id="b198a-103">Post jobs to external career sites from Attract</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b198a-104">Chcesz dotrzeć z informacją o wakacie do jak największej liczby kandydatów posiadających odpowiednie kwalifikacje.</span><span class="sxs-lookup"><span data-stu-id="b198a-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="b198a-105">Serwisy rekrutacyjne, takie jak Broadbean mogą pomóc w osiągnięciu tych celów.</span><span class="sxs-lookup"><span data-stu-id="b198a-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="b198a-106">Microsoft Dynamics 365 Talent: Attract umożliwia teraz publikowanie ofert pracy na Broadbean, a Microsoft stale udostępnia nowe możliwości w tym zakresie.</span><span class="sxs-lookup"><span data-stu-id="b198a-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="b198a-107">Publikowanie ofert pracy na Broadbean</span><span class="sxs-lookup"><span data-stu-id="b198a-107">Post jobs to Broadbean</span></span>

<span data-ttu-id="b198a-108">Przed opublikowaniem ofert pracy w Broadbean należy skonfigurować integrację Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-108">Before you can post jobs to Broadbean, you must configure the Broadbean integration.</span></span>

> [!NOTE]
> - <span data-ttu-id="b198a-109">Aby opublikować oferty pracy na zewnętrznych stronach, musisz mieć [dodatek kompleksowej obsługi rekrutacji](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="b198a-109">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="b198a-110">Aby publikować oferty pracy w Broadbean za pośrednictwem Attract, należy posiadać subskrypcję Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-110">To post jobs to Broadbean through Attract, you must have a Broadbean subscription.</span></span>
> - <span data-ttu-id="b198a-111">Ta funkcja jest obecnie w wersjach zapoznawczych.</span><span class="sxs-lookup"><span data-stu-id="b198a-111">This feature is currently in preview.</span></span> <span data-ttu-id="b198a-112">Jeśli chcesz ją wypróbować, musisz najpierw [ją włączyć w ustawieniach administratora Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="b198a-112">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

### <a name="configure-broadbean-integration"></a><span data-ttu-id="b198a-113">Konfigurowanie integracji Broadbean</span><span class="sxs-lookup"><span data-stu-id="b198a-113">Configure Broadbean integration</span></span>

1. <span data-ttu-id="b198a-114">Zaloguj się w Attract jako administrator.</span><span class="sxs-lookup"><span data-stu-id="b198a-114">Sign in to Attract as an admin.</span></span>
2. <span data-ttu-id="b198a-115">Wybierz przycisk **ustawienia** (symbol koła zębatego) w prawym górnym rogu strony, a następnie wybierz opcję **Centrum administracyjnego**.</span><span class="sxs-lookup"><span data-stu-id="b198a-115">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>
3. <span data-ttu-id="b198a-116">Na karcie **Ustawienia tablicy funkcji** w sekcji **Włącz integrację z aplikacją Broadbean** włącz integrację.</span><span class="sxs-lookup"><span data-stu-id="b198a-116">On the **Job board settings** tab, in the **Enable Broadbean integration** section, turn on the integration.</span></span>
4. <span data-ttu-id="b198a-117">Skontaktuj się z Broadbean i wprowadź informacje w **Nazwa użytkownika, identyfikator klienta, token szyfrowania**.</span><span class="sxs-lookup"><span data-stu-id="b198a-117">Contact Broadbean, and enter your information in **Username, Client ID, Encryption Token**.</span></span>

> [!WARNING]
> <span data-ttu-id="b198a-118">Twoje poświadczenia Broadbean są poufne.</span><span class="sxs-lookup"><span data-stu-id="b198a-118">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="b198a-119">W związku z tym przechowuj je z zachowaniem odpowiednich środków ostrożności.</span><span class="sxs-lookup"><span data-stu-id="b198a-119">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="b198a-120">Każda osoba z rolą administratora w Attract może wyświetlać te poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="b198a-120">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="b198a-121">Microsoft i Attract nie uczestniczą w tworzeniu ani przechowywaniu tych wartości.</span><span class="sxs-lookup"><span data-stu-id="b198a-121">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="b198a-122">Użytkownik ponosi odpowiedzialność za zachowanie aktualności danych w systemie Attract oraz współpracę z Broadbean w celu rozwiązywania wszelkich problemów związanych z jego poświadczeniami.</span><span class="sxs-lookup"><span data-stu-id="b198a-122">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>

### <a name="post-a-job-to-broadbean"></a><span data-ttu-id="b198a-123">Publikowanie ofert pracy na Broadbean</span><span class="sxs-lookup"><span data-stu-id="b198a-123">Post a job to Broadbean</span></span>

<span data-ttu-id="b198a-124">Po włączeniu systemu Broadbean osoby rekrutujące i administratorzy mogą publikować oferty pracy w tym systemie.</span><span class="sxs-lookup"><span data-stu-id="b198a-124">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="b198a-125">Musisz mieć adres URL zgłaszania się na dane stanowisko.</span><span class="sxs-lookup"><span data-stu-id="b198a-125">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="b198a-126">W Attract otwórz ofertę pracy, którą chcesz opublikować na Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-126">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="b198a-127">W sekcji **Ogłoszenia** wybierz przycisk **Opublikuj teraz** odpowiadający systemowi Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-127">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="b198a-128">Wykonaj instrukcje wyświetlane w oknie Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-128">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="b198a-129">Attract przekazuje następujące informacje do Broadbean:</span><span class="sxs-lookup"><span data-stu-id="b198a-129">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="b198a-130">Identyfikator zgłoszenia</span><span class="sxs-lookup"><span data-stu-id="b198a-130">Request ID</span></span>
- <span data-ttu-id="b198a-131">Nazwa funkcji</span><span class="sxs-lookup"><span data-stu-id="b198a-131">Job title</span></span>
- <span data-ttu-id="b198a-132">Tytuł zadania</span><span class="sxs-lookup"><span data-stu-id="b198a-132">Job description</span></span>
- <span data-ttu-id="b198a-133">Lokalizacja funkcji</span><span class="sxs-lookup"><span data-stu-id="b198a-133">Job location</span></span>
- <span data-ttu-id="b198a-134">Adres URL do zgłaszania się</span><span class="sxs-lookup"><span data-stu-id="b198a-134">Apply URL</span></span>
- <span data-ttu-id="b198a-135">Osoba rekrutująca</span><span class="sxs-lookup"><span data-stu-id="b198a-135">Recruiter information</span></span>

<span data-ttu-id="b198a-136">Gdy oferta zostanie opublikowana w Broadbean, sekcja **Ogłoszenia** w Attract pokaże status w Broadbean oznaczony jako **Opublikowano**.</span><span class="sxs-lookup"><span data-stu-id="b198a-136">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="b198a-137">Broadbean wymaga wypełnienia pola **Branża**.</span><span class="sxs-lookup"><span data-stu-id="b198a-137">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="b198a-138">Obecnie pole to jest domyślnie ustawione jako **IT**.</span><span class="sxs-lookup"><span data-stu-id="b198a-138">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="b198a-139">Możesz jednak zmienić tę wartość na odpowiednią branżę w oknie publikowania oferty pracy na Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-139">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="b198a-140">Opublikowanie oferty pracy na wszystkich wybranych tablicach w Broadbean może chwilę potrwać.</span><span class="sxs-lookup"><span data-stu-id="b198a-140">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="b198a-141">Z tego względu Attract może wyświetlić aktualny stan oferty pracy z pewnym opóźnieniem.</span><span class="sxs-lookup"><span data-stu-id="b198a-141">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="b198a-142">Wyświetlanie oferty pracy opublikowanej na Broadbean</span><span class="sxs-lookup"><span data-stu-id="b198a-142">View a Broadbean job posting</span></span>

<span data-ttu-id="b198a-143">Po opublikowaniu oferty pracy na Broadbean można ją wyświetlić w aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="b198a-143">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="b198a-144">W Attract otwórz ofertę pracy, którą chcesz wyświetlić na Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-144">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="b198a-145">W sekcji **Ogłoszenia** wybierz przycisk wielokropka (**...**) odpowiadający Broadbean, a następnie wybierz opcję **Wyświetl**.</span><span class="sxs-lookup"><span data-stu-id="b198a-145">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="b198a-146">Oferta pracy opublikowana w Broadbean zostanie wyświetlona w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="b198a-146">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="b198a-147">Aktualizowanie oferty pracy opublikowanej na Broadbean</span><span class="sxs-lookup"><span data-stu-id="b198a-147">Update a Broadbean job posting</span></span>

<span data-ttu-id="b198a-148">Ofertę pracy opublikowaną na Broadbean można zaktualizować na dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="b198a-148">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="b198a-149">W Attract otwórz ofertę pracy, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="b198a-149">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="b198a-150">W sekcji **Ogłoszenia** wybierz przycisk **Aktualizuj ogłoszenie** odpowiadający systemowi Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-150">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="b198a-151">Edytuj ofertę w oknie Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-151">Edit the posting in the Broadbean window.</span></span>

<span data-ttu-id="b198a-152">– lub –</span><span class="sxs-lookup"><span data-stu-id="b198a-152">–or–</span></span>

1. <span data-ttu-id="b198a-153">W Attract otwórz ofertę pracy, którą chcesz wyświetlić na Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-153">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="b198a-154">W sekcji **Ogłoszenia** wybierz przycisk wielokropka (**...**) odpowiadający Broadbean, a następnie wybierz opcję **Wyświetl**.</span><span class="sxs-lookup"><span data-stu-id="b198a-154">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="b198a-155">W oknie Broadbean edytuj szczegóły oferty pracy, a następnie ponownie ją opublikuj.</span><span class="sxs-lookup"><span data-stu-id="b198a-155">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="b198a-156">Szczegóły oferty pracy w Attract nie ulegają zmianie.</span><span class="sxs-lookup"><span data-stu-id="b198a-156">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="b198a-157">Usuwanie oferty pracy opublikowanej na Broadbean</span><span class="sxs-lookup"><span data-stu-id="b198a-157">Remove a Broadbean job posting</span></span>

<span data-ttu-id="b198a-158">W razie potrzeby można usunąć ofertę pracy z Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b198a-158">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="b198a-159">W Attract otwórz ofertę pracy, którą chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="b198a-159">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="b198a-160">W sekcji **Ogłoszenia** wybierz przycisk wielokropka (**...**) odpowiadający Broadbean, a następnie wybierz opcję **Usuń ogłoszenie**.</span><span class="sxs-lookup"><span data-stu-id="b198a-160">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="b198a-161">Po usunięciu ogłoszenia w Broadbean, element systemu Broadbean w Attract będzie miał przycisk **Opublikuj teraz**.</span><span class="sxs-lookup"><span data-stu-id="b198a-161">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="b198a-162">Obecność tego przycisku wskazuje, że oferta została usunięta i można ją ponownie opublikować.</span><span class="sxs-lookup"><span data-stu-id="b198a-162">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-the-broadbean-integration"></a><span data-ttu-id="b198a-163">Rozwiązywanie problemów z integracją Broadbean</span><span class="sxs-lookup"><span data-stu-id="b198a-163">Troubleshoot the Broadbean integration</span></span>

<span data-ttu-id="b198a-164">Jeśli masz problemy z opublikowaniem oferty pracy na Broadbean, wypróbuj poniższe rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="b198a-164">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="b198a-165">Sprawdź, czy poświadczenia Broadbean, które zostały wprowadzone w Attract, są ważne i prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="b198a-165">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="b198a-166">Jeśli poświadczenia są ważne i prawidłowe, skontaktuj się z [Obsługą Broadbean](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="b198a-166">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="b198a-167">Jeśli ten problem będzie nadal występował, skontaktuj się z [pomocą techniczną firmy Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="b198a-167">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>
