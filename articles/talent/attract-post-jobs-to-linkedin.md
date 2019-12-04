---
title: Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Attract
description: W tym temacie wyjaśniono, jak korzystać z Dynamics 365 Talent - Attract do publikowania ofert pracy w serwisie LinkedIn.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
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
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 782a2e5de6edf0e85c4d32a0910f5f3c01981a01
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2019
ms.locfileid: "2833012"
---
# <a name="post-jobs-to-linkedin-from-attract"></a><span data-ttu-id="d76e2-103">Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="d76e2-103">Post jobs to LinkedIn from Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d76e2-104">LinkedIn to największa sieć profesjonalistów w trybie online, która daje dostęp do talentów na świecie.</span><span class="sxs-lookup"><span data-stu-id="d76e2-104">LinkedIn is the largest online professional network, giving you access to the world's top talent.</span></span> <span data-ttu-id="d76e2-105">Microsoft Dynamics 365 Talent: Attract pomaga uzyskać talent, którego potrzebujesz, umożliwiając publikację ofert pracy bezpośrednio z Attract do LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="d76e2-105">Microsoft Dynamics 365 Talent: Attract helps you get the talent that you need by letting you post your jobs directly from Attract to LinkedIn.</span></span>

<span data-ttu-id="d76e2-106">Attract pozwala na wysyłanie nieograniczonych list do serwisu LinkedIn bez dodatkowych kosztów.</span><span class="sxs-lookup"><span data-stu-id="d76e2-106">Attract lets you post Limited Listings to LinkedIn at no extra cost.</span></span> <span data-ttu-id="d76e2-107">Te listy są dostępne tylko dla partnerów programowych serwisu LinkedIn takich jak Attract.</span><span class="sxs-lookup"><span data-stu-id="d76e2-107">These listings are available only through LinkedIn software partners such as Attract.</span></span> <span data-ttu-id="d76e2-108">Nie są one widoczne w panelu **Kariery** na stronie firmy w LinkedIn, ponieważ w tym miejscu pojawiają się tylko listy opłacane.</span><span class="sxs-lookup"><span data-stu-id="d76e2-108">They don't appear in the **Careers** panel on your company's LinkedIn page, because only paid listings appear there.</span></span> <span data-ttu-id="d76e2-109">Są jednak wyświetlane, gdy potencjalni kandydaci widzą wszystkie dostępne prace.</span><span class="sxs-lookup"><span data-stu-id="d76e2-109">However, they are shown when potential candidates view all available jobs.</span></span> <span data-ttu-id="d76e2-110">Listy z ograniczeniami są także wyświetlane w wyszukiwaniach prac LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="d76e2-110">Limited Listings are also shown in LinkedIn job searches.</span></span>

<span data-ttu-id="d76e2-111">Po [utworzeniu pracy](./creating-jobs-attract.md) w Attract wystarczy jedno kliknięcie, aby udostępnić ofertę o pracę tysiącom potencjalnym kandydatom w LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="d76e2-111">After you [create a job](./creating-jobs-attract.md) in Attract, you just have to select a button to put your job in front of thousands of potential candidates on LinkedIn.</span></span>

<span data-ttu-id="d76e2-112">W poniższej tabeli przedstawiono akcje, które można wykonać w serwisie LinkedIn, w zależności od roli użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d76e2-112">The following table shows the actions that you can perform on LinkedIn, depending on your user role.</span></span>

