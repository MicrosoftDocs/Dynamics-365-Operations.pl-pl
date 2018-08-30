---
title: "Dostęp do funkcji w wersji zapoznawczej w aplikacji Talent"
description: "W tym temacie opisano, jak administrator może włączyć funkcje zapoznawcze, oraz podano listę funkcji dostępnych obecnie w wersji zapoznawczej."
author: rschloma
manager: AnnBe
ms.date: 04/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: eb99f169ada2a227ebe8e64ee56bbb38cdfda4e0
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="access-preview-features-in-talent"></a>Dostęp do funkcji w wersji zapoznawczej w aplikacji Talent

[!include[banner](../includes/banner.md)]

W ramach ciągłego wdrażania nowych funkcji produktów chcemy stworzyć klientom możliwość jak najszybszego zetknięcia się z nimi. Administratorzy mogą przeglądać i używać funkcji zapoznawczych w swoich środowiskach. Te funkcje są prawie gotowe do ogólnego udostępnienia i przeszły wszechstronne testy. Jednak zanim je upublicznimy, chcemy jeszcze poznać finalne opinie klientów i przeprowadzić ostatnią weryfikację.

W tym temacie opisano, jak administrator może włączyć funkcje zapoznawcze, oraz podano listę funkcji dostępnych obecnie w wersji zapoznawczej. Lista będzie aktualizowana wraz z przekazywaniem kolejnych funkcji ogółowi użytkowników i udostępnianiem wersji zapoznawczych. Dodawanie nowych funkcji zapoznawczych nie będzie w żaden sposób anonsowane. Użytkownicy po prostu zaczną je widzieć.

## <a name="enable-or-disable-preview-features"></a>Włączanie i wyłączanie funkcji zapoznawczych

Ustawienie **Funkcje w wersji zapoznawczej** dostępne w centrum administracyjnym programu Microsoft Dynamics 365 for Talent umożliwia włączanie i wyłączanie funkcji zapoznawczych. Domyślnie to ustawienie jest wyłączone. Akcja włączanie lub wyłączania funkcji zapoznawczych jest specyficzna dla środowiska.

> [!IMPORTANT]
> Włączając ustawienie **Funkcje w wersji zapoznawczej**, włączasz funkcje w wersji zapoznawczej wszystkim użytkownikom w organizacji pracującym w tym środowisku. Wyłączenie ustawienia powoduje wyłączenie funkcji zapoznawczych i zablokowanie użytkownikom dostępu do nich. Funkcje zapoznawcze są obsługiwane w ograniczonym zakresie w aplikacji Talent. Mogą korzystać ze słabszych narzędzi ochrony prywatności i bezpieczeństwa oraz nie są objęte umową dotyczącą poziomu usług zawieraną dla aplikacji Talent. Nie należy używać funkcji zapoznawczych do przetwarzania danych osobowych (tzn. wszelkich informacji, które mogą jednoznacznie identyfikować użytkownika) ani innych danych, które podlegają prawnym lub ustawowym wymogom dotyczącym zgodności.

### <a name="enable-or-disable-preview-features-for-your-organization"></a>Włączanie i wyłączanie funkcji zapoznawczych w organizacji

#### <a name="attract"></a>Attract

1. Zaloguj się w aplikacji Microsoft Dynamics 365 for Talent: Attract.
2. W menu **Ustawienia** (symbol koła zębatego) w prawym górnym rogu wybierz opcję **Ustawienia administratora**.
3. Na karcie **Zarządzanie funkcjami** zaznacz opcję obok napisu **Funkcje w wersji zapoznawczej**, tak aby zmieniła kolor na niebieski.
4. Odśwież przeglądarkę, a zaczniesz widzieć nowe funkcje. (Wszyscy użytkownicy, którzy są już zalogowani, zobaczą funkcje po następnym zalogowaniu, lub też mogą odświeżyć przeglądarki, a zobaczą je natychmiast).

#### <a name="core-hr"></a>Core HR

1. Zaloguj się w aplikacji Talent. Zostanie otwarty obszar roboczy podstawowych funkcji kadrowych, w którym należy wykonać pozostałe kroki. 
2. Wybierz kolejno opcje **Administrowanie systemem\> Linki > Parametry systemu**.
3. Na stronie **Parametry systemu** na karcie **Funkcje w wersji zapoznawczej** w opcji **Włącz tryb zapoznawczy dla wszystkich użytkowników** ustaw wartość **Tak**, a funkcje zapoznawcze staną się dostępne.

> [!NOTE]
> Aby wyłączyć funkcje zapoznawcze, wykonaj te same podstawowe kroki. Po wyłączeniu funkcji zapoznawczych staną się one niedostępne dla użytkowników, a w procesach związanych z funkcjami mogą się pojawiać błędy.

