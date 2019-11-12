---
title: Konfigurowanie integracji z serwisem LinkedIn dla aplikacji Microsoft Dynamics 365 Talent - Attract
description: W tym temacie opisano sposób konfigurowania integracji LinkedIn w aplikacji Microsoft Dynamics 365 Talent - Attract, dzięki czemu można łatwo publikować ogłoszenia o pracę w serwisie LinkedIn, aby umożliwić im synchronizowanie informacji o rekrutacji z profilem serwisu LinkedIn.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 5cdce69396d6972d810e65e15b27c79119a0a9e6
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2552124"
---
# <a name="set-up-integration-with-linkedin-for-microsoft-dynamics-365-talent---attract"></a>Konfigurowanie integracji z serwisem LinkedIn dla aplikacji Microsoft Dynamics 365 Talent - Attract

[!include[banner](../includes/banner.md)]

Pomóż swoim rekruterom i menedżerom zatrudniającym znaleźć najlepsze talenty dzięki skonfigurowaniu integracji serwisu LinkedIn z aplikacją Microsoft Dynamics 365 Talent: Attract. Attract umożliwia publikowanie ogłoszeń o pracę bezpośrednio w serwisie LinkedIn, największej profesjonalnej sieci online.

Zadania, które są księgowane w serwisie LinkedIn przez Attract, są ograniczonymi ofertami i są dostarczane firmie bez dodatkowych kosztów. Te listy są dostępne tylko dla partnerów programowych serwisu LinkedIn takich jak Attract. Nie są one widoczne w panelu **Kariery** na stronie firmy w LinkedIn, ponieważ w tym miejscu pojawiają się tylko listy opłacane. Są jednak wyświetlane, gdy potencjalni kandydaci widzą wszystkie dostępne prace. Listy z ograniczeniami są także wyświetlane w wyszukiwaniach prac LinkedIn.

Attract pozwala na integrację na dwa sposoby z serwisem LinkedIn, które ułatwiają dostęp do kandydatów z tej popularnej witryny kariery:

- Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Attract.
- Pozyskuj kandydatów z serwisu LinkedIn do Attract.

Obie opcje konfiguruje się na karcie **Integracja z usługą LinkedIn** w centrum administracyjnym. Otwórz centrum administracyjne w <https://attract.talent.dynamics.com/adminsettings>.

