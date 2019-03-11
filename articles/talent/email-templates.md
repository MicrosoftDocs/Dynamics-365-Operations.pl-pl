---
title: Szablony wiadomości e-mail
description: Ten temat zawiera informacje o szablonach wiadomości e-mail, które można tworzyć i ich używać w aplikacji Microsoft Dynamics 365 for Talent - Attract.
author: josaw
manager: AnnBe
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: e02912ad242186fe3e2dd8d7a4cc7312aec6015e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "305833"
---
# <a name="email-templates"></a>Szablony wiadomości e-mail
[!include[banner](../includes/banner.md)]

Za pomocą biblioteki szablonów wiadomości e-mail administratorzy mogą utworzyć jednolity motyw i identyfikację wizualną dla wszystkich wiadomości e-mail wysyłanych z aplikacji Microsoft Dynamics 365 for Talent: Attract. Administratorzy mogą również przechowywać zbiór szablonów zawartości wiadomości e-mail z przeznaczeniem dla innych użytkowników. Zespół rekrutacyjny może używać tych szablonów w swoich procesach, aby sprawniej wysyłać wiadomości e-mail. Niektóre wiadomości e-mail w aplikacji Attract są skonfigurowane do wysyłania automatycznego, a administrator może używać biblioteki szablonów wiadomości e-mail do personalizowania zawartości tych wiadomości.

> [!NOTE]
> Aby korzystać z szablonów wiadomości E-mail, organizacja musi mieć dodatek kompleksowej obsługi rekrutacji.

## <a name="global-template-configurations"></a>Globalne konfiguracje szablonów

Aby utworzyć spójną identyfikację wizualną dla całej korespondencji pocztą e-mail, administrator musi najpierw ustawić globalne nagłówek i stopkę dla wszystkich szablonów wiadomości e-mail. W Centrum administracyjnym na karcie **Ustawienia szablonu wiadomości e-mail** w sekcji **Nagłówek** administrator może przekazać obraz, który będzie używany jako nagłówek lub transparent we wszystkich wiadomościach e-mail. Obrazem może być logo firmy, nagłówek listowy lub jakikolwiek inny reprezentatywny obraz. Zalecamy, aby obraz miał szerokość od 25 do 800 pikseli, a wysokość od 25 do 150 pikseli, ponieważ te wymiary są optymalne dla większości klienckich aplikacji poczty e-mail, takich jak Microsoft Outlook. Obraz musi być plikiem w formacie JPG, JPEG, PNG lub SVG, a jego rozmiar nie może przekraczać 1 megabajta (MB). Po przekazaniu obrazu zostanie wygenerowany i wyświetlony podgląd nagłówka. Jeśli obraz nagłówka należy usunąć lub zamienić, administrator można użyć opcji **Usuń** znajdującej się nad podglądem.

W sekcji **Stopka** administrator może umieścić łącza do firmowych zasad ochrony prywatności w komunikacji oraz do warunków i postanowień. Te łącza znajdą się w automatycznie generowanej stopce. Zostanie wyświetlony podgląd stopki.

Pamiętaj, aby zapisać zmiany, zanim zamkniesz Centrum administracyjne.

> [!NOTE] 
> Nagłówek i stopka są ustawieniami globalnymi dla wszystkich wiadomości e-mail. W związku z tym będą występować we wszystkich wiadomościach e-mail wysyłanych z aplikacji Attract. Jeśli ustawienia nie zostaną skonfigurowane, obszary nagłówka i stopki będą puste we wszystkich wiadomościach e-mail.

## <a name="email-template-library"></a>Biblioteka szablonów wiadomości e-mail 

Po utworzeniu globalnych konfiguracji szablonów administrator może rozpocząć tworzenie i nadzorowanie szablonów dla wszystkich wiadomości e-mail wysyłanych z aplikacji Attract. Biblioteka szablonów wiadomości e-mail jest dostępna tylko dla administratorów. Aby otworzyć bibliotekę, w głównym menu nawigacji wybierz kartę **Szablony wiadomości e-mail**. Biblioteka jest uporządkowana według różnych działań w aplikacji Attract, dla których należy wysyłać wiadomości e-mail, takich jak planowanie, ocena i tworzenie funkcji. Administrator może wybrać dowolną kategorię i wtedy zobaczy wszystkie typy wiadomości e-mail skojarzone z działaniem. Na przykład po wybraniu opcji **Planowanie** zobaczysz różne typy wiadomości e-mail wysyłane w procesie planowania oraz wszystkie szablony, które są dostępne dla każdego typu wiadomości e-mail. Każda podsekcja w kategorii reprezentuje typ wiadomości e-mail.

