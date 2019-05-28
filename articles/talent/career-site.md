---
title: Funkcjonalność witryny rozwoju kariery w aplikacji Attract
description: Ten temat zawiera omówienie funkcji witryny kariery zawodowej w aplikacji Attract dostępne dla kandydatów.
author: hasrivas
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: a56f162ccc6b6099fd62e0cb7e10076368d8e653
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518879"
---
# <a name="career-site-functionality-in-attract"></a>Funkcjonalność witryny rozwoju kariery w aplikacji Attract

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie funkcji witryny kariery zawodowej w Microsoft Dynamics 365 for Talent: Attract dostępne dla kandydatów. Wyjaśniono również, jak skonfigurować tę funkcjonalność.

Aplikacja Attract udostępnia jedną witrynę rozwoju kariery dla każdego środowiska w dzierżawie. Na przykład jeśli organizacja ma środowiska projektowe i testowe, dla każdego z nich jest generowana osobna witryna rozwoju kariery. Każda witryna rozwoju kariery jest całkowicie odizolowana i ma własny mechanizm uwierzytelniania. Funkcje i profile kandydatów nie są udostępniane między witrynami rozwoju kariery.

Domyślnie witryna rozwoju kariery jest publiczna. Z tego względu kandydaci mogą wyświetlić wszystkie funkcje oznaczone jako zewnętrzne bez konieczności logowania się. Jednak wszystkie pozostałe czynności wymagają, aby kandydaci się zalogowali.

## <a name="career-site-management"></a>Zarządzanie witryną rozwoju kariery

Aby ustawić wartości następujących elementów, zaloguj się w aplikacji Attract jako administrator, wybierz opcję **Centrum administracyjne** w menu **Ustawienia** (symbol koła zębatego), a następnie wybierz kartę **Informacje o firmie**.

-   **Nazwa organizacji:** Nazwa organizacji jest wyświetlana na pasku nawigacji u góry witryny rozwoju kariery. Gdy kandydat kliknie nazwę organizacji, przejdzie do strony, która zawiera listę wszystkich otwartych funkcji.

-   **Logo organizacji:** Obraz logo organizacji pojawia się w lewym górnym rogu witryny rozwoju kariery. Gdy kandydat kliknie obraz logo, przejdzie do strony, która zawiera listę wszystkich otwartych funkcji.

    > [!NOTE] 
    > Obraz logo wyświetlany w witrynie rozwoju kariery ma stałą wysokość 20 pikseli (px). Obraz dodany w Centrum administracyjnym zostanie wyskalowany, tak aby pasował do tego limitu. W związku z tym w zależności od obrazu szerokość może się zmienić.
 
Aby ustawić wartości następujących elementów, zaloguj się w aplikacji Attract jako administrator, wybierz opcję **Centrum administracyjne** w menu **Ustawienia**, a następnie wybierz kartę **Zarządzanie witryną rozwoju kariery**.

-   **Optymalizacja aparatu wyszukiwania:** Po włączeniu tej opcji wszystkie publicznie dostępne oferty w witrynie rozwoju kariery Attract będzie można znaleźć za pomocą wyszukiwarek, takich jak Bing i Google.

    > [!NOTE] 
    > Może wystąpić opóźnienie między włączeniem tego ustawienia, a uwzględnianiem ofert w wynikach wyszukiwania, w zależności od używanego aparatu wyszukiwania.
         
## <a name="career-site-urls"></a>Adresu URL witryny rozwoju kariery

Poniższa lista zawiera często używane adresy URL witryny rozwoju kariery i metody dostępu do nich.

-   **Adres URL strony głównej witryny kariery zawodowej** — Aby wyświetlić adres URL strony głównej witryny kariery zawodowej, zaloguj się w Attract jako administrator, wybierz opcję **Centrum administracyjne** w menu **ustawienia**, a następnie wybierz opcję **Zarządzanie witryną kariery zawodowej**.

