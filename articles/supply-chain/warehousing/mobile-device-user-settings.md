---
title: Ustawienia użytkownika urządzenia przenośnego
description: W tym temacie wyjaśniono, jak zarządzać ustawieniami użytkownika urządzenia przenośnego dla pracowników magazynu.
author: MarkusFogelberg
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppDeviceBrand,WHSMobileAppUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: mafoge
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 77b4276cec5e046a19d6d001acf41fc410052fba
ms.sourcegitcommit: c53de2c09b9296b41653e739178edf29f79e0679
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049299"
---
# <a name="mobile-device-user-settings"></a>Ustawienia użytkownika urządzenia przenośnego

[!include [banner](../../includes/banner.md)]

Nowa aplikacja mobilna Zarządzanie magazynem zawiera zestaw specyficznych dla aplikacji ustawień, które ułatwiają dostosowanie możliwości użytkowników. Ponieważ aplikacji można używać na urządzeniach o różnych rozmiarach ekranu i konfiguracjach (takich jak tablet, telefon lub trzymany z ręką), przydatne może być centralne zarządzanie tymi ustawieniami z poziomu Microsoft Dynamics 365 Supply Chain Management.

Funkcja *ustawień użytkownika urządzenia przenośnego* umożliwia definiowanie globalnych ustawień użytkownika, które będą używane na wszystkich urządzeniach. Można także zdefiniować bardziej szczegółowe ustawienia użytkownika dla poszczególnych marek urządzeń, modeli urządzeń i/lub pracowników. Gdy pracownik loguje się do aplikacji mobilnej Warehouse Management, aplikacja pobiera i stosuje najbardziej szczegółowy profil ustawień przechowywany w Supply Chain Management dla pasującej marki, urządzenia i / lub identyfikatora użytkownika.

Ta funkcja pomaga pracownikom szybciej rozpocząć, gdy zaczynają korzystać z nowego urządzenia. Oto kilka przykładów:

- Administratorzy mogą ustalić standardowy zestaw preferencji, które najlepiej działają w przypadku urządzeń poszczególnych producentów i/lub określonych modeli urządzeń. Dzięki temu pracownicy mogą zacząć używać nowego urządzenia bez konieczności zmiany tych ustawień.
- Jeśli Twoja firma ma pulę identycznych urządzeń, które są współużytkowane przez pracowników, pracownicy zobaczą preferowaną konfigurację za każdym razem, gdy się zalogują, nawet jeśli nigdy nie korzystali z konkretnego urządzenia fizycznego, które wybrali w danym dniu.
- W Supply Chain Management administratorzy mogą wyświetlać i edytować wszystkie przechowywane ustawienia, nawet dla poszczególnych pracowników. Te możliwości mogą pomóc w rozwiązywaniu problemów z nowymi funkcjami lub dostrajania ich.

> [!IMPORTANT]
> Funkcja *ustawień użytkownika urządzenia przenośnego* dotyczy tylko nowej aplikacji mobilnej Zarządzanie magazynem. Nie działa ze starą aplikacją magazynu.

## <a name="turn-on-the-mobile-device-user-settings-feature"></a>Włącz funkcję ustawień użytkownika urządzenia przenośnego

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *ustawienia użytkownika, ikony i tytuły kroków dla nowej aplikacji magazynowej*

## <a name="create-and-manage-user-settings"></a>Umożliwia tworzenie ustawień użytkownika i zarządzanie nimi

Strona **Ustawienia użytkownika urządzenia przenośnego** umożliwia tworzenie, wyświetlanie i zarządzanie profilami ustawień na wszystkich poziomach szczegółowości. Gdy pracownik edytuje ustawienia użytkownika po raz pierwszy na nowym urządzeniu, na tej stronie jest automatycznie dodawany nowy profil, jeśli jeszcze nie istnieje. Profil jest aktualizowany za każdym razem, gdy pracownik wprowadza zmianę.

Możesz także zdefiniować profil ustawień, który ma zastosowanie do wszystkich marek urządzeń, modeli urządzeń i / lub pracowników. Następnie można zwiększyć stopień szczegółowości, stosując bardziej szczegółowe ustawienia dla pojedynczych marek, modeli i/lub pracowników.

Aby utworzyć ustawienia użytkownika dla urządzeń przenośnych i zarządzać nimi, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Urządzenie przenośne \> Menu ustawień użytkownika urządzenia przenośnego**.
1. Wybierz istniejący profil ustawień użytkownika w okienku listy, aby otworzyć jego rekord. Możesz również wybrać opcję **Nowy** w okienku akcji, aby utworzyć nowy profil.

    Każdy profil w okienku listy jest oznaczony etykietą wskazującą markę, model i/lub identyfikator użytkownika, do których odnosi się ten profil. W przypadku niektórych lub wszystkich tych cech więcej profilów ogólnych ma wartość *Wszystkie*.

1. W sekcji nagłówka rekordu dla nowego lub wybranego profilu ustawień należy ustawić następujące pola:

    - **Nazwa marki urządzenia** – wybierz nazwę marki urządzenia, do których ma być zastosowanie profil. Jeśli profil ma dotyczyć wszystkich marek, należy pozostawić to pole puste. Lista wartości obejmuje wszystkie marki zdefiniowane w systemie. Aby uzyskać informacje dotyczące sposobu definiowania listy marek, zobacz następną sekcję.
    - **Identyfikator modelu urządzenia** – Wybierz model urządzenia, którego ma dotyczyć profil. Jeśli profil ma dotyczyć wszystkich modeli wybranej marki, pozostaw to pole puste. Lista wartości zawiera wszystkie modele zdefiniowane dla marki wybranej w polu **Nazwa marki urządzenia**. Aby uzyskać informacje o tym, jak zdefiniować listę modeli dla każdej marki, zobacz następną sekcję.
    - **Identyfikator użytkownika** — umożliwia wybranie identyfikatora użytkownika pracownika magazynu, do których ma być zastosowanie profil ustawień. Jeśli profil ma dotyczyć wszystkich użytkowników, należy pozostawić to pole puste.

