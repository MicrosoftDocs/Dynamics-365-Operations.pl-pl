---
title: Dostęp do funkcji w wersji zapoznawczej w aplikacji Microsoft Dynamics 365 for Talent
description: W tym temacie opisano, jak administrator może włączyć funkcje w wersji zapoznawczej w aplikacji Microsoft Dynamics 365 for Talent, oraz podano listę funkcji dostępnych obecnie w wersji zapoznawczej.
author: tracykeya
manager: AnnBe
ms.date: 05/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: 6a5aa8d6ea72ec3d3910edea291c4340ab607326
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739594"
---
# <a name="manage-preview-features"></a>Zarządzaj funkcjami w wersji zapoznawczej

[!include[banner](../includes/banner.md)]

W ramach ciągłego wdrażania nowych funkcji zarządzania kapitałem ludzkim (HCM) w aplikacji Microsoft Dynamics 365 for Talent chcemy stworzyć klientom możliwość jak najszybszego zetknięcia się z nimi. Administratorzy mogą przeglądać i używać funkcji zapoznawczych w swoich środowiskach. Te funkcje są prawie gotowe do ogólnego udostępnienia i przeszły wszechstronne testy. Jednak zanim je upublicznimy powszechnie, chcemy jeszcze poznać finalne opinie klientów i przeprowadzić ostatnią weryfikację.