| <span data-ttu-id="d76e2-113">Rola</span><span class="sxs-lookup"><span data-stu-id="d76e2-113">Role</span></span> | <span data-ttu-id="d76e2-114">Akcje, które można wykonać</span><span class="sxs-lookup"><span data-stu-id="d76e2-114">Actions that you can take</span></span> |
|---|---|
| <span data-ttu-id="d76e2-115">Administrator</span><span class="sxs-lookup"><span data-stu-id="d76e2-115">Admin</span></span> | <span data-ttu-id="d76e2-116">Publikacja, ponowna publikacja i cofanie publikacji</span><span class="sxs-lookup"><span data-stu-id="d76e2-116">Post, repost, and unpost</span></span> |
| <span data-ttu-id="d76e2-117">Zatrudnianie menedżera</span><span class="sxs-lookup"><span data-stu-id="d76e2-117">Hiring manager</span></span> | <span data-ttu-id="d76e2-118">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d76e2-118">Read only</span></span> |
| <span data-ttu-id="d76e2-119">Osoba rekrutująca</span><span class="sxs-lookup"><span data-stu-id="d76e2-119">Recruiter</span></span> | <span data-ttu-id="d76e2-120">Publikacja, ponowna publikacja i cofanie publikacji</span><span class="sxs-lookup"><span data-stu-id="d76e2-120">Post, repost, and unpost</span></span> |
| <span data-ttu-id="d76e2-121">Osoby przeprowadzającej rozmowę kwalifikacyjną</span><span class="sxs-lookup"><span data-stu-id="d76e2-121">Interviewer</span></span> | <span data-ttu-id="d76e2-122">Brak dostępu</span><span class="sxs-lookup"><span data-stu-id="d76e2-122">No access</span></span> |
| <span data-ttu-id="d76e2-123">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d76e2-123">Read-only</span></span> | <span data-ttu-id="d76e2-124">Tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d76e2-124">Read only</span></span> |

<span data-ttu-id="d76e2-125">Aby uzyskać więcej informacji o rolach użytkowników w Attract, zobacz [Zarządzanie zabezpieczeniami i rolami w aplikacji Attract](./security-attract.md).</span><span class="sxs-lookup"><span data-stu-id="d76e2-125">For more information about user roles in Attract, see [Security and role management in Attract](./security-attract.md).</span></span>