1. Na skróconej karcie **Ogólne** ustaw następujące pola:

    - **Pozycja przycisku** — umożliwia wybór sposobu pozycji przycisków na urządzeniu Elementy w aplikacji zostaną przeniesione, aby lepiej pasowały do preferencji lub poręczności pracownika. Dostępne opcje to: *Prawy dolny (domyślnie)*, *Lewa dolna*, *Prawy górny* i *Lewa górna*.
    - **Orientacja wyświetlania** — umożliwia wybór orientacji wyświetlania, która powinna być domyślnie stosowana w aplikacji.
    - **Skanuj z użyciem kamery** – Ustaw dla tej opcji wartość *Tak*, aby za pomocą kamery urządzenia skanować pola wejściowe, w których jest ustawiony preferowany tryb wejściowy *Skanowanie*. Jeśli urządzenie ma wbudowany skaner, ustaw tę opcję na *Nie*, aby użyć skanera.
    - **Pokaż zdjęcie produktu** – Określ, czy mają być pokazywane zdjęcia produktu, jeśli są dostępne dla zwolnionego produktu. Aby uzyskać więcej informacji dotyczących dodawania obrazów produktów, zobacz temat [Dodawanie obrazu do produktu](../pim/tasks/add-image-product.md).
    - **Kompozycja kolorów wyświetlania** — umożliwia wybór motywu kolorów dla urządzenia.
    - **Poziom dźwięku** – umożliwia wybór poziomu dźwięku dla urządzenia. Wybierz wartość od 0 (zero) do 10. Wartość *0* oznacza brak dźwięku, a wartość *10* oznacza maksymalną głośność. Wartość domyślna to *4*.
    - **Poziom wibracji** – umożliwia wybór poziomu wibracji dla urządzenia. Wybierz wartość od 0 (zero) do 5. Wartość *0* oznacza brak wibracji, a wartość *5* oznacza maksymalną wibrację. Wartość domyślna to *1*.
    - **Procent skali tekstu** — umożliwia określenie rozmiaru tekstu jako procentu rozmiaru standardowego. Wprowadź wartość z zakresu od 70 do 400. Wartość *70* oznacza najmniejszą skalę tekstową, a wartość *400* oznacza największą skalę tekstową. Wartość domyślna to *100*.
    - **Procent skali przycisku** — umożliwia określenie rozmiaru przycisku jako procentu rozmiaru standardowego. Wprowadź wartość z zakresu od 50 do 200. Wartość *50* oznacza najmniejszą skalę przycisków, a wartość *200* oznacza największą skalę przycisków. Wartość domyślna to *100*.

## <a name="create-and-manage-mobile-device-brands"></a>Tworzenie marek urządzeń przenośnych i zarządzanie nimi

Strona **Marki urządzenia przenośnego** umożliwia przeglądanie i tworzenie marek urządzeń oraz modeli używanych w profilach ustawień oraz zarządzanie nimi. Aplikacja mobilna automatycznie pobiera i przesyła lokalną nazwę marki i identyfikator modelu po raz pierwszy, gdy pracownik edytuje ustawienia na danym urządzeniu. Dlatego większość z tych rekordów jest zwykle generowana automatycznie. Jednak można także zarządzać wszystkimi rekordami na tej stronie. Na przykład dla każdej marki i modelu można podać bardziej użyteczne opisy, aby ułatwić rozróżniać podobne lub niezaszyfrowane identyfikatory modeli.

Wykonaj poniższe czynności, aby tworzyć marki i modele urządzeń mobilnych oraz zarządzać nimi.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Urządzenie przenośne \> Marki urządzeń przenośnych**.
1. W okienku listy wybierz markę urządzenia mobilnego, aby otworzyć jego rekord. Możesz również wybrać opcję **Nowy** w okienku akcji, aby utworzyć nową markę.
1. W sekcji nagłówka rekordu dla nowej lub wybranej marki urządzenia ustaw następujące pola:

    - **Nazwa marki urządzenia** – nazwa marki urządzenia, taka jak *Microsoft Corporation*.
    - **Opis** — można wprowadzić opis ułatwiający rozróżnianie nazw marki.

1. Na skróconej karcie **Modele urządzeń przenośnych** są dostępne wszystkie modele wybranej marki urządzeń. Użyj przycisków na pasku narzędzi, aby dodać wiersze do siatki lub usunąć wiersze. Dla każdego wiersza możesz ustawić następujące pola:

    - **Identyfikator modelu urządzenia** – Identyfikator modelu urządzenia, np. *Surface Book 2*.
    - **Opis** — można wprowadzić opis ułatwiający rozróżnianie identyfikatorów modeli.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Instalowanie i łączenie aplikacji mobilnej Zarządzanie magazynem](install-configure-warehouse-management-app.md)
- [Przypisanie ikon i tytułów kroków dla aplikacji mobilnej Warehouse Management](step-icons-titles.md)