---
title: "Funkcjonalność witryny rozwoju kariery w aplikacji Attract"
description: "Ten artykuł zawiera omówienie funkcjonalności witryny rozwoju kariery dostępnej dla kandydatów w programie Microsoft Dynamics 365 for Talent - Attract. Wyjaśniono również, jak skonfigurować tę funkcjonalność."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: pl-pl
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a>Funkcjonalność witryny rozwoju kariery w aplikacji Attract

[!include [banner](includes/banner.md)]

Ten artykuł zawiera omówienie funkcjonalności witryny rozwoju kariery dostępnej dla kandydatów w programie Microsoft Dynamics 365 for Talent Attract. Wyjaśniono również, jak skonfigurować tę funkcjonalność.

## <a name="overview"></a>Przegląd

Aplikacja Attract udostępnia jedną witrynę rozwoju kariery dla każdego środowiska w dzierżawie. Na przykład jeśli organizacja ma środowiska projektowe i testowe, dla każdego z nich jest generowana osobna witryna rozwoju kariery. Każda witryna rozwoju kariery jest **całkowicie odizolowana** i ma własny mechanizm uwierzytelniania. Funkcje i profile kandydatów nie są udostępniane między witrynami rozwoju kariery.

Domyślnie witryna rozwoju kariery jest publiczna. Z tego względu kandydaci mogą wyświetlić wszystkie funkcje oznaczone jako zewnętrzne bez konieczności logowania się. Jednak wszystkie pozostałe czynności wymagają, aby kandydaci się zalogowali.

## <a name="career-site-management"></a>Zarządzanie witryną rozwoju kariery

Następujące elementy w witrynie rozwoju kariery są kontrolowane przez ustawienia:

- **Nazwa organizacji:** Nazwa organizacji jest wyświetlana na pasku nawigacji u góry witryny rozwoju kariery. Gdy kandydat kliknie nazwę organizacji, przejdzie do strony, która zawiera listę wszystkich otwartych funkcji.
- **Logo organizacji:** Obraz logo organizacji pojawia się w lewym górnym rogu witryny rozwoju kariery. Gdy kandydat kliknie obraz logo, przejdzie do strony, która zawiera listę wszystkich otwartych funkcji.

Aby ustawić wartości nazwy i logo organizacji, zaloguj się w aplikacji Attract jako administrator, wybierz opcję **Centrum administracyjne** w menu **Ustawienia** (symbol koła zębatego), a następnie wybierz kartę **Informacje o firmie**.

> [!NOTE]
> Obraz logo wyświetlany w witrynie rozwoju kariery ma stałą wysokość 20 pikseli (px). Obraz dodany w Centrum administracyjnym zostanie wyskalowany, tak aby pasował do tego limitu. W związku z tym w zależności od obrazu szerokość może się zmienić.

## <a name="career-site-url"></a>Adres URL witryny rozwoju kariery

Gdy [publikujesz ofertę na funkcję dla kandydatów zewnętrznych](./Creating-jobs-Attract.md#postings) po raz pierwszy, możesz skopiować łącze **Zgłoś się** z aplikacji Attract. Adres URL tego łącza będzie miał następujący format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`

Adres URL witryny rozwoju kariery jest podciągiem adresu URL **Zgłoś się**. Zawiera wszystkie elementy aż do nazwy firmy włącznie. Z tego względu w podanym wyżej adresie URL **Zgłoś się** adresem URL witryny rozwoju kariery jest `https://jobs.talent.dynamics.com/jobs/<company_name>/`.

## <a name="authentication-options"></a>Opcje uwierzytelniania

Kandydaci mają do dyspozycji następujące opcje logowania do witryny rozwoju kariery w aplikacji Attract:

- Konto osobiste:

    - LinkedIn
    - Microsoft
    - Google
    - Facebook

- Konto służbowe:

    - Microsoft Azure Active Directory (Azure AD)

Logowanie przez usługę Azure AD jest przeznaczone tylko dla kandydatów wewnętrznych. Z tego względu działa tylko dla kandydatów wewnętrznych, którzy używają firmowych poświadczeń dostępu do usługi Azure AD. Na przykład kandydat, który jest obecnie pracownikiem firmy Contoso Ltd., chce ubiegać się o pracę w niepowiązanej firmie Alpine Ski House. W takim przypadku logowanie się nie powiedzie, jeśli pracownik spróbuje użyć swoich poświadczeń dostępu do usługi Azure AD z firmy Contoso Ltd.

## <a name="create-and-maintain-a-profile"></a>Tworzenie profilu i zarządzanie nim

Gdy kandydaci logują się do witryny rozwoju kariery, mogą wybrać opcję **Mój profil** na pasku nawigacji u góry strony, aby utworzyć sobie profil i nim zarządzać. Profil zawiera informacje osobiste, informacje o doświadczeniu zawodowym, szczegóły wykształcenia, dokumenty, łącza oraz informacji o umiejętnościach. Po utworzeniu profilu można go używać do ubiegania się o funkcje interesujące kandydata. Profile pomagają również aplikacji Attract rekomendować odpowiednie stanowiska dla kandydatów.

## <a name="find-the-right-job"></a>Znajdowanie odpowiedniej funkcji

Na stronie listy funkcji kandydaci mogą wyszukiwać konkretne funkcje, wpisując konkretne terminy. Funkcjonalność wyszukiwania szuka kryteriów wyszukiwania w tytułach funkcji i opisach funkcji, a następnie pokazuje pasujące funkcje jako wyniki. Kandydaci mogą filtrować wyniki w dowolnym momencie według lokalizacji funkcji lub czynności związanych z funkcją.

Kandydaci mogą również w witrynie rozwoju kariery przeglądać zestaw zalecanych funkcji. Funkcje rekomendowane kandydatowi bazują na poprzednich zgłoszeniach, profilu i życiorysie kandydata.

> [!NOTE]
> Rekomendacje funkcji są wyświetlane tylko wtedy, gdy co najmniej 10 funkcji jest opublikowanych w witrynie rozwoju kariery, a kandydat ma uzupełniony profil.

## <a name="apply-for-jobs"></a>Ubieganie się o pracę

Gdy kandydat znajdzie odpowiednią funkcję, może złożyć podanie, klikając przycisk **Zgłoś się** na stronie szczegółów funkcji. W tym momencie kandydat może utworzyć całkowicie nowy profil lub przejrzeć informacje w swoim istniejącym profilu. Kandydat może także w razie potrzeby przekazać życiorys, a następnie przesłać zgłoszenie na funkcję (podanie o pracę).

## <a name="check-application-status"></a>Sprawdzanie stanu zgłoszenia

Gdy kandydat prześle zgłoszenie na jedną lub więcej funkcji, może wybrać opcję **Zgłoszenia** na pasku nawigacji u góry strony i wyświetlić swoje otwarte i zamknięte zgłoszenia. Gdy kandydat otworzy jedno ze swoich zgłoszeń, zobaczy jego obecny etap oraz wszelkie oczekujące czynności, jakie musi wykonać. Na przykład jeśli kandydat musi zaproponować daty osobistej rozmowy kwalifikacyjnej, na stronie będą widoczne odpowiednie opcje.

## <a name="internal-jobs"></a>Funkcje wewnętrzne

Obecnie funkcje oznaczone jako wewnętrzne i opublikowane w witrynie rozwoju kariery w aplikacji Attract nie są wyświetlane w witrynie rozwoju kariery. Są one dostępne wyłącznie za pośrednictwem bezpośredniego adresu URL **Zgłoś się**, który można skopiować z aplikacji Attract.