<span data-ttu-id="d76e2-126">Jeśli jesteś administratorem i potrzebujesz więcej informacji na temat konfigurowania integracji serwisu LinkedIn z Attract, skorzystaj z opcji [Konfigurowanie integracji z serwisem LinkedIn dla Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="d76e2-126">If you're an admin and need more information about how to configure LinkedIn integration with Attract, see [Set up integration with LinkedIn for Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md).</span></span>

<span data-ttu-id="d76e2-127">Oferty pracy, które są publikowane na LinkedIn są wyświetlane od razu na oficjalnej stronie LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="d76e2-127">Jobs that are posted to LinkedIn appear on the live LinkedIn site.</span></span> <span data-ttu-id="d76e2-128">Nie ma środowiska testowego dla publikowania ofert pracy na LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="d76e2-128">LinkedIn doesn't have a test environment for posting jobs.</span></span> <span data-ttu-id="d76e2-129">Dlatego należy się upewnić, że nie są one przypadkowo publikowane żadne oferty testowe.</span><span class="sxs-lookup"><span data-stu-id="d76e2-129">Therefore, make sure that you don't accidentally post any test jobs.</span></span>

## <a name="post-jobs-to-linkedin"></a><span data-ttu-id="d76e2-130">Publikowanie ofert pracy w serwisie LinkedIn</span><span class="sxs-lookup"><span data-stu-id="d76e2-130">Post jobs to LinkedIn</span></span>

1. <span data-ttu-id="d76e2-131">W Attract otwórz ofertę pracy, którą chcesz opublikować na LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="d76e2-131">In Attract, open the job that you want to post to LinkedIn.</span></span>
2. <span data-ttu-id="d76e2-132">Na karcie **Ogłoszenia** wybierz przycisk **Opublikuj teraz** odpowiadający systemowi LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="d76e2-132">On the **Postings** tab, select the **Post Now** button that corresponds to LinkedIn.</span></span>

    <span data-ttu-id="d76e2-133">[![Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Attract](./media/attract-post-job-to-linkedin.png)](./media/attract-post-job-to-linkedin.png)</span><span class="sxs-lookup"><span data-stu-id="d76e2-133">[![Attract post job to LinkedIn](./media/attract-post-job-to-linkedin.png)](./media/attract-post-job-to-linkedin.png)</span></span>

3. <span data-ttu-id="d76e2-134">W oknie dialogowym **Utwórz adres sieci Web „Zastosuj teraz”** wybierz opcję w obszarze **Metoda zgłaszania się udostępniana kandydatom:**.</span><span class="sxs-lookup"><span data-stu-id="d76e2-134">In the **Create an "Apply now" web address** dialog box, select an option under **Candidates can apply using a**.</span></span> <span data-ttu-id="d76e2-135">Zaleca się, aby w wybrać **Link w aplikacji Attract**.</span><span class="sxs-lookup"><span data-stu-id="d76e2-135">We recommend that you select **Link in Attract**.</span></span>
4. <span data-ttu-id="d76e2-136">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="d76e2-136">Select **Done**.</span></span>
5. <span data-ttu-id="d76e2-137">W polu komunikatu **Prześlij do opublikowania** wybierz opcję **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="d76e2-137">In the **Submit for posting** message box, select **Confirm**.</span></span>

<span data-ttu-id="d76e2-138">Gdy oferta zostanie opublikowana w LinkedIn, sekcja **Ogłoszenia** w Attract pokaże status w LinkedIn oznaczony jako **Opublikowano**.</span><span class="sxs-lookup"><span data-stu-id="d76e2-138">After LinkedIn successfully completes the posting, the **Postings** section of the job in Attract shows the LinkedIn status as **Posted**.</span></span> <span data-ttu-id="d76e2-139">Aby oferta pracy była wyświetlana w LinkedIn, może potrwać do 48 godzin.</span><span class="sxs-lookup"><span data-stu-id="d76e2-139">It can take up to 48 hours for your job to appear in LinkedIn.</span></span>

<span data-ttu-id="d76e2-140">Gdy zainteresowani kandydaci wybiorą **Zobacz** obok listy, zobaczysz pełne szczegóły dotyczące pracy wraz z informacjami o sposobach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d76e2-140">When interested candidates select **View** next to your listing, they will see the full job details, together with your information about how to apply.</span></span>

<span data-ttu-id="d76e2-141">Wszystkie ogłoszenia o pracę wykonywane za pośrednictwem Attract to listy z ograniczeniami.</span><span class="sxs-lookup"><span data-stu-id="d76e2-141">All job postings that are done through Attract are Limited Listings.</span></span> <span data-ttu-id="d76e2-142">Aby uzyskać więcej informacji o ograniczonych listach w serwisie LinkedIn, zapoznaj się z [Miejsca na zadania z ograniczoną oferta a miejsca na zadania premium w kontekście zawijania zadań](https://www.linkedin.com/help/recruiter/answer/79049).</span><span class="sxs-lookup"><span data-stu-id="d76e2-142">For more information about Limited Listings on LinkedIn, see [Limited Listings vs Premium Job Slots for Job Wrapping](https://www.linkedin.com/help/recruiter/answer/79049).</span></span>

<span data-ttu-id="d76e2-143">Jeśli występują problemy z publikacją ofert pracy w serwisie LinkedIn, przejrzyj informacje [Rozwiązywanie problemów z integracją usługi LinkedIn i Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="d76e2-143">If you're having trouble posting jobs to LinkedIn, see [Troubleshooting integration with LinkedIn and Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d76e2-144">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="d76e2-144">See also</span></span>

[<span data-ttu-id="d76e2-145">Konfigurowanie integracji Attract z serwisem LinkedIn — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="d76e2-145">Attract integration with LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="d76e2-146">Konfigurowanie integracji z serwisem LinkedIn dla aplikacji Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="d76e2-146">Set up integration with LinkedIn for Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-admin-linkedin.md)

[<span data-ttu-id="d76e2-147">Tworzenie, zatwierdzanie i publikowanie funkcji w aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="d76e2-147">Create, approve, and post jobs in Attract</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="d76e2-148">Pozyskiwanie kandydatów za pomocą usługi LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="d76e2-148">Source candidates with LinkedIn Recruiter</span></span>](./attract-linkedin-recruiter.md)

[<span data-ttu-id="d76e2-149">Rozwiązywanie problemów integracji z serwisem LinkedIn</span><span class="sxs-lookup"><span data-stu-id="d76e2-149">Troubleshoot integration with LinkedIn</span></span>](./attract-troubleshoot-linkedin.md)