> [!NOTE]
> Aby można było korzystać z integracji aplikacji LinkedIn Recruiter z aplikacją Attract, trzeba mieć [Dodatek kompleksowej obsługi rekrutacji](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring) oraz [licencje LinkedIn Recruiter](https://business.linkedin.com/talent-solutions/cx/17/08/recruiter-demo-fs2-k18). Aby uzyskać więcej informacji, zajrzyj do [Która wersja aplikacji Attract?](./attract-comprehensive-hiring.md).

Jeśli występują problemy z zaksięgowaniem zadań w serwisie LinkedIn, przejrzyj informacje [Rozwiązywanie problemów z integracją z serwisem LinkedIn](./attract-troubleshoot-linkedin.md).

Aby uzyskać informacje na temat innych sposobów ogłaszania zadań w serwisie LinkedIn, przejrzyj [Często zadawane pytania dotyczące serwisu LinkedIn](./attract-linkedin-faq.md).

## <a name="configure-job-posting-to-linkedin"></a>Skonfiguruj publikację ofert pracy w serwisie LinkedIn

Aby można było zaksięgować zadania z Attract do serwisu LinkedIn, należy posiadać [Identyfikator firmy LinkedIn](https://aka.ms/findID). Identyfikator firmy LinkedIn to ciąg liczb, które jednoznacznie identyfikują Twoją firmę na portalu LinkedIn. Aby uzyskać więcej informacji, zobacz [Kojarzenie identyfikatora firmy w serwisie LinkedIn z tablicą ofert pracy serwisu LinkedIn — często zadawane pytania](https://aka.ms/findID).

Attract przesyła Twoje ogłoszenia o prace do LinkedIn, a w serwisie LinkedIn sprawdza kanał informacyjny w przybliżeniu raz na dzień. Czas do publikacji ofert w witrynie może potrwać do 48 godzin.

Oferty pracy, które są publikowane na LinkedIn są wyświetlane od razu na oficjalnej stronie LinkedIn. Nie ma środowiska testowego dla publikowania ofert pracy na LinkedIn. Dlatego należy się upewnić, że nie są one przypadkowo publikowane żadne oferty testowe. 

1. W menu **Ustawienia** (symbol koła zębatego) w prawym górnym rogu wybierz opcję **Centrum administracyjne**. Alternatywnie przejdź do <https://attract.talent.dynamics.com/adminsettings>.
2. Wybierz kartę **Integracja z serwisem LinkedIn**.
3. W obszarze **Nazwa firmy**wprowadź nazwę firmy, a w polu **Identyfikator firmy** wprowadź identyfikator swojej firmy w serwisie LinkedIn. Upewnij się, że nazwa firmy pasuje do nazwy znajdującej się na stronie serwisu LinkedIn firmy. Aby uzyskać więcej informacji na temat identyfikatorów firmy LinkedIn, zobacz [Kojarzenie identyfikatora firmy w serwisie LinkedIn z tablicą ofert pracy serwisu LinkedIn — często zadawane pytania](https://www.linkedin.com/help/linkedin/answer/98972).

    Aby zmienić informacje dotyczące organizacji, należy zapoznać się z tematem [Zmiana adresu organizacji, kontaktu technicznego itp.](https://docs.microsoft.com/office365/admin/manage/change-address-contact-and-more). Jeśli nadal masz problemy, skontaktuj się z [Pomocą techniczną serwisu LinkedIn](https://www.linkedin.com/help/linkedin).

4. Wybierz opcję **Zapisz**.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Ustawianie LinkedIn Recruiter z Attract 

Aby umożliwić rekruterom umieszczanie ogłoszeń o pracę przez LinkedIn Recruiter, należy skonfigurować integrację LinkedIn Recruiter z Attract. W celu przeprowadzenia procesu konfiguracji należy współpracować z użytkownikiem, który jest administratorem kontaktu Twojej organizacji z LinkedIn Recruiter.

1. W menu **Ustawienia** (symbol koła zębatego) w prawym górnym rogu wybierz opcję **Centrum administracyjne**. Alternatywnie przejdź do <https://attract.talent.dynamics.com/adminsettings>.
2. Wybierz kartę **Integracja z serwisem LinkedIn**.

    [![Widok administratora aplikacji Attract przy rozpoczynaniu integracji z aplikacją LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Wybierz opcję **Połącz**, aby rozpocząć konfigurowanie. Nastąpi przeprowadzenie procedury rejestracji w usłudze LinkedIn.
4. Jeśli masz stanowiska w różnych umowach na portalu LinkedIn, zaznacz umowę, którą chcesz połączyć z systemem Attract. Jeśli masz stanowisko tylko w jednej umowie na LinkedIn, ten krok można pominąć.
5. W obszarze **Recruiter System Connect (RSC)** wybierz **Poproś**.

    [![Widok administratora aplikacji Attract przy żądaniu integracji z aplikacją LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6. Ustawienie **Recruiter System Connect (RSC)** powinno teraz pojawić się jako **Partner gotowy**. Jeśli na tej stronie zobaczysz przycisk **Powiadom partnera**, poczekaj kilka sekund, wybierz przycisk **Powiadom partnera**, a następnie odśwież stronę. Ustawienie powinno teraz pojawić się jako **Partner gotowy**.

    [![Widok administratora aplikacji Attract wskazujący, że wszystkie żądania po stronie aplikacji Attract zostały wykonane](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

7. Aby wykonać następne kroki, musisz mieć uprawnienia administratora w umowie na usługę LinkedIn Recruiter.

    1. Zaloguj się do serwisu LinkedIn przy użyciu konta administratora, a następnie wybierz **LinkedIn Recruiter** w prawym górnym rogu. 
    2. W menu **Więcej** w górnej części ekranu kliknij przycisk **Ustawienia administratora**, a następnie kliknij kartę **ATS**.
    3. Aby umożliwić eksport jednego kliknięcia tylko dla jednego kontraktu, włącz dostęp na **poziomie umowy (dla każdego stanowiska w tej umowie)**. Aby włączyć ją dla całej firmy, włącz dostęp na **poziomie firmy (dla wszystkich umów w firmie)**.

    [![Włączanie integracji z aplikacją Attract z widoku administratora aplikacji LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)

8. W centrum administracyjnym Attract wybierz kartę **Integracja z serwisem LinkedIn**. **Recruiter System Connect (RSC)** powinno teraz pojawiać się jako **włączone**.

    [![LinkedIn Recruiter: Składniki integracyjne](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="set-up-apply-with-linkedin-in-attract"></a>Konfigurowanie aplikacji przez aplikację LinkedIn w Attract

Można zezwolić na aplikację kandydatów do ofert pracy, korzystając z ich profili LinkedIn. Aby uzyskać więcej informacji na temat aplikacji w serwisie LinkedIn, odwiedź [Możliwości serwisu LinkedIn wszędzie: Aplikacja z serwisem LinkedIn](https://blog.linkedin.com/2011/07/24/apply-with-linkedin).

Ta funkcja jest obecnie w wersjach zapoznawczych. Przed wykonaniem tych kroków należy się upewnić, że jest włączona funkcja aplikowania w serwisie LinkedIn. Aby uzyskać informacje dotyczące włączania funkcji podglądu, zobacz [Dostęp do funkcji podglądu w Talent](./access-preview-feature.md).

1. W menu **Ustawienia** (symbol koła zębatego) w prawym górnym rogu wybierz opcję **Centrum administracyjne**. Alternatywnie przejdź do <https://attract.talent.dynamics.com/adminsettings>.
2. Wybierz kartę **Integracja z serwisem LinkedIn**.

    [![Widok administratora aplikacji Attract przy rozpoczynaniu integracji z aplikacją LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Dalej, **Aplikować w serwisie LinkedIn** wybierz **Połącz**, aby rozpocząć konfigurowanie. Nastąpi przeprowadzenie procedury w usłudze LinkedIn.

## <a name="see-also"></a>Informacje dodatkowe

[Często zadawane pytania dotyczące serwisu LinkedIn](./attract-linkedin-faq.md)

[Publikowanie funkcji w witrynach zewnętrznych z poziomu aplikacji Attract](./posting-jobs-external.md)

[Pozyskiwanie kandydatów za pomocą usługi LinkedIn Recruiter](./attract-linkedin-recruiter.md)

[Tworzenie pracy](./creating-jobs-attract.md)

[Rozwiązywanie problemów integracji z serwisem LinkedIn](./attract-troubleshoot-linkedin.md)
