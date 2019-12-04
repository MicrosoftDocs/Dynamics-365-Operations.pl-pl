---
title: Publikowanie ofert pracy w serwisie Broadbean z poziomu aplikacji Attract
description: W tym temacie wyjaśniono, jak korzystać z Dynamics 365 Talent - Attract do publikowania ofert pracy w Broadbean
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
ms.openlocfilehash: 41fa057606887069a9ea0f1f2178eeaff59f33ca
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832673"
---
# <a name="post-jobs-to-broadbean-from-attract"></a><span data-ttu-id="30df3-103">Publikowanie ofert pracy w serwisie Broadbean z poziomu aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="30df3-103">Post jobs to Broadbean from Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="30df3-104">Microsoft Dynamics 365 Talent: Attract pomaga uzyskać talent, którego potrzebujesz, umożliwiając publikację ofert pracy bezpośrednio z Attract do Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-104">Microsoft Dynamics 365 Talent: Attract helps you get the talent you need by letting you post your jobs directly from Attract to Broadbean.</span></span> <span data-ttu-id="30df3-105">Po [utworzeniu pracy](./creating-jobs-attract.md) wystarczy jedno kliknięcie, aby udostępnić ofertę o pracę wszystkim potencjalnym kandydatom w Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-105">After you [create a job](./creating-jobs-attract.md), all you have to do is click a button to put your job in front of all the potential job candidates on Broadbean.</span></span>

<span data-ttu-id="30df3-106">Publikacja ofert w Broadbean wymaga odpowiedniej licencji Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-106">Posting jobs to Broadbean requires an appropriate Broadbean license.</span></span> <span data-ttu-id="30df3-107">Broadbean zawiera różne produkty i plany.</span><span class="sxs-lookup"><span data-stu-id="30df3-107">Broadbean offers various products and plans.</span></span> <span data-ttu-id="30df3-108">Aby uzyskać więcej informacji na temat licencjonowania Broadbean i cen [skontaktuj się z Broadbean](https://www.broadbean.com/contact-us/).</span><span class="sxs-lookup"><span data-stu-id="30df3-108">For more information about Broadbean licensing and pricing, [contact Broadbean](https://www.broadbean.com/contact-us/).</span></span>

<span data-ttu-id="30df3-109">Jeśli jesteś administratorem, który potrzebuje więcej informacji na temat konfigurowania integracji Broadbean z Attract, przejdź do [Włącz integrację z aplikacją Broadbean w Microsoft Dynamics 365 Talent - Attract](./attract-admin-job-board-settings.md).</span><span class="sxs-lookup"><span data-stu-id="30df3-109">If you're an admin who needs more information about how to configure Broadbean integration with Attract, see [Enable Broadbean integration in Microsoft Dynamics 365 Talent - Attract](./attract-admin-job-board-settings.md).</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="30df3-110">Publikowanie ofert pracy w serwisie Broadbean</span><span class="sxs-lookup"><span data-stu-id="30df3-110">Post jobs to Broadbean</span></span>

<span data-ttu-id="30df3-111">Po włączeniu systemu Broadbean osoby rekrutujące i administratorzy mogą publikować oferty pracy w tym systemie.</span><span class="sxs-lookup"><span data-stu-id="30df3-111">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="30df3-112">Musisz mieć adres URL zgłaszania się na dane stanowisko.</span><span class="sxs-lookup"><span data-stu-id="30df3-112">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="30df3-113">W Attract otwórz ofertę pracy, którą chcesz opublikować na Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-113">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="30df3-114">W sekcji **Ogłoszenia** wybierz przycisk **Opublikuj teraz** odpowiadający systemowi Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-114">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="30df3-115">Wykonaj instrukcje wyświetlane w oknie Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-115">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="30df3-116">Attract przekazuje następujące informacje do Broadbean:</span><span class="sxs-lookup"><span data-stu-id="30df3-116">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="30df3-117">Identyfikator zgłoszenia</span><span class="sxs-lookup"><span data-stu-id="30df3-117">Request ID</span></span>
- <span data-ttu-id="30df3-118">Nazwa funkcji</span><span class="sxs-lookup"><span data-stu-id="30df3-118">Job title</span></span>
- <span data-ttu-id="30df3-119">Tytuł zadania</span><span class="sxs-lookup"><span data-stu-id="30df3-119">Job description</span></span>
- <span data-ttu-id="30df3-120">Lokalizacja funkcji</span><span class="sxs-lookup"><span data-stu-id="30df3-120">Job location</span></span>
- <span data-ttu-id="30df3-121">Adres URL do zgłaszania się</span><span class="sxs-lookup"><span data-stu-id="30df3-121">Apply URL</span></span>
- <span data-ttu-id="30df3-122">Osoba rekrutująca</span><span class="sxs-lookup"><span data-stu-id="30df3-122">Recruiter information</span></span>