W tym temacie opisano, jak włączyć funkcje w wersji zapoznawczej, oraz podano listę funkcji dostępnych obecnie w wersji zapoznawczej. Lista będzie aktualizowana wraz z przekazywaniem kolejnych funkcji ogółowi użytkowników i udostępnianiem wersji zapoznawczych. Dodawanie nowych funkcji zapoznawczych nie będzie w żaden sposób anonsowane. Użytkownicy po prostu zaczną je widzieć. Aby uzyskać więcej informacji o nowych funkcjach w aplikacji Talent, zobacz [Nowości i zmiany w aplikacji Dynamics 365 for Talent](./whats-new.md) oraz [Informacje o wersji Dynamics 365 i Power Platform](https://docs.microsoft.com/business-applications-release-notes).

## <a name="enable-or-disable-preview-features"></a>Włączanie i wyłączanie funkcji zapoznawczych

Aby uzyskać dostęp do funkcji w wersji zapoznawczej, należy je najpierw włączyć w środowisku. Włączanie lub wyłączanie funkcji zapoznawczych jest specyficzne dla środowiska.

> [!IMPORTANT]
> Włączenie ustawienia **Funkcje w wersji zapoznawczej** skutkuje włączeniem funkcji w wersji zapoznawczej wszystkim użytkownikom w organizacji pracującym w tym środowisku. Wyłączenie ustawienia powoduje wyłączenie funkcji w wersji zapoznawczej i zablokowanie użytkownikom dostępu do nich. Funkcje zapoznawcze są obsługiwane w ograniczonym zakresie w aplikacji Talent. Mogą korzystać ze słabszych narzędzi ochrony prywatności i bezpieczeństwa oraz nie są objęte umową dotyczącą poziomu usług (SLA) zawieraną dla aplikacji Talent. Nie należy używać funkcji zapoznawczych do przetwarzania danych osobowych (tzn. wszelkich informacji, które mogą jednoznacznie identyfikować użytkownika) ani innych danych, które podlegają prawnym lub ustawowym wymogom dotyczącym zgodności.

### <a name="attract"></a>Przyciągaj

1. Zaloguj się do programu Microsoft Dynamics 365 for Talent: Attract.
2. W menu **Ustawienia** (symbol koła zębatego) w prawym górnym rogu wybierz opcję **Centrum administracyjne**.
3. Na karcie **Zarządzanie funkcjami** zaznacz opcję **Funkcje w wersji zapoznawczej**, tak aby zmieniła kolor na niebieski i treść na **Włączone**.

    ![Włączanie funkcji w wersji zapoznawczej w aplikacji Attract](./media/attract-enable-preview-features.png)

4. Wybierz lub anuluj wybór poszczególnych funkcji w wersji zapoznawczej. W przeciwnym razie zostaną włączone wszystkie dostępne funkcje w wersji zapoznawczej.
5. Odśwież przeglądarkę, a zaczniesz widzieć nowe funkcje. Wszyscy użytkownicy, którzy są już zalogowani, zobaczą funkcje po następnym zalogowaniu, lub też mogą odświeżyć przeglądarki, a zobaczą je natychmiast.

> [!NOTE]
> Niektóre funkcje w wersji zapoznawczej mogą wymagać dodatkowej konfiguracji. Obok funkcji w wersji zapoznawczej znajdują się łącza umożliwiające dokończenie ich konfigurowania.

### <a name="core-hr"></a>Core HR

1. Zaloguj się w aplikacji Talent.
2. Wybierz opcję **Administrowanie systemem**, a następnie wybierz kartę **Łącza**.
3. Na stronie **Administrowanie systemem**, w obszarze **Konfiguracja**wybierz opcję **Parametry systemowe**.
4. Na stronie **Parametry systemowe** wybierz kartę **Funkcje w wersji zapoznawczej**.
5. Ustaw opcję **Włącz tryb zapoznawczy dla wszystkich użytkowników** na **Tak**, aby funkcje w wersji zapoznawczej były dostępne.

    ![Włączanie funkcji w wersji zapoznawczej w aplikacji Core HR](./media/corehr-enable-preview-features.png)

> [!NOTE]
> Aby wyłączyć funkcje w wersji zapoznawczej, wykonaj te same kroki, ale ustaw opcję **Włącz tryb zapoznawczy dla wszystkich użytkowników** na **Nie**. Po wyłączeniu funkcji zapoznawczych staną się one niedostępne dla użytkowników, a w procesach związanych z funkcjami mogą się pojawiać błędy.

### <a name="onboard"></a>Rekrutuj

Obecnie nie są dostępne żadne funkcje w wersji zapoznawczej aplikacji Microsoft Dynamics 365 for Talent: Onboard.

## <a name="features-that-are-currently-in-preview"></a>Funkcje istniejące obecnie w wersjach zapoznawczych

### <a name="attract"></a>Przyciągaj

- [Rekomendacja kandydata](./intelligent-recommendations.md#candidate-recommendations) — jeśli na którąkolwiek funkcję jest więcej niż 10 kandydatów mających życiorysy lub kompletne profile, to kandydaci najlepiej spełniający wymagania określone dla funkcji są wyświetlani w sekcji **Kandydaci do wzięcia pod uwagę** na stronie tej funkcji.
- [Rekomendacja funkcji](./intelligent-recommendations.md#job-recommendations) — jeśli w witrynie rozwoju kariery jest opublikowanych więcej niż dziesięć ofert pracy, aplikacja Attact przedstawia rekomendacje funkcji prospektom.
- [Integracja z aplikacją Broadbean](./posting-jobs-external.md#post-jobs-to-broadbean) — oferty pracy z aplikacji Attract można opublikować w aplikacji Broadbean, zewnętrznej witrynie ofert pracy. Po włączeniu tej funkcji w wersji zapoznawczej należy dokończyć konfigurowanie, wprowadzając nazwę użytkownika Broadbean, identyfikator klienta i token szyfrowania.
- [Analizy](./analytic-reports.md) — w centrum analiz zespoły rekrutacyjne mogą wyświetlać kluczowe wskaźniki pojedynczego zadania oraz zagregowane wskaźniki wszystkich zadań.
- [EEO](./activities-attract.md) — nowe typy działań pozwalają użyć wstępnie zdefiniowanego formularza do zbierania od kandydata danych dotyczących amerykańskiej ustawy o równym traktowaniu w zatrudnieniu (EEO) oraz danych wymaganych przez amerykańskie biuro ds. programów przestrzegania przepisów w kontraktach dla instytucji rządowych (OFCCP). Wstępnie zdefiniowanego formularza nie można edytować.
- [Rekomendacja prospektów](./intelligent-recommendations.md#prospect-recommendations) — aplikacja Attract przegląda dawnych i bieżących kandydatów, aby utworzyć listę prospektów dobrze pasujących do danego zadania.
- [Wyszukiwanie wg stopnia zgodności](./attract-talent-pools.md#search-and-view-candidate-profiles) — możliwość przeszukiwania całej bazy danych kandydatów pod kątem konkretnych kwalifikacji, nazwisk lub wykształcenia. Attract przeszukuje cały profil i podświetla wszystkie trafienia, które znajdzie. Ponadto Attract przeszukuje wszystkie dostępne dokumenty na temat kandydata i inteligentnie ocenia wyniki wyszukiwania.
- [Odbiorcy działania](./whats-new-talent-march-20.md#setting-the-audience-on-activities) — możliwość ustawienia jako odbiorców działań (takich jak przeprowadzanie rozmowy kwalifikacyjnej, planowanie lub opiniowanie) opcji **Wszyscy kandydaci**, **Wewnętrzni kandydaci** lub **Zewnętrzni kandydaci**. Działania, na przykład filmy na YouTube, zawartość sieciowa i formularze Microsoft, mogą być wtedy dostarczane wszystkim kandydatom, tylko wewnętrznym kandydatom, tylko zewnętrznym kandydatom lub zespołowi rekrutacyjnemu.
- [Zgłoś się za pomocą LinkedIn](./career-site.md#enable-applying-for-jobs-with-linkedin-profiles) — możliwość skonfigurowania w witrynie kariery Attract opcji zgłaszania się kandydatów przy użyciu LinkedIn. Ta funkcja usprawnia proces zgłaszania dla kandydatów, umożliwiając im korzystanie z profilu LinkedIn w celu automatycznego wypełniania swoich zgłoszeń w witrynie kariery.
- [Śledzenie źródła](./source-tracking.md) — Attract automatycznie śledzi źródła zgłoszeń kandydatów, zapewniając cenne informacje, które pomagają w procesie rekrutacji. Możliwe jest także wybranie źródła aplikacji podczas dodawania kandydata do stanowiska lub puli umiejętności i kandydatów.
- [Srebrny medalista](./whats-new-talent-march-20.md#designate-silver-medalists-to-assign-high-value-applicants-for-future-positions)— jeśli są kandydaci, którzy świetnie pasowaliby do organizacji, ale nie zostali objęciu ofertą na bieżące stanowisko, można ich zaliczyć do srebrnych medalistów. Ta funkcja ułatwia skrócenie czasu rekrutacji, gdy następnym razem będzie dostępne podobne stanowisko.

### <a name="core-hr"></a>Core HR

- [Sprawdź poprawność danych hierarchii stanowisk](./whats-new-talent-may-13-2019.md#new-page-to-validate-position-hierarchy-data) — istnieje możliwość sprawdzenia hierarchii kadry kierowniczej dla wszystkich odwołań cyklicznych, które zostały przypadkowo zaimportowane.
- [Określ kody przyczyn dla typów urlopów](./whats-new-talent-may-13-2019.md#specify-reason-codes-on-leave-types) — można określić kody przyczyny skojarzone z typami urlopów.
- [Wymagaj kodu przyczyny we wnioskach o czas wolny](./whats-new-talent-may-13-2019.md#require-reason-codes-for-specific-leave-types-on-time-off-requests) — oprócz określenia kodów przyczyny można określić typy urlopów wymagające podania kodów przyczyny we wnioskach o czas wolny.
- [Podaj listę transakcji urlopów i nieobecności dla zasobów ludzkich](./whats-new-talent-may-13-2019.md#provide-a-leave-and-absence-transaction-list-for-hr) — istnieje możliwość wyświetlenia listy transakcji urlopu i nieobecności, która jest przydatna podczas analizowania sald czasu wolnego.

### <a name="onboard"></a>Rekrutuj

Obecnie nie są dostępne żadne funkcje w wersji zapoznawczej aplikacji Onboard.

## <a name="feedback"></a>Opinii

Chcemy się dowiedzieć, co sądzisz, na podstawie swojego doświadczenia, o tych funkcjach w wersji zapoznawczej. Zachęcamy do regularnego zamieszczania opinii w podanych witrynach podczas korzystania z tych i innych funkcji:

- [Społeczność](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) — Ta witryna to doskonała platforma, na której użytkownicy mogą omawiać scenariusze zastosowania, zadawać pytania i otrzymywać osób od podobnych im osób.
- Opowiedz nam o funkcjach, które Twoim zdaniem powinny się znaleźć w produkcie, a także o wszelkich zmianach, które Twoim zdaniem należy wprowadzić w istniejących funkcjach. Pomysły na ulepszenie produktu można zgłaszać w następujących witrynach:

    - [Pomysły dotyczące aplikacji Attract](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Pomysły dotyczące aplikacji Core HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    - [Pomysły dotyczące aplikacji Onboard](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

W przesyłanych opiniach i recenzjach produktu nie podawaj żadnych danych osobowych (tzn. informacji, które mogłyby umożliwić identyfikację Ciebie). Zebrane informacje mogą być dalej analizowane, ale ze względu na obowiązujące przepisy o ochronie danych osobowych nie będą wykorzystywane do udzielania odpowiedzi na pytania. Dane osobowe, które na mocy tych programów są zbierane osobno, podlegają [zasadom zachowania poufności informacji firmy Microsoft](https://privacy.microsoft.com/privacystatement).

> [!TIP]
> Dodaj tej temat do zakładek i zaglądaj tu regularnie, aby być na bieżąco z nowo publikowanymi funkcjami w wersjach zapoznawczych.

## <a name="see-also"></a>Informacje dodatkowe

- [Wypróbuj lub kup aplikacje Talent](https://dynamics.microsoft.com/talent/overview/)
- [Co nowego](./whats-new.md)
- [Informacje o wersji](https://docs.microsoft.com/business-applications-release-notes/index)
- [Uzyskiwanie pomocy technicznej dotyczącej rozwiązania Talent](./talent-support.md)