-   **Indywidualny adres URL zgłoszenia na ofertę pracy**Gdy [publikujesz ofertę](Creating-jobs-Attract.md#postings) dla kandydatów zewnętrznych po raz pierwszy, możesz skopiować łącze **Zgłoś się** z aplikacji Attract. Adres URL tego łącza będzie miał następujący format: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)

-   **Indywidualny adres URL oferty pracy** adres URL oferty pracy jest podciągiem adresu URL zgłoszenia. Zawiera wszystkie elementy aż do numeru stanowiska włącznie. Z tego względu w podanym wyżej adresie URL Zgłoś się adresem URL oferty pracy jest [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e).

## <a name="authentication-options"></a>Opcje uwierzytelniania

Kandydaci mają do dyspozycji następujące opcje logowania do witryny rozwoju kariery w aplikacji Attract:

-   Konto osobiste:

    -   LinkedIn

    -   Microsoft

    -   Google

    -   Facebook

-   Konto służbowe lub szkolne:

    -   Microsoft Azure Active Directory (Azure AD)

Azure AD Logowanie przez usługę Azure AD jest przeznaczone tylko dla kandydatów wewnętrznych. Z tego względu działa tylko dla kandydatów wewnętrznych, którzy używają firmowych poświadczeń dostępu do usługi Azure AD. Na przykład kandydat, który jest obecnie pracownikiem firmy Contoso Ltd., chce ubiegać się o pracę w niepowiązanej firmie Alpine Ski House. W takim przypadku logowanie się nie powiedzie, jeśli pracownik spróbuje użyć swoich poświadczeń dostępu do usługi Azure AD z firmy Contoso Ltd. 

Kandydaci muszą zalogować się przy użyciu Azure AD, jeśli oferta pracy, którą oglądają lub chcą aplikować, jest wymieniona jako tylko wewnętrzna.

## <a name="create-and-maintain-a-profile"></a>Tworzenie profilu i zarządzanie nim

Gdy kandydaci logują się do witryny rozwoju kariery, mogą wybrać opcję **Mój profil** na pasku nawigacji u góry strony, aby utworzyć sobie profil i nim zarządzać.
Profil zawiera informacje osobiste, informacje o doświadczeniu zawodowym, szczegóły wykształcenia, dokumenty, łącza oraz informacji o umiejętnościach. Po utworzeniu profilu można go używać do ubiegania się o funkcje interesujące kandydata. Profile pomagają również aplikacji Attract rekomendować odpowiednie stanowiska dla kandydatów.

> [!NOTE]
> Jeśli kandydat używa identyfikatora e-mail, aby zalogować się przy użyciu jednego z dostawców uwierzytelniania wymienionych powyżej, ten identyfikator e-mail zostanie ustawiony jako domyślny dla kontaktowego adresu e-mail skojarzonego z profilem. Jednak to ostatnie można zmienić w dowolnym momencie i jest to całkowicie niezależne od pierwszego. Attract będzie zawsze używać Identyfikatora e-mail osoby kontaktowej do skojarzenia go z Twoim profilem dla całej komunikacji e-mail.

## <a name="find-the-right-job"></a>Znajdowanie odpowiedniej funkcji

Na stronie listy funkcji kandydaci mogą wyszukiwać konkretne funkcje, wpisując konkretne terminy. Funkcjonalność wyszukiwania szuka kryteriów wyszukiwania w tytułach funkcji i opisach funkcji, a następnie pokazuje pasujące funkcje jako wyniki. Kandydaci mogą filtrować wyniki w dowolnym momencie według lokalizacji funkcji lub czynności związanych z funkcją.

Kandydaci mogą również w witrynie rozwoju kariery przeglądać zestaw zalecanych funkcji. Funkcje rekomendowane kandydatowi bazują na poprzednich zgłoszeniach, profilu i życiorysie kandydata.

> [!NOTE] 
> Rekomendacje funkcji są wyświetlane tylko wtedy, gdy co najmniej 10 funkcji jest opublikowanych w witrynie rozwoju kariery, a kandydat ma uzupełniony profil.

Wewnętrzni kandydaci mogą również sprawdzić, kto jest menedżerem zatrudniającym/osobą rekrutującą na stanowisko, jeśli chcą się skontaktować z taką osobą w swoim zespole. Kandydaci zewnętrzni nie mają wglądu w skład zespołu rekrutującego.

## <a name="contact-the-hiring-team"></a>Skontaktuj się z zespołu rekrutacyjnym
Wyłącznie kandydaci wewnętrzni mogą kontaktować się z zespołem zatrudnienia. To ograniczenie dotyczy wszystkich ofert pracy bez względu na to, czy jest to oferta wewnętrzna, czy dostępna publicznie.

Kandydaci mogą chcieć skontaktować się z zespołem rekrutacyjnym, aby wyrazić zainteresowanie ofertą lub dowiedzieć się więcej na ten temat. Mogą skontaktować się z dowolnymi członkami zespołu rekrutacyjnego, którzy zostali wymienieni (menedżer zatrudniający lub osoba rekrutująca). Kandydaci mogą też opcjonalnie dołączyć życiorys do wiadomości lub mogą wybrać istniejący życiorys, który wcześniej przesłali jako część ich profilu.

Jeśli kandydat wewnętrzny wybierze członków zespołu rekrutacyjnego, z którymi chce się skontaktować, Attract wysyła wiadomość e-mail do wybranych osób w imieniu kandydata. W tym samym czasie profil kandydata zostanie dodany do etapu **prospektu**, jeśli ten etap jest dostępny dla danego stanowiska. Na etapie **prospektu** menedżer zatrudniający lub osoba rekrutująca mogą wyświetlać kandydatów, którzy się do nich zgłosili. Mogą także przeglądać profile kandydatów i zaprosić potencjalnych kandydatów do złożenia propozycji.

Kandydaci mogą ubiegać się o pracę, w sprawie której już skontaktowali się z zespołem rekrutacyjnym. Po złożeniu aplikacji kandydat nie może kontaktować się z zespołem rekrutacyjnym za pośrednictwem witryny kariery zawodowej.

## <a name="apply-for-jobs"></a>Ubieganie się o pracę

Gdy kandydat znajdzie odpowiednią funkcję, może złożyć podanie, klikając przycisk  **Zgłoś się**  na stronie  **szczegółów stanowiska**. W tym momencie kandydat może utworzyć całkowicie nowy profil lub przejrzeć informacje w swoim istniejącym profilu.
Kandydat może także w razie potrzeby przekazać życiorys, a następnie przesłać zgłoszenie na funkcję (podanie o pracę).

### <a name="enable-applying-for-jobs-with-linkedin-profiles"></a>Włącz składanie podań o pracę za pomocą profili LinkedIn

Kandydaci mogą łatwo składać aplikacje na stanowisko, jeśli skonfigurujesz Attract w taki sposób, żeby było możliwe przesyłanie zgłoszeń przez LinkedIn.

> [!NOTE] 
> Musisz mieć jedną lub więcej licencji Osoby rekrutującej z LinkedIn, aby zezwolić kandydatom składanie aplikacji przez LinkedIn.

1. Zaloguj się w Attract jako administrator.
2. Wybierz przycisk **ustawienia** (symbol koła zębatego) w prawym górnym rogu strony, a następnie wybierz opcję **Centrum administracyjnego**.
3. Wybierz kartę **integracji LinkedIn** i połącz z kontem LinkedIn Recruiter.
4. W integracji **LinkedIn Recruiter System Connect** zaznacz **Wł.** dla ustawienia **Zgłoś się za pomocą LinkedIn**.

Po włączeniu tego ustawienia kandydaci będą mogli zgłaszać się, używając danych profilowych na LinkedIn. Gdy kandydaci składają aplikacje, naciskając przycisk **Zgłoś się za pomocą LinkedIn**, są proszeni o uwierzytelnienie się na LinkedIn, jeśli nie są zalogowani. Po uwierzytelnieniu kandydatów ich profile LinkedIn zastępują wszelkie istniejące dane profilu wyświetlana na stronie zgłoszenia. Kandydaci mogą edytować informacje i przesłać zgłoszenie. Jeśli kandydat opuści stronę bez zgłoszenia się na stanowisko, jego dane profilowe nie zostaną zaktualizowane w Attract.

## <a name="check-application-status"></a>Sprawdzanie stanu zgłoszenia

Gdy kandydat prześle zgłoszenie na jedną lub więcej funkcji, może wybrać opcję **Zgłoszenia** na pasku nawigacji u góry strony i wyświetlić swoje otwarte i zamknięte zgłoszenia. Gdy kandydat otworzy jedno ze swoich zgłoszeń, zobaczy jego obecny etap oraz wszelkie oczekujące czynności, jakie musi wykonać. Na przykład jeśli kandydat musi zaproponować daty osobistej rozmowy kwalifikacyjnej, na stronie będą widoczne dostępne opcje.

## <a name="internal-jobs"></a>Funkcje wewnętrzne

Obecnie funkcje oznaczone jako wewnętrzne i opublikowane w witrynie rozwoju kariery w aplikacji Attract nie są wyświetlane w witrynie rozwoju kariery. Są one dostępne wyłącznie za pośrednictwem bezpośredniego adresu URL **Zgłoś się**, który można skopiować z aplikacji Attract.