## <a name="features-that-are-currently-in-preview"></a>Funkcje istniejące obecnie w wersjach zapoznawczych

### <a name="attract"></a>Attract

- **Szablony zadań** — Teraz można tworzyć szablony procesów zatrudniania. Dotychczas użytkownicy mogli dostosowywać proces zatrudniania dla określonej funkcji. Jednak teraz mogą tworzyć szablony procesu, a następnie wybierać odpowiednie szablony podczas tworzenia określonej funkcji. W efekcie funkcja pomaga usprawnić proces konfigurowania funkcji do obsadzenia.
- **Witryna rozwoju kariery** — W obecnej wersji witryny rozwoju kariery są po prostu wyświetlane wszystkie otwarte wakaty. Jednak w przyszłości zostanie dodanych więcej funkcji do witryny. Funkcje można oznaczać jako wewnętrzne lub zewnętrzne. Użytkowników wewnętrzni, którzy się zalogują do witryny, zobaczą zarówno funkcje wewnętrzne, jak i zewnętrzne. Natomiast użytkownicy spoza organizacji oraz użytkownicy, którzy się nie zalogują, będą widzieć tylko funkcje zewnętrzne.
- **Oferta pracy** — Teraz można wysyłać oferty pracy do witryny rozwoju kariery.
- **Oferta pracy na LinkedIn** — Teraz można wysyłać oferty pracy do serwisu LinkedIn.

    > [!NOTE]
    > Publikowane funkcje będą widoczne tylko dla klientów, którzy subskrybują co najmniej jeden produkt zarządzania ogłoszeniami o pracę w serwisie LinkedIn. W przeciwnym razie klienci zobaczą ofertę pracy tylko w przypadku, gdy jej specjalnie poszukają. Występuje opóźnienie przy zamieszczaniu ofert pracy w serwisie LinkedIn. Funkcja opublikowana w aplikacji Attract może się pojawić na LinkedIn dopiero po paru godzinach.

- **Zgłoszenie kandydata** — Teraz kandydaci wewnętrzni i zewnętrzni mogą składać podania o pracę bezpośrednio ze strony funkcji w witrynie rozwoju kariery.
- **Zarządzanie ofertami** — Użytkownicy mogą teraz tworzyć pisma ofertowe za pomocą szablonów zawierających symbole zastępcze. Gdy kandydat dociera do etapu oferty, osoby rekrutujące i menedżerowie ds. zatrudnienia mogą za pomocą narzędzia Offer przygotować formalną ofertę dla kandydata przy użyciu szablonów, wysłać ofertę do wewnętrznego zatwierdzenia, a na koniec wysłać ofertę kandydatowi do podpisu. Z czasem do narzędzia Offer zostanie dodanych wiele nowych możliwości, a funkcja zapoznawcza zostanie zaktualizowana o te możliwości, gdy je dopracujemy do poziomu wersji zapoznawczej.

### <a name="core-hr"></a>Core HR

- **Otwarcie rejestracji** — Otwarta rejestracja na świadczenia to proste, samoobsługowe narzędzie, w którym pracownicy mogą wybierać sobie świadczenia. Administratorzy modułu Zasoby ludzkie mogą konfigurować proces otwartej rejestracji na świadczenia w swoich organizacjach i przebieg rejestracji dla pracowników przy wsparciu łatwego przewodnika.

## <a name="feedback"></a>Informacja zwrotna

Bez względu na to, czy Twoje opinie o korzystaniu z funkcji zapoznawczych będą pozytywne, czy negatywne, chcielibyśmy je poznać. Zachęcamy do regularnego zamieszczania opinii w podanych witrynach podczas korzystania z tych i innych funkcji.

- [Społeczność](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) — Ta witryna to doskonała platforma, na której użytkownicy mogą omawiać scenariusze zastosowania, zadawać pytania i otrzymywać osób od podobnych im osób.
- W następujących witrynach można zgłaszać pomysły na ulepszenie produktu. Opowiedz nam o funkcjach, które Twoim zdaniem powinny się znaleźć w produkcie, a także o wszelkich zmianach, które być może należy wprowadzić w istniejących funkcjach.

    - [Attract Ideas](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Core HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)

W przesyłanych opiniach i recenzjach produktu nie podawaj żadnych danych osobowych (tzn. informacji, które mogłyby Cię identyfikować). Zebrane informacje mogą być dalej analizowane, ale zgodnie z odnośnymi przepisami o ochronie danych nie będą wykorzystywane do udzielania odpowiedzi na pytania. Dane osobowe, które na mocy tych programów są zbierane osobno, podlegają [zasadom zachowania poufności informacji firmy Microsoft](https://privacy.microsoft.com/privacystatement).

> [!TIP]
> Dodaj tej temat do zakładek i zaglądaj tu regularnie, aby być na bieżąco z nowo publikowanymi funkcjami w wersjach zapoznawczych.