<span data-ttu-id="30df3-123">Gdy oferta zostanie opublikowana w Broadbean, sekcja **Ogłoszenia** w Attract pokaże status w Broadbean oznaczony jako **Opublikowano**.</span><span class="sxs-lookup"><span data-stu-id="30df3-123">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="30df3-124">Broadbean wymaga wypełnienia pola **Branża**.</span><span class="sxs-lookup"><span data-stu-id="30df3-124">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="30df3-125">Obecnie pole to jest domyślnie ustawione jako **IT**.</span><span class="sxs-lookup"><span data-stu-id="30df3-125">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="30df3-126">Możesz jednak zmienić tę wartość na odpowiednią branżę w oknie publikowania oferty pracy na Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-126">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="30df3-127">Opublikowanie oferty pracy na wszystkich wybranych tablicach w Broadbean może chwilę potrwać.</span><span class="sxs-lookup"><span data-stu-id="30df3-127">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="30df3-128">Z tego względu Attract może wyświetlić aktualny stan oferty pracy z pewnym opóźnieniem.</span><span class="sxs-lookup"><span data-stu-id="30df3-128">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="30df3-129">Wyświetlanie oferty pracy opublikowanej na Broadbean</span><span class="sxs-lookup"><span data-stu-id="30df3-129">View a Broadbean job posting</span></span>

<span data-ttu-id="30df3-130">Po opublikowaniu oferty pracy na Broadbean można ją wyświetlić w aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="30df3-130">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="30df3-131">W Attract otwórz ofertę pracy, którą chcesz wyświetlić na Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-131">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="30df3-132">W karcie **Ogłoszenia** wybierz przycisk wielokropka (**...**) odpowiadający Broadbean, a następnie wybierz opcję **Wyświetl**.</span><span class="sxs-lookup"><span data-stu-id="30df3-132">On the **Postings** tab, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="30df3-133">Oferta pracy opublikowana w Broadbean zostanie wyświetlona w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="30df3-133">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="30df3-134">Aktualizowanie oferty pracy opublikowanej na Broadbean</span><span class="sxs-lookup"><span data-stu-id="30df3-134">Update a Broadbean job posting</span></span>

<span data-ttu-id="30df3-135">Ofertę pracy opublikowaną na Broadbean można zaktualizować na dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="30df3-135">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="30df3-136">W Attract otwórz ofertę pracy, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="30df3-136">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="30df3-137">W sekcji **Ogłoszenia** wybierz przycisk **Aktualizuj ogłoszenie** odpowiadający systemowi Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-137">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="30df3-138">Edytuj ofertę w oknie Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-138">Edit the posting in the Broadbean window.</span></span>

    <span data-ttu-id="30df3-139">– lub –</span><span class="sxs-lookup"><span data-stu-id="30df3-139">–or–</span></span>

1. <span data-ttu-id="30df3-140">W Attract otwórz ofertę pracy, którą chcesz wyświetlić na Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-140">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="30df3-141">W sekcji **Ogłoszenia** wybierz przycisk wielokropka (**...**) odpowiadający Broadbean, a następnie wybierz opcję **Wyświetl**.</span><span class="sxs-lookup"><span data-stu-id="30df3-141">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="30df3-142">W oknie Broadbean edytuj szczegóły oferty pracy, a następnie ponownie ją opublikuj.</span><span class="sxs-lookup"><span data-stu-id="30df3-142">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="30df3-143">Szczegóły oferty pracy w Attract nie ulegają zmianie.</span><span class="sxs-lookup"><span data-stu-id="30df3-143">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="30df3-144">Usuwanie oferty pracy opublikowanej na Broadbean</span><span class="sxs-lookup"><span data-stu-id="30df3-144">Remove a Broadbean job posting</span></span>

<span data-ttu-id="30df3-145">W razie potrzeby można usunąć ofertę pracy z Broadbean.</span><span class="sxs-lookup"><span data-stu-id="30df3-145">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="30df3-146">W Attract otwórz ofertę pracy, którą chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="30df3-146">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="30df3-147">W sekcji **Ogłoszenia** wybierz przycisk wielokropka (**...**) odpowiadający Broadbean, a następnie wybierz opcję **Usuń ogłoszenie**.</span><span class="sxs-lookup"><span data-stu-id="30df3-147">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="30df3-148">Po usunięciu ogłoszenia w Broadbean, element systemu Broadbean w Attract będzie miał przycisk **Opublikuj teraz**.</span><span class="sxs-lookup"><span data-stu-id="30df3-148">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="30df3-149">Obecność tego przycisku wskazuje, że oferta została usunięta i można ją ponownie opublikować.</span><span class="sxs-lookup"><span data-stu-id="30df3-149">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-job-posting-to-broadbean"></a><span data-ttu-id="30df3-150">Rozwiązywanie problemów z umieszczaniem ofert w Broadbean</span><span class="sxs-lookup"><span data-stu-id="30df3-150">Troubleshoot job posting to Broadbean</span></span>

<span data-ttu-id="30df3-151">Jeśli masz problemy z opublikowaniem oferty pracy na Broadbean, wypróbuj poniższe rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="30df3-151">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="30df3-152">Sprawdź, czy poświadczenia Broadbean, które zostały wprowadzone w Attract, są ważne i prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="30df3-152">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="30df3-153">Jeśli poświadczenia są ważne i prawidłowe, skontaktuj się z [Obsługą Broadbean](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="30df3-153">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="30df3-154">Jeśli ten problem będzie nadal występował, skontaktuj się z [pomocą techniczną firmy Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="30df3-154">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="30df3-155">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="30df3-155">See also</span></span>

[<span data-ttu-id="30df3-156">Tworzenie, zatwierdzanie i publikowanie funkcji w aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="30df3-156">Create, approve, and post jobs in Attract</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="30df3-157">Włącz integrację z aplikacją Broadbean w Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="30df3-157">Enable Broadbean integration in Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-admin-job-board-settings.md)
