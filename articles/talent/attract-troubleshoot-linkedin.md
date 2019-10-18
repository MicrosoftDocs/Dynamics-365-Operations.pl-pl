---
title: Rozwiązywanie problemów z integracją usługi LinkedIn i Microsoft Dynamics 365 Talent - Attract
description: W tym temacie wyjaśniono, jak rozwiązywać problemy podczas próby publikacji ofert pracy w serwisie LinkedIn z aplikacji Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
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
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 79f138ad9aeb203bce19cc93237fca96bffd015f
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008227"
---
# <a name="troubleshoot-integration-with-linkedin"></a><span data-ttu-id="cc2e0-103">Rozwiązywanie problemów integracji z serwisem LinkedIn</span><span class="sxs-lookup"><span data-stu-id="cc2e0-103">Troubleshoot integration with LinkedIn</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cc2e0-104">Poniższe informacje ułatwiają rozwiązywanie problemów, które mogą wystąpić podczas próby publikacji ofert pracy w serwisie LinkedIn z aplikacji Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="cc2e0-104">Use the following information to help troubleshoot issues that you might have when you try to post jobs to LinkedIn from Microsoft Dynamics 365 Talent: Attract.</span></span>

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a><span data-ttu-id="cc2e0-105">Nie można zalogować się do serwisu LinkedIn przez Attract</span><span class="sxs-lookup"><span data-stu-id="cc2e0-105">You can't sign in to LinkedIn from Attract</span></span>

<span data-ttu-id="cc2e0-106">Jeśli występują problemy z logowaniem w serwisie LinkedIn przez program Attract, spróbuj wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="cc2e0-106">If you're having trouble signing in to LinkedIn from Attract, try these steps:</span></span>

1. <span data-ttu-id="cc2e0-107">Sprawdź, czy poświadczenia LinkedIn, które zostały wprowadzone w Attract, są ważne i prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="cc2e0-107">Verify that the LinkedIn credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="cc2e0-108">Jeśli poświadczenia są ważne i prawidłowe, skontaktuj się z [Pomocą techniczną serwisu LinkedIn](https://www.linkedin.com/help/linkedin).</span><span class="sxs-lookup"><span data-stu-id="cc2e0-108">If the credentials are valid and correct, contact [LinkedIn support](https://www.linkedin.com/help/linkedin).</span></span>
3. <span data-ttu-id="cc2e0-109">Jeśli ten problem będzie nadal występował, skontaktuj się z [pomocą techniczną firmy Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="cc2e0-109">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a><span data-ttu-id="cc2e0-110">Ogłoszenia o pracę z Attract nie są wyświetlane w serwisie LinkedIn</span><span class="sxs-lookup"><span data-stu-id="cc2e0-110">Job posts from Attract don't appear on LinkedIn</span></span>

<span data-ttu-id="cc2e0-111">Jeśli po 24 godzinach praca nie pojawiła się w serwisie LinkedIn, spróbuj wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="cc2e0-111">If your job hasn't appeared on LinkedIn after 24 hours, try these steps:</span></span>

1. <span data-ttu-id="cc2e0-112">Upewnij się, że identyfikator firmy w serwisie LinkedIn jest mapowany na stronę firmy w serwisie LinkedIn i poprawnie wpisany w centrum administracyjnym Attract.</span><span class="sxs-lookup"><span data-stu-id="cc2e0-112">Make sure that your LinkedIn Company ID maps to your LinkedIn company page and is correctly entered in the Attract Admin center.</span></span> <span data-ttu-id="cc2e0-113">Aby uzyskać więcej informacji na temat zmiany ustawień serwisu LinkedIn w centrum administracyjnym, zobacz [Konfigurowanie integracji z serwisem LinkedIn](attract-admin-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="cc2e0-113">For more information about how to change LinkedIn settings in the Admin center, see [Set up integration with LinkedIn](attract-admin-linkedin.md).</span></span> <span data-ttu-id="cc2e0-114">Aby uzyskać więcej informacji na temat identyfikatorów firmy LinkedIn, zobacz [Kojarzenie identyfikatora firmy w serwisie LinkedIn z tablicą ofert pracy serwisu LinkedIn — często zadawane pytania](https://www.linkedin.com/help/linkedin/answer/98972).</span><span class="sxs-lookup"><span data-stu-id="cc2e0-114">For more information about LinkedIn Company IDs, see [Associating your LinkedIn Company ID with the LinkedIn Job Board - Frequently Asked Questions](https://www.linkedin.com/help/linkedin/answer/98972).</span></span>
2. <span data-ttu-id="cc2e0-115">Sprawdź szczegóły dotyczące pracy w serwisie LinkedIn, aby upewnić się, że adres jest zakończony.</span><span class="sxs-lookup"><span data-stu-id="cc2e0-115">Check the job details on LinkedIn to make sure that the address is complete.</span></span> <span data-ttu-id="cc2e0-116">Aby opublikować ofertę pracy pomyślnie, serwis LinkedIn potrzebuje co najmniej nazwy miasta i kraju lub regionu pracy.</span><span class="sxs-lookup"><span data-stu-id="cc2e0-116">To post a job successfully, LinkedIn needs at least the city and country or region of the job.</span></span>
3. <span data-ttu-id="cc2e0-117">Upewnij się, że praca nie duplikuje innej pracy, która została opublikowana w serwisie LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="cc2e0-117">Make sure that the job doesn't duplicate another job that has been posted on LinkedIn.</span></span> <span data-ttu-id="cc2e0-118">Serwis LinkedIn nie opublikuje ofert pracy, które są duplikatami Miejsc Pracy Premium serwisu LinkedIn lub ofertami limitowanymi z innego źródła.</span><span class="sxs-lookup"><span data-stu-id="cc2e0-118">LinkedIn won't post jobs that are duplicates of either LinkedIn Premium Job Slots or Limited Listings from another source.</span></span> <span data-ttu-id="cc2e0-119">Sprawdź, czy inna osoba w firmie nie opublikowała jeszcze ręcznie pracy.</span><span class="sxs-lookup"><span data-stu-id="cc2e0-119">Verify that another person at your company didn't already post the job manually.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc2e0-120">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="cc2e0-120">See also</span></span>

[<span data-ttu-id="cc2e0-121">Często zadawane pytania dotyczące serwisu LinkedIn</span><span class="sxs-lookup"><span data-stu-id="cc2e0-121">LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="cc2e0-122">Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="cc2e0-122">Post jobs to LinkedIn from Attract</span></span>](./attract-post-jobs-to-linkedin.md)

[<span data-ttu-id="cc2e0-123">Pozyskiwanie kandydatów za pomocą usługi LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="cc2e0-123">Source candidates with LinkedIn Recruiter</span></span>](./attract-linkedin-recruiter.md)

[<span data-ttu-id="cc2e0-124">Tworzenie pracy</span><span class="sxs-lookup"><span data-stu-id="cc2e0-124">Create jobs</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="cc2e0-125">Rozwiązywanie problemów integracji z serwisem LinkedIn</span><span class="sxs-lookup"><span data-stu-id="cc2e0-125">Troubleshoot integration with LinkedIn</span></span>](./attract-troubleshoot-linkedin.md)
