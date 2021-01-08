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
ms.openlocfilehash: ec095642f556b8d0087dd22f35097671a30047a6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462198"
---
# <a name="troubleshoot-integration-with-linkedin-and-attract"></a><span data-ttu-id="a6808-103">Rozwiązywanie problemów z aplikacjami LinkedIn i Attract</span><span class="sxs-lookup"><span data-stu-id="a6808-103">Troubleshoot integration with LinkedIn and Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a6808-104">Poniższe informacje ułatwiają rozwiązywanie problemów, które mogą wystąpić podczas próby publikacji ofert pracy w serwisie LinkedIn z aplikacji Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="a6808-104">Use the following information to help troubleshoot issues that you might have when you try to post jobs to LinkedIn from Microsoft Dynamics 365 Talent: Attract.</span></span>

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a><span data-ttu-id="a6808-105">Nie można zalogować się do serwisu LinkedIn przez Attract</span><span class="sxs-lookup"><span data-stu-id="a6808-105">You can't sign in to LinkedIn from Attract</span></span>

<span data-ttu-id="a6808-106">Jeśli występują problemy z logowaniem w serwisie LinkedIn przez program Attract, spróbuj wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a6808-106">If you're having trouble signing in to LinkedIn from Attract, try these steps:</span></span>

1. <span data-ttu-id="a6808-107">Sprawdź, czy poświadczenia LinkedIn, które zostały wprowadzone w Attract, są ważne i prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="a6808-107">Verify that the LinkedIn credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="a6808-108">Jeśli poświadczenia są ważne i prawidłowe, skontaktuj się z [Pomocą techniczną serwisu LinkedIn](https://www.linkedin.com/help/linkedin).</span><span class="sxs-lookup"><span data-stu-id="a6808-108">If the credentials are valid and correct, contact [LinkedIn support](https://www.linkedin.com/help/linkedin).</span></span>
3. <span data-ttu-id="a6808-109">Jeśli ten problem będzie nadal występował, skontaktuj się z [pomocą techniczną firmy Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="a6808-109">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a><span data-ttu-id="a6808-110">Ogłoszenia o pracę z Attract nie są wyświetlane w serwisie LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a6808-110">Job posts from Attract don't appear on LinkedIn</span></span>

<span data-ttu-id="a6808-111">Jeśli po 24 godzinach praca nie pojawiła się w serwisie LinkedIn, spróbuj wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a6808-111">If your job hasn't appeared on LinkedIn after 24 hours, try these steps:</span></span>

1. <span data-ttu-id="a6808-112">Upewnij się, że identyfikator firmy w serwisie LinkedIn jest mapowany na stronę firmy w serwisie LinkedIn i poprawnie wpisany w centrum administracyjnym Attract.</span><span class="sxs-lookup"><span data-stu-id="a6808-112">Make sure that your LinkedIn Company ID maps to your LinkedIn company page and is correctly entered in the Attract Admin center.</span></span> <span data-ttu-id="a6808-113">Aby uzyskać więcej informacji na temat zmiany ustawień serwisu LinkedIn w centrum administracyjnym, zobacz [Konfigurowanie integracji z serwisem LinkedIn dla Microsoft Dynamics 365 Talent - Attract](attract-admin-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="a6808-113">For more information about how to change LinkedIn settings in the Admin center, see [Set up integration with LinkedIn for Microsoft Dynamics 365 Talent - Attract](attract-admin-linkedin.md).</span></span> <span data-ttu-id="a6808-114">Aby uzyskać więcej informacji na temat identyfikatorów firmy LinkedIn, zobacz [Kojarzenie identyfikatora firmy w serwisie LinkedIn z tablicą ofert pracy serwisu LinkedIn — często zadawane pytania](https://www.linkedin.com/help/linkedin/answer/98972).</span><span class="sxs-lookup"><span data-stu-id="a6808-114">For more information about LinkedIn Company IDs, see [Associating your LinkedIn Company ID with the LinkedIn Job Board - Frequently Asked Questions](https://www.linkedin.com/help/linkedin/answer/98972).</span></span>
2. <span data-ttu-id="a6808-115">Sprawdź szczegóły dotyczące pracy w serwisie LinkedIn, aby upewnić się, że adres jest zakończony.</span><span class="sxs-lookup"><span data-stu-id="a6808-115">Check the job details on LinkedIn to make sure that the address is complete.</span></span> <span data-ttu-id="a6808-116">Aby opublikować ofertę pracy pomyślnie, serwis LinkedIn potrzebuje co najmniej nazwy miasta i kraju lub regionu pracy.</span><span class="sxs-lookup"><span data-stu-id="a6808-116">To post a job successfully, LinkedIn needs at least the city and country or region of the job.</span></span>
3. <span data-ttu-id="a6808-117">Upewnij się, że praca nie duplikuje innej pracy, która została opublikowana w serwisie LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="a6808-117">Make sure that the job doesn't duplicate another job that has been posted on LinkedIn.</span></span> <span data-ttu-id="a6808-118">Serwis LinkedIn nie opublikuje ofert pracy, które są duplikatami Miejsc Pracy Premium serwisu LinkedIn lub ofertami limitowanymi z innego źródła.</span><span class="sxs-lookup"><span data-stu-id="a6808-118">LinkedIn won't post jobs that are duplicates of either LinkedIn Premium Job Slots or Limited Listings from another source.</span></span> <span data-ttu-id="a6808-119">Sprawdź, czy inna osoba w firmie nie opublikowała jeszcze ręcznie pracy.</span><span class="sxs-lookup"><span data-stu-id="a6808-119">Verify that another person at your company didn't already post the job manually.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6808-120">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="a6808-120">See also</span></span>

[<span data-ttu-id="a6808-121">Konfigurowanie integracji Attract z serwisem LinkedIn — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="a6808-121">Attract integration with LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="a6808-122">Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="a6808-122">Post jobs to LinkedIn from Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-post-jobs-to-linkedin.md)

[<span data-ttu-id="a6808-123">Pozyskiwanie kandydatów za pomocą LinkedIn Recruiter w Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="a6808-123">Source candidates with LinkedIn Recruiter in Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-linkedin-recruiter.md)

[<span data-ttu-id="a6808-124">Tworzenie, zatwierdzanie i publikowanie funkcji w aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="a6808-124">Create, approve, and post jobs in Attract</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="a6808-125">Rozwiązywanie problemów z integracją usługi LinkedIn i Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="a6808-125">Troubleshooting integration with LinkedIn and Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-troubleshoot-linkedin.md)
