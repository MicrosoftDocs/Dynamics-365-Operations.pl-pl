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
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898510"
---
# <a name="troubleshoot-integration-with-linkedin-and-attract"></a>Rozwiązywanie problemów z aplikacjami LinkedIn i Attract

[!include [banner](includes/banner.md)]

Poniższe informacje ułatwiają rozwiązywanie problemów, które mogą wystąpić podczas próby publikacji ofert pracy w serwisie LinkedIn z aplikacji Microsoft Dynamics 365 Talent: Attract.

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a>Nie można zalogować się do serwisu LinkedIn przez Attract

Jeśli występują problemy z logowaniem w serwisie LinkedIn przez program Attract, spróbuj wykonać następujące czynności:

1. Sprawdź, czy poświadczenia LinkedIn, które zostały wprowadzone w Attract, są ważne i prawidłowe.
2. Jeśli poświadczenia są ważne i prawidłowe, skontaktuj się z [Pomocą techniczną serwisu LinkedIn](https://www.linkedin.com/help/linkedin).
3. Jeśli ten problem będzie nadal występował, skontaktuj się z [pomocą techniczną firmy Microsoft](./talent-support.md).

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a>Ogłoszenia o pracę z Attract nie są wyświetlane w serwisie LinkedIn

Jeśli po 24 godzinach praca nie pojawiła się w serwisie LinkedIn, spróbuj wykonać następujące czynności:

1. Upewnij się, że identyfikator firmy w serwisie LinkedIn jest mapowany na stronę firmy w serwisie LinkedIn i poprawnie wpisany w centrum administracyjnym Attract. Aby uzyskać więcej informacji na temat zmiany ustawień serwisu LinkedIn w centrum administracyjnym, zobacz [Konfigurowanie integracji z serwisem LinkedIn dla Microsoft Dynamics 365 Talent - Attract](attract-admin-linkedin.md). Aby uzyskać więcej informacji na temat identyfikatorów firmy LinkedIn, zobacz [Kojarzenie identyfikatora firmy w serwisie LinkedIn z tablicą ofert pracy serwisu LinkedIn — często zadawane pytania](https://www.linkedin.com/help/linkedin/answer/98972).
2. Sprawdź szczegóły dotyczące pracy w serwisie LinkedIn, aby upewnić się, że adres jest zakończony. Aby opublikować ofertę pracy pomyślnie, serwis LinkedIn potrzebuje co najmniej nazwy miasta i kraju lub regionu pracy.
3. Upewnij się, że praca nie duplikuje innej pracy, która została opublikowana w serwisie LinkedIn. Serwis LinkedIn nie opublikuje ofert pracy, które są duplikatami Miejsc Pracy Premium serwisu LinkedIn lub ofertami limitowanymi z innego źródła. Sprawdź, czy inna osoba w firmie nie opublikowała jeszcze ręcznie pracy.

## <a name="see-also"></a>Informacje dodatkowe

[Konfigurowanie integracji Attract z serwisem LinkedIn — często zadawane pytania](./attract-linkedin-faq.md)

[Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md)

[Pozyskiwanie kandydatów za pomocą LinkedIn Recruiter w Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md)

[Tworzenie, zatwierdzanie i publikowanie funkcji w aplikacji Attract](./creating-jobs-attract.md)

[Rozwiązywanie problemów z integracją usługi LinkedIn i Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)