Niektóre typy wiadomości e-mail mogą mieć więcej niż jednego adresata. Na przykład w kategorii **Planowanie** wiadomości e-mail, które są wysyłane, gdy jest potrzebne podsumowanie harmonogramu rozmów kwalifikacyjnych, są wysyłane do kandydatów i osób przeprowadzających rozmowy kwalifikacyjne. Każda sekcja zawiera dwie główne kolumny: **Tytuł szablonu** i **Adresat**. Każdy wiersz w sekcji reprezentuje jeden szablon dla typu wiadomości e-mail. Na początku w wierszu każdego szablonu znajduje się symbol kłódki. Ten symbol oznacza, że szablon jest standardowym szablonem dostarczonym w aplikacji Attract i nie można go usunąć. Dla każdego szablonu administrator może użyć przycisku wielokropka (**...**) w celu zduplikowania szablonu, ustawienia go jako domyślnego lub usunięcia. Gdy szablon jest ustawiony jako szablon domyślny, może wystąpić jedno z dwóch zachowań. Zachowanie jest wskazane na znaczku lub znaczkach wyświetlanych w wierszu szablonu:

- **Domyślnie** — Ten znaczek wskazuje, że szablon jest domyślnym szablonem wysyłanych wiadomości e-mail, a informacje zostaną w nim wprowadzone, gdy użytkownik wysyła wiadomość e-mail tego określonego typu.
- **Domyślnie** + **Wyślij automatycznie** — Ta kombinacja znaczków wskazuje, że szablon jest aktywnym szablonem dla wiadomości e-mail generowanych przez system, które są wysyłane automatycznie.

Aby edytować szablon, zaznacz wiersz, a następnie wprowadź zmiany w szablonie.

> [!NOTE]
> Każdy adresat określonego typu wiadomości e-mail ma szablon domyślny. Wszystkie standardowe szablony aplikacji Attract są ustawione jako szablony domyślne, dopóki administrator nie utworzy nowego szablonu dla określonego typu wiadomości e-mail i nie ustawi go jako domyślnego szablonu.

## <a name="create-a-template"></a>Utwórz szablon

Aby utworzyć szablon, w prawym górnym rogu biblioteki szablonów wiadomości e-mail wybierz opcję **+ Nowy szablon**. Aby wybrać typ wiadomości e-mail, dla której tworzysz szablon, zaznacz adresata, proces i wydarzenie, o którym należy wysłać wiadomość e-mail. Następnie wybierz opcję **Utwórz**.

Szablon zostanie otwarty w widoku do edycji i możesz nadać mu nazwę. Na przykład jeśli szablon jest przeznaczony dla kandydatów z uniwersytetu amerykańskiego, ale zawartość jest napisana w języku francuskim, możesz nadać szablonowi tytuł **Uniwersytet\_USA\_Po francusku**. Tytuł, wiersz tematu i treść szablonu mogą być w różnych językach, nie tylko w angielskim.

Pole **Do** w szablonie nie może być edytowane, ponieważ już wybrano adresata podczas tworzenia szablonu.

W wierszu DW (do wiadomości) można dodać inne osoby, takie jak **Osoba rekrutująca** lub **Menedżer zatrudniający**. Podczas wysyłania wiadomości e-mail te role są automatycznie zastępowane odpowiednimi użytkownikami na podstawie kontekstu funkcji.

W wierszu tematu i treści można używać symboli zastępczych. Aby wstawić symbol zastępczy, wpisz znak **\#**, a następnie wybierz odpowiedni symbol zastępczy z listy rozwijanej z funkcją autouzupełniania. Lista dostępnych symboli zastępczych jest wyświetlana przy prawym boku strony. Podczas wysyłania wiadomości e-mail symbole zastępcze są automatycznie zastępowane na podstawie kontekstu funkcji i danych adresata. Na przykład szablon wiadomości e-mail wysyłanych kandydatom zawiera symbol zastępczy \#{Candidate\_Name}. Podczas wysyłania wiadomości e-mail do kandydata o nazwisku Kowalski symbol zastępczy zostanie zastąpiony nazwiskiem Kowalski.

Edytor treści jest edytorem tekstu sformatowanego, który umożliwia sformatowanie tekstu i nadanie mu stylu. Pozwala także wstawiać hiperłącza i punkty kotwice.

Po utworzeniu szablonu dla określonego typu wiadomości e-mail kliknij przycisk wielokropka (**...**) w wierszu szablonu i ustaw szablon jako domyślny.

## <a name="consume-templates"></a>Wykorzystywanie szablonów

Gdy zespół rekrutacyjny wysyła wiadomość e-mail, może używać szablonów utworzonych przez administratora. Jeśli utworzono wiele szablonów dla wiadomości e-mail wysyłanych przez użytkownika, w przepływie pracy redagowania wiadomości e-mail pojawi się lista rozwijana. Domyślny szablon jest wprowadzany automatycznie, ale użytkownik może wybrać inny szablon.

> [!NOTE] 
> Dla wiadomości e-mail wysyłanych automatycznie można utworzyć wiele szablonów. Jednak tylko jeden szablon można ustawić jako aktywny. Ponieważ ten proces jest uruchamiany przez zdarzenia, tylko administrator może określić, który szablon powinien zostać użyty, jako kryterium stosując kombinację znaczków **Domyślnie** i **Wyślij automatycznie** wyświetlanych w bibliotece szablonów.
